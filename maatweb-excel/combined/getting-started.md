## === contributing.md ===

[#](#contributing) Contributing
===============================

*   [Important Links](#important-links)
*   [Etiquette](#etiquette)
*   [Viability](#viability)
*   [How to submit changes?](#how-to-submit-changes)
*   [How to report a bug?](#how-to-report-a-bug)
*   [PR Requirements](#pr-requirements)

Please read and understand the contribution guide before creating an issue or pull request.

[#](#important-links) Important Links
-------------------------------------

*   [Docs (opens new window)](https://docs.laravel-excel.com/)
*   [Issue tracker (opens new window)](https://github.com/SpartnerNL/Laravel-Excel/issues)
*   [Support](/3.1/getting-started/support.html)

[#](#etiquette) Etiquette
-------------------------

This project is an open source project, and as such, the maintainers use their free time to build and maintain it. The code is freely available and can be used, forked and modified.

Please be considerate towards maintainers when raising issues or presenting pull requests.

It's the duty of the maintainer to ensure that all submissions to the project are of sufficient quality to benefit the project. Many developers have different skill sets, strengths, and weaknesses. Respect the maintainer's decision, and do not be upset or abusive if your submission is not used.

[#](#viability) Viability
-------------------------

When requesting or submitting new features, first consider whether it might be useful to others. Open source projects are used by many developers, who may have entirely different needs to your own. Think about whether or not your feature is likely to be used by other users of the project.

[#](#how-to-submit-changes) How to submit changes?
--------------------------------------------------

*   Check the codebase to ensure that your feature doesn't already exist.
*   Check the pull requests to ensure that another person hasn't already submitted the feature or fix.
*   Use the [pull request template (opens new window)](https://github.com/SpartnerNL/Laravel-Excel/blob/3.1/.github/PULL_REQUEST_TEMPLATE.md).

[#](#how-to-report-a-bug) How to report a bug?
----------------------------------------------

*   Attempt to replicate the problem, to ensure that it wasn't a coincidental incident.
*   Check to make sure your bug report isn't already present within the project.
*   Check the pull requests tab to ensure that the bug doesn't have a fix in progress.
*   Check the pull requests tab to ensure that the feature isn't already in progress.
*   Use the [issue template (opens new window)](https://github.com/SpartnerNL/Laravel-Excel/blob/3.1/.github/ISSUE_TEMPLATE.md).

[#](#pr-requirements) PR Requirements
-------------------------------------

*   The PR **must** apply to [PSR-2 Coding Standard (opens new window)](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md). StyleCI help you detect code style issues.
*   The PR **must** be as clean as possible. Try to remove all inline TODOs and unneeded comments. They are noise and distraction for the reviewer. Use Github's (inline) comment system to start a discussion about a change.
*   The existing tests **must** not fail after your changes. This would indicate that existing functionality is broken and should be addressed before a review is started. You can run the test by running `vendor/bin/phpunit`
*   The changes **must** be backed-up with tests.
*   The PR **must** only have one feature. Split up multiple features in multiple PRs, so they can be individually reviewed and merged.
*   The PR **must** be accompanied by a PR to the docs in case of new features. Documentation is located in the [https://github.com/SpartnerNL/laravel-excel-docs (opens new window)](https://github.com/SpartnerNL/laravel-excel-docs) repository.
*   The PR should contain meaningful commit messages.

## === index.md ===

[#](#introduction) Introduction
===============================

🚀 Laravel Excel is intended at being Laravel-flavoured PhpSpreadsheet: a simple, but elegant wrapper around PhpSpreadsheet with the goal of simplifying exports and imports.

🔥 [PhpSpreadsheet (opens new window)](https://phpspreadsheet.readthedocs.io/) is a library written in pure PHP and providing a set of classes that allow you to read from and to write to different spreadsheet file formats, like Excel and LibreOffice Calc.

[#](#laravel-excel-features) Laravel Excel Features
---------------------------------------------------

*   Easily export collections to Excel.
*   Export queries with automatic chunking for better performance.
*   Queue exports for better performance.
*   Easily export Blade views to Excel.
*   Easily import to collections.
*   Read the Excel file in chunks.
*   Handle the import inserts in batches.

## === installation.md ===

[#](#installation) Installation
===============================

*   [Requirements](#requirements)
*   [Installation](#installation)

[#](#requirements) Requirements
-------------------------------

*   PHP: `^7.2\|^8.0`
*   Laravel: `^5.8`
*   PhpSpreadsheet: `^1.21`
*   PHP extension `php_zip` enabled
*   PHP extension `php_xml` enabled
*   PHP extension `php_gd2` enabled
*   PHP extension `php_iconv` enabled
*   PHP extension `php_simplexml` enabled
*   PHP extension `php_xmlreader` enabled
*   PHP extension `php_zlib` enabled

[#](#installation-2) Installation
---------------------------------

Require this package in the `composer.json` of your Laravel project. This will download the package and _PhpSpreadsheet_.

    composer require "maatwebsite/excel:^3.1"
    

1  

If installing your receive the following error

      Your requirements could not be resolved to an installable set of packages.
    
      Problem 1
        - Root composer.json requires maatwebsite/excel 3.1 -> satisfiable by maatwebsite/excel[3.1.0].
        - maatwebsite/excel 3.1.0 requires php ^7.0 -> your php version (8.2.8) does not satisfy that requirement.
    

1  
2  
3  
4  
5  

You can try simply to install without the caret

    composer require maatwebsite/excel
    

1  

If you don't get the latest version or run into more composer errors, please make sure you have installed all required PHP extensions like zip, gd, etc.

The `Maatwebsite\Excel\ExcelServiceProvider` is **auto-discovered** and registered by default.

If you want to register it yourself, add the ServiceProvider in `config/app.php`:

    'providers' => [
        /*
         * Package Service Providers...
         */
        Maatwebsite\Excel\ExcelServiceProvider::class,
    ]
    

1  
2  
3  
4  
5  
6  

The `Excel` facade is also **auto-discovered**.

If you want to add it manually, add the Facade in `config/app.php`:

    'aliases' => [
        ...
        'Excel' => Maatwebsite\Excel\Facades\Excel::class,
    ]
    

1  
2  
3  
4  

To publish the config, run the vendor publish command:

    php artisan vendor:publish --provider="Maatwebsite\Excel\ExcelServiceProvider" --tag=config
    

1  

This will create a new config file named `config/excel.php`.

## === license.md ===

[#](#license) License
=====================

*   [MIT](#mit)
*   [Postcardware](#postcardware)
*   [Created by Spartner (formerly Maatwebsite)](#created-by-spartner-formerly-maatwebsite)
*   [Support](#support)

[#](#mit) MIT
-------------

Our software is open source and licensed under the [MIT license (opens new window)](https://choosealicense.com/licenses/mit/). You are free to use the software as you like. The code can be forked and modified, but the original copyright author should always be included!

[#](#postcardware) Postcardware
-------------------------------

According to the [postcardware (opens new window)](https://en.wikipedia.org/wiki/Postcardware) concept, if you use the software for your project(s) we would appreciate to receive a postcard of your hometown. Please send it to:

**Spartner**  
Markt 2  
6231 LS Meerssen  
The Netherlands

[#](#created-by-spartner-formerly-maatwebsite) Created by Spartner (formerly Maatwebsite)
-----------------------------------------------------------------------------------------

We are a strategic development partner, creating web-based custom built software from Laravel. In need of a digital solution for your challenge? Give us a call.

[https://spartner.software (opens new window)](https://spartner.software)  
[info@spartner.nl](mailto:info@spartner.nl)  
+31 (0) 10 - 7449312

[#](#support) Support
---------------------

Support

We hold no liability and will provide support on a best effort basis. For more information about support please see [support (opens new window)](https://docs.laravel-excel.com/3.1/getting-started/support.html).

Commercial Support

🚀 If you use the software commercially and need support urgently, we can offer this on a commercial basis. Please contact [info@spartner.nl](mailto:info@spartner.nl) or phone +31 (0)10 744 9312.

## === support.md ===

[#](#support) Support
=====================

*   [Supported Versions](#supported-versions)
*   [Requesting support](#requesting-support)

Our software is free and open source, meaning that the use of our software is optional. We hold no liability and there is no obligation to support. We will provide support on a best effort basis.

Commercial Support

If you use the software commercially and need elaborate support or need it urgently, we can offer this on a commercial basis. Please contact [info@spartner.nl](mailto:info@spartner.nl) or via phone +31 (0)10 744 9312.

[#](#supported-versions) Supported Versions
-------------------------------------------

Versions will be supported for a limited amount of time.

Version

Laravel Version

Php Version

Support

2.1

<=5.6

<=7.0

Unsupported since 15-5-2018

3.0

^5.5

^7.0

Unsupported since 31-12-2018

3.1

^5.8|^6.0|^7.0|^8.0|^9.0|^10.0

^7.2|^8.0

New features

PHP version support

Support for PHP versions will only be maintained for a period of six months beyond the end-of-life of that PHP version.

[#](#requesting-support) Requesting support
-------------------------------------------

Before you request support, please check the following:

*   Attempt to replicate the problem, to ensure that it wasn't a coincidental incident.
*   Check to make sure your support request isn't already present within the project.
*   Check the pull requests tab to ensure that the bug doesn't have a fix in progress.
*   Use one of the [issue templates (opens new window)](https://github.com/SpartnerSoftware/Laravel-Excel/tree/3.1/.github/ISSUE_TEMPLATE).

Filling out the template is required. Issues that do not include enough information might not be picked up. Please write in English (or Dutch).

Please prefix your issue with one of the following: \[BUG\] \[PROPOSAL\] \[QUESTION\].

And please be considerate towards maintainers when raising issues.

## === upgrade.md ===

[#](#upgrade-guide) Upgrade Guide
=================================

*   [Upgrading to 3.1 from 3.0](#upgrading-to-3-1-from-3-0)
*   [Upgrading to 3.\* from 2.1](#upgrading-to-3-from-2-1)

[#](#upgrading-to-3-1-from-3-0) Upgrading to 3.1 from 3.0
---------------------------------------------------------

Version 3.1 is backwards compatible with 3.0. Only features were added in this release.

**Additions**

*   Imports feature.
*   ChunkReading
*   BatchInserts
*   Queued imports
*   ToArray concern for Exports.
*   Custom value binders for Imports and Exports.

**Removals**

*   `Excel::filter('chunk')` method is removed, chunk filter is automatically added when using chunk reading.

[#](#upgrading-to-3-from-2-1) Upgrading to 3.\* from 2.1
--------------------------------------------------------

Version 3.\* is not backwards compatible with 2.\*. It's not possible to provide a step-by-step migration guide as it's a complete paradigm shift.

**New dependencies**

3.\* introduces some new dependencies.

*   Requires PHP 7.0 or higher.
*   Requires Laravel 5.5 (or higher).
*   Requires PhpSpreadsheet instead of PHPExcel.

**Deprecations**

ALL Laravel Excel 2.\* methods are deprecated and will not be able to use in 3.0 .

*   `Excel::load()` is removed and replaced by `Excel::import($yourImport)`
*   `Excel::create()` is removed and replaced by `Excel::download/Excel::store($yourExport)`
*   `Excel::create()->string('xlsx')` is removed an replaced by `Excel::raw($yourExport, Excel::XLSX)`
*   3.0 provides no convenience methods for styling, you are encouraged to use PhpSpreadsheets native methods.

You can find an example upgrade for an export here: [https://github.com/SpartnerNL/Laravel-Excel/issues/1799 (opens new window)](https://github.com/SpartnerNL/Laravel-Excel/issues/1799)