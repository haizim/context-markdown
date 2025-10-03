Introduction

Starter Kit
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
*   [Frontend Assets](/v6/frontend-assets) - Managing CSS and JavaScript resources