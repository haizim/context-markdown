# Build Tools

Using Gulp with Semantic UI

## Overview

#### 30 Second Explanation
[Download Semantic UI](/introduction/getting-started.html) navigate to the install folder then run a [gulp command](#gulp-commands).

To build all files:
```bash
gulp build
```

To watch for changes
```bash
gulp watch
```

#### Why Build Tools?
Semantic UI uses Gulp for several reasons:

*   Process LESS files with [theming variables](/usage/theming.html)
*   Add vendor prefixes for [supported browsers](https://github.com/Semantic-Org/Semantic-UI/blob/master/tasks/config/project/tasks.js#L96) with [autoprefixer](https://github.com/postcss/autoprefixer)
*   Watch file changes and rebuild the necessary files when adjusting themes
*   Automatically process asset paths, so that minified and concatenated releases can exist in different directories
*   Allow custom builds with only the required components for your site
*   Allow advanced usage like Right-To-Left (RTL) languages using [RTLCSS](https://github.com/MohammadYounes/rtlcss)

### Folder Structure
A Semantic UI project includes the following folder structure.

*   src
    *   [site](/usage/theming.html#site-theme)
        *   Your site's theme
    *   themes
        *   [default](/usage/theming.html#default-theme)
            *   Default theme
        *   [packaged-theme](/usage/theming.html#packaged-theme)
            *   Additional themes
    *   [theme.config](#themeconfig)
        *   Config file for setting packaged themes
*   dist
    *   components
        *   Individual component CSS and JS
    *   semantic.css
        *   concatenated release
    *   semantic.js
        *   concatenated release
*   [semantic.json](#semanticjson)
    *   Contains build settings for gulp

#### Gulp Commands
Below is a list of all available gulp commands
```html
<table class="ui definition table">
  <thead>
    <th>Command</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>install</td>
      <td>Asks install questions to setup semantic.json</td>
    </tr>
    <tr>
      <td>watch (default)</td>
      <td>Watches for changes in source files, and builds file on change</td>
    </tr>
    <tr>
      <td>build</td>
      <td>Build all files</td>
    </tr>
    <tr>
      <td>clean</td>
      <td>Cleans `dist/` folder</td>
    </tr>
    <tr>
      <td>version</td>
      <td>Outputs current version</td>
    </tr>
    <tr>
      <td>build-javascript</td>
      <td>Build JS files</td>
    </tr>
    <tr>
      <td>build-css</td>
      <td>Build CSS files</td>
    </tr>
    <tr>
      <td>build-assets</td>
      <td>Build assets files</td>
    </tr>
    <tr>
      <td>serve-docs</td>
      <td>Serves files to local docs instance</td>
    </tr>
    <tr>
      <td>build-docs</td>
      <td>Builds files to docs folder</td>
    </tr>
  </tbody>
</table>
```

## Configuration Files

#### semantic.json
Build tool settings are stored in a special file called `semantic.json` It can be included in any folder that is in a parent folder of the semantic install folder.

If you used the npm or meteor, a `semantic.json` file is automatically generated for you in the root of your project. If you used a different package manager you can run `gulp install` to run the interactive installer.
```
{
  // base path added to all other paths specified in "paths"
  "base": "",

  // current version of Semantic UI
  "version": "<%= @getVersion() %>",

  "paths": {

    "source": {

      // source theme.config
      "config"      : "src/theme.config",

      // source definition folder
      "definitions" : "src/definitions/",

      // source site theme
      "site"        : "src/site/",

      // source themes folder
      "themes"      : "src/themes/"
    },

    "output": {
      // packaged source (both compressed/uncompressed)
      "packaged"     : "dist/",

      // uncompressed source
      "uncompressed" : "dist/components/",

      // compressed source
      "compressed"   : "dist/components/",

      // output directory for theme assets
      "themes"       : "dist/themes/"
    },

    // directory for gulp clean task
    "clean"        : "dist/"
  },

  // when set to an integer permission, will set dist files with this file permission
  "permission" : false,

  // whether gulp watch/build should run RTLCSS
  "rtl": false,

  // will only include components with these names
  "components": [
    "reset",
    "site",
    "button",
    "container",
    "divider",
    "flag",
    "header",
    "icon",
    "image",
    "input",
    "label",
    "list",
    "loader",
    "rail",
    "reveal",
    "segment",
    "step",
    "breadcrumb",
    "form",
    "grid",
    "menu",
    "message",
    "table",
    "ad",
    "card",
    "comment",
    "feed",
    "item",
    "statistic",
    "accordion",
    "checkbox",
    "dimmer",
    "dropdown",
    "embed",
    "modal",
    "nag",
    "popup",
    "progress",
    "rating",
    "search",
    "shape",
    "sidebar",
    "sticky",
    "tab",
    "transition",
    "api",        
    "state",
    "visibility"
  ],
  // whether to include special project maintainer tasks
  "admin": false
}
```

#### theme.config
LESS uses a special configuration file `theme.config` which lets you specify what theme each component should use. If you have not generated this file yet, you will receive an error message when running build tools

You can learn more about `theme.config` by checking out the [theming guide](/usage/theming.html#using-packaged-themes)

#### Importing Gulp Tasks
See our [recipes section](/introduction/advanced-usage.html) for examples on how to import individual gulp tasks into your custom Gulpfile.

#### Auto-Install & Continuous Integration
We've added a new setting to `semantic.json` in 2.2 to help make working with a CLI, or other automated deployments more streamlined.

Specifying `autoInstall: true` in an environments `semantic.json` configuration will prevent any user prompting when running `npm install` allowing for automated deployment.
