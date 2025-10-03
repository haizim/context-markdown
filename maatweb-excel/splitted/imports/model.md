[#](#importing-to-models) Importing to models
=============================================

*   [Upserting models](#upserting-models)
    *   [Upserting with specific columns](#upserting-with-specific-columns)
*   [Skipping duplicate rows](#skipping-duplicate-rows)
*   [Skipping specific rows](#skipping-specific-rows)
*   [Possible column names](#possible-column-names)
*   [Cascading relation persistence](#cascading-relation-persistence)
*   [Handling persistence on your own](#handling-persistence-on-your-own)
    *   [Macro's and Mixins](#macro-s-and-mixins)

In case you want to import a workbook to an Eloquent model, you can use the `ToModel` concern. The concern enforces a `model()` method which accepts a model to be returned.

    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    
    class UsersImport implements ToModel
    {
        public function model(array $row)
        {
            return new User([
                'name' => $row[0],
            ]);
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

The returned model will be saved for you. Each row will result into (at least) one save and will also fire model events.

When using `ToModel` you should never save the model yourself, as that will break the batch insert functionality. If you need this, consider using `OnEachRow`.

[#](#upserting-models) Upserting models
---------------------------------------

In case you want to upsert models, instead of inserting, you can implement the `WithUpserts` concern.

    class UsersImport implements ToModel, WithUpserts
    {
        /**
         * @return string|array
         */
        public function uniqueBy()
        {
            return 'email';
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

In the example above, if a user already exists with the same email, the row will be updated instead. Behind the scenes, this feature uses the Laravel `upsert` method and the `uniqueBy` method is used for the second argument of the `upsert` method, which lists the column(s) that uniquely identify records within the associated table.

All databases except SQL Server require the `uniqueBy` columns to have a "primary" or "unique" index.

### [#](#upserting-with-specific-columns) Upserting with specific columns

By default, `upsert`, in case of updating, will update all columns that match model's attributes. However, if you need to update only specific column(s) during `upsert`, you can also implement the `WithUpsertColumns` concern.

    class UsersImport implements ToModel, WithUpserts, WithUpsertColumns
    {
        /**
         * @return array
         */
        public function upsertColumns()
        {
            return ['name', 'role'];
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

In this example, if a user already exists, only "name" and "role" columns will be updated.

[#](#skipping-duplicate-rows) Skipping duplicate rows
-----------------------------------------------------

In case you want to skip duplicate models, you can implement the `WithSkipDuplicates` concern.

    class UsersImport implements ToModel, WithSkipDuplicates
    {
        // No additional methods are required for this concern
    }
    

1  
2  
3  
4  

In the example above, if a user already exists with the same primary or unique key, the row will be ignored. Behind the scenes, this feature uses the Laravel `insertOrIgnore` method to insert records while ignoring duplicates, preventing any errors that would normally occur due to duplicate entries.

[#](#skipping-specific-rows) Skipping specific rows
---------------------------------------------------

In case you want to skip a row, you can return null.

    public function model(array $row)
    {
        if (!isset($row[0])) {
            return null;
        }
    
        return new User([
            'name' => $row[0],
        ]);
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

[#](#possible-column-names) Possible column names
-------------------------------------------------

In case you want to import rows by several possible column names (using `WithHeadingRow`), you can use null coalescing operator (`??`). If the column with the first name (in example _client\_name_) exists and is not NULL, return its value; otherwise look for second possible name (in example _client_) etc.

    public function model(array $row)
    {
        return new User([
            'name' => $row['client_name'] ?? $row['client'] ?? $row['name'] ?? null
        ]);
    }
    

1  
2  
3  
4  
5  
6  

[#](#cascading-relation-persistence) Cascading relation persistence
-------------------------------------------------------------------

By default, ToModel doesn't save relations, you can enable this behaviour for `BelongsTo` and `BelongsToMany` relations by adding the `PersistRelations` concern.

    class UsersImport implements ToModel, PersistRelations
    {
        public function model(array $row)
        {
            $user = new User([
                'name' => $row[0],
            ]);
            
            // There should be a `public function team(): BelongsTo` relation in the User model.
            $user->setRelation('team', new Team(['name' => $row[1]]));
            
            return $user;
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

`PersistRelations` doesn't work together with BatchInserts.

[#](#handling-persistence-on-your-own) Handling persistence on your own
-----------------------------------------------------------------------

In some cases you might not have an import in which each row is an Eloquent model and you want more control over what happens. In those cases you can use the `OnEachRow` concern.

    namespace App\Imports;
    
    use App\Group;
    use App\User;
    use Maatwebsite\Excel\Row;
    use Maatwebsite\Excel\Concerns\OnEachRow;
    
    class UsersImport implements OnEachRow
    {
        public function onRow(Row $row)
        {
            $rowIndex = $row->getIndex();
            $row      = $row->toArray();
            
            $group = Group::firstOrCreate([
                'name' => $row[1],
            ]);
        
            $group->users()->create([
                'name' => $row[0],
            ]);
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

When using `OnEachRow` you cannot use batch inserts, as the model is already persisted in the `onRow` method.

### [#](#macro-s-and-mixins) Macro's and Mixins

The Eloquent Builder/Model has a macro to directly import an excel to Eloquent rows. When using this, make sure your file has a heading row with the database table column names.

    User::query()->import('import-users-with-headings.xlsx');
    

1  

If you want to define the mapping yourself, you can use the `importAs` method.

    User::query()->importAs('import-users.xlsx', function (array $row) {
        return [
            'name'     => $row[0],
            'email'    => $row[1],
            'password' => 'secret',
        ];
    });
    

1  
2  
3  
4  
5  
6  
7