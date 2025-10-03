[#](#row-validation) Row Validation
===================================

*   [Validating with a heading row](#validating-with-a-heading-row)
*   [Custom validation messages](#custom-validation-messages)
*   [Custom validation attributes](#custom-validation-attributes)
*   [Handling validation errors](#handling-validation-errors)
    *   [Database transactions](#database-transactions)
    *   [Gathering all failures at the end](#gathering-all-failures-at-the-end)
    *   [Skipping failures](#skipping-failures)
*   [Skipping empty rows](#skipping-empty-rows)
*   [Extend empty rows logic](#extend-empty-rows-logic)
    *   [Skipping errors](#skipping-errors)
*   [Row Validation without ToModel](#row-validation-without-tomodel)
*   [Prepare data for validation](#prepare-data-for-validation)
*   [Configuring the validator](#configuring-the-validator)

Sometimes you might want to validate each row before it's inserted into the database. By implementing the `WithValidation` concern, you can indicate the rules that each row need to adhere to.

The `rules()` method, expects an array with Laravel Validation rules to be returned.

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Illuminate\Validation\Rule;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\WithValidation;
    
    class UsersImport implements ToModel, WithValidation
    {
        use Importable;
    
        public function model(array $row)
        {
            return new User([
                'name'     => $row[0],
                'email'    => $row[1],
                'password' => 'secret',
            ]);
        }
    
        public function rules(): array
        {
            return [
                '1' => Rule::in(['patrick@maatwebsite.nl']),
    
                 // Above is alias for as it always validates in batches
                 '*.1' => Rule::in(['patrick@maatwebsite.nl']),
                 
                 // Can also use callback validation rules
                 '0' => function($attribute, $value, $onFailure) {
                      if ($value !== 'Patrick Brouwers') {
                           $onFailure('Name is not Patrick Brouwers');
                      }
                  }
            ];
        }
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15  
16  
17  
18  
19  
20  
21  
22  
23  
24  
25  
26  
27  
28  
29  
30  
31  
32  
33  
34  
35  
36  
37  
38  
39  
40  

[#](#validating-with-a-heading-row) Validating with a heading row
-----------------------------------------------------------------

When using the `WithHeadingRow` concern, you can use the heading row name as rule attribute.

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Illuminate\Validation\Rule;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\WithValidation;
    use Maatwebsite\Excel\Concerns\WithHeadingRow;
    
    class UsersImport implements ToModel, WithValidation, WithHeadingRow
    {
        use Importable;
    
        public function model(array $row)
        {
            return new User([
                'name'     => $row['name'],
                'email'    => $row['email'],
                'password' => 'secret',
            ]);
        }
    
        public function rules(): array
        {
            return [
                'email' => Rule::in(['patrick@maatwebsite.nl']),
    
                 // Above is alias for as it always validates in batches
                 '*.email' => Rule::in(['patrick@maatwebsite.nl']),
            ];
        }
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15  
16  
17  
18  
19  
20  
21  
22  
23  
24  
25  
26  
27  
28  
29  
30  
31  
32  
33  
34  

If your validation rules reference other field names, as in the `different`, `lt`, `lte`, `gt`, `gte`, and `same` rules, the field name must be prefixed with `*.` as in the example below, because validation is done in batches.

    public function rules(): array
    {
        return [
            'maximum' => 'gte:*.minimum',
        ];
    }
    

1  
2  
3  
4  
5  
6  

[#](#custom-validation-messages) Custom validation messages
-----------------------------------------------------------

By adding `customValidationMessages()` method to your import, you can specify custom messages for each failure.

    /**
    * @return array
    */
    public function rules(): array
    {
        return [
            '1' => Rule::in(['patrick@maatwebsite.nl']),
        ];
    }
    
    /**
     * @return array
     */
    public function customValidationMessages()
    {
        return [
            '1.in' => 'Custom message for :attribute.',
        ];
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15  
16  
17  
18  
19  

[#](#custom-validation-attributes) Custom validation attributes
---------------------------------------------------------------

By adding `customValidationAttributes()` method to your import, you can specify custom attribute names for each column.

    /**
    * @return array
    */
    public function rules(): array
    {
        return [
            '1' => Rule::in(['patrick@maatwebsite.nl']),
        ];
    }
    
    /**
     * @return array
     */
    public function customValidationAttributes()
    {
        return ['1' => 'email'];
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15  
16  
17  

[#](#handling-validation-errors) Handling validation errors
-----------------------------------------------------------

### [#](#database-transactions) Database transactions

The entire import is automatically wrapped in a **database transaction**, that means that _every_ error will rollback the entire import. When using batch inserts, only the **current** batch will be rollbacked.

#### [#](#disable-transactions) Disable transactions

If you prefer to not have any database transactions around your import (or chunk import), you can change which transaction handler you want to use in the config:

In `config/excel.php`:

    'transactions' => [
        'handler' => 'db',
    ],
    

1  
2  
3  

Supported handlers are currently: `null` or `db`.

#### [#](#custom-transaction-handlers) Custom transaction handlers

If you want a custom transaction handler (for e.g. a MongoDB database), you can add your own handler:

    $this->app->make(\Maatwebsite\Excel\Transactions\TransactionManager::class)->extend('your_handler', function() {
        return new YourTransactionHandler();
    });
    

1  
2  
3  

The Handler should implement `Maatwebsite\Excel\Transactions\TransactionHandler`.

### [#](#gathering-all-failures-at-the-end) Gathering all failures at the end

You can gather all validation failures at the end of the import, when used in conjunction with Batch Inserts. You can try-catch the `ValidationException`. On this exception you can get all failures.

Each failure is an instance of `Maatwebsite\Excel\Validators\Failure`. The `Failure` holds information about which row, which column and what the validation errors are for that cell.

    try {
        $import->import('import-users.xlsx');
    } catch (\Maatwebsite\Excel\Validators\ValidationException $e) {
         $failures = $e->failures();
         
         foreach ($failures as $failure) {
             $failure->row(); // row that went wrong
             $failure->attribute(); // either heading key (if using heading row concern) or column index
             $failure->errors(); // Actual error messages from Laravel validator
             $failure->values(); // The values of the row that has failed.
         }
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  

### [#](#skipping-failures) Skipping failures

Sometimes you might want to skip failures. By using the `SkipsOnFailure` concern, you get control over what happens the moment a validation failure happens. When using `SkipsOnFailure` the entire import will **not** be rollbacked when a failure occurs.

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Validators\Failure;
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\SkipsOnFailure;
    use Maatwebsite\Excel\Concerns\WithValidation;
    
    class UsersImport implements ToModel, WithValidation, SkipsOnFailure
    {
        use Importable;
    
        /**
         * @param Failure[] $failures
         */
        public function onFailure(Failure ...$failures)
        {
            // Handle the failures how you'd like.
        }
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15  
16  
17  
18  
19  
20  
21  
22  
23  

If you automatically want to skip all failed rows and collect the failures at the end of the import, you can use the `Maatwebsite\Excel\Concerns\SkipsFailures` trait.

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Validators\Failure;
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\SkipsOnFailure;
    use Maatwebsite\Excel\Concerns\WithValidation;
    use Maatwebsite\Excel\Concerns\SkipsFailures;
    
    class UsersImport implements ToModel, WithValidation, SkipsOnFailure
    {
        use Importable, SkipsFailures;
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15  
16  

Every row that has failed the validation rules, will have been skipped. We can now collect all the failures at the end:

    $import = new UsersImport();
    $import->import('users.xlsx');
    
    foreach ($import->failures() as $failure) {
         $failure->row(); // row that went wrong
         $failure->attribute(); // either heading key (if using heading row concern) or column index
         $failure->errors(); // Actual error messages from Laravel validator
         $failure->values(); // The values of the row that has failed.
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  

[#](#skipping-empty-rows) Skipping empty rows
---------------------------------------------

Sometimes you might want to skip empty rows, for example when using the `required` validation rule. By using the `SkipsEmptyRows` concern, empty rows will get skipped during both validation **and the import**.

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\SkipsEmptyRows;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\WithHeadingRow;
    use Maatwebsite\Excel\Concerns\WithValidation;
    
    class UsersImport implements ToModel, SkipsEmptyRows, WithHeadingRow, WithValidation
    {
        use Importable;
        
        public function rules(): array
        {
            return [
                'name' => [
                    'required',
                    'string',
                ],
            ];
        }
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15  
16  
17  
18  
19  
20  
21  
22  
23  
24  
25  

[#](#extend-empty-rows-logic) Extend empty rows logic
-----------------------------------------------------

Along with `SkipsEmptyRows` you can have your own logic to skip rows by having `isEmptyWhen` in the importer

    <?php
    
    namespace App\Imports;
    
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\ToArray;
    
    class UsersImport implements ToArray,
    {
        use Importable;
        
        public function isEmptyWhen(array $row): bool
        {
            return $row['name'] === 'John Doe';
        }
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15  
16  

### [#](#skipping-errors) Skipping errors

Sometimes you might want to skip **all** errors, e.g. duplicate database records. By using the `SkipsOnError` concern, you get control over what happens the moment a model import fails. When using `SkipsOnError` the entire import will **not** be rollbacked when an database exception occurs.

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\SkipsOnError;
    use Maatwebsite\Excel\Concerns\WithValidation;
    
    class UsersImport implements ToModel, WithValidation, SkipsOnError
    {
        use Importable;
    
        /**
         * @param \Throwable $e
         */
        public function onError(\Throwable $e)
        {
            // Handle the exception how you'd like.
        }
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15  
16  
17  
18  
19  
20  
21  
22  

If you automatically want to skip all exceptions and collect them at the end of the import, you can use the `Maatwebsite\Excel\Concerns\SkipsErrors` trait.

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Validators\Failure;
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\SkipsOnError;
    use Maatwebsite\Excel\Concerns\WithValidation;
    use Maatwebsite\Excel\Concerns\SkipsErrors;
    
    class UsersImport implements ToModel, WithValidation, SkipsOnError
    {
        use Importable, SkipsErrors;
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15  
16  

Every row that has errored, will have been skipped. We can now collect all the errors at the end:

    $import = new UsersImport();
    $import->import('users.xlsx');
    
    dd($import->errors());
    

1  
2  
3  
4  

[#](#row-validation-without-tomodel) Row Validation without ToModel
-------------------------------------------------------------------

If you are not using the `ToModel` concern, you can very easily do row validation by just using the Laravel validator.

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Illuminate\Support\Collection;
    use Illuminate\Support\Facades\Validator;
    use Maatwebsite\Excel\Concerns\ToCollection;
    
    class UsersImport implements ToCollection
    {
        public function collection(Collection $rows)
        {
             Validator::make($rows->toArray(), [
                 '*.0' => 'required',
             ])->validate();
    
            foreach ($rows as $row) {
                User::create([
                    'name' => $row[0],
                ]);
            }
        }
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15  
16  
17  
18  
19  
20  
21  
22  
23  
24  

[#](#prepare-data-for-validation) Prepare data for validation
-------------------------------------------------------------

Sometimes data may not pass validation directly, but still be valid. When this happens you may want to tweak the data slightly before sending it to the validator, to do this you may add a `prepareForValidation` method on your import, this method receives row data as well as the row number and should return the manipulated row data.

    class UsersImport implements WithValidation
    {
        public function prepareForValidation($data, $index)
        {
            $data['email'] = $data['email'] ?? $this->myOtherWayOfFindingTheEmail($data);
            
            return $data;
        }
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  

[#](#configuring-the-validator) Configuring the validator
---------------------------------------------------------

If you want to add conditional validation or complex validation that cannot be expressed through rules you can configure the validator similar to how you would do this with a [Form request (opens new window)](https://laravel.com/docs/master/validation#form-request-validation)

Manual validation

You can use `$validator->getData()` to get access to the data under validation

    class UsersImport implements WithValidation
    {
        public function withValidator($validator)
        {
            $validator->after(function ($validator) {
                if ($this->somethingElseIsInvalid()) {
                    $validator->errors()->add('field', 'Something is wrong with this field!');
                }
            });
    
            // or...
    
            $validator->sometimes('*.email', 'required', $this->someConditionalRequirement());
        }
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15  

Validation rules

For a list of all validation rules, please refer to the [Laravel document (opens new window)](https://laravel.com/docs/master/validation#available-validation-rules).

Validating Across Multiple Rows

Validation rules that check multiple rows (such as `distinct`) will work only when using `WithBatchInserts` or `ToCollection` concerns.