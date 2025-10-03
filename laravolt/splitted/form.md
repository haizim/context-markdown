Core Components

Form Component
==============

Laravolt provides a powerful Form component for creating forms that follow Fomantic UI styling, with automatic handling of input validation, error messages, and model binding.

* * *

Introduction
------------

Laravolt Form is a helper for creating forms that follow the [Fomantic UI](https://fomantic-ui.com) styling guidelines. It handles many common form-related tasks automatically, letting you focus on functionality rather than markup.

Without Laravolt Form, typical code needed to create a form with Laravel, complete with `Old Input` and `Error` handling, usually looks like this:

HTML

    <form class="ui form">  <div class="field {{ $errors->has('name') ? 'error' : '' }}">    <label>Your Fullname</label>    <input type="text" name="name" value="{{ old('name') }}" />  </div></form>

With Laravolt Form, the code above can be simplified to:

PHP

    {!! form()->open() !!}{!! form()->text('name')->label('Your Fullname') !!}{!! form()->close() !!}

You can focus on form functionality. The structure (HTML), appearance (CSS), and behavior (JS) are all handled by Laravolt.

Features
--------

Laravolt Form automatically handles the following:

*   Styling according to Fomantic UI guidelines
*   Error state display
*   Preserving old input, so entries don't disappear when form submission errors occur
*   Model binding, automatically filling forms from Eloquent models

Usage
-----

### Overview

Laravolt Form can be called in two ways:

*   Through the **Form** Facade, e.g., `Form::open()`
*   Through the **form()** helper, e.g., `form()->open()`

Using the `form()` helper function is recommended as it supports auto-completion.

Here's a general overview of creating a form:

PHP

    // Open the formform()->open()->route('post.store');// Other fields here...// Submit buttonform()->submit('Save');// Close the formform()->close();

### Opening Forms

PHP

    form()->open('search'); // action="search"form()->open()->get();form()->open()->post();form()->open()->put();form()->open()->patch();form()->open()->delete();form()->open(); // default to method="GET"form()->open()->action('search');form()->open()->url('search'); // alias for action()form()->open()->route('route.name');form()->open()->post()->action(route('comment.store'));form()->open()->post()->multipart(); // Required if the form is used for file uploads

### Opening Forms (Shortcuts)

PHP

    form()->open('search'); // action="search" method=POSTform()->get('search'); // action="search" method=GETform()->post('search'); // action="search" method=POSTform()->put('search'); // action="search" method=POST _method=PUTform()->patch('search'); // action="search" method=POST _method=PATCHform()->delete('search'); // action="search" method=POST _method=DELETE

### CSRF Token

The [CSRF Token](https://laravel.com/docs/master/csrf), which is one of Laravel's form security methods, is handled automatically. A CSRF Token is generated whenever a form is created, except for forms with the `GET` method.

If you want to force Laravolt Form to remove the CSRF Token, you can call the `withoutToken()` method when opening the form:

PHP

    form()->post('search')->withoutToken();

Form Fields
-----------

### Basic Inputs

#### Checkbox

PHP

    form()->checkbox($name, $value, $checked)->label('Remember Me');

#### Checkbox Group

PHP

    $values = ['apple' => 'Apple', 'banana' => 'Banana'];$checkedValue = 'banana';form()->checkboxGroup($name, $values, $checkedValue)->label('Select Fruit');

#### Coordinate

PHP

    form()->coordinate('location');

Displays a map that can be clicked or dragged to obtain latitude and longitude coordinates, using the Google Maps API.

#### Email

PHP

    form()->email($name, $value)->label('Email Address');

#### Hidden

PHP

    form()->hidden($name, $value);

#### Input Wrapper

PHP

    form()->input($name, $defaultvalue, $type = 'text');form()->input($name, $defaultvalue)->appendIcon('search');form()->input($name, $defaultvalue)->prependIcon('users');form()->input($name, $defaultvalue)->appendLabel($label);form()->input($name, $defaultvalue)->prependLabel($label);form()->input($name, $defaultvalue)->type("password");

Reference: [Fomantic UI Input Element](https://fomantic-ui.com/elements/input.html)

#### Number

PHP

    form()->number($name, $integerValue)->label('Total');// Additional methods specific to number inputsform()  ->number("age", 17)  ->min(7) // set minimum allowed value  ->max(35) // set maximum allowed value  ->step(1);

#### Password

PHP

    form()->password($name)->label('Password');

#### Text

PHP

    form()->text($name, $value)->label('Username');

#### Textarea

PHP

    form()->textarea($name, $value)->label('Note');

#### Time

PHP

    form()->time($name, $value)->label('Start Time');

#### Radio

PHP

    $checked = true;form()->radio($name, $value, $checked)->label('Item Label');

#### Radio Group

PHP

    $values = ['apple' => 'Apple', 'banana' => 'Banana'];$checkedValue = 'banana';form()->radioGroup($name, $values, $checkedValue)->label('Select Fruit');

#### Rupiah

PHP

    form()->rupiah('price', $defaultValue);

Displays a number input with automatic thousands formatting, using [AutoNumeric.js](http://autonumeric.org/).

### Date & Time

#### Date

PHP

    form()->date($name, $value)->label('Birthday');

#### Datepicker

For date only:

PHP

    form()->datepicker($name, $value, $format);// $format can be set according to formats specified in https://www.php.net/manual/en/function.date.php// To convert localized format to standard (SQL) datetime format, you can use Jenssegers\Date\Date library (already included):// Jenssegers\Date\Date::createFromFormat('d F Y', '12 February 2000')->startOfDay()->toDateTimeString();// Jenssegers\Date\Date::createFromFormat('d F Y', '12 February 2000')->startOfDay()->toDateString();

#### Datepicker with time

For both date and time:

PHP

    form()->datepicker()->withTime();

#### Timepicker

Time dropdown only, without date:

PHP

    form()->timepicker($name, $value);

#### Select Date & Select Date Time

PHP

    form()->selectDate('myDate', $startYear, $endYear)->label('Birth Date');form()->selectDateTime('myDate', $startYear, $endYear, $intervalInMinute)->label('Schedule');

Dates and times selected through `selectDate` and `selectDateTime` will be sent with the name `_myDate` in array format:

PHP

    // $_POST[  '_myDate' => ['date'=>4, 'month'=>5, 'year'=>2016]]

For automatic conversion to a database-recognized date format, such as `2016-5-4`, Laravolt Form provides two middleware options: `SelectDateMiddleware` and `SelectDateTimeMiddleware`. They're easy to use:

##### 1\. Register the Middleware

###### app/Http/Kernel.php

PHP

    protected $routeMiddleware = [    'selectdate' => \Laravolt\Form\Middleware\SelectDateMiddleware::class,    'selectdatetime' => \Laravolt\Form\Middleware\SelectDateTimeMiddleware::class];

##### 2\. Call the Middleware

###### routes/web.php

PHP

    Route::post('myForm', ['middleware' => ['web', 'selectdate:myDate'], function () {	dd($_POST['myDate']); // 2016-5-4}]);

### Select/Dropdown

#### Single Value Select (Dropdown)

PHP

    $options = [    'id' => 'Indonesia',    'ms' => 'Malaysia',];form()->select($name, $options)->label('Choose Country');form()->select($name, $options, $selected)->label('Choose Country');form()->select($name, $options)->placeholder('--Select--');form()->select($name, $options)->appendOption($key, $label);form()->select($name, $options)->prependOption($key, $label);

#### Multiple Select (Tagging)

PHP

    $options = [    'id' => 'Indonesia',    'ms' => 'Malaysia',];form()->select($name, $options, $selected)->multiple()->label('Select Multiple');

#### Select Range

PHP

    form()->selectRange($name, $begin, $end)->label('Number of children');

#### Select Month

PHP

    form()->selectMonth($name, $format = '%B')->label('Month');

#### Dropdown DB

PHP

    $query = 'SELECT id, name from provinces order by name';form()->dropdownDB('province', $query, $keyColumn = 'id', $valueColumn = 'name');

With the code above, dropdown options will be automatically populated using raw query results from the database. Additionally, you can easily create chained dropdowns using the `dependency()` method:

PHP

    $query = 'SELECT id, name from districts where province_id = %s'form()->dropdownDB('district', $query, 'id', 'name')->dependency('province');

Whenever the province dropdown changes its value, the district dropdown will also update its options according to the selected province.

> _Under the hood_, the province **ID** will be sent to the server via AJAX, and the query for the district dropdown will be executed by replacing the **%s** placeholder with that province **ID**.

**Prepopulate Child Dropdown**

By default, only the parent dropdown will query when the page first loads. Queries for child dropdowns are only executed when their parent values change. However, sometimes the child dropdown options also need to be generated initially, such as when creating an edit page.

For example, if a user has previously selected a province and district, we can display the selected values initially like this:

PHP

    $selectedProvince = 1;$selectedDistrict = 56;$provinceQuery = 'SELECT id, name from provinces order by name';form()->dropdownDB('province', $query, $keyColumn = 'id', $valueColumn = 'name')->value($selectedProvince);$districtQuery = 'SELECT id, name from districts where province_id = %s'form()->dropdownDB('district', $query, 'id', 'name')->value($selectedDistrict)->dependency('province', $selectedProvince);

As you can see, we just need to set each dropdown's value with `->value($selectedValue)` and add a second parameter to the `->dependency('province', $selectedProvince)` method. This way, both dropdown options will be populated initially, and their selected values can be set as usual.

### File Inputs

#### Standard HTML File Input

PHP

    form()->file($name);

#### Uploader

A wrapper for the [fileuploader](https://innostudio.de/fileuploader/documentation/) library.

PHP

    {!!  form()  ->uploader('files')  ->limit($maxUploadedFile) //optional, default to 1 (single file upload)  ->extensions(['jpg', 'png']) // optional, default to null (all files allowed)  ->fileMaxSize($sizeInMB)  //optional, default to 1000 MB  ->mediaUrl($customURL) //optional, default to route("media::store"), handled by Laravolt!!}

### Rich Text Editor (WYSIWYG)

#### Redactor

PHP

    form()->redactor($name, $value);//Additional Methodsform()->redactor($name, $value)->mediaUrl($url); //custom URL to handle file upload, default to route("media::store")

### Actions

#### Button

PHP

    form()->button($value);

#### Link

PHP

    form()->link($label, $url);

#### Submit

PHP

    form()->submit($value);

### Model Binding

#### Version 1

PHP

    {!! form()->bind($model) !!}

#### Version 2

PHP

    // as parameter for method open(){!! form()->open($route, $model) !!}// or chaining it{!! form()->bind($model)->get($route) !!}

> **Warning** This syntax is OK in version 1, but will produce an error in version 2:
> 
> PHP
> 
>     {!! form()->bind($model) !!}

### Macros

Macros are used to register custom fields for easier calling.

PHP

    form()->macro('trix', function ($id, $name, $value = null) {    return sprintf(        "%s %s",        form()->hidden($name, $defaultValue)->id($id),        "<trix-editor input='{$id}'></trix-editor>"    );});

Once registered, macros can be called directly by Laravolt Form:

PHP

    form()->trix('contentId', 'content', '<b>some content</b>');

### Actions

`Action` is used to group action buttons (Save, Cancel, Reset, etc.) in a form. Combining `Action` and `Macro` can simplify form creation, especially if many forms have uniform buttons.

#### Manual Action

PHP

    form()->action(form()->submit('Save'), form()->button('Cancel'));

#### Shortcut With Macro 1

PHP

    // Assume you've already defined some macros:form()->macro('submit', function(){    return form()->submit('Submit');});form()->macro('cancel', function(){    return form()->button('Cancel');});// Then you can just call macro names as stringsform()->action('submit', 'cancel');

#### Shortcut With Macro 2

PHP

    // Going further, you can define a macro that wraps multiple buttons:Form()->macro('default', function(){    return new \Laravolt\Form\Elements\Wrapper(      form()->button('Cancel'),      form()->submit('Submit')    );});// Making the call simpler:form()->action('default');

### Layout

By default, Laravolt Form will generate a vertically arranged form from top to bottom.

If you want to apply a two-column side-by-side layout (labels on the left, inputs on the right), simply call the `horizontal()` method when creating the form:

PHP

    form()->open()->horizontal()

### Other Methods

For any type of form, these methods can be called as needed:

*   `id($string)`
*   `addClass($string)`
*   `removeClass($string)`
*   `attribute($name, $value)`
*   `clear($attribute)`
*   `required()`
*   `readonly()`
*   `data($name, $value)`
*   `enable($flag = true)`
*   `disable($flag = true)`
*   `hint($text)`
*   `hint($text, $class = "hint")`

### Override Hint Class Globally

PHP

    // Add this code when booting, for example in AppServiceProviderLaravolt\Form\Elements\Hint::$defaultClass = 'custom-class';

#### Examples

PHP

    form()->text($name, $value)->label('Username')->id('username')->addClass('foo');form()->text($name, $value)->label('Username')->data('url', 'https://laravolt.dev');form()->password($name, $value)->label('Password')->hint('Minimum 6 characters');form()->password($name, $value)->label('Password')->hint('Minimum 6 characters', 'my-custom-css-class');

Credits
-------

Laravolt Form is inspired by [AdamWathan\\Form](https://github.com/adamwathan/form).