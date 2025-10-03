## === overview.md ===
## Introduction

Introduction to Laravolt
========================

Laravolt is a comprehensive digital empowerment platform that combines technical frameworks and philosophical approaches to build sustainable information systems, born from deep experience addressing the unique complexities of Indonesia's technology landscape.

* * *

Overview
--------

As a platform, Laravolt represents far more than just a collection of code written by contributors and packaged under a name. It's not merely an admin template for repeated use, nor is it just a set of battle-tested libraries you can confidently employ. And it's definitely not just a marketing gimmick from [Javan](https://javan.co.id).

More importantly, Laravolt is:

1.  An open source movement where programmers can learn, collaborate, and contribute locally while following international code standards
2.  A practical and effective coding guide for solving everyday problems
3.  An ecosystem designed to improve Indonesia through information technology

Core Principles
---------------

Laravolt was built with a set of guiding principles that shape its development and usage:

### Simplicity

We believe that well-designed software should be intuitive and straightforward. Laravolt aims to reduce complexity by providing clean abstractions and sensible defaults that make development more productive and enjoyable.

### Flexibility

Every project has unique requirements. Laravolt is designed to be adaptable, allowing you to use just the components you need and customize them to fit your specific use case.

### Community-Driven

Laravolt is built by and for developers. We value community contributions and feedback, which help shape the platform's evolution and ensure it addresses real-world needs.

### Indonesian Context

Laravolt is specifically designed to address the unique challenges faced in Indonesian software development, from bureaucratic processes to specific cultural considerations.

Key Objectives
--------------

### 1\. Successful System Development

Information system development in Indonesia has uniquely challenging characteristics. There are often requirements that may not seem ideal from a vendor's perspective but must be fulfilled for the system to be adopted and used.

The ideal Software Development Life Cycle (SDLC) process that looks promising in initial presentations typically cannot be implemented comprehensively. There are numerous stakeholders, bureaucratic procedures, and challenges to overcome for a successful information system project.

Laravolt exists to ensure technical success, allowing development teams to focus on other equally important aspects of project delivery.

### 2\. Programmer Development

Another crucial factor is the quality of human resources (specifically programmers). Experienced developers often prefer joining startups, founding their own companies, or working on international projects.

This leaves behind programmers with great potential who are still developing their competencies—those who have recently completed formal education or are building their foundations in the technology sector. They represent the future of Indonesia's IT ecosystem and are key to successful digital transformation and e-government initiatives. They don't lack quality; they lack opportunities to hone their skills and face real challenges.

Laravolt serves as a bridge connecting potential with experience.

Platform Components
-------------------

Laravolt consists of several integrated components that work together to provide a comprehensive development experience:

### Core Framework

Built on Laravel, Laravolt extends the framework with additional functionality specifically designed for Indonesian contexts and common use cases in government and enterprise applications.

### UI Components

A complete set of user interface components that follow consistent design patterns, making it easy to build professional-looking applications with minimal effort.

### Development Tooling

Tools and utilities that streamline the development process, helping teams maintain code quality and follow best practices.

### Documentation and Guides

Comprehensive documentation, tutorials, and guides to help both new and experienced developers get the most out of the platform.

Getting Started
---------------

Ready to start building with Laravolt? Check out the following resources:

*   [Installation Guide](/v6/installation) - Set up Laravolt in your project
*   [Hello World](/v6/hello-world) - Create your first Laravolt application
*   [Starter Kit](/v6/starter-kit) - Jump-start your development with pre-built templates

Community and Support
---------------------

Join the Laravolt community to connect with other developers, get help with your projects, and contribute to the platform:

*   [GitHub Repository](https://github.com/laravolt/laravolt) - Report issues and contribute code
*   [Official Website](https://laravolt.dev) - Latest news and announcements

Are you ready to become part of this change?## === installation.md ===
## Installation
============

This guide will walk you through the process of installing Laravolt in your Laravel project.

* * *

Server Requirements
-------------------

Before installing Laravolt, make sure your environment meets the following requirements:

1.  PHP >= 8.2
2.  Laravel >= 11.0
3.  SQLite, MySQL, MariaDB, or PostgreSQL database
4.  Essential PHP Extensions:
    *   BCMath - For high-precision mathematics
    *   Ctype - For character type validation
    *   cURL - For HTTP requests to external services
    *   DOM - For XML/HTML document manipulation
    *   Exif - For reading metadata from image files
    *   Fileinfo - For MIME type detection
    *   Filter - For data sanitization and validation
    *   GD - For image manipulation (required for media and avatar features)
    *   Hash - For hashing and encryption
    *   Iconv - For character encoding conversion
    *   JSON - For JSON data processing
    *   Libxml - Required for DOM and XML extensions
    *   Mbstring - For multibyte string handling
    *   OpenSSL - For encryption and security features
    *   PCRE - For regular expressions
    *   PDO - For database connections
    *   Session - For user session management
    *   Tokenizer - For PHP code processing
    *   XML - For XML data processing and API responses
    *   XMLWriter - For generating XML files
    *   Zip - For file compression and decompression
    *   Zlib - For data compression

### Checking PHP Extensions

There are several ways to check which PHP extensions are installed on your system:

1.  **Using Terminal/Command Line**:
    
    Bash
    
        php -m
    
    This command displays a list of all installed PHP extensions.
    
2.  **Using a PHP Script**: Create a file named `phpinfo.php` with the following content:
    
    PHP
    
        <?php phpinfo(); ?>
    
    Place this file in your web server directory and access it via browser.
    
3.  **Using Composer in a Laravolt Project**:
    
    Bash
    
        composer check-platform-reqs
    
    This command checks whether your system meets all platform requirements from installed packages.
    

### Installing PHP Extensions

Here's how to install commonly used PHP extensions on various operating systems:

#### On Ubuntu/Debian:

Bash

    sudo apt-get updatesudo apt-get install php8.2-bcmath php8.2-curl php8.2-xml php8.2-gd php8.2-mbstring php8.2-zip# Replace 8.2 with your PHP version

#### On CentOS/RHEL:

Bash

    sudo yum install php-bcmath php-curl php-xml php-gd php-mbstring php-zip

#### On macOS (using Homebrew):

Bash

    brew install php# PHP from Homebrew usually includes most required extensions

#### On Windows (XAMPP/WAMP):

Most extensions are enabled by default. To enable additional extensions:

1.  Open the `php.ini` file (usually located in the PHP installation folder)
2.  Find the line containing the extension name (e.g., `;extension=gd`)
3.  Remove the semicolon (`;`) at the beginning of the line to enable the extension
4.  Restart the web server

### Common Troubleshooting

1.  **"Call to undefined function" error**: This error message typically indicates that a required PHP extension is not installed or enabled.
    
2.  **Error during Composer installation**:
    
    Bash
    
        Problem 1    - laravolt/laravolt requires ext-gd * -> the requested PHP extension gd is missing from your system.
    
    Solution: Install the requested extension using the instructions above.
    
3.  **Image or avatar errors**: If image manipulation features aren't working, make sure the GD extension is properly installed:
    
    Bash
    
        php -m | grep gd
    
    If there's no output, the GD extension is not installed.
    
4.  **Checking PHP version**:
    
    Bash
    
        php --version
    
    Make sure you're using PHP 8.2 or higher for Laravolt.
    

Installing Laravolt
-------------------

**Laravolt** is a package, so you must already have a Laravel application set up before installation. For Laravel installation, refer to the [official documentation](https://laravel.com/docs/master#installing-laravel). Ensure your configuration is correct and the default Laravel page is accessible in your browser.

Once your Laravel application is ready, follow these steps:

### 1\. Install the Package

Bash

    composer require laravolt/laravolt

### 2\. Set Up Laravolt

Several files need to be generated and customized for Laravolt to run properly. Simply run the following command:

Bash

    php artisan laravolt:install

### 3\. Migrate the Database

Next, don't forget to run the migrations (fresh, because Laravel installation auto migrate itself):

Bash

    php artisan migrate:fresh

### 4\. Add an Admin User

To add a user with admin role, run the interactive command:

Bash

    php artisan laravolt:admin

Or, for a quicker method without answering questions one by one:

Bash

    php artisan laravolt:admin Administrator [email protected] secret

### 5\. Local Development

As known, running a PHP application requires a **_web server_**. Here are several ways to run Laravolt in a local development environment:

#### Using Laravel's PHP Built-in Server

The simplest way to run a Laravel application is with the development server via PHP's built-in server. Run the following command:

Bash

    php artisan serve

The application will be accessible at http://localhost:8000.

#### Using Composer Scripts

Since Laravel 11, there's a `dev` script that can be used to run multiple services simultaneously. If you're using Laravel 11.28 or above, simply run:

Bash

    composer dev

This script will run multiple services (Vite, queue worker, logs, web server) in a single terminal.

#### Alternative Local Development Tools

If you need a more comprehensive development server, try these alternatives:

1.  [Laravel Herd](https://herd.laravel.com/) - Official development server from Laravel
2.  [Laragon](https://laragon.org/) - Recommended for Windows, all needs are integrated
3.  [XAMPP](https://www.apachefriends.org/index.html) - Popular for beginners
4.  [WampServer](http://www.wampserver.com/en) - Alternative for Windows
5.  [Laravel Valet](https://laravel.com/docs/master/valet) - Specifically for macOS
6.  [Laradock](https://laradock.io/) - Complete Docker solution for the Laravel ecosystem

### 6\. Log in to the Application

After the server is running, access the application through your browser and log in using the admin credentials you created earlier:

*   URL: http://localhost:8000/auth/login
*   Email: the email you entered when running the `laravolt:admin` command (default: [\[email protected\]](/cdn-cgi/l/email-protection))
*   Password: the password you entered when running the `laravolt:admin` command (default: secret)

Congratulations, you've successfully installed and launched Laravolt!

What's Next?
------------

Now that you have Laravolt installed, you might want to explore:

1.  [UI Components](/docs/form) - Learn about Laravolt's form, table, and other UI components
2.  [Workflow](/docs/workflow) - Integrate complex business processes with Camunda
3.  [Access Control](/docs/acl) - Set up roles and permissions for your application## === hello-world.md ===
## Hello World
===========

Laravolt integrates seamlessly with Laravel, preserving all the familiar elements you already know. Everything you've learned about Laravel applies to Laravolt without any structural changes, command modifications, or feature limitations. If you know Laravel, you already know how to use Laravolt.

* * *

Overview
--------

This guide will walk you through creating a simple dashboard page in Laravolt that will be accessible through the sidebar menu. By the end, you'll have created a fully functional page that demonstrates the core concepts of building applications with Laravolt.

![Dashboard Example](https://cdn.statically.io/gh/laravolt/storage/master/2021/10/hello-world-dashboard-spWIgC.png)

Basic Usage
-----------

Let's create a dashboard page that can be accessed from the side menu. Here's a step-by-step guide:

### 1\. Creating the Controller

First, generate an invokable controller for our dashboard:

Bash

    php artisan make:controller DashboardController --invokable

Then edit the generated controller to render a view:

PHP

    <?phpnamespace App\Http\Controllers;use Illuminate\Http\Request;class DashboardController extends Controller{    public function __invoke(Request $request)    {        return view('dashboard');    }}

### 2\. Creating the View

Laravolt provides a command to generate view files with basic structure:

Bash

    php artisan make:view dashboard --title=Dashboard

This creates a file at `resources/views/dashboard.blade.php`. Open and edit the file to add your content:

PHP

    <x-volt-app title="Dashboard">    Hello world!</x-volt-app>

### 3\. Adding a Route

Define a route for the dashboard in your routes file:

PHP

    Route::get('dashboard', \App\Http\Controllers\DashboardController::class)->name('dashboard');

### 4\. Adding a Menu Item

Configure the dashboard to appear in the sidebar menu by editing the menu configuration:

PHP

    // config/laravolt/menu/app.phpreturn [    'App' => [        'menu' => [            'Dashboard' => [                'route' => 'dashboard',            ],        ],    ],];

Advanced Features
-----------------

### Code Generators

Laravolt provides several code generators to accelerate development:

*   `php artisan make:view` - Create skeleton Blade files
*   `php artisan make:table` - Generate datatable configurations
*   `php artisan make:chart` - Create chart components
*   `php artisan make:crud` - Generate complete CRUD functionality

These generators help you quickly scaffold common application components with Laravolt's best practices built in.

### Blade Components

Laravolt extensively utilizes Laravel's Blade Components for UI construction. We've already seen `<x-volt-app>` for page layouts, but Laravolt includes many more:

*   `<x-volt-panel>` - Content panels with headers and footers
*   `<x-volt-grid>` - Grid layouts for responsive design
*   `<x-volt-icon>` - Icon components with consistent styling
*   And many more...

Best Practices
--------------

When building applications with Laravolt, consider these recommendations:

1.  **Use Blade Components**: Leverage the built-in components to ensure UI consistency and reduce redundant code.
    
2.  **Organize Menu Configuration**: Keep your menu structure clean and intuitive in the configuration files.
    
3.  **Stick to Defaults**: Most applications work well with Laravolt's default configuration. Only customize when necessary.
    
4.  **Encapsulate UI Logic**: Use components to hide styling (CSS) and logic (JavaScript), keeping your blade files clean and focused on structure.
    

Troubleshooting
---------------

### Menu Items Not Appearing

If your menu items don't appear in the sidebar:

*   Verify that the route name in the menu configuration matches the defined route
*   Check user permissions if you're using Laravolt's ACL features
*   Clear configuration cache with `php artisan config:clear`

### View Not Rendering Correctly

If your view doesn't look as expected:

*   Ensure you're using the correct Blade components
*   Check for missing CSS or JS assets
*   Verify that the view name matches what's referenced in your controller

Related Components/Features
---------------------------

*   [Menu Configuration](/v6/menu) - Learn more about configuring application menus
*   [Blade Components](/v6/blade-components) - Explore all available UI components
*   [Form Building](/v6/form) - Create interactive forms with Laravolt
*   [Table Management](/v6/table) - Display and manage data in tables## === starter-kit.md ===
## Starter Kit
===========

During installation, Laravolt automatically generates several components to make your application ready for immediate use. Understanding these automatically generated elements helps you better comprehend how the application works and provides the freedom to modify them according to your specific requirements.

* * *

Overview
--------

The Laravolt Starter Kit provides a foundation for your application with pre-configured components and features that address common requirements in information systems. This guide explains what gets generated during installation and how you can customize these elements to suit your needs.

Installation/Setup
------------------

When you install Laravolt, the following setup processes occur automatically:

### Asset Symlink

Laravolt includes a set of assets (CSS, JavaScript, and images) essential for proper application functionality. These assets are "copied" to the `public` folder using a symlink mechanism.

The assets are located at `/public/laravolt`.

If for any reason these assets cannot be accessed from the web, you can remove the `/public/laravolt` folder and recreate the symlink by running:

Bash

    php artisan laravolt:link

Due to this symlink approach, the `/public/laravolt` folder is automatically added to your `.gitignore` file.

### Database Migration

Laravolt generates several migration scripts to create tables and columns required for authentication and authorization. The resulting database structure is illustrated in the Entity Relationship Diagram below:

Before running `php artisan migrate`, you can freely modify these migration scripts to match your specific requirements.

Basic Usage
-----------

### Authentication Components

Laravolt automatically generates a complete authentication system including:

1.  **Login** - A secure authentication interface
2.  **Logout** - Clean session termination
3.  **Password Recovery** - Self-service password reset functionality
4.  **Registration** - User sign-up capability
5.  **Email Verification** - Account verification process

### User Profile Management

A dedicated interface for users to manage their profiles and passwords is included. This provides:

*   Profile information editing
*   Password changing capability
*   User preference management

### Error Handling

Laravolt implements several global handlers to manage common application errors:

1.  **TokenMismatchException** - Manages errors when forms are submitted after tokens expire
2.  **AuthorizationException** - Handles unauthorized access attempts
3.  **Sentry Integration** - Automatic error reporting to Sentry if installed

### Front-End Setup

The starter kit includes a webpack configuration framework integrated with [Tailwind CSS](https://tailwindcss.com/), providing:

*   Modern asset compilation pipeline
*   Utility-first CSS framework
*   Hot module replacement for development

### Documentation

An informative README file is generated with:

*   System requirements
*   Setup instructions
*   Initial installation guide

Advanced Features
-----------------

### Customizing the Starter Kit

While the starter kit provides a solid foundation, you may need to adapt it to your specific requirements:

1.  **Modifying Authentication Flow**:
    
    *   Edit controllers in `app/Http/Controllers/Auth`
    *   Customize views in `resources/views/auth`
2.  **Extending User Management**:
    
    *   Modify the User model to add custom fields
    *   Update migrations to include additional tables or columns
3.  **Tailoring the UI**:
    
    *   Customize Tailwind configuration in `tailwind.config.js`
    *   Override default styles in your CSS files

Best Practices
--------------

When working with the Laravolt Starter Kit, consider these recommendations:

1.  **Review Before Migration** - Carefully examine the generated migration files before running them, ensuring they align with your database design requirements.
    
2.  **Extend, Don't Replace** - When possible, extend the existing functionality rather than replacing it entirely to maintain compatibility with future Laravolt updates.
    
3.  **Document Customizations** - Keep track of any modifications you make to the starter kit components for easier maintenance and knowledge transfer.
    
4.  **Test Authentication Changes** - When modifying authentication components, thoroughly test all flows to ensure security is maintained.
    

Troubleshooting
---------------

### Missing Assets

If your application lacks styling or JavaScript functionality:

*   Verify the symlink exists at `/public/laravolt`
*   Run `php artisan laravolt:link` to recreate the symlink
*   Check browser console for resource loading errors

### Migration Issues

If you encounter problems during database migration:

*   Examine migration files for compatibility with your database
*   Check database permissions and connection settings
*   Run migrations with `--pretend` flag first to preview changes

Related Components/Features
---------------------------

*   [Installation Guide](/v6/installation) - Complete setup instructions
*   [Authentication](/v6/authentication) - Detailed documentation on authentication features
*   [User Management](/v6/user-management) - Working with user data and permissions
*   [Frontend Assets](/v6/frontend-assets) - Managing CSS and JavaScript resources## === form.md ===
## Form Component
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

Laravolt Form is inspired by [AdamWathan\\Form](https://github.com/adamwathan/form).## === table.md ===
## Table Component
===============

Laravolt provides a powerful Table component for displaying data in a tabular format with features like searching, sorting, and filtering - all without writing JavaScript.

![Table Component Example](https://cdn.statically.io/gh/laravolt/storage/master/2021/10/image-20211002210333023-k5QGay.png)

* * *

Introduction
------------

Laravolt Table provides a UI for displaying data in tabular form with supporting features like searching, sorting, and filtering. Built on [Livewire](https://laravel-livewire.com/), tables can be interacted with without full page refreshes. You don't need to worry about JavaScript because all UI-related aspects are already handled by Laravolt - just focus on writing PHP code.

Creating Tables
---------------

Because tables are built on Livewire, all Table classes are stored in the `app\Http\Livewire\Table` folder. To create a new Table, run the `make:table` command:

Bash

    php artisan make:table UserTable

Then, define your data source and the columns to display:

PHP

    use Laravolt\Suitable\Columns\Text;class UserTable extends TableView{    public function data()    {        return \App\Models\User::where('status', 'ACTIVE')->paginate();    }    public function columns(): array    {        return [            Text::make('name', 'Name'),            Text::make('email', 'Email'),        ];    }}

Displaying Tables
-----------------

To display a table, simply call the Blade component or directive from your view:

PHP

    <livewire:table.user-table />// or@livewire('table.user-table')// or@livewire(\App\Http\Livewire\Table\UserTable::class)

### Reference

*   [Livewire Documentation on Rendering Components](https://laravel-livewire.com/docs/2.x/rendering-components)

Data Sources
------------

Laravolt Table can process several types of data sources to display in a table. The available options for the `data()` method return value are:

*   Array
*   Collection
*   Eloquent
*   Query Builder
*   Response from HTTP Client

### Array

The simplest data source is an `array`:

PHP

    public function data(){    return [        ['name' => 'Andi', 'email' => '[email protected]'],        ['name' => 'Budi', 'email' => '[email protected]'],    ];}

### Collection

You can also use `\Illuminate\Support\Collection` as a data source:

PHP

    public function data(){    $users = [        ['name' => 'Andi', 'email' => '[email protected]'],        ['name' => 'Budi', 'email' => '[email protected]'],        ['name' => 'Citra', 'email' => null],    ];    return collect($users)->reject(fn($user) => $user->email === null);}

### Eloquent

The most commonly used data source is Eloquent:

PHP

    use App\Models\User;public function data(){    return User::whereNull('deleted_at')->paginate();}

If you don't need pagination, you can directly call `get()`:

PHP

    use App\Models\User;public function data(){    return User::query()->whereNull('deleted_at')->get();}

### Query Builder

If Eloquent isn't your preference and you prefer Query Builder, you can still apply the same approach:

PHP

    public function data(){    return \DB::table('users')->whereNull('email')->paginate();}

Or without pagination:

PHP

    public function data(){    return \DB::table('users')->get();}

### Response From HTTP Client

To retrieve data directly from an API, you can use Laravel's built-in [HTTP Client](https://laravel.com/docs/master/http-client):

PHP

    use Illuminate\Support\Facades\Http;public function data(){    return Http::get('https://jsonplaceholder.typicode.com/users');}

Column Types
------------

Laravolt Table provides various column types to display different kinds of data appropriately:

### Avatar

The `Avatar` column automatically displays avatar images generated from initials. In the example below, the email initials will be used to generate an appropriate avatar image:

PHP

    use Laravolt\Suitable\Columns\Avatar;public function columns(): array{    return [        Avatar::make('email', 'Avatar'),    ];}

Complete documentation about `Avatar` can be found at [https://github.com/laravolt/avatar](https://github.com/laravolt/avatar).

### Boolean

The `Boolean` column displays **_true_** or **_false_** values as icons. Non-boolean values will be automatically cast to `(bool)`:

PHP

    use Laravolt\Suitable\Columns\Boolean;public function columns(): array{    return [        Boolean::make('is_active'),    ];}

### Button

The `Button` column adds buttons that function as navigation to other pages:

PHP

    use Laravolt\Suitable\Columns\Button;public function columns(): array{    return [        Button::make('permalink', 'Info')->label('Profile')->icon('external link'),    ];}

In the example above, `permalink` contains a valid URL, either a hardcoded "http://example.com" or the result of calling Laravel's `route()` or `url()` function:

PHP

    class User extends Model{    public function getPermalinkAttribute()    {        return route('users.show', $this->id);    }}

`Button::make()` also accepts a `Closure` to dynamically generate URLs:

PHP

    use Laravolt\Suitable\Columns\Button;public function columns(): array{    return [        // using arrow function syntax        Button::make(fn ($user) => route('users.show', $user['id'])),        // or the longer traditional way        Button::make(            function ($user) {                return route('users.show', $user['id']);            }        ),    ];}

### Checkall

The `Checkall` column adds a **checkbox** to each row that can be used for multiple selection. Selected IDs can then be sent as parameters when defining `Table Action`:

PHP

    use Laravolt\Suitable\Columns\Checkall;public function columns(): array{    return [        Checkall::make('id'),    ];}

### Date

The `Date` column converts database dates with format `2021-06-02` to a more human-readable format, like **June 2, 2021**:

PHP

    use Laravolt\Suitable\Columns\Date;public function columns(): array{    return [        Date::make('created_at'),    ];}

Additional methods available for the `Date` column type:

*   `format(string $format)` where $format is a string that follows the format accepted by [Moment.js](https://momentjs.com/).
*   `timezone(string $timezone)` for automatic date conversion to the appropriate timezone. Valid timezones can be found in the [official PHP documentation](https://www.php.net/manual/en/timezones.php). If `timezone()` is not explicitly called, the conversion will consider:
    *   The `timezone` attribute of the currently logged-in user: `auth()->user()->timezone`.
    *   If null, the timezone will be taken from `config('app.timezone')`.

### DateTime

Similar to the `Date` column, `DateTime` changes values like **2021-06-02 22:54:00** to **June 2, 2021 at 22:45**:

PHP

    use Laravolt\Suitable\Columns\DateTime;public function columns(): array{    return [        DateTime::make('created_at'),    ];}

The `format()` and `timezone()` methods are also available, with the same behavior as the `Date` column.

### Html

The `Html` column is used when the content to be displayed contains HTML tags, and you want to display it according to HTML format:

PHP

    public function data(){    return [        ['bio' => '<b>Strong</b> <i>foo</i>'],    ];}public function columns(): array{    return [        Html::make('bio')    ];}

In the example above, the table will display the content as "**Strong** _foo_". This column is commonly used when the stored data comes from a **WYSIWYG** or **_rich text editor_** like Redactor or TinyMCE.

### Id

The `Id` column is used to display the primary key of an Eloquent model. Behind the scenes, this column will call `getKey()`. So make sure to only use this column when the data source comes from Eloquent:

PHP

    use Laravolt\Suitable\Columns\Id;public function columns(): array{    return [      Id::make(),    ];}

### Image

The `Image` column is used to display images:

PHP

    use Laravolt\Suitable\Columns\Image;public function columns(): array{    return [      Image::make('profile_picture')    ];}

Additional methods available:

*   `height(int $sizeInPixel)` to set the image height.
*   `width(int $sizeInPixel)` to set the image width.
*   `alt(string $text)` to set the `alt` attribute (alternate text).

### Label

The `Label` column is used to display a value so it stands out more. Examples of values suitable to be displayed as `Label` include: status, category, type, and similar attributes:

PHP

    use Laravolt\Suitable\Columns\Label;public function columns(): array{    return [        Label::make('status'),    ];}

To add CSS classes to a `Label`, you can use the `addClass` method:

PHP

    use Laravolt\Suitable\Columns\Label;public function columns(): array{    return [        Label::make('status')->addClass('green small'),    ];}

There are several **_built-in_** classes that can be used to determine the color of a `Label`: `red`, `orange`, `yellow`, `olive`, `green`, `teal`, `blue`, `violet`, `purple`, `pink`, `brown`, `grey`, and `black`.

In practice, there's a need to give different colors to each _value_. This can be done using the `map()` method:

PHP

    use Laravolt\Suitable\Columns\Label;public function columns(): array{    return [        Label::make('status')->map([            'active' => 'green',            'banned' => 'red',        ]),    ];}

### Number

The `Number` column is used to display a _value_ in a more human-friendly number format. For example, a value of 1000000 will automatically be changed to **1,000,000** and displayed **right-aligned**:

PHP

    use Laravolt\Suitable\Columns\Number;public function columns(): array{    return [        Number::make('salary',)    ];}

The number format currently used is the format commonly used in Indonesia.

### Raw

The `Raw` column is used to display a `value` **as is** (_unescaped_), without going through the `htmlspecialchars` function. Be careful when using `Raw` for a _value_ that comes from _user_ input, as there's a potential for **_Cross-Site Scripting (XSS)_**:

PHP

    use Laravolt\Suitable\Columns\Raw;public function data(){    return [        ['bio' => '<b>Strong</b><script>alert("foo")</script>'],    ];}public function columns(): array{    return [        Raw::make('bio'),    ];}

In the example above, we'll get a **Strong** text (in bold) and the JavaScript code to display an _alert_ will be executed by the _browser_.

If you need more flexible _custom logic_, the `Raw` column type can also accept a _Closure_:

PHP

    // Display a list of roles for a user, separated by commasRaw::make(    function ($user) {        return $user->roles->implode('name', ', ');    },    'Roles'),

### RestfulButton

The `RestfulButton` column is used to create standard buttons for a _create-read-update-delete_ or **CRUD** process. You only need to define the _resource name_ to generate three buttons: **show**, **edit**, and **destroy**:

PHP

    use Laravolt\Suitable\Columns\RestfulButton;public function columns(): array{    return [        RestfulButton::make('users'),    ];}

In the example code above, the three buttons generated will have routes:

*   show: `route('users.show', <id>)`
*   edit: `route('users.edit', <id>)`
*   destroy: `route('users.destroy', <id>)`

`<id>` is automatically taken from the _primary key_ of the _object_ in question. Therefore, `RestfulButton` **can only be used if the data source comes from Eloquent**.

Additional methods available:

*   `only($action1, $action2)` if you only want to display certain actions, for example `only('show')`.
*   `except($action1, $action2)` if you want to hide certain buttons, for example `except('destroy')`.

To learn more about _resource controllers_, please read the [official documentation from Laravel](https://laravel.com/docs/master/controllers#resource-controllers).

### RowNumber

The `RowNumber` column is used to display row numbers in sequence, starting from 1:

PHP

    use Laravolt\Suitable\Columns\RowNumber;public function columns(): array{    return [        RowNumber::make(),    ];}

### Text

The `Text` column is used to display values safely, protected from **_Cross-Site Scripting (XSS)_**, using PHP's built-in `htmlspecialchars` function:

PHP

    use Laravolt\Suitable\Columns\Text;public function data(){    return [        ['bio' => '<b>Strong</b><script>alert("foo")</script>'],    ];}public function columns(): array{    return [        Text::make('bio'),    ];}

In the example above, "bio" will be displayed as-is according to the written text:

Text

    <b>Strong</b><script>alert("foo")</script>

### Text vs Html vs Raw

There are three columns that can be used to display content from WYSIWYG editors containing HTML tags (and JavaScript). Here's the difference between the three:

Column

Output

Notes

Text

`<b>Strong</b> <script>alert("foo")</script>`

Safest, displays text as-is.

Html

**Strong** `<script>alert("foo")</script>`

If you only want to execute HTML tags.

Raw

**Strong** (and alert appears in the browser)

If you want to fully execute HTML and JavaScript code.

### Url

The `Url` column is used to automatically display a URL as a clickable _link_:

PHP

    use Laravolt\Suitable\Columns\Url;public function columns(): array{    return [        Url::make('website'),    ];}

### View

When the display becomes more complex, we can use the `View` column to move the _logic_ for rendering the contents of a column to a separate blade file:

PHP

    use Laravolt\Suitable\Columns\View;public function columns(): array{    return [        View::make('profile')    ];}

Then create a blade file `profile.blade.php`:

HTML

    <dl>  <dt>Name</dt>  <dd>{{ $data->name }}</dd>  <dt>Email</dt>  <dd>{{ $data->email }}</dd></dl>

Custom Column
-------------

If you don't find a suitable column type, then `Raw` is the first choice to display data with your own _custom logic_.

If this _custom logic_ is needed in multiple places and you want to apply the **_Don't Repeat Yourself (DRY)_** principle, then creating a specific Class for a _custom column_ becomes a wiser choice.

Here's the framework for a _custom column_ that functions to _mask_ the displayed data:

PHP

    <?phpnamespace App\Tables\Columns;use Laravolt\Suitable\Columns\Column;use Laravolt\Suitable\Columns\ColumnInterface;class MaskColumn extends Column implements ColumnInterface{    public function cell($cell, $collection, $loop)    {        return \Str::mask($cell->{$this->field});    }}

All you need to create is a _class_ that _extends_ `Column` (base class), implements _ColumnInterface_, and defines _logic_ to display data in the _cell($cell, $collection, $loop)_ function.

**`$cell`** is an item from the Collection (can be an Eloquent model or other object) that will currently be displayed in the _cell_ of a table.

**`$collection`** is the entire data (Collection).

**`$loop`** contains information about _looping_, according to [Laravel's documentation](https://laravel.com/docs/master/blade#the-loop-variable).

In the example above, the _custom column_ is saved in `app/tables/columns`. This is not a standard rule. Please adjust the namespace according to your application structure.

Searching
---------

### Search Query

When users type something in the search field (searchbox), the input will automatically be _bound_ to the `$search` property, so we can access it by calling `$this->search`.

Here's an example code to search by name:

PHP

    class UserTable extends TableView{    public function data()    {        return \App\Models\User::where('status', 'ACTIVE')            ->whereLike(['name', 'email'], $this->search)            ->paginate();    }}

> `whereLike` is an additional _method_ from Laravolt to search multiple columns at once using the `where <column> like "%<keyword>%"` mechanism. For large amounts of data, this query may not be optimal. Please create your own search _logic_ as needed.

### Show/Hide Searchbox

PHP

    class UserTable extends TableView{    public bool $showSearchbox = false; // default is "true"}

### Search Debounce

Every time a User types something in the searchbox, the search query will automatically run with an AJAX mechanism. Debounce is a mechanism to **wait a few moments** until the User is considered to have really stopped typing, then the query is executed to update the displayed data.

PHP

    class UserTable extends TableView{    public int $searchDebounce = 1000; // in milliseconds, default is 300}

Sorting
-------

When defining a table, we can add the `sortable()` function to any defined column. Automatically, that column will be clickable.

PHP

    use Laravolt\Suitable\Columns\Text;class UserTable extends TableView{    public function data()    {        return \App\Models\User::where('status', 'ACTIVE')->paginate();    }    public function columns(): array    {        return [            Text::make('name', 'Name')->sortable(),            Text::make('email', 'Email')->sortable(),            Raw::make(                fn ($data) => DateHelper::formatDate($data->birth_date),                'Birth Date'            )->sortable('birth_date'),        ];    }}

But don't forget, we also need to modify the _query_ so that the resulting data is also sorted. Laravolt has provided the `AutoSort` Trait to _handle_ this need.

First, make sure the Model that is the data source is already using `AutoSort`:

PHP

    namespace App\Models;use Laravolt\Suitable\AutoSort;class User extends Model{    use AutoSort;}

Next, we just need to call the _autoSort()_ function when _querying_ the data:

PHP

    class UserTable extends TableView{    public function data()    {        return \App\Models\User::where('status', 'ACTIVE')            ->autoSort($this->sortPayload())            ->paginate();    }}

Filtering
---------

Filtering functions to perform more **_exact_** searches. When adding Filtering, try to ensure the table data source is still in the form of a Query Builder. This is necessary because the Filtering _logic_ will be applied after calling `data()`.

PHP

    class UserTable extends TableView{    public function data()    {        // NOT OK        return \App\Models\User::get();        // NOT OK        return \App\Models\User::paginate();        // OK        return \App\Models\User::query();        // OK        return \App\Models\User::where('status', 'ACTIVE');    }}

To add a Filter, create a _class_ with a skeleton like the following:

PHP

    <?phpnamespace App\Tables\Filters;use Laravolt\Ui\Filters\TextFilter;class EmailFilter extends TextFilter{    protected string $label = 'Email';    public function apply($data, $value)    {        if ($value) {            $data->where('email', $value);        }        return $data;    }}

You can change the query _logic_ in the `apply` _method_ as needed. In the example above, filtering is done with an _exact match_.

Then add that _class_ to the `filters()` _method_ of the `Table`:

PHP

    use App\Models\User;use App\Tables\Filters\EmailFilter;class UserTable extends TableView{    public function data()    {        return User::where('status', 'ACTIVE'); // don't forget to import the class on top with "use"    }    public function filters(): array    {        return [            new EmailFilter(), // don't forget to import the class on top with "use"        ];    }}

The result will look something like this:

![Filter Example](https://cdn.statically.io/gh/laravolt/storage/master/2021/10/image-20211003212947424-rEVmUN.png)

### Built-in Filters

There are several types of Filters already available and ready to be _extended_, namely:

*   TextFilter
*   DropdownFilter
*   CheckboxFilter
*   DateFilter

#### Text Filter

PHP

    <?phpnamespace App\Tables\Filters;use Laravolt\Ui\Filters\TextFilter;class EmailFilter extends TextFilter{    protected string $label = 'Email';    public function apply($data, $value)    {        if ($value) {            $data->where('email', $value);        }        return $data;    }}

#### Dropdown Filter

![Dropdown Filter Example](https://cdn.statically.io/gh/laravolt/storage/master/2021/10/image-20211003213815998-V8Eycb.png)

PHP

    <?phpnamespace App\Tables\Filters;use App\Models\Role;use Laravolt\Ui\Filters\DropdownFilter;class RoleFilter extends DropdownFilter{    protected string $label = 'Roles';    public function apply($data, $value)    {        if ($value) {            $data->whereHas('roles', fn ($query) => $query->where('id', $value));        }        return $data;    }    public function options(): array    {        return Role::query()->pluck('name', 'id')->prepend('All Roles', '0')->toArray();    }}

#### Checkbox Filter

![Checkbox Filter Example](https://cdn.statically.io/gh/laravolt/storage/master/2021/10/image-20211003213844901-t469HS.png)

PHP

    <?phpnamespace App\Tables\Filters;use Laravolt\Ui\Filters\CheckboxFilter;class StatusFilter extends CheckboxFilter{    protected string $label = 'Status';    public function apply($data, $value)    {        $status = collect($value)->filter()->values()->toArray();        if (! empty($status)) {            $data->whereIn('status', $status);        }        return $data;    }    public function options(): array    {        return [            'ACTIVE' => 'ACTIVE',            'PENDING' => 'PENDING',        ];    }}

#### Date Filter

![Date Filter Example](https://cdn.statically.io/gh/laravolt/storage/master/2021/10/image-20211003213928740-ksvUUP.png)

PHP

    <?phpnamespace App\Tables\Filters;use Laravolt\Ui\Filters\DateFilter;class RegisteredFilter extends DateFilter{    protected string $label = 'Registered At';    public function apply($data, $value)    {        if ($value) {            $data->where('created_at', $value);        }        return $data;    }}

Pagination
----------

Pagination will be displayed automatically according to the data source returned in the `data()` _method_. Pagination customization can be done by changing several properties:

PHP

    class UserTable extends TableView{    // change the default number of data shown per page    private const DEFAULT_PER_PAGE = 15;    // change the options for data shown per page    protected array $perPageOptions = [5, 15, 30, 50, 100, 250];    // if you want to change the view    protected $paginationView = 'laravolt::pagination.livewire.simple';}

Query String
------------

Every time a User interacts with the Table, the current **_state_** will be saved as a _query string_. For example, after searching for data with the keyword "foo", the browser URL will automatically change to:

Http

    /users?search=foo

The advantages of explicitly storing **_state_** in the URL include:

1.  Users can easily share the current URL.
2.  When Users refresh their browser, the displayed data will match the last **_state_**.

Here are the **_states_** that will automatically change the _query string_ in the _browser_:

PHP

    protected $queryString = [    'page' => ['except' => 1],    'search' => ['except' => ''],    'sort' => ['except' => null],    'direction',    'perPage' => ['except' => self::DEFAULT_PER_PAGE],];

Please study [Livewire's official documentation](https://laravel-livewire.com/docs/2.x/query-string) regarding _query strings_.

However, if for some reason you don't want the above _behavior_ (for example when having to display 2 tables on the same page), simply empty the `$queryString` property:

PHP

    class UserTable extends TableView{    protected $queryString = [];}

Afterwards, whenever Users interact with the table (_searching, sorting, filtering, pagination_), the browser URL will not change.## === menu.md ===
## Menu
====

Laravolt uses a config-file approach to display menus in the sidebar, with the following goals:

1.  Creating a single source of truth for developers
2.  Tracking menu changes through version control since config files are tracked by Git
3.  Separating content from presentation - config files only contain essential menu information like labels, URLs, and icons, while Laravolt handles the HTML and CSS

* * *

Introduction
------------

Laravolt automatically reads the `config/laravolt/menu` directory to look for menu configuration files. You can organize your menus by creating multiple config files in this directory.

In brief, the anatomy of a menu is:

*   Group 1
    *   Menu 1
    *   Menu 2
        *   Sub menu 2.1
        *   Sub menu 2.2
    *   Menu 3
*   Group 2

Registering Menus
-----------------

Create a new file `config/laravolt/menu/app.php`:

PHP

    <?phpreturn [    'App' => [        'order' => 1,        'menu' => [            'Dashboard' => [                'route' => ['dashboard'],                'active' => 'dashboard/*',                'icon'  => 'chart-bar'            ],            'Manage Posts' => [                'route' => ['posts.index'],                'active' => 'posts/*',                'icon'  => 'newspaper'            ],        ],    ],];

Config files help you group menus. You can create as many config files as needed for your application, for example:

*   `config/laravolt/menu/app.php`
*   `config/laravolt/menu/master-data.php`
*   `config/laravolt/menu/settings.php`

Nested Menus
------------

Laravolt supports up to 2 levels of menus (menu and submenu). To create nested menus, just add a `'menu'` entry with the same array schema:

PHP

    <?phpreturn [    'App' => [        'order' => 1,        'menu' => [            'Dashboard' => [                'route' => ['dashboard'],                'active' => 'dashboard/*',                'icon' => 'chart-bar',            ],            'Posts' => [                'icon' => 'newspaper',                'menu' => [                    'Published' => [                        'route' => ['posts.index', ['type' => 'published']],                        'active' => 'posts?type=published',                    ],                    'Draft' => [                        'route' => ['posts.index', ['type' => 'draft']],                        'active' => 'posts?type=draft',                    ],                ],            ],        ],    ],];

Available Options
-----------------

### order

Only available at the group level. Used to determine the order of menus.

PHP

    <?phpreturn [    'Main Menu' => [        'order' => 2,        'menu' => [            // ...        ],    ],];

### route

PHP

    'route' => ['route.name', ['param1' => 'value']],

Don't call the `route()` helper directly from the config file as it may cause errors in production.

### url

If you're not accustomed to using named routes, you can simply write the hardcoded URL.

PHP

    'url' => 'posts/create',

### active

Determines which menu entry needs to be set as active and expanded. Can use wildcards.

PHP

    'active' => 'posts/*',

### icon

Sets the icon to display. Icons can be viewed at [Font Awesome](https://fontawesome.com/v5/search?s=duotone). Laravolt has an official license for Font Awesome 5 Pro.

PHP

    'icon' => 'users',

Currently, only first-level menus can display icons, while category labels (menu groups) and submenus cannot.

### permissions

Determines whether a menu should be displayed or not, based on the Permissions that the User has.

PHP

    'permissions' => [\App\Enum\Permissions::MANAGE_POST],

Dynamic Menus
-------------

To add menus dynamically, add the following code to the `boot()` method in your `AppServiceProvider`:

PHP

    public function boot(){    app('laravolt.menu.sidebar')->register(function (\Lavary\Menu\Builder $menu) {        // Add menu to existing group        $group1 = $menu->get('system');        $group1->add('My Menu', 'my-menu')            ->data('icon', 'list')            ->data('order', 10)            ->data('permission', 'foo')            ->active("my-menu/*");        // Add new group and menu        $group2 = $menu->add('New Group');        $group2->add('My Menu 2', 'my-menu-2')            ->data('icon', 'list')            ->data('order', 10)            ->data('permission', 'foo')            ->active("my-menu-2/*");        // Add group, menu, and submenu        $group3 = $menu->add('Nested Menu');        $menu3 = $group3->add('My Menu 3')            ->data('icon', 'list')            ->data('order', 10)            ->data('permission', 'foo');        $menu3->add('Sub Menu A', '#');    });}

Menu with Authorization
-----------------------

Menus can be conditionally displayed based on user permissions. There are two ways to implement this:

### Using Permission Strings

PHP

    <?phpreturn [    'App' => [        'order' => 1,        'menu' => [            'Dashboard' => [                'route' => ['dashboard'],                'active' => 'dashboard/*',                'icon'  => 'chart-bar'            ],            'Manage Posts' => [                'route' => ['posts.index'],                'active' => 'posts/*',                'icon'  => 'newspaper',                'permissions' => ['manage-posts']            ],        ],    ],];

In this example, the "Manage Posts" menu will only be visible to users who have the 'manage-posts' permission.

### Using Role-Based Authorization

You can also restrict menu visibility based on user roles:

PHP

    <?phpreturn [    'Admin Area' => [        'order' => 99,        'menu' => [            'User Management' => [                'route' => ['users.index'],                'active' => 'users/*',                'icon'  => 'users',                'roles' => ['admin', 'super-admin']            ],            'System Settings' => [                'route' => ['settings.index'],                'active' => 'settings/*',                'icon'  => 'cogs',                'roles' => ['super-admin']            ],        ],    ],];

The "User Management" menu will only be visible to users with 'admin' or 'super-admin' roles, while "System Settings" will only be visible to 'super-admin'.

Menu with Badges
----------------

You can add badges to menu items to display counts or status indicators:

PHP

    <?phpreturn [    'App' => [        'order' => 1,        'menu' => [            'Dashboard' => [                'route' => ['dashboard'],                'active' => 'dashboard/*',                'icon'  => 'chart-bar'            ],            'Notifications' => [                'route' => ['notifications.index'],                'active' => 'notifications/*',                'icon'  => 'bell',                'badge' => function() {                    return auth()->user()->unreadNotifications()->count();                }            ],        ],    ],];

The badge can be a static value or a callback function that returns a value:

PHP

    'badge' => 5 // Static badge with value 5

PHP

    'badge' => function() {    return auth()->user()->unreadNotifications()->count();}

You can also customize the badge appearance:

PHP

    'badge' => [    'value' => function() {        return auth()->user()->unreadNotifications()->count();    },    'class' => 'red' // Use any Fomantic UI color class]

Menu Ordering
-------------

Menu groups and menu items can be ordered using the 'order' key:

### Group Ordering

PHP

    <?phpreturn [    'Main Menu' => [        'order' => 1,        'menu' => [            // ...        ],    ],    'Secondary Menu' => [        'order' => 2,        'menu' => [            // ...        ],    ],];

### Menu Item Ordering

PHP

    <?phpreturn [    'Main Menu' => [        'order' => 1,        'menu' => [            'Dashboard' => [                'route' => ['dashboard'],                'active' => 'dashboard/*',                'icon'  => 'chart-bar',                'order' => 1            ],            'Reports' => [                'route' => ['reports.index'],                'active' => 'reports/*',                'icon'  => 'chart-line',                'order' => 2            ],        ],    ],];

Lower numbers appear first in the menu.

Menu Customization
------------------

### Menu Theme

You can customize the sidebar theme by editing the `config/laravolt/ui.php` file:

PHP

    return [    'sidebar' => [        'theme' => 'light', // Options: 'light', 'dark', 'primary'    ],    // ...];

### Sidebar Collapsed State

You can set the default state of the sidebar (expanded or collapsed) in the same config file:

PHP

    return [    'sidebar' => [        'collapsed' => false, // Set to true to have the sidebar collapsed by default    ],    // ...];

Users can toggle the sidebar state by clicking the collapse/expand button at the bottom of the sidebar.

Best Practices
--------------

1.  **Organize Logically**: Group related menu items together in meaningful categories
2.  **Keep It Simple**: Aim for a maximum of 7-8 main menu groups to prevent overwhelming users
3.  **Use Consistent Icons**: Choose icons that clearly represent the destination or action
4.  **Clear Labels**: Use short, descriptive menu labels
5.  **Proper Authorization**: Always implement proper authorization to ensure users only see menus relevant to their roles and permissions

Troubleshooting
---------------

### Menus Not Displaying

1.  Check that your config files are in the correct location: `config/laravolt/menu/`
2.  Verify that all required configuration keys are present and formatted correctly
3.  Run `php artisan config:clear` to clear cached configurations
4.  Ensure the user has the necessary permissions if the menu is permission-restricted

### Active State Not Working

1.  Check your 'active' patterns to ensure they match the correct URL patterns
2.  Remember that 'active' patterns support wildcards, e.g., `posts/*`
3.  For query parameter-dependent active states, include the query string in your pattern: `posts?type=draft`

### Icon Not Displaying

1.  Verify the icon name in [Font Awesome](https://fontawesome.com/v5/search?s=duotone)
2.  Ensure you're using the correct icon style (solid, regular, light, or duotone)
3.  Check for any typos in the icon name## === action-button.md ===
## Action Button
=============

Action buttons are essential UI elements that allow users to perform primary actions on a page, such as creating new resources, editing content, or triggering workflows.

* * *

Introduction
------------

In Laravolt, Action Buttons are designed to provide consistent UI elements for primary actions across your application. They are typically placed in the header of pages and offer a standardized way to present actions to users.

Basic Usage
-----------

The most common use case is adding action buttons to page headers. You can do this by using the `actions` slot in the `volt-app` component:

HTML

    <x-volt-app title="Posts">  <x-slot name="actions">    <x-volt-link-button      url="{{ route('posts.create') }}"      icon="plus"      label="New Post"    />  </x-slot></x-volt-app>

This will render a "New Post" button with a plus icon in the header of your page, aligned to the right side.

Button Types
------------

Laravolt provides several button types to accommodate different kinds of actions:

### Link Button

Used for navigation to other pages:

HTML

    <x-volt-link-button  url="{{ route('posts.create') }}"  icon="plus"  label="New Post"/>

### Submit Button

Used for form submissions:

HTML

    <x-volt-submit-button icon="save" label="Save Post" />

### Button

A general-purpose button that can be used for various actions:

HTML

    <x-volt-button icon="refresh" label="Refresh Data" onclick="refreshData()" />

Button Properties
-----------------

All button types support the following properties:

### Icon

You can add icons to your buttons using Fomantic UI icon names:

HTML

    <x-volt-link-button  url="{{ route('posts.create') }}"  icon="plus"  label="New Post"/>

Laravolt supports all icons from the [Fomantic UI icon set](https://fomantic-ui.com/elements/icon.html).

### Label

The text to display on the button:

HTML

    <x-volt-link-button url="{{ route('posts.create') }}" label="New Post" />

You can also use the button without a label, displaying only the icon:

HTML

    <x-volt-link-button url="{{ route('posts.create') }}" icon="plus" />

### Color

You can change the color of the button using Fomantic UI color classes:

HTML

    <x-volt-link-button  url="{{ route('posts.create') }}"  icon="plus"  label="New Post"  class="blue"/>

Available color options include: `primary`, `secondary`, `red`, `orange`, `yellow`, `olive`, `green`, `teal`, `blue`, `violet`, `purple`, `pink`, `brown`, `grey`, and `black`.

### Size

Control the size of the button:

HTML

    <x-volt-link-button  url="{{ route('posts.create') }}"  icon="plus"  label="New Post"  class="tiny"/>

Available size options include: `mini`, `tiny`, `small`, `medium`, `large`, `big`, `huge`, and `massive`.

Button Groups
-------------

You can group multiple buttons together for related actions:

HTML

    <x-volt-app title="Posts">  <x-slot name="actions">    <div class="ui buttons">      <x-volt-link-button        url="{{ route('posts.create') }}"        icon="plus"        label="New Post"      />      <x-volt-link-button        url="{{ route('posts.import') }}"        icon="upload"        label="Import"      />      <x-volt-link-button        url="{{ route('posts.export') }}"        icon="download"        label="Export"      />    </div>  </x-slot></x-volt-app>

Dropdown Action Button
----------------------

For cases where you need to conserve space or group related actions, you can use a dropdown button:

HTML

    <x-volt-dropdown-button label="Actions" icon="settings">  <a href="{{ route('posts.create') }}" class="item">    <i class="plus icon"></i> New Post  </a>  <a href="{{ route('posts.import') }}" class="item">    <i class="upload icon"></i> Import  </a>  <a href="{{ route('posts.export') }}" class="item">    <i class="download icon"></i> Export  </a></x-volt-dropdown-button>

Confirmation Dialogs
--------------------

For actions that need confirmation (like delete operations), you can add a confirmation dialog:

HTML

    <x-volt-link-button  url="{{ route('posts.destroy', $post) }}"  icon="trash"  label="Delete"  class="red"  data-confirm="Are you sure you want to delete this post?"/>

The `data-confirm` attribute will trigger a confirmation dialog when the button is clicked, asking the user to confirm before proceeding with the action.

Disabled State
--------------

You can disable buttons when needed:

HTML

    <x-volt-link-button  url="{{ route('posts.create') }}"  icon="plus"  label="New Post"  class="disabled"/>

Responsive Considerations
-------------------------

On smaller screens, buttons with both icons and labels might take up too much space. You can use the `mobile-text` class to show only the icon on mobile devices:

HTML

    <x-volt-link-button  url="{{ route('posts.create') }}"  icon="plus"  label="New Post"  class="mobile-text"/>

Best Practices
--------------

1.  **Consistent Placement**: Always place primary actions in the page header using the `actions` slot.
2.  **Clear Labels**: Use clear, action-oriented labels for buttons (e.g., "Create Post" rather than "New").
3.  **Meaningful Icons**: Choose icons that clearly represent the action being performed.
4.  **Color Coding**: Use colors consistently across your application (e.g., red for destructive actions, green for confirming).
5.  **Priority**: Order buttons by their importance, with the most important action first.

Examples
--------

### Basic Page with Create Action

HTML

    <x-volt-app title="Users">  <x-slot name="actions">    <x-volt-link-button      url="{{ route('users.create') }}"      icon="plus"      label="Create User"    />  </x-slot>  <!-- Page content here --></x-volt-app>

### Resource Detail Page with Edit and Delete Actions

HTML

    <x-volt-app title="User Details: {{ $user->name }}">  <x-slot name="actions">    <x-volt-link-button      url="{{ route('users.edit', $user) }}"      icon="edit"      label="Edit"    />    <x-volt-link-button      url="{{ route('users.destroy', $user) }}"      icon="trash"      label="Delete"      class="red"      data-confirm="Are you sure you want to delete this user? This action cannot be undone."    />  </x-slot>  <!-- User details here --></x-volt-app>

### Form Page with Submit and Cancel Actions

HTML

    <x-volt-app title="Create New User">  {!! form()->open()->route('users.store') !!}  <!-- Form fields here -->  <x-slot name="actions">    <x-volt-submit-button icon="save" label="Save User" />    <x-volt-link-button url="{{ route('users.index') }}" label="Cancel" />  </x-slot>  {!! form()->close() !!}</x-volt-app>## === flash-messages.md ===
## Flash Messages
==============

Flash messages provide contextual feedback to users about their actions and system events. Laravolt's flash message system automatically detects validation errors and session flash messages to display elegant toast notifications.

* * *

Overview
--------

Flash messages (also known as toast notifications) are temporary messages that appear after user actions or system events to provide immediate feedback. They typically disappear after a few seconds or can be manually dismissed by the user.

Laravolt provides a seamless integration with Laravel's session and validation systems to automatically display these notifications with minimal configuration.

Installation
------------

Flash message functionality is included by default in Laravolt. During the Laravolt installation process, the middleware `Laravolt\Middleware\DetectFlashMessage` is automatically added to the `web` middleware group in your application's `app/Http/Kernel.php` file.

To verify that it's properly installed, check your middleware configuration:

PHP

    // app/Http/Kernel.phpprotected $middlewareGroups = [    'web' => [        // ... other middleware        \Laravolt\Middleware\DetectFlashMessage::class,        // ... other middleware    ],];

Basic Usage
-----------

### Form Validation Messages

One of the most common uses for flash messages is displaying form validation errors. Laravolt automatically detects Laravel validation errors and displays them as flash messages without requiring any additional code.

PHP

    public function store(Request $request){    // Validation errors will automatically be displayed as flash messages    $request->validate([        'name' => 'required|min:3',        'email' => 'required|email|unique:users',        'password' => 'required|min:8|confirmed',    ]);    // Process the validated data...    User::create($request->all());    return redirect()->route('users.index');}

### Session Flash Messages

For more explicit control, you can set flash messages directly in your controller by using Laravel's session flash methods. These messages will be displayed on the next request, making them perfect for use with redirects.

PHP

    public function update(Request $request, User $user){    $user->update($request->validated());    // Flash message will be displayed after redirection    return redirect()        ->route('users.index')        ->with('success', 'User profile updated successfully');}

### Available Message Types

Laravolt supports four types of messages, each with distinctive styling to convey different levels of information:

Type

Purpose

Example

`info`

General information

`->with('info', 'Welcome back, John')`

`success`

Successful operations

`->with('success', 'Profile updated successfully')`

`warning`

Warnings that require attention

`->with('warning', 'Please complete your profile')`

`error`

Errors that prevented an action

`->with('error', 'Unable to connect to server')`

Advanced Features
-----------------

### Current Request Flash Messages

Sometimes, you may want to display a flash message for the current request instead of waiting for the next request. You can do this using Laravel's `session()->now()` method:

PHP

    public function dashboard(){    // These messages will be displayed immediately    session()->now('info', 'Welcome to your dashboard');    if (!auth()->user()->hasCompletedProfile()) {        session()->now('warning', 'Please complete your profile information');    }    return view('dashboard');}

### Multiple Messages

You can set multiple flash messages of different types, and all will be displayed:

PHP

    return redirect()->route('home')    ->with('success', 'Your settings have been saved')    ->with('info', 'You might want to check out our new features');

### HTML Content in Messages

By default, flash messages support plain text only. If you need to include HTML in your messages, you'll need to customize the flash message template.

Customization
-------------

### Message Duration

You can modify how long flash messages stay visible before automatically dismissing by publishing and editing the Laravolt configuration:

Bash

    php artisan vendor:publish --tag=laravolt-config

Then edit the `config/laravolt/ui.php` file:

PHP

    'flash' => [    'display_duration' => 5000, // Duration in milliseconds],

### Message Templates

To customize the appearance of flash messages, you can publish the view files:

Bash

    php artisan vendor:publish --tag=laravolt-views

Then edit the flash message template located at `resources/views/vendor/laravolt/flash.blade.php`.

Best Practices
--------------

### Keep Messages Clear and Concise

*   Use simple, action-oriented language
*   Keep messages under 10 words when possible
*   Make the feedback specific to the action that was performed

### Use Appropriate Message Types

*   `info` for general information that doesn't require action
*   `success` for confirmation of completed actions
*   `warning` for non-critical issues that might need attention
*   `error` for critical issues that prevented an action from completing

### Avoid Overusing Flash Messages

*   Reserve flash messages for important information
*   Don't display notifications for routine actions that don't need confirmation

Troubleshooting
---------------

### Flash Messages Not Appearing

If your flash messages aren't appearing, check the following:

1.  Verify that the `DetectFlashMessage` middleware is properly registered in your `app/Http/Kernel.php` file
2.  Check that your layout template includes the flash message component:
    
    PHP
    
        @include('laravolt::_flash')
    
3.  Inspect your browser console for any JavaScript errors that might prevent the flash messages from displaying

### Messages Displaying Incorrectly

If flash messages appear but don't look right:

1.  Ensure you're using the correct message type (`info`, `success`, `warning`, `error`)
2.  Check if you've customized the flash message template and revert to the default if needed
3.  Verify that the required CSS and JavaScript assets are being loaded

Related Components
------------------

*   [Forms](/v6/form) - Form components that integrate with validation
*   [Tables](/v6/table) - Table components with action feedback
*   [Action Buttons](/v6/action-button) - Buttons that can trigger flash messages## === blade-components.md ===
## Blade Components
================

Laravolt provides a comprehensive set of Blade Components that help you build consistent, accessible, and beautiful user interfaces with minimal effort.

* * *

Overview
--------

Blade Components are a powerful feature in Laravel that allows you to create reusable, encapsulated UI elements. Laravolt extends this functionality with a set of pre-designed components that follow best practices for web design and accessibility.

These components help you:

*   Maintain design consistency across your application
*   Reduce duplication of HTML and CSS code
*   Implement complex UI patterns with minimal effort
*   Create accessible interfaces that work for all users

Basic Usage
-----------

Laravolt Blade Components use Laravel's component syntax. Here's a basic example:

Blade

    <x-volt-button>Click Me</x-volt-button>

Most components accept attributes that modify their appearance or behavior:

Blade

    <x-volt-button color="primary" size="large" icon="save">    Save Changes</x-volt-button>

Component Prefixing
-------------------

All Laravolt components use the `volt-` prefix to avoid conflicts with your own components or those from other packages. For example:

*   `<x-volt-button>` for buttons
*   `<x-volt-card>` for cards
*   `<x-volt-icon>` for icons

Available Components
--------------------

### Button

The Button component provides a consistent way to trigger actions across your application.

Blade

    <x-volt-button    icon="plus"    class="pink">    Export</x-volt-button>

#### Button Properties

Property

Type

Default

Description

`icon`

string

null

Name of the icon to display with the button

`class`

string

null

Additional CSS classes

`color`

string

'default'

Button color: 'default', 'primary', 'secondary', 'success', 'warning', 'danger'

`size`

string

'medium'

Button size: 'small', 'medium', 'large'

`type`

string

'button'

HTML button type: 'button', 'submit', 'reset'

`disabled`

boolean

false

Whether the button is disabled

### Card

The Card component is used to group related content in a flexible container.

Blade

    <x-volt-card    title="Card Title"    cover="https://via.placeholder.com/300"    meta.before="foo"    content="Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat"    meta.after="foo"/>

#### Card Properties

Property

Type

Default

Description

`title`

string

null

Card title

`cover`

string

null

URL to the cover image

`content`

string

null

Main content for the card

`meta.before`

string

null

Metadata to display before the content

`meta.after`

string

null

Metadata to display after the content

#### Card with Slots

For more complex cards, you can use slots:

Blade

    <x-volt-card>    <x-slot name="header">Card Header</x-slot>    <p>This is the main content of the card.</p>    <p>You can include any HTML here.</p>    <x-slot name="footer">Card Footer</x-slot></x-volt-card>

### Brand Image

The Brand Image component helps maintain consistent branding across your application.

Blade

    <x-volt-brand-image    src="/path/to/logo.png"    alt="Company Name"/>

#### Brand Image Properties

Property

Type

Default

Description

`src`

string

null

Image source URL

`alt`

string

'Brand logo'

Alternative text for accessibility

`width`

string/integer

null

Image width

`height`

string/integer

null

Image height

`class`

string

null

Additional CSS classes

### Breadcrumb

The Breadcrumb component shows the hierarchical path to the current page.

Blade

    <x-volt-breadcrumb>    <x-volt-breadcrumb-item label="Home" link="/" />    <x-volt-breadcrumb-item label="Products" link="/products" />    <x-volt-breadcrumb-item label="Current Product" /></x-volt-breadcrumb>

#### Breadcrumb Item Properties

Property

Type

Default

Description

`label`

string

required

Text label for the breadcrumb item

`link`

string

null

URL for the breadcrumb item (omit for current page)

`icon`

string

null

Optional icon to display with the item

### Icon

The Icon component provides an easy way to include SVG icons in your interface.

Blade

    <x-volt-icon name="user" class="large" />

#### Icon Properties

Property

Type

Default

Description

`name`

string

required

Name of the icon to display

`class`

string

null

Additional CSS classes

`size`

string

'medium'

Icon size: 'small', 'medium', 'large'

`color`

string

null

Icon color class

### Link

The Link component provides consistent styling for text links.

Blade

    <x-volt-link href="/dashboard" icon="home">    Go to Dashboard</x-volt-link>

#### Link Properties

Property

Type

Default

Description

`href`

string

required

URL for the link

`icon`

string

null

Optional icon to display with the link

`class`

string

null

Additional CSS classes

`target`

string

'\_self'

Target for the link: '\_self', '\_blank', etc.

### Link Button

The Link Button component creates links that are styled as buttons.

Blade

    <x-volt-link-button href="/dashboard" icon="home" color="primary">    Dashboard</x-volt-link-button>

#### Link Button Properties

Property

Type

Default

Description

`href`

string

required

URL for the link

`icon`

string

null

Optional icon to display

`color`

string

'default'

Button color: 'default', 'primary', 'secondary', etc.

`size`

string

'medium'

Button size: 'small', 'medium', 'large'

`class`

string

null

Additional CSS classes

`target`

string

'\_self'

Target for the link: '\_self', '\_blank', etc.

### Form

The Form component provides a standardized way to create forms.

Blade

    <x-volt-form action="/users" method="POST">    <!-- Form fields go here -->    <x-volt-button type="submit">Save</x-volt-button></x-volt-form>

#### Form Properties

Property

Type

Default

Description

`action`

string

null

Form submission URL

`method`

string

'POST'

HTTP method: 'GET', 'POST', 'PUT', 'PATCH', 'DELETE'

`files`

boolean

false

Whether the form allows file uploads

`class`

string

null

Additional CSS classes

`id`

string

null

Form ID

### Media Library

The Media Library component helps manage and display media content.

Blade

    <x-volt-media-library    name="attachments"    :collection="$mediaLibrary"    multiple    accept="image/*"/>

#### Media Library Properties

Property

Type

Default

Description

`name`

string

required

Input name for the files

`collection`

array

\[\]

Existing media items to display

`multiple`

boolean

false

Whether multiple files can be selected

`accept`

string

null

MIME types to accept (e.g., 'image/\*', 'application/pdf')

`max`

integer

null

Maximum number of files

### Panel

The Panel component groups content in collapsible sections.

Blade

    <x-volt-panel title="Settings">    <p>Panel content goes here.</p></x-volt-panel>

#### Panel Properties

Property

Type

Default

Description

`title`

string

null

Panel title

`collapsed`

boolean

false

Whether the panel is initially collapsed

`class`

string

null

Additional CSS classes

`icon`

string

null

Optional icon for the panel header

### Tab

The Tab component organizes content into tabbed interfaces.

Blade

    <x-volt-tab>    <x-volt-tab-panel title="First Tab" active>        Content for the first tab    </x-volt-tab-panel>    <x-volt-tab-panel title="Second Tab">        Content for the second tab    </x-volt-tab-panel></x-volt-tab>

#### Tab Panel Properties

Property

Type

Default

Description

`title`

string

required

Tab title

`active`

boolean

false

Whether the tab is initially active

`icon`

string

null

Optional icon for the tab

Customization
-------------

### Styling

Most components accept styling attributes like `class`, `color`, and `size`:

Blade

    <x-volt-button class="my-custom-class" color="red">    Custom Button</x-volt-button>

### Slots

Components that wrap content use Laravel's slot system:

Blade

    <x-volt-card>    <x-slot name="header">Card Title</x-slot>    <p>Card content goes here</p>    <x-slot name="footer">Card Footer</x-slot></x-volt-card>

### Attributes

Additional HTML attributes are passed through to the root element:

Blade

    <x-volt-button id="submit-btn" data-action="save">    Save</x-volt-button>

Best Practices
--------------

### Consistency

Use components consistently throughout your application to maintain a uniform look and feel.

### Accessibility

Laravolt components are designed with accessibility in mind, but you should ensure that your implementation follows accessibility best practices:

*   Provide descriptive labels for buttons and links
*   Use appropriate heading levels in cards and panels
*   Ensure sufficient color contrast for text and background colors

### Performance

While components make development easier, excessive nesting of complex components can impact performance. Monitor your page load times and optimize where necessary.

Related Documentation
---------------------

*   [Form Components](/v6/form) - Advanced form handling capabilities
*   [Menu Components](/v6/menu) - Navigation menu components
*   [Table Components](/v6/table) - Data table components## === statistics.md ===
## Statistics Components
=====================

Statistics components provide an elegant way to display important single-value metrics in your application. These visually appealing components combine values, labels, and icons to highlight key data points for users.

* * *

Overview
--------

Statistics components are designed to present focused metrics that give users immediate insights into application data. Built on Livewire, these components are dynamic, reactive, and easy to customize.

![Statistics Example](https://cdn.statically.io/gh/laravolt/storage/master/2021/10/statistic-preview-br07F2.png)

Installation
------------

Statistics components are included in the Laravolt UI package. If you haven't installed Laravolt UI yet, refer to the [installation guide](/v6/installation).

The statistics component relies on Laravel Livewire, which should be installed as part of the Laravolt installation process.

Basic Usage
-----------

### Creating a Statistics Component

To create a new statistics component, use the Artisan command:

Bash

    php artisan make:statistic TotalUser

This command generates a new Livewire component class in the `app/Http/Livewire/Statistic` directory. The generated class extends `Laravolt\Ui\Statistic` and provides a template for you to customize:

PHP

    <?phpnamespace App\Http\Livewire\Statistic;use Laravolt\Ui\Statistic;class TotalUser extends Statistic{    public string $label = 'Total User';    public ?string $icon = 'user';    public function value(): int|string    {        return \App\Models\User::count();    }}

### Displaying a Statistics Component

Once created, you can display your statistic component in any Blade view using one of these methods:

Blade

    <livewire:statistic.total-user />{{-- Or using the @livewire directive --}}@livewire('statistic.total-user'){{-- Or using the full class name --}}@livewire(\App\Http\Livewire\Statistic\TotalUser::class)

You can include multiple statistics components in the same view to create dashboards:

Blade

    <div class="ui three statistics">    <livewire:statistic.total-user />    <livewire:statistic.active-user />    <livewire:statistic.new-registrations /></div>

Customization
-------------

### Label Customization

The label appears below the value and describes what the statistic represents. You can set a static label using the `$label` property:

PHP

    public string $label = 'Total Users';

For dynamic labels that change based on external factors, override the `label()` method:

PHP

    public function label(): string{    $month = request()->query('month', date('F'));    return "New Users in {$month}";}

### Value Configuration

The value is the main focus of a statistics component. Override the `value()` method to determine what value should be displayed:

PHP

    public function value(): int|string{    // Simple count    return \App\Models\User::count();    // More complex calculation    $startDate = now()->startOfMonth();    $endDate = now()->endOfMonth();    return \App\Models\User::whereBetween('created_at', [$startDate, $endDate])->count();}

You can format the value for better readability:

PHP

    public function value(): int|string{    $amount = Order::sum('total');    return 'Rp ' . number_format($amount, 0, ',', '.');}

### Color Options

Set the component's color using the `$color` property:

PHP

    public ?string $color = 'red';

Available color options include:

*   red
*   orange
*   yellow
*   olive
*   green
*   teal
*   blue
*   violet
*   purple
*   pink
*   brown
*   grey
*   black

For dynamic colors that change based on the value or other conditions, override the `color()` method:

PHP

    public function color(): ?string{    $value = $this->value();    if ($value > 1000) {        return 'green';    } elseif ($value > 500) {        return 'blue';    } else {        return 'red';    }}

### Icon Selection

Set an icon using the `$icon` property:

PHP

    public ?string $icon = 'user';

For dynamic icons that change based on conditions, override the `icon()` method:

PHP

    public function icon(): ?string{    $trend = $this->calculateTrend();    if ($trend === 'up') {        return 'arrow-up';    } elseif ($trend === 'down') {        return 'arrow-down';    }    return 'minus';}

Laravolt statistics components use Font Awesome v5 Duotone icons. You can browse the available icons at [Font Awesome](https://fontawesome.com/v5/search?s=duotone).

Advanced Features
-----------------

### Polling for Real-time Updates

You can make your statistics update automatically at regular intervals by adding Livewire's polling feature:

PHP

    class ActiveUsers extends Statistic{    // Update every 5 seconds    protected $listeners = ['$refresh'];    protected $polling = 5000;    // Rest of the class}

### Conditional Display

You can conditionally show or hide specific elements of your statistic component:

PHP

    public function shouldDisplayIcon(): bool{    return $this->value() > 0;}

### Custom Templates

If you need more customization than the default template provides, you can publish the view:

Bash

    php artisan vendor:publish --tag=laravolt-views

Then edit the statistic component view at `resources/views/vendor/laravolt/statistic/default.blade.php`.

Examples
--------

### Basic User Counter

PHP

    class TotalUsers extends Statistic{    public string $label = 'Registered Users';    public ?string $icon = 'users';    public ?string $color = 'blue';    public function value(): int|string    {        return \App\Models\User::count();    }}

### Revenue Monitor with Formatting

PHP

    class TotalRevenue extends Statistic{    public string $label = 'Monthly Revenue';    public ?string $icon = 'money-bill';    public ?string $color = 'green';    public function value(): int|string    {        $revenue = Order::whereMonth('created_at', now()->month)            ->whereYear('created_at', now()->year)            ->sum('total');        return 'Rp ' . number_format($revenue, 0, ',', '.');    }}

### Dynamic Task Status

PHP

    class PendingTasks extends Statistic{    public string $label = 'Pending Tasks';    public function icon(): ?string    {        $count = $this->value();        if ($count > 10) {            return 'exclamation-triangle';        }        return 'tasks';    }    public function color(): ?string    {        $count = $this->value();        if ($count > 10) {            return 'red';        } elseif ($count > 5) {            return 'yellow';        }        return 'green';    }    public function value(): int|string    {        return \App\Models\Task::where('status', 'pending')->count();    }}

Best Practices
--------------

### Keep It Simple

*   Statistics components are most effective when they show a single, clear value
*   Avoid complex calculations that could slow page loading
*   Use appropriate formatting to make large numbers readable

### Provide Context

*   Choose clear, descriptive labels
*   Use colors consistently throughout your application
*   Consider adding trends or comparisons to previous periods

### Performance Considerations

*   For expensive calculations, consider caching the results
*   Use database aggregations rather than PHP calculations when possible
*   If polling for updates, keep the interval reasonable (5+ seconds)

Troubleshooting
---------------

### Component Not Updating

If your statistic component isn't updating:

1.  Check that Livewire is properly installed and working
2.  Verify that your component's namespace matches its location
3.  Clear view cache and compiled assets:
    
    Bash
    
        php artisan view:clearphp artisan livewire:discover
    

### Icons Not Displaying

If icons aren't showing up:

1.  Ensure Font Awesome is properly loaded in your layout
2.  Verify you're using icon names available in Font Awesome v5
3.  Check console for any JavaScript errors

Related Components
------------------

*   [Charts](/v6/charts) - For displaying more complex data visualizations
*   [Tables](/v6/table) - For displaying tabular data
*   [Dashboard Layouts](/v6/layout) - For arranging multiple statistics components## === charts.md ===
## Charts
======

Charts provide powerful data visualization capabilities for your Laravel applications. Laravolt's chart components leverage the popular ApexCharts library, wrapped in Livewire components for a seamless PHP development experience.

* * *

Overview
--------

Laravolt charts enable you to create sophisticated data visualizations without writing any JavaScript. The package serves as a wrapper around [ApexCharts](https://apexcharts.com/), a modern JavaScript charting library, but exposes its API entirely through PHP.

Installation
------------

Charts functionality is included in the Laravolt UI package. If you haven't installed Laravolt yet, refer to the [installation guide](/v6/installation).

The charts component relies on Laravel Livewire, which should be installed as part of the Laravolt installation process.

Basic Usage
-----------

### Creating a Chart Component

To create a new chart component, use the provided Artisan command:

Bash

    php artisan make:chart DailyRegistration

This command generates a new Livewire component in the `app/Http/Livewire/Chart` directory. The generated class extends the appropriate chart type base class and provides a template for you to customize:

PHP

    <?phpnamespace App\Http\Livewire\Chart;use Laravolt\Charts\Line;class DailyRegistration extends Line{    public string $title = 'Daily Registration';    public function series(): array    {        return [            'series-1' => [                'Label 1' => 10,                'Label 2' => 14,                'Label 3' => 40            ],        ];    }}

### Displaying a Chart Component

Once created, you can display your chart component in any Blade view using one of these methods:

Blade

    <livewire:chart.daily-registration />{{-- Or using the @livewire directive --}}@livewire('chart.daily-registration'){{-- Or using the full class name --}}@livewire(\App\Http\Livewire\Chart\DailyRegistration::class)

Chart Types
-----------

Laravolt provides several chart types, each extending a base class that configures the appropriate ApexCharts settings:

### Bar Charts

For vertical bar charts, extend the `Bar` class:

PHP

    use Laravolt\Charts\Bar;class MonthlyRevenue extends Bar{    public string $title = 'Monthly Revenue';    public function series(): array    {        return [            'revenue' => [                'January' => 12000,                'February' => 14000,                'March' => 18000,                // ...            ],        ];    }}

### Line Charts

For line charts that highlight trends over time, extend the `Line` class:

PHP

    use Laravolt\Charts\Line;class DailyActiveUsers extends Line{    public string $title = 'Daily Active Users';    public function series(): array    {        return [            'users' => [                'Monday' => 120,                'Tuesday' => 140,                'Wednesday' => 180,                // ...            ],        ];    }}

### Area Charts

For filled line charts that emphasize volume, extend the `Area` class:

PHP

    use Laravolt\Charts\Area;class WebsiteTraffic extends Area{    public string $title = 'Website Traffic';    public function series(): array    {        // Your data here        return [            'visits' => [                'Week 1' => 4500,                'Week 2' => 5200,                'Week 3' => 4800,                // ...            ],        ];    }}

### Donut Charts

For circular charts that show composition, extend the `Donut` class:

PHP

    use Laravolt\Charts\Donut;class BrowserUsage extends Donut{    public string $title = 'Browser Usage';    public function series(): array    {        return [            'Chrome' => 64.4,            'Firefox' => 10.3,            'Safari' => 8.5,            'Edge' => 13.6,            'Others' => 3.2,        ];    }}

Customization
-------------

### Title Configuration

Set a static title using the `$title` property:

PHP

    public string $title = 'Monthly Sales Data';

For dynamic titles that respond to filters or other context, override the `title()` method:

PHP

    public function title(): string{    $month = request()->query('month', date('F'));    $year = request()->query('year', date('Y'));    return "Monthly Sales Data - {$month} {$year}";}

### Height Adjustment

Control the chart height using the `$height` property:

PHP

    protected int $height = 500;

For dynamic height based on conditions, override the `height()` method:

PHP

    public function height(): int{    if (request()->has('detailed')) {        return 600;    }    return 400;}

### Labels Customization

By default, chart labels come from the keys in your series data. To customize labels, override the `labels()` method:

PHP

    public function labels(): array{    return ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];}

### Chart Options

ApexCharts provides many options to customize the appearance and behavior of charts. You can set these options by overriding the `options()` method:

PHP

    public function options(): array{    $defaultOptions = parent::options();    $customOptions = [        'legend' => [            'position' => 'top',        ],        'colors' => ['#008FFB', '#00E396', '#FEB019'],        'tooltip' => [            'shared' => true,            'intersect' => false,        ],    ];    return array_merge($defaultOptions, $customOptions);}

Data Processing Examples
------------------------

### Monthly User Registrations Example

This example shows how to generate a chart showing user registration data by month:

PHP

    public function series(): array{    // Initialize 12 months with zero values    $months = collect()->pad(12, 0);    // Get monthly registration data from database    $users = User::whereYear('created_at', now()->year)        ->get()        ->groupBy(function ($user) {            // Month index starts at 0 to match array indexing            return Carbon::parse($user->created_at)->month - 1;        })        ->map(function ($users) {            return $users->count();        });    // Merge real data with the zero-filled array to ensure all months are included    $data = $users->union($months)->toArray();    return [        'registrations' => $data,    ];}public function labels(): array{    return ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];}

### Multiple Series Example

This example creates a chart comparing two different metrics:

PHP

    public function series(): array{    // Get order data grouped by month    $orders = Order::whereYear('created_at', now()->year)        ->get()        ->groupBy(function ($order) {            return Carbon::parse($order->created_at)->month - 1;        });    // Calculate revenue by month    $revenue = collect()->pad(12, 0);    $orders->each(function ($monthlyOrders, $month) use (&$revenue) {        $revenue[$month] = $monthlyOrders->sum('total');    });    // Calculate order count by month    $count = collect()->pad(12, 0);    $orders->each(function ($monthlyOrders, $month) use (&$count) {        $count[$month] = $monthlyOrders->count();    });    return [        'revenue' => $revenue->toArray(),        'orders' => $count->toArray(),    ];}

Advanced Features
-----------------

### Real-time Updates with Polling

Make your charts update automatically at regular intervals using Livewire's polling feature:

PHP

    class ActiveUsersChart extends Line{    protected $listeners = ['$refresh'];    protected $polling = 10000; // Update every 10 seconds    // Chart definition}

### Handling User Interactions

You can respond to user input by defining Livewire methods and properties:

PHP

    class SalesChart extends Bar{    public $selectedYear;    public function mount()    {        $this->selectedYear = now()->year;    }    public function updatedSelectedYear()    {        // Chart will automatically refresh when the year changes    }    public function series(): array    {        return [            'sales' => Order::whereYear('created_at', $this->selectedYear)                ->get()                ->groupBy(function ($order) {                    return Carbon::parse($order->created_at)->month - 1;                })                ->map(function ($orders) {                    return $orders->sum('total');                })                ->union(collect()->pad(12, 0))                ->toArray(),        ];    }}

The corresponding Blade template:

Blade

    <div>    <select wire:model="selectedYear">        @foreach(range(2018, now()->year) as $year)            <option value="{{ $year }}">{{ $year }}</option>        @endforeach    </select>    <livewire:chart.sales-chart :key="$selectedYear" /></div>

Best Practices
--------------

### Performance Considerations

*   For complex data processing, consider caching results
*   Use database aggregations (using SQL `SUM()`, `COUNT()`, etc.) rather than collecting all records and processing in PHP
*   Limit the amount of data displayed to maintain responsiveness

### Visual Clarity

*   Choose appropriate chart types for your data:
    *   Line/area charts for trends over time
    *   Bar charts for comparing discrete categories
    *   Pie/donut charts for showing composition (limit to 5-7 segments)
*   Use a consistent color palette throughout your application
*   Avoid cluttering charts with too many data series

### Responsive Design

*   Test your charts on different screen sizes
*   Consider simplified views for mobile devices
*   Adjust the chart height based on the viewport

Troubleshooting
---------------

### Charts Not Displaying

If your charts aren't showing up:

1.  Check the browser console for JavaScript errors
2.  Verify that Livewire is properly installed and registered
3.  Ensure your data format matches what ApexCharts expects
4.  Check that the chart height is set to a positive value

### Performance Issues

If charts are slow to render:

1.  Optimize your data queries to minimize processing time
2.  Consider adding database indexes to columns used for filtering or grouping
3.  Implement caching for expensive calculations
4.  Reduce the amount of data displayed if appropriate

Related Components
------------------

*   [Statistics](/v6/statistics) - For displaying single-value metrics
*   [Tables](/v6/table) - For displaying tabular data
*   [Dashboard Layouts](/v6/layout) - For arranging multiple visualization components## === routes.md ===
## Laravel Route Best Practices
============================

Laravel's routing system provides an elegant and expressive way to define application routes. Following consistent naming conventions and best practices ensures your application remains maintainable as it grows.

* * *

Overview
--------

Routes define the entry points to your application, connecting URLs to controller actions. Implementing a consistent routing strategy improves code organization, readability, and makes your application easier to maintain over time.

Route Naming Conventions
------------------------

Consistency in naming routes and URLs helps maintain a clean codebase and improves developer experience. Follow these conventions for best results:

Element

Convention

Good Examples

Poor Examples

**URL Paths**

singular, kebab-case

`/laporan-harian`

`/laporanHarian`<br />`/laporan_harian`

**Route Names**

singular, kebab-case

`->name("laporan-harian")`

`->name("laporanHarian")`<br />`->name("laporan_harian")`

RESTful Resource Routes
-----------------------

Laravel provides a convenient way to define RESTful routes that map to standard CRUD operations. Always follow these seven standard REST actions for consistency:

HTTP Verb

URI

Controller Action

Route Name

GET

`/user`

index

user.index

GET

`/user/create`

create

user.create

POST

`/user`

store

user.store

GET

`/user/{user}`

show

user.show

GET

`/user/{user}/edit`

edit

user.edit

PUT/PATCH

`/user/{user}`

update

user.update

DELETE

`/user/{user}`

destroy

user.destroy

### Explicit Route Definition

You can define resource routes explicitly:

PHP

    Route::get('/user', 'UserController@index')->name('user.index');Route::get('/user/create', 'UserController@create')->name('user.create');Route::post('/user', 'UserController@store')->name('user.store');Route::get('/user/{user}', 'UserController@show')->name('user.show');Route::get('/user/{user}/edit', 'UserController@edit')->name('user.edit');Route::put('/user/{user}', 'UserController@update')->name('user.update');Route::delete('/user/{user}', 'UserController@destroy')->name('user.destroy');

### Implicit Resource Routes

Laravel provides a shorthand for defining all seven RESTful routes in a single line:

PHP

    Route::resource('user', 'UserController');

Advanced Routing Strategies
---------------------------

When your application requires additional actions beyond the standard RESTful routes, consider these approaches:

### Feature-Based Controllers

For actions that don't fit into the seven standard RESTful methods, create dedicated controllers that focus on a specific feature while still adhering to RESTful conventions.

#### Example: Managing User Passwords

❌ **Avoid creating non-standard action names**:

PHP

    // Bad: "editPassword" and "updatePassword" are not standard REST actionsRoute::get('/user/{user}/password', 'UserController@editPassword');Route::put('/user/{user}/password', 'UserController@updatePassword');

✅ **Create feature-specific controllers**:

PHP

    // Good: Using dedicated controller with standard REST verbsRoute::get('/user/{user}/password', 'UserPasswordController@edit');Route::put('/user/{user}/password', 'UserPasswordController@update');

✅ **Or use nested controllers**:

PHP

    // Also good: Using nested namespace approachRoute::get('/user/{user}/password', 'User\\PasswordController@edit');Route::put('/user/{user}/password', 'User\\PasswordController@update');

### Example: Displaying User Followers

❌ **Avoid non-standard controller methods**:

PHP

    // Bad: "follower" is not a standard REST actionRoute::get('/user/{user}/follower', 'UserController@follower');

✅ **Use resource-specific controllers**:

PHP

    // Good: Using composite controller name with standard REST verbRoute::get('/user/{user}/follower', 'UserFollowerController@index');

✅ **Or use nested controllers**:

PHP

    // Also good: Using nested namespace approachRoute::get('/user/{user}/follower', 'User\\FollowerController@index');

Single Action Controllers
-------------------------

Single Action Controllers are ideal for standalone operations that:

1.  Don't fit into standard CRUD operations
2.  Can be called from multiple places in your application
3.  Relate to pivot tables or many-to-many relationships
4.  Represent atomic actions with clear, singular purposes

### When to Use Single Action Controllers

Consider using Single Action Controllers for these common scenarios:

*   File uploads
*   Password reset workflows
*   Cache management operations
*   Post-login landing pages
*   Authentication actions (logout)
*   Toggleable actions (like/unlike, follow/unfollow)

### Implementation Example

PHP

    namespace App\Http\Controllers;class DownloadInvoiceController extends Controller{    public function __invoke(Invoice $invoice)    {        // Authorization logic        $this->authorize('download', $invoice);        // Processing logic        $pdf = $this->generateInvoicePdf($invoice);        // Return response        return response()->download($pdf);    }}

Route definition:

PHP

    Route::get('/invoices/{invoice}/download', DownloadInvoiceController::class);

Best Practices
--------------

*   **Be consistent** with your route naming throughout your application
*   **Use route groups** to apply middleware, prefixes, or namespaces to related routes
*   **Leverage route model binding** to automatically inject models into your routes
*   **Name all routes** to make them easier to reference in views and controllers
*   **Avoid hardcoding URLs** in your views - use the `route()` helper instead
*   **Keep controllers focused** on specific resources or features
*   **Use route caching** in production to improve performance

Troubleshooting
---------------

### Common Routing Issues

Issue

Solution

Route not found (404)

Check route definition and ensure correct HTTP verb is used

Method not allowed (405)

Verify that you're using the correct HTTP method for the route

Route parameter conflicts

Place more specific routes before wildcard routes

Controller method not found

Verify namespace and method name in route definition

### Route Caching Issues

If your application behaves differently after running `php artisan route:cache`:

1.  Check for route definitions using closures (they can't be cached)
2.  Ensure all controller classes exist and are correctly namespaced
3.  Clear the route cache with `php artisan route:clear` and try again

Related Documentation
---------------------

*   [Laravel Routing](/v6/basics)
*   [Controller Organization](/v6/controller)
*   [Middleware](/v6/middleware)
*   [Authentication](/v6/authentication)## === controller.md ===
## Controller Best Practices
=========================

Well-structured controllers are essential for maintainable Laravel applications. Following the "thin controller" approach helps keep your application's business logic organized and testable.

* * *

Overview
--------

Controllers serve as the bridge between HTTP requests and your application's business logic. They should remain focused on handling request/response interactions rather than implementing complex application logic. This separation of concerns leads to more maintainable, testable, and scalable applications.

Core Principles
---------------

The "thin controller" philosophy is built on several key principles:

### 1\. Focus on HTTP Concerns

Controllers should primarily deal with HTTP-related tasks:

*   Receiving input from requests
*   Coordinating with other application layers
*   Returning appropriate responses
*   Managing redirects and status codes

### 2\. Delegate Business Logic

Complex business logic should be delegated to dedicated services or models:

PHP

    // ❌ Business logic in controllerpublic function store(Request $request){    $data = $request->validate([        'title' => 'required|max:255',        'content' => 'required',    ]);    // Business logic mixed with controller code    $post = new Post();    $post->title = $data['title'];    $post->content = $data['content'];    $post->slug = Str::slug($data['title']);    $post->user_id = auth()->id();    $post->published_at = $request->has('publish') ? now() : null;    $post->save();    // More business logic    if ($request->has('notify_subscribers')) {        $subscribers = User::subscribers()->get();        foreach ($subscribers as $subscriber) {            Mail::to($subscriber)->send(new NewPostNotification($post));        }    }    return redirect()->route('posts.index')        ->with('success', 'Post created successfully');}// ✅ Thin controller with delegated business logicpublic function store(CreatePostRequest $request, PostService $postService){    $post = $postService->create($request->validated(), $request->has('publish'));    if ($request->has('notify_subscribers')) {        $postService->notifySubscribers($post);    }    return redirect()->route('posts.index')        ->with('success', 'Post created successfully');}

Implementation Guidelines
-------------------------

### Use Form Requests for Validation

Controllers should not contain form validation logic. Instead, use Laravel's Form Request classes for validation:

PHP

    // Controllerpublic function store(StorePostRequest $request){    // $request is already validated    $post = Post::create($request->validated());    return redirect()->route('posts.show', $post)        ->with('success', 'Post created successfully');}// Form Requestclass StorePostRequest extends FormRequest{    public function rules()    {        return [            'title' => 'required|max:255',            'content' => 'required',            'category_id' => 'required|exists:categories,id',        ];    }    public function messages()    {        return [            'category_id.exists' => 'The selected category does not exist',        ];    }}

### Implement Authorization

Controllers should handle authorization, typically using Laravel's policies:

PHP

    public function update(UpdatePostRequest $request, Post $post){    $this->authorize('update', $post);    $post->update($request->validated());    return redirect()->route('posts.show', $post)        ->with('success', 'Post updated successfully');}

### Follow Resource Controller Pattern

Organize your controllers using Laravel's resource controller pattern:

HTTP Verb

URI

Action

Route Name

GET

`/posts`

index

posts.index

GET

`/posts/create`

create

posts.create

POST

`/posts`

store

posts.store

GET

`/posts/{post}`

show

posts.show

GET

`/posts/{post}/edit`

edit

posts.edit

PUT/PATCH

`/posts/{post}`

update

posts.update

DELETE

`/posts/{post}`

destroy

posts.destroy

Generate a resource controller with:

Bash

    php artisan make:controller PostController --resource

Use route registration:

PHP

    // routes/web.phpRoute::resource('posts', PostController::class);

### Create Single-Action Controllers for Custom Operations

When actions don't fit the resource pattern, use single action controllers:

PHP

    // Single Action Controller exampleclass PublishPostController extends Controller{    public function __invoke(Post $post)    {        $this->authorize('publish', $post);        $post->publish();        return redirect()->back()->with('success', 'Post published successfully');    }}// RoutesRoute::post('/posts/{post}/publish', PublishPostController::class)->name('posts.publish');

Advanced Patterns
-----------------

### Service Classes

For complex operations that involve multiple models or external services, create dedicated service classes:

PHP

    // Controller remains thinpublic function store(StoreOrderRequest $request, OrderService $orderService){    $order = $orderService->createOrder(        $request->validated(),        $request->user()    );    return redirect()->route('orders.show', $order)        ->with('success', 'Order placed successfully');}// Service class handles the complex business logicclass OrderService{    public function createOrder(array $data, User $user)    {        DB::transaction(function () use ($data, $user, &$order) {            // Create order            $order = Order::create([                'user_id' => $user->id,                'total' => 0,                'status' => 'pending',            ]);            // Process items            $total = 0;            foreach ($data['items'] as $item) {                $product = Product::findOrFail($item['product_id']);                $subtotal = $product->price * $item['quantity'];                $orderItem = $order->items()->create([                    'product_id' => $product->id,                    'quantity' => $item['quantity'],                    'unit_price' => $product->price,                    'subtotal' => $subtotal,                ]);                $total += $subtotal;            }            // Update order total            $order->update(['total' => $total]);            // Check inventory            $this->checkAndUpdateInventory($order);            // Process payment            $this->processPayment($order, $data['payment_method']);            // Send notifications            $this->sendNotifications($order);        });        return $order;    }    // Additional methods...}

### Controller Namespacing

For complex applications, organize controllers in namespaces:

Plain Text

    app/Http/Controllers/  ├── Admin/  │   ├── UserController.php  │   ├── ProductController.php  │   └── OrderController.php  ├── Api/  │   ├── V1/  │   │   └── UserController.php  │   └── V2/  │       └── UserController.php  └── Front/      ├── HomeController.php      ├── ProductController.php      └── CartController.php

Best Practices
--------------

### Keep Methods Small

Each controller method should be concise and focused on a single responsibility. If a method grows beyond 15-20 lines, consider refactoring into smaller components.

### Use Dependency Injection

Leverage Laravel's service container to inject dependencies into your controllers:

PHP

    class ReportController extends Controller{    private $reportGenerator;    public function __construct(ReportGeneratorInterface $reportGenerator)    {        $this->reportGenerator = $reportGenerator;    }    public function generate(Request $request)    {        return $this->reportGenerator->generate($request->validated());    }}

### Return Appropriate Responses

Ensure your controller methods return appropriate responses based on context:

PHP

    public function show(Post $post){    $this->authorize('view', $post);    if (request()->wantsJson()) {        return response()->json([            'data' => new PostResource($post)        ]);    }    return view('posts.show', compact('post'));}

### Use View Models or Presenters

For complex view data preparation, consider using view models or presenters:

PHP

    public function show(Post $post){    return view('posts.show', [        'viewModel' => new PostViewModel($post)    ]);}

Troubleshooting
---------------

### Controller Methods Growing Too Large

**Issue**: Controller methods become too long and complex.

**Solution**: Look for repeating patterns and extract them into services, actions, or helper methods.

### Duplicate Logic Across Controllers

**Issue**: Similar logic appears in multiple controllers.

**Solution**: Extract shared functionality into traits, base controller classes, or dedicated services.

### Controller Testing Difficulties

**Issue**: Complex controllers are difficult to test.

**Solution**: Move business logic to testable services and only test HTTP concerns in controller tests.

Related Documentation
---------------------

*   [Form Requests](/v6/form)
*   [Routes and Naming](/v6/routes)
*   [Service Pattern](/v6/best-practices)
*   [Action Classes](/v6/action-classes)## === naming-conventions.md ===
## Naming Conventions
==================

Consistent naming conventions are crucial for maintaining readability and collaboration in software projects. Following these guidelines will help you create code that is easier to understand, maintain, and extend.

* * *

Overview
--------

As the saying goes, "There are only two hard things in Computer Science: cache invalidation and naming things." While we can't make naming easier, we can establish consistent patterns that improve code readability and reduce cognitive load when working on Laravel projects.

General Principles
------------------

Good names should be:

*   **Descriptive** - clearly communicate purpose and intent
*   **Concise** - as short as possible without sacrificing clarity
*   **Consistent** - follow established patterns throughout the project
*   **Contextual** - consider where and how the name will be used

Naming Standards by Category
----------------------------

### Code Elements

Element

Convention

Examples

Variables

camelCase

`$userId`, `$totalAmount`, `$isActive`

Class properties

camelCase

`private $accessToken`, `protected $createdAt`

Class methods

camelCase

`getFullName()`, `calculateTotal()`, `featuredArticle()`

Global helpers

snake\_case

`format_rupiah()`, `convert_date()`

Classes

StudlyCase (nouns)

`User`, `PaymentGateway`, `UserProfile`

Interfaces

StudlyCase (adjectives)

`Authenticatable`, `Reportable`

Traits

StudlyCase (adjectives)

`Notifiable`, `Searchable`

### Controllers

Type

Convention

Examples

Resource controllers

StudlyCase (noun + `Controller`)

`UserController`, `ProductController`, `BukuTamuController`

Single action controllers

StudlyCase (verb + `Controller`)

`ClearCacheController`, `LogoutController`, `DownloadLaporanHarianController`

### Files and Paths

Type

Convention

Examples

View files

kebab-case

`user-profile.blade.php`, `laporan-harian.blade.php`

Partial views

kebab-case with leading underscore

`_header.blade.php`, `_tabel-pegawai.blade.php`

Config files

kebab-case

`app.php`, `dynamic-form.php`

Config keys

snake\_case

`'allowed_types' => ['text', 'textarea']`

### Routing

Element

Convention

Examples

Route URLs

kebab-case

`https://example.com/laporan-harian`

Route names

kebab-case with dot separating resource and action

`lowongan-kerja.index`, `user.create`

Route parameters

camelCase

`{userId}`, `{lowonganKerja}`

### Database

Element

Convention

Examples

Table names

snake\_case (plural nouns)

`users`, `blog_posts`, `order_items`

Grouped tables

Prefixed snake\_case

`master_provinsi`, `master_kabupaten`

Pivot tables

Singular model names in alphabetical order

`role_user`, `permission_role`

Column names

snake\_case

`first_name`, `created_at`, `is_active`

Primary keys

`id`

`id`

Foreign keys

Singular model name with `_id` suffix

`user_id`, `post_id`

### Commands and Jobs

Element

Convention

Examples

Artisan commands

kebab-case

`php artisan generate-laporan`

Command classes

StudlyCase

`GenerateLaporanCommand`

Jobs

StudlyCase (verb)

`ProcessPayment`, `SendReminderEmails`

Best Practices
--------------

### Be Consistent

Consistency is more important than the specific convention chosen. If you're joining an existing project, follow its established conventions even if they differ from these guidelines.

### Use Descriptive Names

Avoid abbreviations and single-letter variables except in very limited contexts (like loop counters). Names should be self-explanatory:

PHP

    // Poor naming$u = User::find(1);$r = $u->roles;$p = [];foreach ($r as $i) {    $p[] = $i->permissions;}// Better naming$user = User::find(1);$roles = $user->roles;$permissions = [];foreach ($roles as $role) {    $permissions[] = $role->permissions;}

### Consider Search-ability

Names should be distinct enough to allow for effective code searching:

PHP

    // Hard to search for$data = User::all();// Better - unique and searchable$activeUsers = User::where('status', 'active')->get();

### Use Domain Language

Align your naming with the domain language of your project:

PHP

    // Generic naming$items = Order::find(1)->products;// Domain-specific naming$lineItems = Order::find(1)->products;

Common Pitfalls
---------------

### Avoid Multiple Standards

Don't mix naming conventions for the same type of elements:

PHP

    // Inconsistent$user_id = 1;$orderID = 100;$productId = 25;// Consistent (choose one style)$userId = 1;$orderId = 100;$productId = 25;

### Don't Reflect Type in Name

Modern IDEs provide type information, so don't include types in names:

PHP

    // Unnecessary$usersArray = User::all()->toArray();$nameString = $user->name;// Better$users = User::all()->toArray();$name = $user->name;

### Avoid Unnecessary Context

Don't repeat the context that's already clear:

PHP

    // Redundant contextclass User {    public function getUserName() {...}    public function getUserEmail() {...}}// Betterclass User {    public function name() {...}    public function email() {...}}

Troubleshooting
---------------

### Resolving Naming Conflicts

When you encounter naming conflicts:

1.  Consider adding more specific context
2.  Use namespaces to separate identical names in different contexts
3.  Refactor to better represent the domain concepts

### Managing Legacy Code

When working with legacy code that doesn't follow these conventions:

1.  Follow existing patterns for modifications to maintain consistency
2.  Create style guides for new code
3.  Refactor incrementally when possible

Related Documentation
---------------------

*   [Code Style Guide](/v6/code-quality)
*   [Laravel Routes](/v6/routes)
*   [Laravel Controllers](/v6/controller)## === performance.md ===
## Performance Optimization
========================

Optimizing performance is crucial for delivering a responsive, efficient user experience. Laravolt applications can benefit from several performance tweaks that significantly reduce resource usage and response times.

* * *

Overview
--------

Application performance optimization involves identifying and addressing bottlenecks that impact response times, resource usage, and overall user experience. Laravel provides several built-in tools and techniques to enhance performance, which are easily implementable in Laravolt applications.

Laravel Built-In Optimizers
---------------------------

Laravel includes several commands to optimize application performance in production environments.

### Route and Config Caching

The `optimize` command combines route and configuration caching to improve application boot time:

Bash

    php artisan optimize

This command generates cached files for faster loading, reducing the need for Laravel to scan and load files on every request.

To clear the cache when making changes to routes or configurations:

Bash

    php artisan optimize:clear

### View Caching

Precompile Blade templates to avoid compiling them on each request:

Bash

    php artisan view:cache

Clear the view cache when you modify Blade templates:

Bash

    php artisan view:clear

### Event Caching

For applications with many event listeners, cache the event discovery process:

Bash

    php artisan event:cache

Clear when adding or changing event listeners:

Bash

    php artisan event:clear

Production Environment Settings
-------------------------------

### Disable Debug Mode

Debug mode provides helpful information during development but significantly impacts performance and can expose sensitive information in production. Always disable it in production:

Dotenv

    APP_DEBUG=false

### Optimize Composer Autoloader

When deploying to production, optimize the Composer autoloader:

Bash

    composer install --optimize-autoloader --no-dev

This creates a class map for all PSR-4 compatible classes, reducing the time Composer spends looking for files.

Laravolt-Specific Optimizations
-------------------------------

### Cache Blade Iconset

Laravolt uses SVG icons in Blade components. Cache these icons to improve rendering performance:

Bash

    php artisan icon:cache

To clear the icon cache (after adding or updating icons):

Bash

    php artisan icon:clear

### Cache Eloquent User Provider

Reduce database queries by using the cached Eloquent user provider. Update `config/auth.php`:

PHP

    'providers' => [    'users' => [        // Change from 'eloquent' to 'eloquent-cached'        'driver' => 'eloquent-cached',        'model' => App\Models\User::class,    ],],

This optimization caches user data, reducing authentication-related queries on each request.

Database Optimizations
----------------------

### Query Optimization

#### Use Eager Loading

Avoid N+1 query problems by using eager loading with relationships:

PHP

    // Inefficient - causes N+1 queries$posts = Post::all();foreach ($posts as $post) {    echo $post->user->name;}// Efficient - uses eager loading$posts = Post::with('user')->get();foreach ($posts as $post) {    echo $post->user->name;}

#### Use Query Caching

For expensive or frequently executed queries, implement caching:

PHP

    use Illuminate\Support\Facades\Cache;$users = Cache::remember('all-active-users', 3600, function () {    return User::where('active', true)->get();});

### Database Indexing

Properly indexed tables significantly improve query performance. Add indexes to columns frequently used in WHERE, ORDER BY, and JOIN clauses:

PHP

    // In a migration fileSchema::table('posts', function (Blueprint $table) {    $table->index('user_id');    $table->index(['status', 'created_at']);});

Frontend Optimizations
----------------------

### Asset Bundling and Minification

Use Laravel Mix or Vite to bundle and minify CSS and JavaScript:

Bash

    # Using Mixnpm run production# Using Vitenpm run build

### Image Optimization

Optimize images to reduce load times:

1.  Use appropriate formats (WebP, AVIF for modern browsers)
2.  Implement responsive images using srcset
3.  Consider lazy loading for below-the-fold images

HTML

    <img  src="small.jpg"  srcset="medium.jpg 1000w, large.jpg 2000w"  sizes="(max-width: 500px) 100vw, (max-width: 1500px) 50vw, 30vw"  loading="lazy"  alt="Description"/>

Caching Strategies
------------------

### Response Caching

For pages with static content or content that changes infrequently, implement HTTP response caching:

PHP

    public function index(){    return Cache::remember('homepage', 3600, function () {        return view('home', [            'featuredPosts' => Post::featured()->get(),        ]);    });}

### Fragment Caching

Cache specific parts of views that are expensive to generate:

Blade

    @cache('user-list', 60)    @foreach($users as $user)        @include('partials.user-card', ['user' => $user])    @endforeach@endcache

Monitoring and Performance Testing
----------------------------------

### Laravel Telescope

Install Laravel Telescope to monitor application performance in development:

Bash

    composer require laravel/telescope --devphp artisan telescope:installphp artisan migrate

### Profiling with Laravel Debugbar

Use Laravel Debugbar to identify performance bottlenecks:

Bash

    composer require barryvdh/laravel-debugbar --dev

Best Practices
--------------

### Optimize Background Jobs

*   Use queued jobs for resource-intensive operations
*   Implement batching for large data processing tasks
*   Set appropriate timeouts and retry settings

### Implement Lazy Collections for Large Datasets

When working with large datasets, use lazy collections to reduce memory usage:

PHP

    $users = User::cursor()->filter(function ($user) {    return $user->isPremium();});

### Use Pagination for Large Result Sets

Always paginate results when returning large collections:

PHP

    // Return paginated resultsreturn User::paginate(25);

Troubleshooting Performance Issues
----------------------------------

### Identifying Bottlenecks

1.  **Database queries**: Look for slow queries in database logs or using Laravel Debugbar
2.  **Memory usage**: Check if your application is hitting memory limits
3.  **External services**: Monitor response times for API calls to third-party services
4.  **Server configuration**: Verify that your server is properly configured for your application's needs

### Common Issues and Solutions

Issue

Potential Cause

Solution

Slow API responses

N+1 query problem

Use eager loading with `with()`

High memory usage

Loading large datasets

Use lazy collections and pagination

Slow page loads

Unoptimized assets

Bundle, minify, and use browser caching

Database timeouts

Missing indexes

Add appropriate indexes to frequently queried columns

Related Documentation
---------------------

*   [Laravel Optimization Documentation](https://laravel.com/docs/deployment#optimization)
*   [Database Indexing](/v6/database-optimization)
*   [Server Configuration](/v6/server-configuration)## === editor-ide.md ===
## Editor & IDE Setup
==================

Choosing the right development environment significantly impacts your productivity and code quality. This guide provides recommendations for setting up your editor or IDE for efficient Laravel and Laravolt development.

* * *

Overview
--------

A well-configured development environment makes coding more efficient, helps catch errors early, and provides features like autocompletion, debugging, and code navigation. While personal preference plays a significant role in choosing your tools, we recommend several options that work particularly well for Laravel and PHP development.

Recommended Editors
-------------------

### PHPStorm

[PHPStorm](https://www.jetbrains.com/phpstorm/) is a professional, full-featured IDE designed specifically for PHP development.

#### Strengths

*   Comprehensive out-of-box PHP support
*   Deep Laravel integration
*   Advanced debugging capabilities
*   Powerful refactoring tools
*   Database tools and SQL support
*   Git integration with visual merge tool

#### Considerations

*   Paid license (free for students through the GitHub Student Developer Pack)
*   Requires more system resources (especially RAM)
*   Steeper learning curve for new users

### Visual Studio Code

[Visual Studio Code](https://code.visualstudio.com/) (VS Code) is a lightweight, highly extensible editor that can be customized to provide excellent PHP and Laravel support.

#### Strengths

*   Free and open-source
*   Lightweight with fast startup
*   Highly customizable through extensions
*   Strong community support
*   Works well across multiple programming languages

#### Considerations

*   Requires additional configuration and extensions to match PHPStorm's PHP capabilities
*   May require more manual setup for advanced features

Setting Up Visual Studio Code for Laravel
-----------------------------------------

Visual Studio Code is an excellent choice for Laravel development when configured with the right extensions. Follow these steps to set up an optimal Laravel development environment.

### Essential Extensions

#### 1\. Settings Sync

Synchronize your VS Code settings, snippets, themes, and extensions across multiple machines.

*   [Settings Sync](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync)

**Quick Setup:**

1.  Install the Settings Sync extension
2.  Press `SHIFT + ALT + D` to open the GUI
3.  Click "Download Public Gist"
4.  Enter Gist ID: `25cef208ec0fa79cebfeb0a653370b91` (Laravolt recommended settings)
5.  Wait for the installation and download process to complete

#### 2\. PHP Intelephense

A high-performance PHP code intelligence extension providing features like autocompletion, signature help, and go-to definition.

*   [PHP Intelephense](https://marketplace.visualstudio.com/items?itemName=bmewburn.vscode-intelephense-client)

**Key Features:**

*   Fast autocompletion and intellisense
*   Code navigation (go to definition, find all references)
*   Code linting and error detection
*   PHPDoc support
*   Lower resource usage than some alternatives

#### 3\. Laravel Extension Pack

A collection of extensions for Laravel development, including:

*   [Laravel Extension Pack](https://marketplace.visualstudio.com/items?itemName=onecentlin.laravel-extension-pack)

This pack includes:

*   Laravel Blade Snippets - Syntax highlighting and snippets for Blade
*   Laravel Snippets - Laravel snippets for common patterns
*   Laravel Artisan - Run Artisan commands from VS Code
*   Laravel Extra Intellisense - Advanced autocompletion for Laravel
*   Laravel Goto View - Jump to view files from controllers
*   Laravel Goto Controller - Navigate between routes and controllers
*   DotENV - .env file syntax highlighting

#### 4\. SonarLint

Code quality and security analysis tool that helps detect and fix issues before committing your code.

*   [SonarLint](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarlint-vscode)

**Benefits:**

*   Real-time feedback on code quality
*   Detection of bugs and security vulnerabilities
*   Clean code recommendations
*   Consistent coding standards

#### 5\. GitLens

Enhance Git capabilities within VS Code for better repository visualization and history tracking.

*   [GitLens](https://gitlens.amod.io/)

**Key Features:**

*   Inline Git blame annotations
*   File and line history exploration
*   Branch and tag visualization
*   Commit search and comparison

### Additional Recommended Extensions

#### PHP DocBlocker

Provides automatic PHP docblock generation for functions and classes.

Bash

    ext install neilbrayfield.php-docblocker

#### Tailwind CSS IntelliSense

If you're using Tailwind CSS with Laravel, this extension provides autocompletion and linting for Tailwind classes.

Bash

    ext install bradlc.vscode-tailwindcss

#### Laravel Blade Formatter

Format your Blade templates with this specialized formatter.

Bash

    ext install shufo.vscode-blade-formatter

#### Better PHPUnit

Run PHPUnit tests directly from VS Code.

Bash

    ext install calebporzio.better-phpunit

Setting Up PHPStorm for Laravel
-------------------------------

PHPStorm comes with excellent PHP support out of the box, but adding a few plugins can enhance your Laravel development experience.

### Recommended Plugins

To add these plugins, go to **Preferences** > **Plugins** > **Marketplace**.

#### 1\. Laravel

Official Laravel plugin providing enhanced support for Laravel-specific features.

**Features:**

*   Advanced completion for facade methods
*   Route, config, view, and translation references
*   Blade template support
*   Artisan command integration

#### 2\. SonarLint

Integrates SonarLint code quality tools directly into PHPStorm.

**Benefits:**

*   Real-time code quality analysis
*   Security vulnerability detection
*   Customizable rules

#### 3\. PHP Inspection (EA Extended)

Extends PHPStorm's code inspection capabilities with additional checks.

**Features:**

*   Advanced code analysis
*   Additional inspections not covered by PHPStorm's defaults
*   Performance optimization suggestions

#### 4\. Additional Optional Plugins

*   **WakaTime**: Track your coding time and habits
*   **Code With Me**: Collaborative coding sessions with team members

### PHPStorm Configuration Tips

#### Enable Laravel Plugin

1.  Go to **Preferences** > **PHP** > **Laravel**
2.  Check "Enable plugin for this project"
3.  Make sure the Laravel paths are correctly set

#### Configure Composer

1.  Go to **Preferences** > **PHP** > **Composer**
2.  Set path to composer.phar or composer executable
3.  Enable "Synchronize IDE settings with composer.json"

#### PHP CS Fixer Integration

1.  Install PHP CS Fixer via Composer
2.  Go to **Preferences** > **Tools** > **External Tools**
3.  Add PHP CS Fixer as an external tool
4.  Configure keyboard shortcut for easy formatting

Development Workflow Enhancements
---------------------------------

### Terminal Integration

Both VS Code and PHPStorm offer integrated terminals. Configure yours to:

*   Set the default shell (e.g., Bash, Zsh)
*   Configure split terminal views for running multiple commands
*   Add aliases for common Laravel commands

### Database Connection

Connect your IDE directly to your project's database:

**VS Code**:

*   Install the "SQLTools" extension
*   Configure your database connection

**PHPStorm**:

*   Go to **Database** in the right sidebar
*   Click "+" to add a data source
*   Configure connection to your database

### Xdebug Configuration

Configure Xdebug for step-through debugging:

1.  Install Xdebug PHP extension
2.  Configure your editor to connect to Xdebug
3.  Set breakpoints and start debugging sessions

Best Practices
--------------

### Consistent Formatting

Use tools like PHP CS Fixer or Laravel Pint to maintain consistent code formatting:

Bash

    # Using Laravel Pint./vendor/bin/pint# Using PHP CS Fixerphp-cs-fixer fix --config=.php-cs-fixer.php

### Regular Updates

Keep your editor and extensions updated for the latest features and security fixes.

### Keyboard Shortcuts

Learn keyboard shortcuts to speed up your workflow. Both VS Code and PHPStorm offer shortcut cheat sheets:

*   [VS Code Keyboard Shortcuts](https://code.visualstudio.com/docs/getstarted/keybindings)
*   [PHPStorm Keyboard Shortcuts](https://www.jetbrains.com/help/phpstorm/mastering-keyboard-shortcuts.html)

Troubleshooting
---------------

### Extension Conflicts

If you experience performance issues or conflicts:

1.  Try disabling extensions one by one to identify the culprit
2.  Make sure extensions are compatible with your editor version
3.  Check for duplicate functionality across multiple extensions

### Performance Issues

If your editor becomes slow:

**VS Code**:

*   Disable unnecessary extensions
*   Use the "workbench.editor.enablePreview" setting to reduce memory usage
*   Increase available memory with the "--max-memory" flag

**PHPStorm**:

*   Increase memory allocation in Help > Edit Custom VM Options
*   Disable plugins you don't use
*   Exclude large directories from indexing

Related Documentation
---------------------

*   [Laravel Development Environment](/v6/installation)
*   [Coding Standards](/v6/code-quality)
*   [Git Workflow](/v6/git-guidelines)## === auto-crud.md ===
## Auto CRUD
=========

Create, Read, Update, Delete operations are among the most common features in information system development.

* * *

Overview
--------

Typical CRUD features include:

1.  A page containing a list of data, usually displayed in a datatable complete with searching, sorting, and pagination.
2.  Buttons to add, edit, and delete data.

With Auto CRUD, these features don't need to be coded at all. Simply **"define"** what fields need to be displayed from an Eloquent Model, and a complete CRUD feature can automatically be accessed through the application without coding.

Installation
------------

### Enable Auto CRUD

Make sure `auto-crud` has been enabled:

###### config/laravolt/platform.php

PHP

    <?phpreturn [    'middleware' => ['web', 'auth'],    'features' => [        'auto-crud' => true,    ],];

### Define Your Model

Define your Eloquent Model including its **_relationships_**. The Model here is a regular [Eloquent](https://laravel.com/docs/master/eloquent) class, just like what we usually define in Laravel. The Model is used to interact with the database in the CRUD process.

PHP

    class User extends Model{    public function country()    {        return $this->belongsTo("App\\Models\\Country");    }}

This relationship is optional, but very useful when there are 2 or more models that are interconnected, such as Post and Category. Please read Laravel's official documentation on [Eloquent Relationships](https://laravel.com/docs/master/eloquent-relationships).

### Register Configuration File

Create a new configuration file in the `config/laravolt/auto-crud-resources` folder. The configuration file defines which fields will be displayed in:

*   Forms, including validation
*   Tables, including `searchable` and `sortable` flags
*   Detail pages

Here's a minimal example of a configuration file to create a CRUD based on the User model:

###### config/laravolt/auto-crud-resources/user.php

PHP

    return [    'label' => 'User',    'model' => \App\Models\User::class,    // optional, if you want to override the default Table    //'table' => \App\Http\Livewire\Table\UserCustomTable::class    'schema' => [        [            'name' => 'name',            'type' => \Laravolt\Fields\Field::TEXT,            'label' => 'Full Name',        ],        [            'name' => 'email',            'type' => \Laravolt\Fields\Field::EMAIL,            'label' => 'Email',        ],        [            'name' => 'password',            'type' => \Laravolt\Fields\Field::PASSWORD,            'label' => 'Password',        ],    ],];

Customization
-------------

### Table Customization

#### Create a Table

Bash

    php artisan make:table UserCustomTable

#### Define Columns

Modify the skeleton class to look like this:

PHP

    <?phpnamespace App\Http\Livewire\Table;use Laravolt\AutoCrud\Tables\ResourceTable;use Laravolt\Suitable\Columns\Label;class UserCustomTable extends ResourceTable{    protected function prepareColumns(): array    {        // keep default columns, call parent method        $columns = parent::prepareColumns();        // or override and prepare columns from scratch        // $columns = [];        // Define additional columns here as needed        $columns[] = Label::make('status', 'Status');        return $columns;    }}

Column documentation can be found at https://laravolt.dev/docs/v6/table/.

#### Add the following entry to your configuration file:

###### config/laravolt/auto-crud-resources/user.php

PHP

    return [    // ...existing configuration    'table' => \App\Http\Livewire\Table\UserCustomTable::class    // ...];

#### Refresh Your Browser!

Available Options
-----------------

### `label`

The text that will be displayed in the menu.

### `model`

The Eloquent Model class that will be called for each CRUD action performed.

### `restful_button`

By default, each row will have three buttons: detail, edit, and delete (restful button). To hide these buttons, change the `restful_button` option to `false`:

PHP

    'restful_button' => false,

### `schema`

Defines which fields need to be displayed. The minimum entries that must exist are `name`, `type`, and `label`:

PHP

    'schema' => [    [        'name' => 'fullname',        'type' => 'text',        'label' => 'Full Name',    ],    [        // others fields...    ]]

You can refer to the `\Laravolt\Fields\Field` interface to see the available `type` values:

PHP

    // Input Elements\Laravolt\Fields\Field::BOOLEAN;\Laravolt\Fields\Field::CHECKBOX;\Laravolt\Fields\Field::CHECKBOX_GROUP;\Laravolt\Fields\Field::COLOR;\Laravolt\Fields\Field::DATE;\Laravolt\Fields\Field::DATE_PICKER;\Laravolt\Fields\Field::DATETIME_PICKER;\Laravolt\Fields\Field::DROPDOWN;\Laravolt\Fields\Field::DROPDOWN_COLOR;\Laravolt\Fields\Field::DROPDOWN_DB;\Laravolt\Fields\Field::EMAIL;\Laravolt\Fields\Field::HIDDEN;\Laravolt\Fields\Field::NUMBER;\Laravolt\Fields\Field::MULTIROW;\Laravolt\Fields\Field::PASSWORD;\Laravolt\Fields\Field::RADIO_GROUP;\Laravolt\Fields\Field::REDACTOR;\Laravolt\Fields\Field::RUPIAH;\Laravolt\Fields\Field::TEXT;\Laravolt\Fields\Field::TEXTAREA;\Laravolt\Fields\Field::TIME;\Laravolt\Fields\Field::UPLOADER;// Other Elements\Laravolt\Fields\Field::ACTION;\Laravolt\Fields\Field::BUTTON;\Laravolt\Fields\Field::HTML;\Laravolt\Fields\Field::RESTFUL_BUTTON;\Laravolt\Fields\Field::SEGMENT;\Laravolt\Fields\Field::SUBMIT;// Relationship\Laravolt\Fields\Field::BELONGS_TO;

### Visibility

For each field, the following options can be used to determine whether the field needs to be displayed or not. _By default_ all are **true**.

PHP

    'show_on_index' => false,'show_on_detail' => true,'show_on_create' => true,'show_on_edit' => true,

### Sorting

To determine whether a field can be sorted or not, you can use the `sortable` option. For **Input Elements** type fields, by default `sortable` will be `true`. To disable _sorting_, simply set it to `false`:

PHP

    'sortable' => false,

For **Relationship** type fields, the default value is `false`. To enable sorting, we need to set it to the column name that will be used for sorting on the _related table_:

PHP

    // sort by "name" column on the "countries" table (or whatever the table name is, according to the relationship definition)'type' => Laravolt\Fields\Field::BELONGS_TO,'name' => 'country','sortable' => 'name','label' => 'Country',

By default, the `Laravolt\Fields\Field::BELONGS_TO` field will display data from its relation model in JSON format. To change this, add a public **display()** method to the relation model.

PHP

    class Country extends Model{    public function display()    {        //display data from the name column        return $this->name;    }}

When adding sorting to a Relationship field, we also need to add the `Laravolt\Suitable\AutoSort` trait to the original model, which is `\App\Models\User`:

PHP

    use Laravolt\Suitable\AutoSort;class User extends Model{    use AutoSort;    public function country()    {        return $this->belongsTo("App\\Models\\Country");    }}

The `AutoSort` trait will automatically modify the _query_ to be able to sort on related tables using the join mechanism.

### Searching

To determine whether a field can be searched or not, you can use the `searchable` option. For **Input Elements** type fields, by default `searchable` will be `true`. If you want to remove a column from the search list, simply set it to `false`:

PHP

    'searchable' => false,

For **Relationship** type fields, the default value is `false`. To enable searching on the related table, we need to set it to the appropriate column name:

PHP

    // search will also be done on the countries.name column'type' => Laravolt\Fields\Field::BELONGS_TO,'name' => 'country','searchable' => 'name','label' => 'Country',

### Form Validation

To add validation, simply add "rules":

PHP

    'rules' => ['required', 'size:10'],

#### Using Rule Objects

You can also use Laravel's Rule objects for more complex validation:

PHP

    'rules' => ['required', \Illuminate\Validation\Rule::unique('users', 'name')],

However, when using Rule objects in configuration files, be aware of potential serialization issues when running `php artisan config:cache`. Laravel's `Rule` objects are not directly serializable. To avoid this issue, you have two options:

1.  **Use string representation** (Recommended for config files):
    
    PHP
    
        'rules' => ['required', 'unique:users,name'],
    
2.  **Use Rule objects** (Available but requires proper handling):
    
    PHP
    
        'rules' => ['required', \Illuminate\Validation\Rule::unique('users', 'name')],
    
    If you choose to use Rule objects, ensure your application correctly handles the serialization process or avoid using `config:cache`.
    

For comprehensive validation examples, see the [Advanced Configuration](#advanced-configuration-considerations) section.

[All validations available in Laravel](https://laravel.com/docs/master/validation#available-validation-rules) can be applied here.

Field Types (Schema)
--------------------

### Boolean

PHP

    [    'type' => \Laravolt\Fields\Field::BOOLEAN,    'name' => 'approved',    'label' => 'Approved?',],

### Checkbox

PHP

    [    'type' => \Laravolt\Fields\Field::CHECKBOX,    'name' => 'remember',    'label' => 'Remember Me',],

### Checkbox Group

PHP

    [    'type' => \Laravolt\Fields\Field::CHECKBOX_GROUP,    'name' => 'education',    'label' => 'Last Education',    'options' => ['elementary', 'junior high', 'high school', 'undergraduate'],    'inline' => false, // false (default value) or true],

### Color

PHP

    [    'type' => \Laravolt\Fields\Field::COLOR,    'name' => 'color',    'label' => 'Color',],

### Date

PHP

    [    'type' => \Laravolt\Fields\Field::DATE,    'name' => 'date',    'label' => 'Date',],

### Date Picker

PHP

    [    'type' => \Laravolt\Fields\Field::DATE_PICKER,    'name' => 'datepicker',    'label' => 'Date Picker',],

### Datetime Picker

PHP

    [    'type' => \Laravolt\Fields\Field::DATETIME_PICKER,    'name' => 'datetimepicker',    'label' => 'Datetime Picker',],

### Dropdown

PHP

    [    'type' => \Laravolt\Fields\Field::DROPDOWN,    'name' => 'dropdown',    'label' => 'Dropdown',    'options' => [1 => 'Elementary', 2 => 'Junior High', 3 => 'High School'],],

### Dropdown Color

PHP

    [    'type' => \Laravolt\Fields\Field::DROPDOWN_COLOR,    'name' => 'dropdown_color',    'label' => 'Dropdown Color',],

### Dropdown DB

Dropdown with _option_ choices obtained from database query results.

PHP

    [    'type' => \Laravolt\Fields\Field::DROPDOWN_DB,    'name' => 'dropdown_db',    'label' => 'Dropdown DB',    'query' => 'select id, name from users limit 10'],

### Email

PHP

    [    'type' => \Laravolt\Fields\Field::EMAIL,    'name' => 'email',    'label' => 'Email',],

### Hidden

PHP

    [    'type' => \Laravolt\Fields\Field::HIDDEN,    'name' => 'user_id',],

### Number

PHP

    [    'type' => \Laravolt\Fields\Field::NUMBER,    'name' => 'number',    'label' => 'Number',],

### Multirow

//TODO

PHP

### Password

PHP

    [    'type' => \Laravolt\Fields\Field::PASSWORD,    'name' => 'password',    'label' => 'Password',],

### Radio Group

PHP

    [    'type' => \Laravolt\Fields\Field::RADIO_GROUP,    'name' => 'radio_group',    'label' => 'Radio Group',    'options' => [1 => 'Elementary', 2 => 'Junior High', 3 => 'High School'],    'inline' => false, // false (default value) or true],

### Redactor

PHP

    [    'type' => \Laravolt\Fields\Field::REDACTOR,    'name' => 'article',    'label' => 'Article',],

### Restful Button

PHP

    [    'type' => \Laravolt\Fields\Field::RESTFUL_BUTTON,    'show_on_create' => false,    'show_on_edit' => false,    'show_on_detail' => false,    'only' => ['show'], // available options: 'show', 'edit', 'destroy']

### Rupiah

PHP

    [    'type' => \Laravolt\Fields\Field::RUPIAH,    'name' => 'rupiah',    'label' => 'Rupiah',],

### Text

PHP

    [    'type' => \Laravolt\Fields\Field::TEXT,    'name' => 'text',    'label' => 'Text',],

### Textarea

PHP

    [    'type' => \Laravolt\Fields\Field::TEXTAREA,    'name' => 'textarea',    'label' => 'Textarea',],

### Time

PHP

    [    'type' => \Laravolt\Fields\Field::TIME,    'name' => 'time',    'label' => 'Time (Standard Browser)',],

### Uploader

PHP

    [    'name' => 'profile_picture',    'type' => \Laravolt\Fields\Field::UPLOADER,    'label' => 'Profile Picture',    'limit' => 1, // maximum number of files that can be uploaded    'extensions' => ['jpg', 'png'],    'fileMaxSize' => 5, // in MB],

Autofill Value
--------------

We can add parameters in the URL query string to provide default values to certain fields. For example, if we have a form schema like this:

PHP

    [    'type' => \Laravolt\Fields\Field::TEXT,    'name' => 'name',    'label' => 'Name',],

To provide an initial value to the form, we can add a query string as follows:

Bash

    http://localhost/resource/user/create?name=John

When the user create page is opened for the first time, the `name` field will automatically be filled with the value "John".

Advanced Configuration Considerations
-------------------------------------

### Serialization of Configuration Files

When running `php artisan config:cache` in Laravel, all configuration files are serialized into a single cached file. This can cause issues with certain object types that are not serializable, such as validation `Rule` objects.

#### Error Symptoms

If you're using Rule objects in your config files, you might encounter this error when running `php artisan config:cache` or `php artisan optimize`:

Bash

    LogicException: Your configuration files are not serializable.Error::("Call to undefined method Illuminate\Validation\Rules\Unique::__set_state()")

#### Handling Non-Serializable Rule Objects

To resolve the serialization issue, consider these solutions:

1.  **Use string representation for validation rules (Simplest approach):**
    
    PHP
    
        // Instead of:'rules' => ['required', \Illuminate\Validation\Rule::unique('users', 'name')],// Use:'rules' => ['required', 'unique:users,name'],
    
    This is the most straightforward solution and works in all cases.
    
2.  **Create a custom service provider that converts Rule objects to strings:**
    
    PHP
    
        <?phpnamespace App\Providers;use Illuminate\Support\ServiceProvider;use Illuminate\Validation\Rules\Unique;class AutoCrudRuleSerializationProvider extends ServiceProvider{    public function boot()    {        if (!$this->app->configurationIsCached()) {            $this->processAutoCrudResources();        }    }    protected function processAutoCrudResources(): void    {        $resources = config('laravolt.auto-crud-resources', []);        if (empty($resources)) {            return;        }        $processed = [];        foreach ($resources as $key => $resource) {            $processed[$key] = $this->processResource($resource);        }        // Update the config repository with the processed resources        config(['laravolt.auto-crud-resources' => $processed]);    }    protected function processResource(array $resource): array    {        if (!isset($resource['schema']) || !is_array($resource['schema'])) {            return $resource;        }        foreach ($resource['schema'] as $index => $field) {            if (isset($field['rules']) && is_array($field['rules'])) {                $resource['schema'][$index]['rules'] = $this->processRules($field['rules']);            }        }        return $resource;    }    protected function processRules(array $rules): array    {        return array_map(function ($rule) {            if (is_array($rule)) {                return $this->processRules($rule);            }            if ($rule instanceof Unique) {                // Convert Unique rule to string format                return $this->uniqueRuleToString($rule);            }            return $rule;        }, $rules);    }    protected function uniqueRuleToString(Unique $rule): string    {        // Extract table and column using reflection        $table = $this->extractProperty($rule, 'table', 'unknown_table');        $column = $this->extractProperty($rule, 'column', 'NULL');        return "unique:{$table},{$column}";    }    protected function extractProperty($object, $property, $default = null)    {        try {            $reflector = new \ReflectionClass($object);            $prop = $reflector->getProperty($property);            $prop->setAccessible(true);            $value = $prop->getValue($object);            return $value ?: $default;        } catch (\Exception $e) {            return $default;        }    }        config(['laravolt.auto-crud-resources' => $processed]);    }    // Additional helper methods...}
    
    Then register this provider in your `config/app.php` or `bootstrap/providers.php` file.
    

#### Best Practices Summary

For optimal experience with Auto CRUD validation rules and Laravel's config cache:

1.  **In development environments:**
    
    *   You can use Rule objects directly for better IDE support and type safety
    *   Avoid running `php artisan config:cache` or disable it with `php artisan config:clear`
2.  **In production environments:**
    
    *   Use string-based validation rules in your configuration files
    *   Or implement a rule serialization service provider as shown above
    *   Always test your `php artisan optimize` command before deploying
3.  **For rule objects with special features:** When you need features like `ignore()` for unique rules during updates, create a helper class that converts string rules back to Rule objects at runtime:
    
    PHP
    
        <?phpnamespace App\Support;use Illuminate\Support\Str;use Illuminate\Validation\Rule;class RuleHelper{    /**     * Convert rule strings back to Rule objects during runtime validation.     */    public static function resolveRules(array $rules): array    {        return array_map(function($rule) {            if (is_array($rule)) {                return self::resolveRules($rule);            }            if (!is_string($rule)) {                return $rule;            }            // Convert unique:table,column back to Rule::unique() object            if (Str::startsWith($rule, 'unique:')) {                $parts = explode(':', $rule, 2);                if (isset($parts[1])) {                    $params = explode(',', $parts[1]);                    $table = $params[0] ?? null;                    $column = $params[1] ?? null;                    if ($table) {                        return Rule::unique($table, $column);                    }                }            }            return $rule;        }, $rules);    }}
    

This approach gives you the best of both worlds: serializable configurations and the full power of Laravel's validation Rule objects when needed.## === workflow.md ===
## Workflow
========

Laravolt Workflow provides a graphical user interface (GUI) for executing BPMN diagrams, leveraging [Camunda REST API](https://docs.camunda.org/manual/latest/), enabling business processes to be quickly executed and validated.

* * *

Prerequisites
-------------

*   Successfully installed Laravolt
*   Able to login as an application Admin
*   Understanding of BPMN concepts and Camunda Engine

Installation
------------

Ensure you have installed the Laravolt Camunda package and prepared its configuration:

Bash

    composer require laravolt/camunda

Add to your `.env` file:

Env

    CAMUNDA_URL=http://localhost:8080/engine-rest#optionalCAMUNDA_TENANT_ID=CAMUNDA_USER=CAMUNDA_PASSWORD=

Add to your `config/services.php` file:

PHP

    'camunda' => [    'url' => env('CAMUNDA_URL', 'https://localhost:8080/engine-rest'),    'user' => env('CAMUNDA_USER', 'demo'),    'password' => env('CAMUNDA_PASSWORD', 'demo'),    'tenant_id' => env('CAMUNDA_TENANT_ID', ''),],

Run `php artisan laravolt:workflow:check` to ensure connection to the Camunda REST API is successful.

Import BPMN
-----------

Login to the application as Admin, select the Workflow > BPMN menu, and click the Add button.

Select a BPMN you want to import. The BPMNs displayed here are ones that have been previously deployed to the Camunda Engine.

Next, you need to define a Module to execute this BPMN.

Adding a Module
---------------

After successfully importing a BPMN, we need to define a Module to execute it. Think of creating a Module as creating a new page, but instead of manually creating Routes, Controllers, Views, or Models one by one, we simply define a configuration file.

First, add a file `config/laravolt/workflow-modules/recruitment.php`. Change the filename `recruitment.php` to match your application's business process.

###### config/laravolt/workflow-modules/recruitment.php

PHP

    <?phpreturn [    'process_definition_key' => 'proc_bl_recruitment',    'name' => 'Employee Recruitment',    'tasks' => [],];

Based on this configuration file, the Module can now be accessed at `localhost/workflow/module/recruitment/instances`.

Adding to the Menu
------------------

For easier access to the URL, we can add it to the menu. Create a file `config/laravolt/menu/app.php` with the following content:

PHP

    <?phpreturn [    'App' => [        'menu' => [            'Recruitment' => [                'route' => ['workflow::module.instances.index', 'recruitment'],                'icon'  => 'inbox'            ],        ],    ],];

Feel free to adjust the `Recruitment` label, the `recruitment` route key, and the `inbox` icon according to your application's needs.

> Available icons can be viewed at https://fontawesome.com/v5/search?s=duotone

Defining Forms
--------------

For each imported BPMN, we need to define form fields for all Start Events and User Tasks.

Open the `recruitment.php` file again, and add:

PHP

    return [    'process_definition_key' => 'proc_bl_recruitment',    'name' => 'Employee Recruitment',    'tasks' => [        'StartEvent_1' => [            'form_schema' => [                'full_name' => [                    'type' => 'text',                    'label' => 'Applicant Name',                ],            ],        ],    ],];

In the example above, `StartEvent_1` is the ID of the Start Event in the recruitment BPMN. Form definitions can be added in the `form_schema` section. `full_name` is the variable name that will be stored in the application (and sent to the Camunda Engine). Adjust according to your application's needs.

> The IDs of Start Events and User Tasks can be viewed by opening the BPMN file using the Camunda Modeler application.

After all forms for the Start Event have been defined, you can revisit the `localhost/workflow/module/recruitment/instances` page and start a new process by clicking the **\+ New** button.

Fill it out and submit. If successful, the data entered will appear on the previous page.

Continue defining forms for other User Tasks. For reference, the complete form definition for the recruitment BPMN can be viewed at https://gist.github.com/uyab/8cbd4bf94b5842646852b12ee42b853d.

In addition to `text`, there are several other field types provided by Laravolt Workflow, including:

*   `email`
*   `textarea`
*   `datepicker`
*   `checkbox`
*   `boolean`
*   `radioGroup`
*   `dropdown`
*   `uploader`
*   `redactor`

Feel free to explore! :)

If all forms have been defined, press the **Action** button to continue the process until there are no more forms to fill (the process is completed).

Form Listeners
--------------

Sometimes there's a need to send data to the Camunda API where the data doesn't come from a user's input form, such as `user_id`.

There are two Events that can be utilized for this. The `\Laravolt\Workflow\Events\ProcessInstanceStarting::class` event is used for the **Start Form** and the `\Laravolt\Workflow\Events\TaskCompleting::class` event is used for **User Task Forms**.

What we need to do is create a Listener class and register it in the configuration file.

The Listener class can be created using the command:

Bash

    php artisan make:listener AttachUserId

The generated file can be found in the `app/Listeners` folder.

For the `ProcessInstanceStarting` event:

PHP

    <?phpnamespace App\Listeners;use Laravolt\Workflow\Events\ProcessInstanceStarting;class AttachUserId{    public function handle(ProcessInstanceStarting $event)    {        $event->form->modifyVariables(            function ($variables) {                $variables['userId'] = ['value' => auth()->id()];                return $variables;            }        );    }}

For the `TaskCompleting` event:

PHP

    <?phpnamespace App\Listeners;use Laravolt\Workflow\Events\TaskCompleting;class MyListener{    public function handle(TaskCompleting $event)    {        $event->form->modifyVariables(            function ($variables) {                $variables['someVariable'] = ['value' => 'foo'];                return $variables;            }        );    }}

Then, register the Listener that has been created to the corresponding event:

###### config/laravolt/workflow-modules/recruitment.php

PHP

    return [    'process_definition_key' => 'proc_bl_recruitment',    'name' => 'Employee Recruitment',    'tasks' => [        'StartEvent_1' => [            'form_schema' => [],            'listeners' => [                \Laravolt\Workflow\Events\ProcessInstanceStarting::class => [                    \App\Listeners\AttachUserId::class,                ],            ],        ],        'act_reviewDataDiri' => [            'form_schema' => [],            'listeners' => [                \Laravolt\Workflow\Events\TaskCompleting::class => [                    \App\Listeners\MyListener::class,                ],            ],        ],    ],];

Displaying Data With Tables
---------------------------

After successfully executing the BPMN, the next step is to configure what information needs to be displayed in the table. For simple cases, we can just define `table_variables` in the Module we've created. For more complex cases, we can create our own custom Table View.

### Defining Displayed Columns

Open the `recruitment.php` file again, then add `table_variables`:

###### config/laravolt/workflow-modules/recruitment.php

PHP

    <?phpreturn [    'process_definition_key' => 'proc_bl_recruitment',    'name' => 'Employee Recruitment',    'table_variables' => ['full_name', 'job_title'],    'tasks' => [...]];

All fields we defined in `form_schema` can be used as `table_variables`. Give it a try.

### Custom Table View

For more complex needs, we can create our own Table component by adding the configuration:

PHP

        'table' => \App\Http\Livewire\Tables\MyCustomTable::class    //'table_variables' => ['full_name', 'job_title'], no longer needed

The method for creating a Table component can be learned in the [Laravolt Table documentation](https://laravolt.dev/docs/v6/table/).

Public Form
-----------

\[TODO\]

Task Assignment
---------------

\[TODO\]## === acl.md ===
## Access Control List (ACL)
=========================

Laravolt's Access Control List (ACL) provides a robust system for managing user permissions and roles, giving you fine-grained control over who can access what in your application.

* * *

Concept Overview
----------------

Before diving into technical details, it's important to understand the general concept and how ACL works.

### User

A user is anyone who has an account and can log into the application.

### Role

A role, often called a user group, is a way to categorize users with similar access needs. Grouping users by roles makes it easier to manage their permissions.

Examples of roles in real applications:

#### Hospital Information System

*   Administrator
*   Doctor
*   Nurse

#### Academic Information System

*   Professor
*   Student
*   Administrative Staff

#### Online Store

*   Store Owner
*   Cashier
*   Customer Service

A user can have one or more roles. In Laravolt, the User and Role are defined in a Many-to-Many relationship.

### Permission

A permission, also called an ability, defines what a user can do within the application. Users need specific permissions to access features.

Examples of permissions in real applications:

#### Hospital Information System

*   Can register patients
*   Can view medical records
*   Can view financial dashboard

#### Academic Information System

*   Can input course selections
*   Can view student profiles
*   Can create schedules

Laravolt defines a Many-to-Many relationship between Permissions and Roles. **Permissions are attached to Roles, not directly to Users.**

Database Structure
------------------

The ACL system in Laravolt uses the following tables:

*   `users` - Stores user information
*   `acl_roles` - Stores role definitions
*   `acl_permissions` - Stores permission definitions
*   `acl_role_permission` - Junction table for role-permission relationships
*   `acl_role_user` - Junction table for user-role relationships

Access Checking Methods
-----------------------

There are two common methods to check access rights when coding with Laravel:

1.  Checking Roles
2.  Checking Permissions

Let's compare the coding approaches for each method.

### Checking Roles

PHP

    // The "hasRole" method is a built-in Laravolt functionif (auth()->user()->hasRole(['Administrator'])) {    // Allow access to dashboard}

### Checking Permissions

PHP

    if (auth()->user()->can('see_dashboard')) {    // Allow access to dashboard}

For small applications, role-based checking is often preferred because it's easier to read and more consistent with the business process. Clients usually say, "feature A can only be accessed by admins." The first example is closer to this requirement.

However, role-based checking has a drawback: **the code is more susceptible to changes**. For example, if requirements change so that both Administrators and Hospital Directors can view the dashboard:

### Checking Roles (After Requirement Change)

PHP

    // We need to add the Hospital Director role hereif (auth()->user()->hasRole(['Administrator', 'Hospital Director'])) {    // Allow access to dashboard}

### Checking Permissions (After Requirement Change)

PHP

    // No code changes neededif (auth()->user()->can('see_dashboard')) {    // Allow access to dashboard}

You can see that no code changes are needed if we check by Permission.

Fixed Permissions, Dynamic Roles
--------------------------------

If access checking is done against Permissions, then when there are requirement changes related to access rights, you only need to change the permissions of the relevant Roles. This can be done by the system administrator through the provided admin panel.

![Edit Role Permissions](https://cdn.statically.io/gh/laravolt/storage/master/2021/10/preview-edit-role-NEpOD3.png)

Conversely, if checking is done against Roles, every time there's a condition change, the application code must also be adjusted. This is not effective. Additionally, role names might change. What happens if "Hospital Director" is changed to "Chief Hospital Director"?

> **Fixed Permissions, Dynamic Roles**
> 
> Permissions are fixed in number and name, according to the application's feature definitions. Roles are dynamic; Administrators can add or reduce them as needed. When requirements change regarding access rights, you only need to modify the role-permission mapping.

Registering Permissions
-----------------------

Since Permissions are fixed, we need to define them in one place for easy reference and documentation (single source of truth).

### 1\. Registering Enum

Laravolt's starter kit provides an [Enum class](https://github.com/BenSampo/laravel-enum) for registering Permissions: `app\Enums\Permission.php`. If this class doesn't exist, you can add it yourself.

#### app\\Enums\\Permission.php

PHP

    <?phpnamespace App\Enums;use BenSampo\Enum\Enum;final class Permission extends Enum{    const DASHBOARD_VIEW = 'dashboard.view';    const POST_VIEW = 'post.view';    const POST_DELETE = 'post.delete';}

### 2\. Synchronizing Enums and Permission Table

Because user-role-permission relationships are stored in the database, we need to synchronize to ensure the `acl_permissions` table content matches the defined enums. Run the command:

Bash

    php artisan laravolt:sync-permission

After registration, we can use these constants for checking:

PHP

    if (auth()->user()->can(\App\Enums\Permission::POST_DELETE)) {    // Do something}

Using constants is more recommended than plain strings because:

1.  It supports autocomplete
2.  It prevents typos
3.  It's easier to refactor

### 3\. Assign Permissions to Roles Through Admin Panel

After Permissions are registered in the database, the application Administrator can manage which Roles have which Permissions through the "System -> Roles" menu.

![Role Management](https://cdn.statically.io/gh/laravolt/storage/master/2021/10/image-20211006065105036-LkFi8U.png)

Since Roles are dynamic, if access rule changes occur, Administrators can make changes independently without asking Programmers to modify the code.

Wildcard Permission
-------------------

There's a wildcard Permission labeled **"\*"** which allows a Role with this Permission to access all application features. By default, this Permission is added when you run the `php artisan laravolt:admin` command.

**Make sure only the superadmin Role has this Permission.**

Implementation Guide
--------------------

### Creating Roles Programmatically

You can create roles programmatically using the Laravolt Role model:

PHP

    use Laravolt\Platform\Models\Role;// Create a new role$role = Role::create(['name' => 'Editor']);// Or find an existing role$role = Role::whereName('Editor')->first();

### Assigning Roles to Users

PHP

    // Using the attachRole method$user->attachRole($role);// Using role ID$user->attachRole($roleId);// Using role name$user->attachRole('Editor');// Attaching multiple roles$user->attachRole(['Editor', 'Reviewer']);

### Revoking Roles from Users

PHP

    // Revoke a specific role$user->detachRole($role);$user->detachRole($roleId);$user->detachRole('Editor');// Revoke multiple roles$user->detachRole(['Editor', 'Reviewer']);// Revoke all roles$user->detachAllRoles();

### Checking User Roles

PHP

    // Check if user has a role$user->hasRole('Editor'); // returns boolean// Check if user has any of the roles$user->hasAnyRole(['Editor', 'Reviewer']); // returns boolean// Check if user has all roles$user->hasAllRoles(['Editor', 'Reviewer']); // returns boolean

### Managing Permissions

PHP

    // Assign permissions to a role$role->attachPermission(\App\Enums\Permission::POST_VIEW);$role->attachPermission([\App\Enums\Permission::POST_VIEW, \App\Enums\Permission::POST_DELETE]);// Revoke permissions from a role$role->detachPermission(\App\Enums\Permission::POST_DELETE);$role->detachPermission([\App\Enums\Permission::POST_VIEW, \App\Enums\Permission::POST_DELETE]);// Revoke all permissions$role->detachAllPermissions();

### Checking Permissions

PHP

    // Using the can methodif ($user->can(\App\Enums\Permission::POST_DELETE)) {    // User can delete posts}// Using the cannot methodif ($user->cannot(\App\Enums\Permission::POST_DELETE)) {    // User cannot delete posts}

Access Control in Blade Templates
---------------------------------

You can use Laravolt's blade directives to control access in your templates:

Blade

    @can(\App\Enums\Permission::POST_DELETE)    <button class="ui button red">Delete</button>@endcan@role('Administrator')    <a href="{{ route('admin.dashboard') }}">Admin Dashboard</a>@endrole@hasrole(['Administrator', 'Manager'])    <div class="ui segment">        Management content here    </div>@endhasrole

Protecting Routes with Middleware
---------------------------------

### Route-Level Protection

PHP

    // Single roleRoute::get('/admin', function () {    // Only administrators can access})->middleware('role:Administrator');// Multiple roles (any of these roles can access)Route::get('/reports', function () {    // Administrators or Managers can access})->middleware('role:Administrator|Manager');// Permission-based protectionRoute::get('/posts/{post}/edit', function () {    // Only users with post.edit permission can access})->middleware('permission:' . \App\Enums\Permission::POST_EDIT);// Multiple permissions (all permissions required)Route::get('/posts/{post}/publish', function () {    // Need both permissions to access})->middleware('permission:' . \App\Enums\Permission::POST_EDIT . ',' . \App\Enums\Permission::POST_PUBLISH);

### Controller-Level Protection

PHP

    class PostController extends Controller{    public function __construct()    {        // Require post.view permission for all methods in this controller        $this->middleware('permission:' . \App\Enums\Permission::POST_VIEW);        // Require post.edit permission only for edit and update methods        $this->middleware('permission:' . \App\Enums\Permission::POST_EDIT, ['only' => ['edit', 'update']]);        // Require post.delete permission only for the destroy method        $this->middleware('permission:' . \App\Enums\Permission::POST_DELETE, ['only' => ['destroy']]);    }    // Controller methods...}

Best Practices
--------------

### Permission Naming Conventions

Follow a consistent naming pattern for permissions:

*   Use resource-based naming: `resource.action`
*   Example: `post.create`, `post.edit`, `post.delete`
*   Use lowercase with dots as separators

### Group Permissions Logically

Organize permissions in the Enum class by grouping them logically:

PHP

    // Post managementconst POST_VIEW = 'post.view';const POST_CREATE = 'post.create';const POST_EDIT = 'post.edit';const POST_DELETE = 'post.delete';// User managementconst USER_VIEW = 'user.view';const USER_CREATE = 'user.create';const USER_EDIT = 'user.edit';const USER_DELETE = 'user.delete';

### Use Authorization Policies

For more complex authorization logic, leverage Laravel's Authorization Policies:

PHP

    // Create a policyphp artisan make:policy PostPolicy --model=Post

In the policy, use Laravolt's permission system:

PHP

    public function update(User $user, Post $post){    // Basic permission check    if (!$user->can(\App\Enums\Permission::POST_EDIT)) {        return false;    }    // Additional logic    // For example, users can only edit their own posts    return $user->id === $post->user_id;}

Then in your controller:

PHP

    public function edit(Post $post){    $this->authorize('update', $post);    // Continue with edit...}

### Seed Default Roles and Permissions

When setting up a new application, create a seeder for default roles and permissions:

PHP

    class AclSeeder extends Seeder{    public function run()    {        // Create roles        $admin = \Laravolt\Platform\Models\Role::firstOrCreate(['name' => 'Administrator']);        $editor = \Laravolt\Platform\Models\Role::firstOrCreate(['name' => 'Editor']);        // Sync permissions from enum to database        Artisan::call('laravolt:sync-permission');        // Assign all permissions to admin        $admin->attachPermission('*');        // Assign specific permissions to editor        $editor->attachPermission([            \App\Enums\Permission::POST_VIEW,            \App\Enums\Permission::POST_CREATE,            \App\Enums\Permission::POST_EDIT        ]);    }}

Troubleshooting
---------------

### Permission Not Working

1.  Make sure the permission is properly registered in the Permission Enum class
2.  Run `php artisan laravolt:sync-permission` to sync permissions to the database
3.  Check that the permission is correctly assigned to the user's role(s)
4.  Verify that you're using the correct permission constant in your checks

### Role Not Working

1.  Ensure the role exists in the database
2.  Verify that the user is correctly assigned to the role
3.  Check for typos in role names (role checks are case-sensitive)

Migration from Other ACL Systems
--------------------------------

If you're migrating from other ACL systems like Spatie's laravel-permission, Laravolt provides a command to help with the transition:

Bash

    php artisan laravolt:import-permission

This command will guide you through the process of importing roles and permissions from other systems into Laravolt's ACL structure.## === thunderclap.md ===
## Thunderclap
===========

Thunderclap is a powerful code generator that accelerates development by automatically generating CRUD (Create, Read, Update, Delete) code based on your database schema and predefined templates.

* * *

Overview
--------

Building CRUD interfaces is a common but often repetitive task in web development. Thunderclap addresses this challenge by automating the generation of controllers, models, views, and routes based on your database structure. This approach offers several advantages:

*   **Consistency**: Maintains coding standards across your entire application
*   **Efficiency**: Reduces development time for routine CRUD operations
*   **Quality**: Eliminates simple errors that can occur during manual coding
*   **Focus**: Frees developers to concentrate on complex business logic

Thunderclap reads your database schema and generates code according to templates that you can customize to match your project's specific requirements.

Basic Usage
-----------

The simplest way to use Thunderclap is with the `laravolt:clap` Artisan command:

Bash

    php artisan laravolt:clap

This interactive command will:

1.  Ask you to select a database table
2.  Generate a complete set of CRUD files based on that table
3.  Create a new module in the `modules` directory

### Command Options

You can also specify options directly on the command line:

Bash

    php artisan laravolt:clap --table=users --template=custom --force

Option

Description

`--table`

The database table to use for code generation

`--template`

The template to use (default: "laravolt")

`--force`

Overwrite existing files

Module Registration
-------------------

After generating code, you need to register the new module in your application:

### 1\. Update Composer Autoloading

Add the modules directory to your PSR-4 autoloading configuration in `composer.json`:

JSON

    "autoload": {    "psr-4": {        "App\\": "app/",        "Modules\\": "modules"    }}

### 2\. Register Service Provider

Add the generated service provider to your `bootstrap/providers.php` file. For example, if you generated code for a table named "categories":

PHP

    <?phpreturn [    // Other service providers...    \Modules\Video\Providers\VideoServiceProvider::class,    // Application service providers...];

### 3\. Update Autoloader

Run the following command to update the Composer autoloader:

Bash

    composer dumpautoload

Customizing Templates
---------------------

Thunderclap comes with default templates designed for Laravolt admin panels, but you can create your own templates tailored to your project needs.

### 1\. Publish the Configuration

First, publish the configuration file:

Bash

    php artisan vendor:publish --provider="Laravolt\Thunderclap\ServiceProvider"

### 2\. Configure Custom Templates

Edit the `config/laravolt/thunderclap.php` file to add your custom template:

PHP

    // Template skeleton (stubs)'default' => 'custom',// name => directory path, relative with stubs directory or absolute path'templates' => [    'laravolt' => 'laravolt',    'custom' => base_path('stubs/custom'),],

### 3\. Create Template Files

Create a new directory for your templates at `stubs/custom`. The easiest way to start is by copying the default templates:

Bash

    mkdir -p stubs/customcp -r vendor/laravolt/thunderclap/stubs/laravolt/* stubs/custom/

### 4\. Modify Template Files

Edit the template files in `stubs/custom` according to your needs. These files are standard PHP files with `.stub` extensions that contain placeholders that will be replaced during code generation.

Common placeholders include:

Placeholder

Description

`{{ class }}`

The class name (e.g., "User")

`{{ namespace }}`

The namespace (e.g., "Modules\\User")

`{{ table }}`

The database table name (e.g., "users")

`{{ fields }}`

Generated form fields based on the table schema

### 5\. Generate Code with Custom Template

Generate code using your custom template:

Bash

    php artisan laravolt:clap --template=custom

Template Structure
------------------

A complete template set should include the following files (all with `.stub` extensions):

Plain Text

    stubs/custom/├── Controller.stub├── Model.stub├── Provider.stub├── Route.stub├── lang.stub├── views/│   ├── create.stub│   ├── edit.stub│   ├── index.stub│   └── show.stub└── tests/    └── Feature.stub

Advanced Template Customization
-------------------------------

### Working with Fields

Thunderclap automatically generates form fields based on the database schema, but you can customize how these fields are rendered by modifying the view templates.

### Example: Custom Form Field Template

Here's an example of how you might customize a form field in a template:

Blade

    @foreach($fields as $field)    <x-volt-field        name="{{ $field->name }}"        label="{{ $field->label }}"        required="{{ $field->required }}"        type="{{ $field->htmlType }}"    >        @if($field->htmlType === 'select')            @foreach($field->options as $value => $label)                <option value="{{ $value }}">{{ $label }}</option>            @endforeach        @endif    </x-volt-field>@endforeach

### Conditional Logic

You can include conditional logic in your templates using standard PHP syntax:

PHP

    @if($hasSoftDeletes)    use Illuminate\Database\Eloquent\SoftDeletes;@endifclass {{ class }} extends Model{    @if($hasSoftDeletes)    use SoftDeletes;    @endif    // Other model code}

### Extending Models

For models that need relationships or additional methods:

PHP

    protected $fillable = [    {{ fillable }}];// Add your relationships herepublic function categories(){    return $this->belongsToMany(Category::class);}

Best Practices
--------------

### 1\. Start with Default Templates

Begin with the default templates and make incremental changes as needed. This approach helps you understand how Thunderclap works before making major customizations.

### 2\. Modular Design

Design your templates with modularity in mind. Focus on creating reusable components that can be included across multiple views.

### 3\. Code Review

Always review the generated code before deploying to production. While Thunderclap aims to produce high-quality code, your specific business requirements may necessitate manual adjustments.

### 4\. Version Control

Keep your templates under version control to track changes and collaborate with team members.

### 5\. Balance Automation and Customization

Aim for a balance between automation and customization. It's often better to generate 80% of the code automatically and manually implement the remaining 20% with complex business logic than to create overly complex templates.

Troubleshooting
---------------

### Common Issues

#### Missing Service Provider

**Issue**: After generating code, the application throws a "Class not found" exception.

**Solution**: Ensure you've registered the service provider in `config/app.php` and run `composer dumpautoload`.

#### Template Not Found

**Issue**: The command reports that a template cannot be found.

**Solution**: Check the path in your `thunderclap.php` configuration file and make sure the template directory exists.

#### Database Connection Issues

**Issue**: Thunderclap cannot read the database schema.

**Solution**: Verify your database connection settings and ensure the table exists.

Related Documentation
---------------------

*   [CRUD Operations](/v6/auto-crud) - For information on the Auto CRUD feature that works with Thunderclap
*   [Form Components](/v6/form) - Documentation on form components that can be used in templates
*   [Table Components](/v6/table) - Learn about table components for displaying data## === react-integration.md ===
## React Integration
=================

Modern web applications often benefit from the interactive UI capabilities of React. Laravolt makes it easy to integrate React components while maintaining the benefits of Laravel's server-side architecture.

* * *

Overview
--------

React is a popular JavaScript library for building interactive user interfaces, particularly for applications that require complex state management and dynamic content updates without page refreshes. Integrating React with Laravolt allows you to:

*   Use React for specific interactive components while keeping the rest of your application in Laravel
*   Gradually introduce React into existing Laravolt projects
*   Leverage both React's frontend capabilities and Laravel's backend strengths

Installation & Setup
--------------------

Before integrating React with your Laravolt application, you need to install and configure the necessary dependencies.

### 1\. Install Required Dependencies

Begin by installing React and related dependencies:

Bash

    npm install react react-dom react-router-dom @babel/preset-react

### 2\. Configure Babel for React

Update your `.babelrc` file or create one in your project root if it doesn't exist:

JSON

    {  "presets": ["@babel/preset-env", "@babel/preset-react"]}

### 3\. Create React Entry Point

Create a new file `resources/js/react.js` to serve as the entry point for your React application:

Javascript

    import ReactDOM from 'react-dom'import React from 'react'import ReactIndex from './react/ReactIndex'ReactDOM.render(  <React.StrictMode>    <ReactIndex />  </React.StrictMode>,  document.getElementById('reactContainer'),)

### 4\. Configure Laravel Mix

Update your `webpack.mix.js` file to include React compilation:

Javascript

    const mix = require('laravel-mix')// Existing mix configurationmix.js('resources/js/app.js', 'public/js')// Add React configurationmix.js('resources/js/react.js', 'public/js').react() // This ensures React components are properly compiled

Folder Structure
----------------

Organize your React components using the following recommended structure:

Plain Text

    resources/├── js/│   ├── react/│   │   ├── components/│   │   │   ├── Dashboard.js│   │   │   ├── UserProfile.js│   │   │   └── ...│   │   ├── contexts/│   │   │   ├── AuthContext.js│   │   │   └── ...│   │   ├── hooks/│   │   │   ├── useData.js│   │   │   └── ...│   │   └── ReactIndex.js│   └── react.js

This structure separates concerns and makes your React codebase easier to maintain as it grows.

Creating React Components
-------------------------

Let's build a simple component that fetches and displays a quote of the day.

### Create a Component

Create a new file at `resources/js/react/components/QuoteOfTheDay.js`:

JSX

    import React, { useState, useEffect } from 'react'import axios from 'axios'const QuoteOfTheDay = () => {  const [quote, setQuote] = useState('')  const [author, setAuthor] = useState('')  const [isLoading, setIsLoading] = useState(true)  const [error, setError] = useState(null)  useEffect(() => {    setIsLoading(true)    axios      .get('https://quotes.rest/qod')      .then((response) => {        const quoteData = response.data.contents.quotes[0]        setQuote(quoteData.quote)        setAuthor(quoteData.author)        setIsLoading(false)      })      .catch((err) => {        setError('Failed to load quote')        setIsLoading(false)        console.error(err)      })  }, [])  if (isLoading) {    return <div className="ui segment loading">Loading...</div>  }  if (error) {    return <div className="ui negative message">{error}</div>  }  return (    <div className="ui segment">      <div className="ui large header">Quote of the Day</div>      <blockquote>        <p>{quote}</p>        <footer>          — <cite>{author}</cite>        </footer>      </blockquote>    </div>  )}export default QuoteOfTheDay

### Set Up Routing

Create `resources/js/react/ReactIndex.js` to handle React-side routing:

JSX

    import React from 'react'import { BrowserRouter as Router, Route, Routes } from 'react-router-dom'import QuoteOfTheDay from './components/QuoteOfTheDay'// Import other components// import Dashboard from './components/Dashboard';// import UserProfile from './components/UserProfile';const ReactIndex = () => {  return (    <Router>      <Routes>        <Route path="/integration/react" element={<QuoteOfTheDay />} />        {/* Add more routes as needed */}        {/* <Route path="/dashboard/react" element={<Dashboard />} /> */}        {/* <Route path="/profile/react" element={<UserProfile />} /> */}      </Routes>    </Router>  )}export default ReactIndex

Integrating with Laravolt Views
-------------------------------

Create a Blade view to render your React component:

Blade

    <x-volt-app title="React Integration Example">    <div id="reactContainer"></div>    @push('script')        <script src="{{ asset('js/react.js') }}" defer></script>    @endpush</x-volt-app>

Laravel Routes
--------------

Define a route in your `routes/web.php` file:

PHP

    Route::get('/integration/react', function () {    return view('integration.react');})->name('integration.react');

Make sure to create the view at `resources/views/integration/react.blade.php`.

Compiling Assets
----------------

Compile your assets using Laravel Mix:

Bash

    # For developmentnpm run dev# For productionnpm run production

Advanced Integration Techniques
-------------------------------

### API Endpoints for React

Create dedicated API endpoints for your React components:

PHP

    // routes/api.phpRoute::get('/quotes', [QuoteController::class, 'index']);Route::get('/quotes/{id}', [QuoteController::class, 'show']);

Then consume these endpoints in your React components:

JSX

    // In your React componentuseEffect(() => {  axios.get('/api/quotes').then((response) => {    setQuotes(response.data)  })}, [])

### Sharing Authentication

To share authentication between Laravel and React:

1.  Create an endpoint to check authentication status:

PHP

    // routes/api.phpRoute::middleware('auth:sanctum')->get('/user', function (Request $request) {    return $request->user();});

2.  Configure Sanctum in your React setup:

JSX

    // resources/js/react.jsimport axios from 'axios'// Set CSRF token for all requestsaxios.defaults.headers.common['X-CSRF-TOKEN'] = document  .querySelector('meta[name="csrf-token"]')  .getAttribute('content')axios.defaults.withCredentials = true

### Passing Data from Laravel to React

You can pass initial data from Laravel to React using a global window object:

Blade

    <x-volt-app title="React Integration Example">    <div id="reactContainer"></div>    <script>        window.laravoltData = {            user: @json(auth()->user()),            permissions: @json($permissions),            // Other data...        };    </script>    @push('script')        <script src="{{ asset('js/react.js') }}" defer></script>    @endpush</x-volt-app>

Then access this data in your React components:

JSX

    const { user, permissions } = window.laravoltData || {}

Best Practices
--------------

### 1\. Component Granularity

Break down your UI into small, reusable React components rather than creating large monolithic components.

### 2\. State Management

For simple applications, React's built-in state and context API are sufficient. For complex applications, consider:

*   Redux for global state management
*   React Query for data fetching and caching

### 3\. Error Boundaries

Implement error boundaries to prevent a single component's failure from breaking your entire application:

JSX

    class ErrorBoundary extends React.Component {  constructor(props) {    super(props)    this.state = { hasError: false }  }  static getDerivedStateFromError(error) {    return { hasError: true }  }  render() {    if (this.state.hasError) {      return <h1>Something went wrong.</h1>    }    return this.props.children  }}

Troubleshooting
---------------

### React Components Not Rendering

**Issue**: The React container appears empty with no errors in the browser console.

**Solutions**:

*   Ensure your React container ID matches between the Blade view and JS code
*   Check browser console for JavaScript errors
*   Verify the React script is loaded after the container element

### Routing Issues

**Issue**: React Router doesn't recognize routes or shows 404 errors.

**Solutions**:

*   Make sure Laravel routes don't conflict with React routes
*   Consider using a prefix for all React routes (e.g., `/react/*`)
*   Use HashRouter instead of BrowserRouter if you're experiencing issues with direct URL access

### API Communication Problems

**Issue**: React components can't fetch data from Laravel API endpoints.

**Solutions**:

*   Check for CORS issues if API is on a different domain
*   Verify CSRF token is properly included in requests
*   Confirm authentication is properly set up (if endpoints require authentication)

Related Documentation
---------------------

*   [Laravel Mix Configuration](/v6/frontend-assets)
*   [API Development](/v6/api-development)
*   [Authentication Guide](/v6/authentication)## === news-portal-tutorial.md ===
## News Portal Tutorial
====================

This tutorial guides you through building a complete news portal application similar to popular news sites but with a simplified architecture. You'll implement features such as content management, user roles, comments, and analytics.

* * *

Project Overview
----------------

In this tutorial, we'll build a news portal application with both an admin panel and a public-facing website. The project will use Laravolt's built-in features to accelerate development while still providing a comprehensive learning experience.

Application Specifications
--------------------------

### Actors (User Roles)

The application will involve four distinct user roles:

1.  **Admin** - Manages the platform and has access to all features
2.  **Writer** - Creates and manages news content
3.  **Member** - Registered users who can interact with content
4.  **Guest** - Anonymous visitors with limited permissions

### User Stories

#### Admin Capabilities

*   Moderate comments (approve, reject, delete)
*   Manage member and writer accounts
*   Access dashboard with application statistics and summaries
*   (Advanced) Export news and comments to Excel
*   (Advanced) Configure website settings like name, logo, and analytics
*   (Advanced) Switch between multiple themes

#### Writer Capabilities

*   Create, read, update, and delete news articles
*   Access a personal dashboard with content statistics
*   (Advanced) Receive email notifications for comments on their articles

#### Member Capabilities

*   Edit personal profile information
*   Add, edit, and delete their own comments
*   Read news articles and browse content

#### Guest Capabilities

*   Browse and read news articles
*   Search for articles by keywords
*   Filter articles by topic
*   View comments
*   Register for a member account with email verification
*   Authenticate (login/logout)
*   Recover forgotten passwords

Technical Concepts
------------------

### Data Models

The application will use four primary models:

1.  **User** - Stores account information for all user types
2.  **Post** - Represents news articles
3.  **Topic** - Categorizes news articles
4.  **Comment** - Stores user comments on articles

### Relationships

The application will implement these relationships:

*   Member is-a User
*   Writer is-a Member
*   Writer has many Posts
*   Member has many Comments
*   Post belongs to Topic
*   Post belongs to Writer
*   Comment belongs to Member

### Technical Requirements

*   Admin panel built with Laravolt
*   Public-facing website built with TailwindCSS
*   CRUD operations for Post and Topic using AutoCRUD
*   Dashboard charts created with Laravolt Chart

Development Roadmap
-------------------

We'll approach this project in progressive levels, each designed to be demonstrated in a 7-minute YouTube screencast:

### Level 1: Project Setup

The first screencast covers setting up the initial project:

1.  Create a new Laravel project
2.  Install and configure Laravolt
3.  Set up the development environment (database, config)
4.  Overview of the project structure

### Level 2: Data Structure

This screencast focuses on building the data foundation:

1.  Create database migrations with proper relationships
2.  Implement models with appropriate traits (HasUlids, SoftDeletes)
3.  Define model relationships
4.  Run migrations and verify database structure

### Level 3: Authentication & Authorization

This screencast covers user management:

1.  Configure authentication using Laravolt
2.  Set up the ACL system with roles (Admin, Writer, Member)
3.  Create permission enums for access control
4.  Implement policies for Post and Comment models
5.  Create seeders for roles and permissions

### Level 4: Admin Panel - Topic Management

This screencast demonstrates building admin functionality:

1.  Implement AutoCRUD for topic management
2.  Create topic listing with sorting and filtering
3.  Build topic creation and edit forms
4.  Add validation rules for topic data
5.  Implement topic deletion with confirmation

### Level 5: Admin Panel - Post Management

This screencast continues admin functionality:

1.  Build post management with rich text editor
2.  Create post listing with topic filters
3.  Implement featured image uploads
4.  Add post publishing workflow
5.  Set up post status management

### Level 6: Admin Panel - Dashboard & Comments

This screencast completes the admin features:

1.  Create admin dashboard with statistics
2.  Build comment moderation system
3.  Implement user management interface
4.  Add simple analytics charts
5.  Create activity logs

### Level 7: Public Website - Frontend

This screencast starts building the public site:

1.  Set up TailwindCSS for the public site
2.  Create responsive layouts
3.  Build homepage with featured posts
4.  Implement topic browsing pages
5.  Create article detail pages

### Level 8: Public Website - Interactive Features

This screencast adds interactivity to the public site:

1.  Implement comment submission system
2.  Create user registration and profile pages
3.  Build search functionality
4.  Add topic filtering
5.  Implement pagination

### Level 9: Testing & Quality Assurance

The final screencast focuses on ensuring quality:

1.  Configure PHPStan for code quality
2.  Create integration tests for core features
3.  Write unit tests for critical components
4.  Set up CI/CD pipeline configurations
5.  Add performance optimizations## === authorized-menu.md ===
## Creating Authorized Menu
========================

Implementing authorized menus in your Laravolt application ensures that users can only see and access menu items they have permission for. This creates a cleaner user interface and enhances your application's security.

* * *

Overview
--------

Menu authorization in Laravolt involves three key components:

*   Defining permissions
*   Connecting menus to permissions
*   Implementing access control checks in your code

By following this approach, you can create a dynamic permission system where administrators can manage access control without requiring code changes.

Basic Implementation
--------------------

### 1\. Defining Permissions

First, create an enum class to store your application's permissions:

PHP

    <?phpnamespace App\Enums;use BenSampo\Enum\Enum;final class Permission extends Enum{    const DASHBOARD_VIEW = 'dashboard.view';    // Add other permissions as needed}

After defining the permissions, synchronize them with the database:

Bash

    php artisan laravolt:sync-permission

This command registers all defined permissions in your database, making them available for assignment to roles.

### 2\. Connecting Menus and Permissions

Edit your menu configuration to specify required permissions:

PHP

    // config/laravolt/menu/app.phpreturn [    'App' => [        'menu' => [            'Dashboard' => [                'route' => ['dashboard'],                'active' => 'dashboard/*',                'icon'  => 'chart-bar',                'permissions' => [\App\Enums\Permission::DASHBOARD_VIEW],            ],        ],    ],];

This configuration will hide the Dashboard menu from users who don't have the `dashboard.view` permission.

### 3\. Implementing Access Control in Code

While permission-based menu visibility prevents users from seeing unauthorized menu items, you must also implement access control checks in your code to prevent direct URL access.

#### Route-level Authorization:

PHP

    // routes/web.phpRoute::get('dashboard', function () {    // show dashboard})->can(\App\Enums\Permission::DASHBOARD_VIEW);

#### Controller-level Authorization:

PHP

    public function index(){    $this->authorize(\App\Enums\Permission::DASHBOARD_VIEW);    // if authorized, show dashboard    return view('dashboard');}

Role Management
---------------

After defining permissions, administrators can assign them to roles through the administrative interface:

1.  Navigate to "System -> Roles" in the Laravolt admin panel
2.  Select a role you want to modify
3.  Check the permissions that should be granted to this role
4.  Save the changes

![Role Management Interface](https://cdn.statically.io/gh/laravolt/storage/master/2021/10/image-20211006065105036-LkFi8U.png)

Best Practices
--------------

1.  **Use Descriptive Permission Names**: Create permission names that clearly describe the action and resource, like `users.create` or `reports.view`.
    
2.  **Group Related Permissions**: Organize permissions by feature or module for easier management.
    
3.  **Implement Defense in Depth**: Don't rely solely on menu visibility for security. Always implement proper authorization checks in controllers and routes.
    
4.  **Audit Access Regularly**: Periodically review role permissions to ensure they align with current business requirements.
    

Troubleshooting
---------------

### Common Issues

*   **Permissions Not Showing Up**: Make sure you've run `php artisan laravolt:sync-permission` after defining new permissions.
    
*   **Menu Still Visible Despite Permissions**: Check that the permission name in your config matches exactly with what's defined in your Enum class.
    
*   **Authorization Always Fails**: Verify that you've assigned the permission to the user's role and that the user is properly authenticated.
    

Related Features
----------------

*   [ACL System](/v6/acl) - Learn more about Laravolt's Access Control List system
*   [User Management](/v6/users) - Managing users in your application
*   [Role Management](/v6/roles) - Working with user roles## === code-quality.md ===
## Code Quality
============

This guide outlines the standard tools and practices for maintaining high-quality code in Laravolt projects.

* * *

Introduction
------------

What if bugs could be detected without having to run the program? What if bugs could be detected automatically, without requiring manual code review?

The tools described in this document help catch issues early and maintain consistent code quality across projects. While human code reviewers have limited energy and capabilities, automated tools provide consistent, objective analysis based on predefined rules.

This allows code reviewers to focus on more important matters like:

1.  Naming
2.  Algorithms
3.  Class architecture
4.  And other aspects that require human wisdom

Code Style: Pint
----------------

### Purpose

Ensure consistent code writing style across programmers even when using different IDEs/editors.

### Tools

[Laravel Pint](https://github.com/laravel/pint) - An opinionated PHP code style fixer for minimalists.

### Installation

Bash

    composer require laravel/pint --dev

### Usage

> 🌟 Run the following commands from your application folder.

To automatically fix code style issues:

Bash

    vendor/bin/pint

To check for issues without fixing them, add the `--test` option:

Bash

    vendor/bin/pint --test

If the command is too long to remember, add a shortcut/alias to composer.json:

JSON

    "scripts": {    "pint": [        "vendor/bin/pint"    ]}

Then you can simply call the alias defined above:

Bash

    composer pint

### Custom Configuration

Create a `pint.json` file in your project root:

JSON

    {  "preset": "psr12",  "rules": {    "simplified_null_return": true,    "braces": false,    "new_with_braces": { "anonymous_class": false, "named_class": false }  }}

Static Analysis
---------------

### Purpose

Find bugs before bugs find us.

### Tools

*   [PHPStan](https://phpstan.org/)
*   [Larastan](https://github.com/larastan/larastan) - PHPStan extension for Laravel

### Installation

Bash

    composer require larastan/larastan --devcomposer require spaze/phpstan-disallowed-calls --dev

### Configuration

Create a `phpstan.neon` file in your project root:

YAML

    includes:  - ./vendor/larastan/larastan/extension.neon  - ./vendor/spaze/phpstan-disallowed-calls/extension.neonparameters:  paths:    - app    - config  # The level 9 is the highest level  level: 8  disallowedFunctionCalls:    - function: 'env()'      message: 'use config() instead'      allowIn:        - config/*.php

### Usage

Bash

    vendor/bin/phpstan analyse

Cognitive Complexity
--------------------

### Purpose

Ensure code is readable and maintainable over the long term.

### Tools

[SonarLint](https://www.sonarlint.org/) - IDE extension that helps you detect and fix quality issues as you write code.

### Installation

*   For IntelliJ IDEA: Install the SonarLint plugin through the marketplace
*   For VS Code: Install the SonarLint extension from the VS Code marketplace
*   For other IDEs: Check the SonarLint website for available integrations

GrumPHP
-------

### Purpose

Running all the above tools every time we make code changes can be time-consuming and easy to forget. Therefore, Laravolt comes equipped with GrumPHP, which automatically performs checks whenever we commit. If any check fails, the commit cannot proceed, and we must fix the code first.

### Installation

Bash

    composer require phpro/grumphp --dev

### Configuration

Create a `grumphp.yml` file in your project root:

YAML

    grumphp:  tasks:    phpstan:      configuration: phpstan.neon      use_grumphp_paths: false

### Usage

#### Manual Check

Bash

    vendor/bin/grumphp run

#### Automatic Integration with Git

Bash

    vendor/bin/grumphp git:init

After running the above code, GrumPHP will automatically run before each commit.

Best Practices
--------------

### Follow Laravel Conventions

Adhere to the Laravel way of doing things whenever possible. The framework provides many conventions and helpers that maintain code quality and readability.

### Write Tests

Implement automated tests for critical functionality. Laravel provides excellent testing tools that are easy to use.

Bash

    php artisan make:test FeatureTest

### Document Complex Logic

Add comments for complex code sections to help other developers (and your future self) understand the reasoning behind implementation decisions.

### Keep Functions Small and Focused

Each function should have a single responsibility. If a function is growing too large or handling multiple tasks, consider breaking it down into smaller, more manageable parts.

### Use Type Declarations

PHP 7.4+ and Laravel 8+ support type declarations for properties, parameters, and return values, which can help catch type-related bugs early.

PHP

    public function calculateTotal(int $quantity, float $price): float{    return $quantity * $price;}

### Regularly Update Dependencies

Keep your dependencies up-to-date with security patches and new features, but be cautious with major version updates.

Bash

    composer update

### Review Code Changes

Even with all these automated tools, human code review remains essential. Always have another developer review your code before merging it into the main branch.