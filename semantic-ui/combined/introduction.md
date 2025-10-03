## === advanced-usage.md ===

# Recipes

Additional integration paths for advanced users

## Custom Pipelines

#### Importing Gulp Tasks
You don't have to use [our gulp pipeline](/introduction/build-tools.html), just import the task into your own `gulpfile`

You can [fork this example project](https://github.com/Semantic-Org/Example-External-Gulpfile) to see an example of how to import Semantic UI tasks into your project.
```javascript
var
  gulp  = require('gulp'),
  watch = require('./semantic/tasks/watch'),
  build = require('./semantic/tasks/build')
;
// import task with a custom task name
gulp.task('watch ui', watch);
gulp.task('build ui', build);
```

## Semantic.json Settings

#### Auto-Install
Running `npm install` normally will launch an interactive installer, to allow this installer to run without user interaction include a special flag `autoInstall: true`in your `semantic.json` file.
```javascript
{
// install will now automatically build your project files without user interaction
"autoInstall": true,

// these settings may be different
"base": "",
"paths": {
  "source": {
    "config": "src/theme.config",
    "definitions": "src/definitions/",
    "site": "src/site/",
    "themes": "src/themes/"
  },
  "output": {
    "packaged": "dist/",
    "uncompressed": "dist/components/",
    "compressed": "dist/components/",
    "themes": "dist/themes/"
  },
  "clean": "dist/"
},
"permission": false,
"rtl": false,
}
```

#### Right-to-left (RTL) Languages
Including the flag `rtl:true` will build Semantic UI using [RTLCSS](https://github.com/MohammadYounes/rtlcss).

To build both LTR and RTL versions use the flag `rtl: 'both'`
```javascript
{
// builds both LTR and RTL version
"rtl": "both",

// these settings may be different
"base": "",
"paths": {
  "source": {
    "config": "src/theme.config",
    "definitions": "src/definitions/",
    "site": "src/site/",
    "themes": "src/themes/"
  },
  "output": {
    "packaged": "dist/",
    "uncompressed": "dist/components/",
    "compressed": "dist/components/",
    "themes": "dist/themes/"
  },
  "clean": "dist/"
},
"permission": false,
}
```

## Prototyping with Semantic UI

#### Sketch Files
If you are looking to prototype layouts using [Sketch](http://bohemiancoding.com/sketch/) with Semantic UI check out [Semantic UI Sketch Files](https://github.com/guacamoly/semantic-ui-kit-for-sketch)

![snapshot.jpg](https://github.com/guacamoly/semantic-ui-kit-for-sketch/raw/master/snapshot.jpg?raw=true)

## Single Components

#### CDN Releases
Individual components are available on [jsDelivr](https://www.jsdelivr.com/projects/semantic-ui)
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/semantic-ui@<%= @getVersion() %>/dist/semantic.min.css">
```
```html
<script src="https://cdn.jsdelivr.net/npm/semantic-ui@<%= @getVersion() %>/dist/semantic.min.js"></script>
```
[View All CDN Files](https://www.jsdelivr.com/projects/semantic-ui)

#### Tagged Releases
Component repos are released on NPM and as tagged releases on GitHub.

Check the list of repos available under [Semantic Org](https://github.com/Semantic-Org?utf8=%E2%9C%93&query=ui-) on GitHub

Each component's release notes will automatically update with the relevant notes for that component from the main release.
```
npm install semantic-ui-component
```

#### Server-Side Rendering
Individual components repos include an [auto-generated](https://github.com/Semantic-Org/Semantic-UI/blob/master/tasks/admin/components/create.js) `index.js` file to simplify [`require`](http://www.sitepoint.com/understanding-module-exports-exports-node-js/) use with NodeJS, for server-side rendering or with [Browserify](http://browserify.org/).
```
npm install semantic-ui-dropdown
```
```javascript
var
  dropdown = require('semantic-ui-dropdown')
;
foo.dropdown();
```

## Importing LESS

#### LESS Only Distribution
A special distribution [Semantic-UI-LESS](https://github.com/Semantic-Org/Semantic-UI-LESS) is available for projects that use custom integrations and do not require our build tools.
> LESS source files are not prefixed, and will need to be run through [autoprefixer](https://github.com/postcss/autoprefixer) before being used

#### Importing Semantic
`semantic.less` is available in all releases as an entry point for importing multiple components from other LESS files.
```less
/* Import all components */
@import 'src/semantic';
```

#### Importing Components
If you need to import individual components, you should scope each import to avoid inheritance issues.
```less
/* Import specific components with scope */
& { @import 'src/definitions/elements/button'; }
& { @import 'src/definitions/elements/list'; }
```

## Running Docs Locally

#### Download Docs Server
The easiest way to get [Semantic UI docs](https://github.com/Semantic-Org/Semantic-UI-Docs/) is to clone the repo
```
git clone https://github.com/Semantic-Org/Semantic-UI-Docs.git
```

#### Install Dependencies
Semantic UI's documentation is written in [Docpad](http://www.docpad.org) an amazing static site generator built in NodeJS
```
cd docs/
npm install
```

#### A Note About Paths
Semantic UI's [build tools](introduction/build-tools.html) include two special commands `build-docs` and `serve-docs` for use with the documentation. These will pass changes from the ui/ folder directly to a live docs server.

These gulp tasks expect two sibling folders

*   ui/
    *   Files from semantic ui repo
*   docs/
    *   Files from docs repo

#### Build UI
The first time you run docs you will need to build the whole project once
```
cd ui/
gulp build-docs
```

#### Run Docpad Server
Docpad
```
cd docs/
# initial build may take several minutes
docpad run
```

#### Serve UI to Docs
You can then continue to make modifications to UI and "serve" these files to a live docs instance to see your changes immediately
```
cd ui/
gulp serve-docs
```

#### Hosted Docs
If you are managing your documentation you can automatically deploy to GitHub Pages using a built in [docpad gh-pages](https://github.com/docpad/docpad-plugin-ghpages) plugin

For more information about GitHub Pages, check out the [docs on GitHub](https://pages.github.com/)
```
docpad deploy-ghpages --env static
```

#### Custom Docs Paths
Doc task paths are specified in a file [`tasks/config/docs.js`](https://github.com/Semantic-Org/Semantic-UI/blob/master/tasks/config/docs.js) and can be adjusted to use any folder set-up necessary for your project.


## === build-tools.md ===

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


## === getting-started.md ===

# Getting Started

Getting up and running with Semantic UI

## Preface

#### Using Build Tools

Semantic UI packaged Gulp build tools so your project can preserve its [own theme changes](/usage/theming.html).

The easiest way to install Semantic UI is our NPM package which contains special install scripts to make setup interactive and updates seamless.

For installing with specific integrations like Ember, React, or Meteor, see our [integration guide](/introduction/integrations.html)

For integrating Semantic UI tasks into your own build tools, or using a CDN see our [recipes](/introduction/advanced-usage.html) section.

> <div class="ui header">Simpler Setup</div>
> <p>If you are using Semantic UI as a dependency and just want to use our default theme, use our lighter [semantic-ui-css](https://github.com/Semantic-Org/Semantic-UI-CSS) or [semantic-ui-less](https://github.com/Semantic-Org/Semantic-UI-Less) repo. If you just need the files you can download them as a zip from GitHub.</p>
> [Download Zip](https://github.com/Semantic-Org/Semantic-UI-CSS/archive/master.zip)
> [View all Semantic-Org Repos](https://github.com/Semantic-Org/)

## Installing

#### Install NodeJS
If you are unfamiliar with setting up NodeJS you can follow the steps below, or check out the [download page](https://nodejs.org/download/) on [nodejs.org](http://www.nodejs.org)

### Mac

#### Option 1: Homebrew
After installing [homebrew](http://brew.sh/)
```bash
brew install node
```

#### Option 2: Git
```bash
git clone git://github.com/nodejs/node.git
cd node
./configure
make
sudo make install
```

### Linux

#### Install via PPA
Although [Chris Lea's PPA](http://www.ubuntuupdates.org/ppa/chris_lea_nodejs) was once the best way to install node, it is now somewhat out of date.

The recommended path to install Semantic UI is using [Joyent's package manager](https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager) guide.

#### Ubuntu
```bash
curl --silent --location https://deb.nodesource.com/setup_6.x | sudo bash -
sudo apt-get install --yes nodejs
```

#### Debian
```bash
apt-get install curl
curl --silent --location https://deb.nodesource.com/setup_6.x | bash -
apt-get install --yes nodejs
```

#### Red Hat
```bash
curl --silent --location https://rpm.nodesource.com/setup | bash -
yum -y install nodejs
```

### Windows

#### Install the exe
Download the [NodeJS executable](http://nodejs.org/download/).

#### Install Gulp
Semantic UI uses [Gulp](http://www.gulpjs.com) to provide command line tools for building themed versions of the library with just the components you need.

Gulp is an NPM module and must be installed globally
```bash
npm install -g gulp
```

#### Install Semantic UI
Semantic UI is available in an eponymous package on NPM

### Video
```html
<script type="text/javascript" src="https://asciinema.org/a/22121.js" id="asciicast-22121" async></script>
```

### Code
```bash
npm install semantic-ui --save
cd semantic/
gulp build
```

#### Include in Your HTML
Running the gulp build tools will compile CSS and Javascript for use in your project. Just link to these files in your HTML along with the latest [jQuery](http://www.jquery.com).
```html
<link rel="stylesheet" type="text/css" href="semantic/dist/semantic.min.css">
<script
  src="https://code.jquery.com/jquery-3.1.1.min.js"
  integrity="sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8="
  crossorigin="anonymous"></script>
<script src="semantic/dist/semantic.min.js"></script>
```

## Updating

#### Updating via NPM
Semantic's NPM install script will automatically update Semantic UI to the latest version while preserving your site and packaged themes.
```bash
npm update
```

## Next Steps

#### All Set!
Well done! Semantic UI is now ready to be used.

```html
<div class="three column divided stackable center aligned ui grid">
  <div class="column">
    <div class="ui icon header">
      <i class="rocket circular icon"></i>
      See how to use <a href="/introduction/build-tools.html">gulp commands</a> and build tools
    </div>
  </div>
  <div class="column">
    <div class="ui icon header">
      <i class="theme circular icon"></i>
      Learn about <a href="/usage/theming.html">changing themes</a>
    </div>
  </div>
  <div class="column">
    <div class="ui icon header">
      <i class="food circular icon"></i>
      See <a href="/introduction/advanced-usage.html">recipes</a> for using Semantic UI in your project
    </div>
  </div>
</div>
```


## === glossary.md ===

# Glossary

Jargon specific to Semantic UI

## Terminology

#### Types of Components
Semantic UI classifies components into different definition types depending on its qualities. Each of these five types uses a unique definition format.
```html
<table class="ui large very padded definition table">
  <tbody>
    <tr>
      <td class="three wide">Globals</td>
      <td>
        Globals are styles that are applied across a site. These include things like CSS resets, and sitewide font, link and sizing defaults.</p>
        <p>Most importantly, globals include site-wide <a href="/usage/theming.html">theming variables</a> that other components can inherit and modify.</td>
    </tr>
    </tr>
    <tr>
      <td>Element</td>
      <td>
        UI elements are page elements with a single function. They can exist alone or in a plural form with elements sharing qualities.</p>
        <p>For example, a group of <a href="/elements/button.html">buttons</a> may use `ui red buttons` as a grouping with individual `ui button` children.</td>
    </tr>
    <tr>
      <td>Collection</td>
      <td>
        <p>Collections are heterogeneous groups of components which are usually found together. They describe a list of "usual suspects" which appear in a certain context. They may include and extend other ui elements for use in certain contexts—for example <a href="/collections/form.html">form</a> may extend <a href="/modules/dropdown.html">dropdown</a> or <a href="/elements/input.html">input</a>—as well as include their own content.</p>
      </td>
    </tr>
    <tr>
      <td>Views</td>
      <td>
        <p>A view is a convention for presenting specific types of content that is usually consistent across a website. These include things like <a href="/views/comment.html">comments</a>, <a href="/views/feed.html">activity feeds</a>, or <a href="/views/card.html">cards</a>.</p>
      </td>
    </tr>
    <tr>
      <td>Modules</td>
      <td>
        <p>Modules are components that include both a definition of how they appear and how they behave. These include components like, accordions, dropdowns, and popups.</p>
      </td>
    </tr>
    <tr>
      <td>Behaviors</td>
      <td>
        <p>Behaviors are standalone Javascript components that describe how page elements should act, but not how they should appear. Behaviors include things like form validation, state management, and API request routing.</p>
      </td>
    </tr>
  </tbody>
</table>
```

#### Project Terminology
Semantic UI classifies components into separate definition groupings.

```html
<table class="ui large very padded definition table">
  <tbody>
    <tr>
      <td class="three wide">Component</td>
      <td>
        A component is a general term used to refer to any user interface element packaged for distribution.
      </td>
    </tr>
    <tr>
      <td>Definition</td>
      <td>
        <p>A definition is a set of CSS and Javascript which describe a component's essential qualities.</p>
        <p>Definition use variables to express arbitrary parts of a component's appearance so that they can be changed with themes.</p>
      </td>
    </tr>
    <tr>
      <td>ui</td>
      <td>
        <p>`ui` is a special class name used to distinguish parts of components from components.</p>
        <p>For example, a [list](/elements/list.html) will receive the class `ui list` because it has a corresponding definition, however a list item, will receive just the class `item`.</p>
        <p>The ui class name helps encapsulate CSS rules by making sure all 'parts of a component' are defined in context to a 'whole' component.</p>
        <p>It also helps make scanning unknown code simpler. If you see `ui` you know you are looking at a component.</p>
      </td>
    </tr>
  </tbody>
</table>
```

#### Definition Terminology
When browsing Semantic UI definitions, you will see content grouped into different sections. These parts of a definition are consistent across definitions, and are common patterns for describing components.

```html
<table class="ui large very padded definition table">
  <tbody>
    <tr>
      <td class="three wide">Component</td>
      <td>
        A component is a general term used to refer to any user interface element packaged for distribution.
      </td>
    </tr>
    <tr>
      <td>Definition</td>
      <td>
        <p>A definition is a set of CSS and Javascript which describe a component's essential qualities.</p>
        <p>Definition use variables to express arbitrary parts of a component's appearance so that they can be changed with themes.</p>
      </td>
    </tr>
    <tr>
      <td>Types</td>
      <td>
        <p>Types are versions of an element that modify the element's standard appearance.</p>
        <p>Types cannot be used simultaneously on the same element. For example, "cats" and "dogs" are types of animals, but are **mutually exclusive**.</p>
      </td>
    </tr>
    <tr>
      <td>Variations</td>
      <td>
        <p>Variations modify qualities of an element like size, or color.</p>
        <p>Variations are **mutually inclusive**, and can be used together to modify an element.</p>
      </td>
    </tr>
    <tr>
      <td>Content</td>
      <td>
        <p>Content are parts which only have meaning in the context of a component. Content use names which describe the type of expected content like header, description, menu, or item.</p>
        <p>Content inside a collection or view often includes stubbed versions of other components. For example cards let you use [image content](/views/card.html#image), which can be extended by using [ui image variations](/elements/image.html#variations).
      </td>
    </tr>
    <tr>
      <td>States</td>
      <td>
        <p>States are modifications to an element that help indicate a change in [affordances](http://www.usabilityfirst.com/glossary/affordance/). Common states include `loading`, `disabled`, and `active`.</p>
      </td>
    </tr>
    <tr>
      <td>Behaviors</td>
      <td>
        <p>Behaviors are actions that a component can perform. Behaviors are represented by simple phrases like "set value" or "increment", that can be invoked in Javascript. Behaviors are automatically converted from spaced lowercase phrases to internal Javascript methods at invocation.</p>
      </td>
    </tr>
  </tbody>
</table>
```

#### General Terms

These terms are general programming terms that may be used without explanation in other documentation pages.

```html
<table class="ui large very padded definition table">
  <tr>
    <td class="three wide">Namespace</td>
    <td>A name given to an element for the explicit purpose of containing the application of properties.</p>
    <p>In Semantic UI, components are given the class name `ui` to help distinguish them from parts of elements in code, and to provide a namespace for definitions which can limit the scope of CSS rules.</td>
  </tr>
  <tr>
    <td>Gulp</td>
    <td>Gulp is a tool for automating command line tasks [Gulpjs.com](http://www.gulpjs.com)</td>
  </tr>
  <tr>
    <td>NPM</td>
    <td>NPM is a package manager used for downloading Node JS packages.</td>
  </tr>
  <tr>
    <td>Node JS</td>
    <td>Node is a event driven programming language frequently used to run command line tools for front end development. [nodejs.org](http://www.nodejs.org)</td>
  </tr>
</table>
```


## === integrations.md ===

# Integrations

Using Semantic UI with Other Libraries

## React

#### Contribute to React Development
Semantic UI React bindings are still in development, but are available for most components.

[Visit React Repo](https://github.com/Semantic-Org/Semantic-UI-React)

## Meteor

#### Install via Atmosphere
Install the [Semantic UI package](https://atmospherejs.com/semantic/ui) from atmosphere.
```bash
meteor add semantic:ui
```
The next step will differ depending on what version of Meteor you are running. Continue to the section relevant to your version of Meteor.

#### (Meteor <1.3) Install less-autoprefixer package
You will need a special package less-autoprefixer, to add vendor prefixes to your LESS pipeline.
> Since `flemay:less-autoprefixer` compiles LESS files you don't need any other less package.
```bash
meteor add flemay:less-autoprefixer
```
Continue to the "Create a custom.semantic.json file" section

#### (Meteor 1.3+) Install less and postcss packages
Remove the standard-minifier-css package.
```bash
meteor remove standard-minifier-css
```
Install the less and postcss packages.
```bash
meteor add less juliancwirko:postcss
```
To configure the postcss package, add the following to your `package.json` file and save it.
```json
{
  "devDependencies": {
    "autoprefixer": "^6.3.1"
  },
  "postcss": {
    "plugins": {
      "autoprefixer": {"browsers": ["last 2 versions"]}
    }
  }
}
```
To finish setting up the postcss package, install the new autoprefixer NPM package.
```bash
meteor npm install
```

#### Create a custom.semantic.json file
With meteor stopped:
```bash
touch client/lib/semantic-ui/custom.semantic.json
```
`custom.semantic.json` is a special file used to determine which themes and components to include in your project's build.

To remove a component from the pipeline, simply set the boolean value to `false`
```json
{
"definitions": {
  "accordion" : true,
  "ad"        : true,
  "api"       : true,
  /* etc */
},
"themes": {
  "amazon"     : false,
  "basic"      : false,
  "bookish"    : false,
  "bootstrap3" : false,
  "chubby"     : false,
  "classic"    : false,
  "default"    : true,
  /* etc */
}
```

#### Start Meteor / Generate

Every time Meteor starts or refreshes it calls the package semantic:ui to generate Semantic UI.

The package has a uses the diff between `custom.semantic.json` and `.custom.semantic.json` to avoid regenerating files unnecessarily.

If the file `.custom.semantic.json` does not exist or it is different than custom.semantic.json then it will generate Semantic UI.

#### Customize Site Variables
Semantic UI meteor includes a site theme, `site/` which can be used to customize less variables for your site. These files are optional, and can safely be removed if customization is not necessary.

Visit our [theming guide](/usage/theming.html) to learn more about theming.

#### Issues & Debugging
For help with Semantic UI Meteor, and for the latest updates, please visit the repository home on GitHub

[Visit Meteor Repo](https://github.com/Semantic-Org/Semantic-UI-Meteor)

## Ember

#### Installing via CLI
Include the library as an NPM dependency, from within an ember-cli app.

If you are using Ember CLI `1.13-2.X`
```
ember install semantic-ui-ember
```
If you are using an older version `< 0.1.5`
```bash
npm install --save-dev Semantic-Org/Semantic-UI-Ember
```

#### Run the Library's Blueprint
```bash
ember generate semantic-ui-ember
```

#### Get Coding
For example of individual components check out the GitHub repository

[Visit Ember Repo](https://github.com/Semantic-Org/Semantic-UI-Ember)

## Angular

#### Contribute to Angular Development
Semantic UI angular bindings are still in development, but are available for some components

[Visit Angular Repo](https://github.com/Semantic-Org/Semantic-UI-Angular)


## === new.md ===

# New in 2.4

An introduction to new features found in the latest release

## New in 2.4

### Solving Empty State
Semantic `2.4` brings a new components for handling content loading [ui placeholder](/elements/placeholder.html), as well as a new type of `segment` used to reserve space for content: [ui placeholder segment](/elements/segment.html#empty).

Additionally several important component updates are included in this release.

*   Modals have been re-architected to use hybrid flex support, falling back to JS positioning for more complex use-cases (or older browsers).
*   Dropdowns now include a `clearable` setting for letting users reset dropdowns to its empty state.

> If you are upgrading from a previous SUI version, be sure to add `@placeholder` to your [theme.config](/introduction/build-tools.html) to include the placeholder component in your code.

## New UI Component

#### Placeholders
[Placeholders](/elements/placeholder.html) can be used to reduce the jarringness, and perceived load time when loading new content
```html
<%- @partial('examples/content-loader') %>
```
```html
<div class="ui relaxed divided list">
  <div class="item">
    <i class="large github middle aligned icon"></i>
    <div class="content">
      <a class="header">Semantic-Org/Semantic-UI-Docs</a>
      <div class="description">Updated 22 mins ago</div>
    </div>
  </div>
  <div class="item">
    <i class="large github middle aligned icon"></i>
    <div class="content">
      <div class="ui placeholder">
        <div class="paragraph">
          <div class="medium line"></div>
          <div class="short line"></div>
        </div>
      </div>
    </div>
  </div>
  <div class="item">
    <i class="large github middle aligned icon"></i>
    <div class="content">
      <div class="ui placeholder">
        <div class="paragraph">
          <div class="medium line"></div>
          <div class="short line"></div>
        </div>
      </div>
    </div>
  </div>
  <div class="item">
    <i class="large github middle aligned icon"></i>
    <div class="content">
      <div class="ui placeholder">
        <div class="paragraph">
          <div class="medium line"></div>
          <div class="short line"></div>
        </div>
      </div>
    </div>
  </div>
  <div class="item">
    <i class="large github middle aligned icon"></i>
    <div class="content">
      <div class="ui placeholder">
        <div class="paragraph">
          <div class="medium line"></div>
          <div class="short line"></div>
        </div>
      </div>
    </div>
  </div>
</div>
```

#### Placeholder Segment
[Placeholder segments](/elements/segment.html#placeholder) allow you to reserve space in your design for where content is intended to appear. This is useful when a page should prompt a user about its intended functionality, even when no content is present.
```html
<div class="ui placeholder segment">
  <div class="ui icon header">
    <i class="dont icon"></i>
    No users have been added yet
  </div>
  <div class="ui primary button">Add User</div>
</div>
```
```html
<div class="ui placeholder segment">
  <div class="ui stackable two column center aligned grid">
    <div class="ui vertical divider">Or</div>
    <div class="middle aligned row">
      <div class="column">
        <div class="ui icon header">
          <i class="search icon"></i>
          Find Country
        </div>
        <div class="field">
          <div class="ui search">
            <div class="ui icon input">
              <input class="prompt" type="text" placeholder="Search countries...">
              <i class="search icon"></i>
            </div>
            <div class="results"></div>
          </div>
        </div>
      </div>
      <div class="column">
        <div class="ui icon header">
          <i class="world icon"></i>
          Add New Country
        </div>
        <div class="ui primary button">
          Create
        </div>
      </div>
    </div>
  </div>
</div>
```

## New Features

#### Clearable Dropdowns
Now dropdowns can specify that their content can be cleared with `clearable: true`.

```html
<div class="ui search selection dropdown">
  <input type="hidden" name="country" value="kr">
  <div class="text">
    <i class="kr flag"></i>South Korea
  </div>
  <i class="dropdown icon"></i>
  <%- @partial('examples/single/flag-menu') %>
</div>
<div class="ui divider"></div>
<div class="ui secondary segment">
  Show me
  <div class="ui inline scrolling dropdown">
    <input type="hidden" name="skill" value="css">
    <div class="text">css</div>
    <i class="dropdown icon"></i>
    <div class="menu">
      <%- @partial('examples/single/preset-menu') %>
    </div>
  </div>
  classes currently available.
</div>
```

#### Improved Flexbox Modals
Although flex-box were introduced in `2.3.0` there were limitations which may have prevented some advanced use-cases. For example, flexbox modals did not support modals that used `detachable: false` and werent directly inside dimmer flex containers. Also some flex browsers (IE11) do not support absolutely positioned elements inside flex containers, so multiple overlapping modals could not be used in those cases.

`2.4.0` solves this by introducing a hybrid flex system, that will fall back to javascript positioning for browsers or layouts that aren't compatible with flex.

## 2.3

### A New Approach
After an extended period of patches, Semantic UI `2.3` marks the return to significant feature changes for the project.

In upcoming Semantic releases we will be releasing more frequently, but with smaller changesets, to make it easier for users to upgrade and adjust to global changes.

## New Features

#### Font Awesome 5.0 & Better Icon Searching
In `2.3` [icons](/elements/icon.html) now include a full port of [Font Awesome](https://fontawesome.com/) `5.0.6`, including 929 icons.

Icon categories now match icon categories in Font Awesome's documentation, making it easier to find icons between docs.
```html
<div class="ui doubling five column vertically padded grid">
  <div class="column"><i class="smile icon"></i>Smile</div>
  <div class="column"><i class="smile outline icon"></i>Smile Outline</div>
  <div class="column"><i class="hand rock icon"></i>Hand Rock </div>
  <div class="column"><i class="hand paper icon"></i>Hand Paper </div>
  <div class="column"><i class="hand scissors icon"></i>Hand Scissors</div>
</div>
```
Semantic UI [icon docs](/elements/icon.html) now includes a global icon search with easy copy and paste access to html

#### Flexbox Modals and Dimmers

Semantic UI `2.3` includes a rewrite of modal to include non-js flexbox positioning for vertical centering. No longer will you have to call `$('.ui.modal').modal('refresh')` if content height changes to recenter.

In addition there's a new setting `centered: false` which makes it easier to do top aligned modals when the internal may be dynamic and you dont want content to shift vertically.

```html
<div class="ui special modal">
  <div class="header">
    Top Aligned Modal
  </div>
  <div class="content">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    <div class="ui hidden divider"></div>
  </div>
  <div class="actions">
    <div class="ui button">
      Cancel
    </div>
    <div class="ui primary right labeled icon button">
      Submit
      <i class="checkmark icon"></i>
    </div>
  </div>
</div>
<a class="ui button" data-url="/images/large-pdf.pdf">
  Open Top Aligned Modal
</a>
```
```javascript
$('.ui.special.modal')
  .modal({
    centered: false
  })
  .modal('attach events', '.modal.example .button')
;
```

#### New Transitions
[Transition](/modules/transition.html) now includes `zoom` and `glow`. Glow is useful for highlighting elements on page,

```javascript
$('.autumn.leaf')
  .transition('zoom')
;
```
```javascript
$('.autumn.leaf')
  .transition('glow')
;
```
```html
<img src="/images/leaves/7.png" class="ui autumn leaf medium image">
```

#### Global Font Weight Variables
Theming now uses two no global variables `@bold` and `@normal` making it easier to modify font weights in a more complex font stack
```less
/* Use some custom font weights */
@bold: 600;
@normal: 400;
```

#### Local Category Search
You can now use category search with the `source` option without having to add API callbacks
```html
<div class="ui search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search countries...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```
```javascript
var categoryContent = [
  { category: 'South America', title: 'Brazil' },
  { category: 'South America', title: 'Peru' },
  { category: 'North America', title: 'Canada' },
  { category: 'Asia', title: 'South Korea' },
  { category: 'Asia', title: 'Japan' },
  { category: 'Asia', title: 'China' },
  { category: 'Europe', title: 'Denmark' },
  { category: 'Europe', title: 'England' },
  { category: 'Europe', title: 'France' },
  { category: 'Europe', title: 'Germany' },
  { category: 'Africa', title: 'Ethiopia' },
  { category: 'Africa', title: 'Nigeria' },
  { category: 'Africa', title: 'Zimbabwe' },
];
$('.local-category.example .ui.search')
  .search({
    type: 'category',
    source: categoryContent,
    searchFields: [
      'title',
      'category'
    ]
  })
;
```

#### Arrow Aligment on Small Popups
Semantic [popups](/modules/popup.html) now detects when horizontally aligning the popup on it's arrow is more reasonable than matching edges with a popup.
> To use this feature be sure to specify `movePopup: false` in your settings
```html
<img src="http://oi66.tinypic.com/2zr2ckk.jpg" class="ui image">

<div class="ui divider"></div>
<img src="/images/avatar/small/elliot.jpg" data-title="Elliot Fu" data-content="Elliot has been a member since July 2012" class="ui avatar image">
```
```javascript
$('.centering.example .avatar.image').popup();
```

#### Popups Support Multiple Coordinate Systems
Popups now can correctly place elements with two different coordinate systems. These are typically caused by having a parent element with css properties `transform` or `position`.
```html
<div id="one">
  <p>Button is in here</p>
  <div class="ui button">Button</div>
</div>
<div id="two">
  <p>Popup is in here</p>
  <div class="ui popup">
    <h4 class="ui header">
      Test
    </h4>
    <p>This popup now appears correct without having to move the popup to the same coordinate system by moving the DOM element.</p>
  </div>
</div>
```
```html
<div id="one">
  <p>Button is in here</p>
  <div class="ui button">Button</div>
</div>
<div id="two">
  <p>Popup is in here</p>
  <div class="ui popup">
    <h4 class="ui header">
      Test
    </h4>
    <p>This popup now appears correct without having to move the popup to the same coordinate system by moving the DOM element.</p>
  </div>
</div>
```
```css
/* Activating element is inside #one with different positioning context */
#one {
  display: block;
  position: relative;
  padding: 50px 100px;
  background-color: #F0F0F0;
}
/* Popup is inside two with position relative (creating another positioning context) */
#two {
  display: block;
  background-color: #E2EAE4;
  position: relative;
  top: 10px;
  padding: 50px 8px;
}
```
```javascript
$('.complex-popup.example .ui.button')
  .popup({
    movePopup: false,
    popup: $('.complex-popup.example .popup')
  })
;
```

#### New Matching Options
In addition, search now includes three tiers of matched results, similar to the options available in dropdown. Fuzzy results now are turned off by the new default `fullTextSearch: 'exact'`

*   Query matches the start of field exactly
*   Query matches any part of field
*   Query "fuzzy" matches field

```javascript
$('.ui.search')
  .search({
    fullTextSearch: 'exact' // only matches exact matches (no fuzzy matching)
  })
;
```

## 2.2

### By The Numbers
`2.2` represents nearly a half year of updates, many new features, and bug patches.

*   **124** [closed issues](https://github.com/Semantic-Org/Semantic-UI/issues?q=is%3Aissue+milestone%3A2.1+is%3Aclosed)
*   **40** new features
*   **70** bug fixes

For the complete list of bugs, their accompanying issue threads and the fixes please consult the release notes

[Release Notes](https://github.com/Semantic-Org/Semantic-UI/blob/master/RELEASE-NOTES.md#version-220---june-26-2016)

## Project Changes

#### Critical Bug Fixes

`2.2` brings many new bug fixes. For a complete list please check out our release notes. Here is a highlight of some critical bugs

```html
<div class="ui styled bug accordion">
  <div class="title">
    <i class="dropdown icon"></i>
    View Critical Bug List
  </div>
  <div class="content">
    <div class="ui large relaxed bulleted list">
      <div class="item">
        <b>All UI</b> - Using `component('setting, {})` to add multiple settings as an object literal, for example `error: {}`, will now deep extend the existing object instead of replacing it.
      </div>
      <div class="item">
        <b>API</b> - `beforeSend` would not correctly cancel request when `return false;` is used in callback.
      </div>
      <div class="item">
        <b>API</b> - `cache: 'local'` would not return the localstorage cached results in some cases
      </div>
      <div class="item">
        <b>Divider</b> - Descenders like "g" are cut off in `horizontal divider`
      </div>
      <div class="item">
        <b>Dropdown</b> - `forceSelection` will now automatically select values with multi dropdowns. When using `userAdditions` setting it will now automatically tokenize the current entered value
      </div>
      <div class="item">
        <b>Dropdown</b> - Fixed issue where value set using javascript DOM metadata would be cleared when a message or user addition triggered `refresh`
      </div>
      <div class="item">
        <b>Form Validation / Dropdown</b> - Using "enter" key in a `search dropdown` could cause a form to be submitted
      </div>
      <div class="item">
        <b>Form Validation</b> - Fix issue with some foreign email addresses with extended charsets causing email validation to fail
      </div>
      <div class="item">
        <b>Form Validation</b> - Revalidating a field `on: blur` could cause fields not yet interacted with to be validated
      </div>
      <div class="item">
        <b>Form</b> - Fixed issue with `(x) fields` and `equal width` fields where middle rows would be slightly smaller because they include both left and right padding in % width. (Edges only have one side padding). Field groups now use negative margins instead.
      </div>
      <div class="item">
        <b>Popup</b> - Fixed issue where clicking element inside popup removed from DOM (like clicking a multi select label) would cause popup to close
      </div>
      <div class="item">
        <b>Rail</b> - Fixed incorrect width for `close rail` and `very close rail` caused by variable addition with mixed units `px` + `em`
      </div>
      <div class="item">
        <b>Search</b> - Fixed bug where a previously XHR query could cause the next one to fail depending on the latency of the request.
      </div>
      <div class="item">
        <b>Search</b> - Fixed an issue where `onResult` returning `false` would not prevent the search menu from hiding. Clicking on an empty results message will also no longer close the search results.
      </div>
      <div class="item">
        <b>Sticky/Visibility</b> -  Added mutation observer to teardown element with `destroy` if removed from DOM context, fixing a possible memory leak
      </div>
      <div class="item">
        <b>Video</b> - Fixed issue with `.video('change')` behavior not properly changing video.
      </div>
    </div>
  </div>
</div>
```

## New Features

#### CSS-Only Tooltips
2.2 includes CSS only popups that work without JS initialization using the `data-tooltip` property on any element. CSS tooltips even support inversion and specified positioning.
```html
<div class="ui icon button" data-tooltip="Add users to your feed" data-delay="500">
  <i class="add icon"></i>
</div>
<div class="ui icon button" data-tooltip="Add users to your feed" data-inverted>
  <i class="add icon"></i>
</div>
<div class="ui button" data-tooltip="Add users to your feed" data-position="top left">
  Top Left
</div>
<div class="ui button" data-tooltip="Add users to your feed" data-position="top center">
  Top Center
</div>
<div class="ui button" data-tooltip="Add users to your feed" data-position="top right">
  Top Right
</div>
<div class="ui divider"></div>
<div class="ui button" data-tooltip="Add users to your feed" data-position="bottom left">
  Bottom Left
</div>
<div class="ui button" data-tooltip="Add users to your feed" data-position="bottom center">
  Bottom Center
</div>
<div class="ui button" data-tooltip="Add users to your feed" data-position="bottom right">
  Bottom Right
</div>
<div class="ui divider"></div>
<div class="ui button" data-tooltip="Add users to your feed" data-position="right center">
  Right Center
</div>
<div class="ui button" data-tooltip="Add users to your feed" data-position="left center">
  Left Center
</div>
```
```html
<div class="ui button" data-inverted data-tooltip="Add users to your feed" data-position="top left">
  Top Left
</div>
<div class="ui button" data-inverted data-tooltip="Add users to your feed" data-position="top center">
  Top Center
</div>
<div class="ui button" data-inverted data-tooltip="Add users to your feed" data-position="top right">
  Top Right
</div>
<div class="ui divider"></div>
<div class="ui button" data-inverted data-tooltip="Add users to your feed" data-position="bottom left">
  Bottom Left
</div>
<div class="ui button" data-inverted data-tooltip="Add users to your feed" data-position="bottom center">
  Bottom Center
</div>
<div class="ui button" data-inverted data-tooltip="Add users to your feed" data-position="bottom right">
  Bottom Right
</div>
<div class="ui divider"></div>
<div class="ui button" data-inverted data-tooltip="Add users to your feed" data-position="right center">
  Right Center
</div>
<div class="ui button" data-inverted data-tooltip="Add users to your feed" data-position="left center">
  Left Center
</div>
```

#### New Icons
2.2 of Semantic UI includes the latest version of [Font Awesome](http://fontawesome.io/) with 50+ new icons. For a complete breakdown of new icons please check [Font Awesome's list](http://fontawesome.io/whats-new/).
```html
<div class="ui doubling five column grid">
  <div class="column"><i class="wheelchair icon"></i>Wheelchair</div>
  <div class="column"><i class="asl interpreting icon"></i>American Sign Language (ASL) Interpreting</div>
  <div class="column"><i class="assistive listening systems icon"></i>Assistive Listening Systems</div>
  <div class="column"><i class="audio description icon"></i>Audio Description</div>
  <div class="column"><i class="blind icon"></i>Blind</div>
  <div class="column"><i class="braille icon"></i>Braille</div>
  <div class="column"><i class="deafness icon"></i>Deafness</div>
  <div class="column"><i class="low vision icon"></i>Low Vision</div>
  <div class="column"><i class="sign language icon"></i>Sign Language</div>
  <div class="column"><i class="universal access icon"></i>Universal Access</div>
  <div class="column"><i class="volume control phone icon"></i>Volume Control Phone</div>
</div>
<div class="ui divider"></div>
<a href="/elements/icon.html" class="ui primary button">View All Icons <i class="right chevron icon"></i></a>
```

#### Rapid-Ready Progress
Progress bars in 2.2 have been recoded to handle rapid update events.

Now developers can trigger updates at fast intervals without causing animations to stutter, or easing tweens to occur unnaturally.
```html
<div class="ui indicating progress" data-value="1" data-total="200" id="example5">
  <div class="bar">
    <div class="progress"></div>
  </div>
  <div class="label">Waiting for you to press button</div>
</div>
<a class="ui button" data-url="/images/large-pdf.pdf">
  Rapidly Update
</a>
```
```javascript
$('.rapid.example .ui.button')
  .on('click', function() {
    var
      $progress       = $('.rapid.example .ui.progress'),
      $button         = $(this),
      updateEvent
    ;
    clearInterval(window.fakeProgress)
    $progress.progress('reset');

    // updates every 10ms until complete
    window.fakeProgress = setInterval(function() {
      $progress.progress('increment');
      $button.text( $progress.progress('get value') );
      // stop incrementing when complete
      if($progress.progress('is complete')) {
        clearInterval(window.fakeProgress)
      }
    }, 10);
  })
;
$('.rapid.example .ui.progress')
  .progress({
    duration : 200,
    total    : 200,
    text     : {
      active: '{value} of {total} done'
    }
  })
;
```

#### Reduced Memory Leaks
[Sticky](/modules/sticky.html), [visibility](/behaviors/visibility.html), [popup](/modules/popup.html), and [dropdown](/modules/dropdown.html), modules that can attach events on initialization to `window` and `body`, for example to detect changes in window scroll, will now use [additional mutation observers](https://github.com/Semantic-Org/Semantic-UI/blob/master/dist/components/visibility.js#L143) to determine if they are removed from the DOM and automatically fire their `destroy` behaviors.

This can prevent memory leaks when the parent element of a component is removed without the element is propertly teared down by calling its `destroy` behavior.
```html
<div class="ui primary button">Simulate Memory Leak</div>
<div class="ui display segment">
  Not Active
</div>
<div class="wrapper">
  <div class="ui demo segment">
    This segment has visibility events attached to modify the button above to say "active" when it is on screen
  </div>
</div>
```
```javascript
$('.memory.example .demo.segment')
  .visibility({
    onOnScreen: function() {
      // this will no longer fire even though element was removed indirectly
      $('.memory.example .display.segment').html('This is active');
    }
  })
;
// button will remove parent of visibility element and callback will stop firing automatically
$('.memory.example .ui.button')
  .on('click', function() {
    $('.memory.example .display.segment').html('De-activated');
    $('.memory.example .wrapper')
      .remove()
    ;
  })
;
```

#### Dependent Form Validation
Form field validation can now specify a [depends property](/behaviors/form.html#dependent-fields) which will only cause validation to occur only when another field, like a checkbox or input, is selected.
```html
<form class="ui form segment">
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" name="isDoctor" />
      <label>Are you a doctor?</label>
    </div>
  </div>
  <div class="field">
    <label>How long have you been a medical professional</label>
    <input type="text" name="yearsPracticed">
  </div>
  <div class="ui divider"></div>
  <div class="ui blue submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```
```javascript
$('.depends.example .ui.form')
  .form({
    onSuccess: function() {
      alert('No form problems');
      return false;
    },
    fields: {
      yearsPracticed: {
        identifier : 'yearsPracticed',
        depends    : 'isDoctor',
        rules      : [
          {
            type   : 'empty',
            prompt : 'Please enter the number of years you have been a doctor'
          }
        ]
      }
    }
  })
;
```

#### Faster Dropdown Selection
We've updated dropdowns to make it simpler to breeze through forms with dropdowns, and provide more intuitive selection controls

*   Multiple select dropdowns use a new algorithm for line breaks based on actual rendered pixels and not estimated length based on glyph width calculations, meaning more choices can squeeze on a line than before.
*   Dropdowns now change selections on keyboards without hitting "enter", this lets users quickly navigate between dropdown elements in a form without having to hit "enter" before "tab" after each field entry, saving an additional keystroke.
*   All dropdown menus now support letter keyboard shortcuts. Hitting "C" for instance will let you jump to "California" in a dropdown list, then hitting it again "Colorado", even without using a search selection dropdown.

```html
<div class="ui two column very relaxed divided grid">
  <div class="column">
    <select class="ui fluid dropdown">
      <%- @partial('examples/single/state-options') %>
    </select>
  </div>
  <div class="column">
    <select class="ui multiple search fluid dropdown" multiple>
      <%- @partial('examples/single/state-options') %>
    </select>
  </div>
</div>
```

#### More Basic Buttons
We've added `primary`, `secondary`, `positive` and `negative` [basic buttons](/elements/button.html#basic)
```html
<button class="ui primary basic button">Primary</button>
<button class="ui secondary basic button">Secondary</button>
<button class="ui positive basic button">Positive</button>
<button class="ui negative basic button">Negative</button>
```

#### Popup Boundaries and Scroll Context
Popups now include a new setting `boundary` that let you specify that a popup should not escape the boundary of another section. This can be useful in complex paned layouts

Additionally popups can now specify a scroll context, to allow for scroll containers other than window to cause a clicked popup to hide on scroll.
```javascript
$('.boundary.example .button')
  .popup({
    boundary: '.boundary.example .segment'
  })
;
```
```html
<div class="ui segment">
  <div class="ui button" data-content="This popup is very long but wont escape the segment it is placed in">Hover Me</div>
  <p>Normally this popup would open in the default position `top center` but because this would escape the boundaries of the segment it will search other available positions until it can find one to place the popup while staying inside the segment</p>
</div>
```

## New Settings

We've added many new settings to components to help provide more granular control for some use-cases.

#### Dropdowns
```html
<table class="ui definition table">
  <tbody>
    <tr>
      <td>selectOnKeydown</td>
      <td>Whether dropdown should change active selection on keyboard shortcuts, preventing the requirement of hitting `enter` to confirm selection before the user tabs out of the field. (This will save one extra keystroke)
      </td>
    </tr>
    <tr>
      <td>allowReselection</td>
      <td>Setting to `true` will allow `onChange` to be triggered even when reselecting the same option</td>
    </tr>
    <tr>
      <td>fullTextSearch</td>
      <td>Setting to true will allow search across any part of string, setting to `exact` will disable fuzzy matching for dropdowns.</td>
    </tr>
    <tr>
      <td>hideAdditions</td>
      <td>Setting to true will allow custom user additions without triggering a special dropdown message for "Add custom choice". This is now enabled by default</td>
    </tr>
    <tr>
      <td>minCharacters</td>
      <td>Minimum characters required to begin showing filtered results</td>
    </tr>
  </tbody>
</table>
```
[Dropdown settings](/modules/dropdown.html#settings)

#### Popup
```html
<table class="ui definition table">
  <tbody>
    <tr>
      <td>boundary</td>
      <td>A selector, or DOM element that the popup should never escape when positioning itself
      </td>
    </tr>
    <tr>
      <td>scrollContext</td>
      <td>A selector or DOM element which should be used for determining if user has scrolled.</td>
    </tr>
    <tr>
      <td>observeChanges</td>
      <td>Whether popup should automatically watch for its own removal from page to avoid memory leaks.</td>
    </tr>
  </tbody>
</table>
```
[Popup settings](/modules/popup.html#settings)

#### Search
```html
<table class="ui definition table">
  <tbody>
    <tr>
      <td>selectFirstResult</td>
      <td>Whether the first search result element should be selected after results appear.
      </td>
    </tr>
    <tr>
      <td>showNoResults</td>
      <td>Whether a message should appear when no search results are returned
      </td>
    </tr>
  </tbody>
</table>
```
[Search settings](/modules/search.html#settings)

#### Rating
```html
<table class="ui definition table">
  <tbody>
    <tr>
      <td>fireOnInit</td>
      <td>Whether the rating component should fire callbacks on initialization.
      </td>
    </tr>
  </tbody>
</table>
```
[Rating settings](/modules/rating.html#settings)

#### Visibility
```html
<table class="ui definition table">
  <tbody>
    <tr>
      <td>zIndex</td>
      <td>Allows you to specify the `z-index` used with `type: 'fixed'`
      </td>
    </tr>
    <tr>
      <td>onFixed</td>
      <td>A callback used with `type: 'fixed'` to occur when content is fixed to the page.
      </td>
    </tr>
    <tr>
      <td>onUnfixed</td>
      <td>A callback used with `type: 'fixed'` to occur when content is fixed to the page.
      </td>
    </tr>
    <tr>
      <td>onLoaded</td>
      <td>A callback used with `type: 'image'` to occur when content is loaded.
      </td>
    </tr>
    <tr>
      <td>onAllLoaded</td>
      <td>A callback used with `type: 'image'` to occur when all images initialized together are loaded.
      </td>
    </tr>
  </tbody>
</table>
```
[Visibility settings](/behaviors/visibility.html#settings)

#### Tab
```html
<table class="ui definition table">
  <tbody>
    <tr>
      <td>cacheType</td>
      <td>When set to `html` will cache the tabs html after load, reloading with the exact same html. Setting to `response` will cache the serve response, allowing for load events to fire with same contents.
      </td>
    </tr>
    <tr>
      <td>deactivate</td>
      <td>When set to `siblings` deactivates only DOM elements that are siblings of the selected tab activator. `all` will deactivate all other elements initialized at the same time.
      </td>
    </tr>
  </tbody>
</table>
```
[Tab settings](/modules/tab.html#settings)

#### Shape
```html
<table class="ui definition table">
  <tbody>
    <tr>
      <td>width</td>
      <td>When set to `next` will use the size of the next `side` during the shape's animation. When set to `initial` it will use the size of the shape at initialization. When set to a specifix pixel width, will force the size to that width.
      </td>
    </tr>
    <tr>
      <td>height</td>
      <td>When set to `next` will use the size of the next `side` during the shape's animation. When set to `initial` it will use the size of the shape at initialization. When set to a specifix pixel height, will force the size to that height.
      </td>
    </tr>
  </tbody>
</table>
```
[Shape settings](/modules/shape.html#settings)

## 2.1

### The Tally
`2.1` sums up around two months of work, including many new features, and updates to help bulletproof existing UI.

*   **72** [closed issues](https://github.com/Semantic-Org/Semantic-UI/issues?q=is%3Aissue+milestone%3A2.1+is%3Aclosed)
*   **70** bug fixes
*   **23** new UI updates
*   **14** feature enhancements

To see the complete list of updates [review our release notes](https://github.com/Semantic-Org/Semantic-UI/blob/<%= @getBranch() %>/RELEASE-NOTES.md#version-210---sep-01-2015)

#### Labeled Buttons
[Labeled buttons](/elements/button.html#labeled) are a useful design pattern for displaying a tally alongside a button.

Labeled buttons are compatible with any label type, but looks great alongside a `basic label`.
```html
<div class="ui labeled button" tabindex="0">
  <div class="ui red button">
    <i class="heart icon"></i> Like
  </div>
  <a class="ui basic red label">
    2,048
  </a>
</div>
<div class="ui labeled button" tabindex="0">
  <div class="ui basic blue button">
    <i class="fork icon"></i> Forks
  </div>
  <a class="ui basic left pointing blue label">
    1,048
  </a>
</div>
<div class="ui labeled button" tabindex="0">
  <div class="ui basic violet button">
    <i class="hospital icon"></i> Hospitals
  </div>
  <a class="ui violet tag label">
    2,048
  </a>
</div>
<div class="ui divider"></div>
<div class="ui labeled button" tabindex="0">
  <div class="ui yellow button">
    <i class="star icon"></i> Star
  </div>
  <a class="ui basic yellow left pointing label">
    1,048
  </a>
</div>
<div class="ui left labeled button" tabindex="0">
  <a class="ui basic right pointing label">
    2,048
  </a>
  <div class="ui button">
    <i class="heart icon"></i> Like
  </div>
</div>
<div class="ui left labeled button" tabindex="0">
  <a class="ui basic label">
    1,048
  </a>
  <div class="ui icon button">
    <i class="fork icon"></i>
  </div>
</div>
```

#### Basic Labels
We've added a new style [basic label](/elements/label.html#basic) that is less intrusive, and compatible with all other label variations, reducing their complexity.
```html
<a class="ui basic label">Basic</a>
<a class="ui pointing basic label">Pointing</a>
<a class="ui basic image label">
  <img src="/images/avatar/small/elliot.jpg">
  Elliot
<a class="ui pointing red basic label">Red Pointing</a>
<a class="ui blue basic label">Blue</a>
</a>
<div class="ui divider"></div>
<div class="ui equal width stretched grid">
  <div class="column">
    <div class="ui segment">
      <a class="ui right pointing basic teal ribbon label">Pointing</a> Look over here
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
  <div class="column">
    <div class="ui segment">
      <a class="ui teal top right attached basic label">So Complex</a>
      <a class="ui orange top left attached basic label">So Simple</a>
      <a class="ui violet bottom attached top pointing basic label">Much adjectives</a>
    </div>
  </div>
</div>
```

#### Multiple Input Labels
[Labeled input](/elements/input.html#labeled) now supports labels on both sides of content at the same time.
```html
<div class="ui right labeled input">
  <div class="ui basic label">$</div>
  <input type="text" placeholder="Amount">
  <div class="ui basic label">.00</div>
</div>
```

#### More Tabular Directions
[Tabular menus](/collections/menu.html#tabular) now support `right` and `bottom` positioning.
```html
<div class="ui grid">
  <div class="twelve wide stretched column">
    <div class="ui segment">
      This is an stretched grid column. This segment will always match the tab height
    </div>
  </div>
  <div class="four wide column">
    <div class="ui vertical fluid right tabular menu">
      <a class="active item">
        Bio
      </a>
      <a class="item">
        Pics
      </a>
      <a class="item">
        Companies
      </a>
      <a class="item">
        Links
      </a>
    </div>
  </div>
</div>
```
```html
<div class="ui top attached segment">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
<div class="ui three item bottom attached tabular menu">
  <a class="active item">
    Active Project
  </a>
  <a class="item">
    Project #2
  </a>
  <a class="item">
    Project #3
  </a>
</div>
```
```html
<div class="ui grid">
  <div class="four wide column">
    <div class="ui vertical fluid tabular menu">
      <a class="active item">
        Bio
      </a>
      <a class="item">
        Pics
      </a>
      <a class="item">
        Companies
      </a>
      <a class="item">
        Links
      </a>
    </div>
  </div>
  <div class="twelve wide stretched column">
    <div class="ui segment">
      This is an stretched grid column. This segment will always match the tab height
    </div>
  </div>
</div>
```

#### Enhanced Vertical Dividers
Grids now support using multiple [vertical dividers](/elements/divider.html#vertical-divider) per column, in any specified arrangement.
```html
<div class="ui very relaxed vertically divided grid">
  <div class="row" style="position:relative;">
    <div class="six wide column">
      <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
    </div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ui vertical divider">and</div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ui vertical divider">and</div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="row" style="position:relative;">
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ui vertical divider">not</div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ui vertical divider">nor</div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="six wide column">
      <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
    </div>
  </div>
</div>
```

#### Inverted Colored Menu
[Inverted menus](/collections/menu.html#inverted) now support individual `item` colors

```html
<div class="ui three item labeled icon inverted menu">
  <a class="active red item">
    <i class="gamepad icon"></i>
    Games
  </a>
  <a class="pink item">
    <i class="video camera icon"></i>
    Channels
  </a>
  <a class="blue item">
    <i class="video play icon"></i>
    Videos
  </a>
</div>
```
```html
<div class="ui vertical inverted menu">
  <a class="active teal item">
    Inbox
  </a>
  <a class="orange item">
    Spam
  </a>
  <a class="violet item">
    Updates
  </a>
  <div class="item">
    <div class="ui transparent inverted icon input">
      <input type="text" placeholder="Search mail...">
      <i class="search icon"></i>
    </div>
  </div>
</div>
```

#### Reversable Grid Columns
Grids now support [reversing their column flow](/collections/grid.html#reversed) per-device. This can be useful when a column should appear on the opposite side of the screen on smaller screens.

Reversing grids are also designed to be compatible with column-order specific variations like divided or celled
```html
<div class="ui tablet reversed divided equal width grid">
  <div class="column">
    Computer First <br>
    Tablet Fourth
  </div>
  <div class="column">
    Computer Second <br>
    Tablet Third
  </div>
  <div class="column">
    Computer Third <br>
    Tablet Second
  </div>
  <div class="column">
    Computer Fourth <br>
    Tablet First
  </div>
</div>
```

#### Stackable Cards
Cards have a [stackable](/views/card.html#stackable) variation so that they appear full width on mobile.
```html
<div class="ui two stackable cards">
  <div class="ui card">
    <div class="content">
      <div class="right floated meta">14h</div>
      <img class="ui avatar image" src="/images/avatar/large/elliot.jpg"> Elliot
    </div>
    <div class="content">
      <span class="right floated">
        <i class="heart outline like icon"></i>
        17 likes
      </span>
      <i class="comment icon"></i>
      3 comments
    </div>
    <div class="extra content">
      <div class="ui large transparent left icon input">
        <i class="heart outline icon"></i>
        <input type="text" placeholder="Add Comment...">
      </div>
    </div>
  </div>
  <div class="ui card">
    <div class="content">
      <div class="right floated meta">14h</div>
      <img class="ui avatar image" src="/images/avatar/large/elliot.jpg"> Elliot
    </div>
    <div class="content">
      <span class="right floated">
        <i class="heart outline like icon"></i>
        17 likes
      </span>
      <i class="comment icon"></i>
      3 comments
    </div>
    <div class="extra content">
      <div class="ui large transparent left icon input">
        <i class="heart outline icon"></i>
        <input type="text" placeholder="Add Comment...">
      </div>
    </div>
  </div>
  <div class="ui card">
    <div class="content">
      <div class="right floated meta">14h</div>
      <img class="ui avatar image" src="/images/avatar/large/elliot.jpg"> Elliot
    </div>
    <div class="content">
      <span class="right floated">
        <i class="heart outline like icon"></i>
        17 likes
      </span>
      <i class="comment icon"></i>
      3 comments
    </div>
    <div class="extra content">
      <div class="ui large transparent left icon input">
        <i class="heart outline icon"></i>
        <input type="text" placeholder="Add Comment...">
      </div>
    </div>
  </div>
  <div class="ui card">
    <div class="content">
      <div class="right floated meta">14h</div>
      <img class="ui avatar image" src="/images/avatar/large/elliot.jpg"> Elliot
    </div>
    <div class="content">
      <span class="right floated">
        <i class="heart outline like icon"></i>
        17 likes
      </span>
      <i class="comment icon"></i>
      3 comments
    </div>
    <div class="extra content">
      <div class="ui large transparent left icon input">
        <i class="heart outline icon"></i>
        <input type="text" placeholder="Add Comment...">
      </div>
    </div>
  </div>
</div>
```

#### Fixed Tables
[Tables](/collections/table.html#fixed) now include a variation for using `table-layout: fixed`, which does not adjust column widths based on size.

This can help present data more cleanly with content that is uniformly formatted.

Fixed tables also support content collapsing using `text-overflow: ellipsis` when used with `single line`.
```html
<table class="ui fixed center aligned celled table">
  <thead>
    <th>Name</th>
    <th>Status</th>
    <th>Gender</th>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>Male</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Male</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>Female</td>
    </tr>
  </tbody>
</table>
```
```html
<h4 class="ui header">
  Fixed Tables
</h4>
<table class="ui fixed single line celled table">
  <thead>
    <th>Name</th>
    <th>Status</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td title="This is much too long to fit I'm sorry about that">This is much too long to fit I'm sorry about that</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Shorter description</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>Shorter description</td>
    </tr>
  </tbody>
</table>
```

## New Behaviors

#### Fully Customizable JSON
In `2.1` all component that uses remote data will let you specify a `fields` array to modify expected JSON property names, saving you the trouble of specifying an [onResponse](/behaviors/api.html#response-callbacks) callback to modify the data structure.
```html
<div class="ui search">
  <div class="ui left icon input">
    <input class="prompt" type="text" placeholder="Search GitHub">
    <i class="github icon"></i>
  </div>
</div>
```
```javascript
$('.ui.search')
  .search({
    apiSettings: {
      url: '//api.github.com/search/repositories?q={query}'
    },
    fields: {
      results : 'items',
      title   : 'name',
      url     : 'html_url'
    }
  })
;
```

#### Fields can also be used with local search to simplify working with unusual search sources.
```javascript
$('.ui.search')
  .search({
    searchFields: ['pickle'],
    fields: {
      title   : 'mustard'
    },
    source: [
      {
        mustard: 'Title #1',
        pickle: 'thing'
      },
      {
        mustard: 'Title #2',
        pickle: 'another thing'
      },
      {
        mustard: 'Title #3',
        pickle: 'thing 100'
      }
    ]
  })
;
```
```html
<div class="ui search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search...">
    <i class="search icon"></i>
  </div>
</div>
```

#### Credit Card Validation
We've added new validation rules for payment. These work with luhn and [non-luhn card numbers](http://stackoverflow.com/questions/7863058/does-the-luhn-algorithm-work-for-all-mainstream-credit-cards-discover-visa-m?answertab=votes#tab-top). If you only accept a certain set of credit cards you can specify that too.
> Try `4565340519181845` a test visa card number
```html
<form class="ui form segment">
  <div class="field">
    <label>Credit Card</label>
    <input name="card" type="text" value="4444444444444444">
  </div>
  <div class="field">
    <label>Visa / Amex</label>
    <input name="exact-card" type="text" value="4444444444444444">
  </div>
  <div class="ui submit button">Submit</div>
</form>
```
```javascript
$('.payment.example form')
  .form({
    on: 'blur',
    inline: true,
    fields: {
      card: {
        identifier  : 'card',
        rules: [
          {
            type   : 'creditCard',
            prompt : 'Please enter a valid credit card'
          }
        ]
      },
      exactCard: {
        identifier  : 'exact-card',
        rules: [
          {
            type   : 'creditCard[visa,amex]',
            prompt : 'Please enter a visa or amex card'
          }
        ]
      }
    }
  })
;
```

#### Cancellable Checkboxes
[Checkboxes](/modules/checkbox.html) now include four new callbacks `beforeChecked`, `beforeUnchecked`, `beforeDeterminate`, and `beforeIndeterminate`, returning `false` from these callbacks will cancel the action from occuring.
```html
<div class="ui checkbox">
  <input type="checkbox" name="example" />
  <label>Maybe this will work</label>
</div>
```
```javascript
$('.cancel.example .ui.checkbox')
  .checkbox({
    beforeChecked: function() {
      var
        luckyPerson = (Math.random() < 0.5)
      ;
      return luckyPerson;
    }
  })
;
```

## Theme Updates

#### Global Form Focus
Global variables have been added to modify form focus color across all components. The default theme now uses a light blue to signal selection.
```html
<form class="ui form">
  <div class="two fields">
    <div class="field">
      <label>First Name</label>
      <input type="text" name="first-name" placeholder="First Name">
    </div>
    <div class="field">
      <label>Last Name</label>
      <input type="text" name="last-name" placeholder="Last Name">
    </div>
  </div>
  <div class="field">
    <label>Gender</label>
    <select class="ui dropdown">
      <option value="">Gender</option>
      <option value="1">Male</option>
      <option value="0">Female</option>
    </select>
  </div>
  <div class="field">
    <div class="ui checkbox">
      <input type="checkbox" />
      <label>I agree to the Terms and Conditions</label>
    </div>
  </div>
  <button class="ui button" type="submit">Submit</button>
</form>
```

#### Updated Form Validation
[Form validation](/behaviors/form.html) now uses `basic label` for validation prompts.
```html
<form class="ui form">
  <div class="field">
    <label>First Name</label>
    <input type="text" name="first-name" placeholder="First Name">
  </div>
  <div class="field">
    <label>Last Name</label>
    <input type="text" name="last-name" placeholder="Last Name">
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" name="terms" />
      <label>I agree to the Terms and Conditions</label>
    </div>
  </div>
  <button class="ui button" type="submit">Submit</button>
</form>
```

#### Colored Basic Buttons
[Basic colored buttons](/elements/button.html#basic) now are colored without `hover`, making the style more similar to common usage on most sites.
```html
<button class="ui red basic button">Red</button>
<button class="ui orange basic button">Orange</button>
<button class="ui yellow basic button">Yellow</button>
<button class="ui olive basic button">Olive</button>
<button class="ui green basic button">Green</button>
<button class="ui teal basic button">Teal</button>
<button class="ui blue basic button">Blue</button>
<button class="ui violet basic button">Violet</button>
<button class="ui purple basic button">Purple</button>
<button class="ui pink basic button">Pink</button>
<button class="ui brown basic button">Brown</button>
<button class="ui grey basic button">Grey</button>
<button class="ui black basic button">Black</button>
```

#### Labeled Icon Menu
Horizontal `labeled icon menu` now use stacked icons to appear more in-tune with common icon menu usage.
```html
<div class="ui three item labeled icon inverted menu">
  <a class="active red item">
    <i class="gamepad icon"></i>
    Games
  </a>
  <a class="pink item">
    <i class="video camera icon"></i>
    Channels
  </a>
  <a class="blue item">
    <i class="video play icon"></i>
    Videos
  </a>
</div>
```

## 2.0

### Introduction

#### The Devil is in the Details
2.0 brings a whopping set of changes to the project:

*   **129** enhancements
*   **118** bug fixes
*   **3** new components
*   Rewrites of many components including [menu](/collections/menu.html), and [input](/elements/input.html)

There's just too much to cover in one page, but we've tried our best to give you examples of some of the new features available in 2.0

To see the full list of what's changed check out the project's release notes.

[View Release Notes](https://github.com/Semantic-Org/Semantic-UI/blob/<%= @getBranch() %>/RELEASE-NOTES.md#version-200---june-30-2015)

## Global Changes

#### Flexbox All The Things
[Flexbox](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Flexible_boxes) allows for elements to intuitively resize to fill available space, making many complex layouts much simpler.

13 components: [Form](/collections/form.html), [Grid](/collections/grid.html), [Menu](/collections/menu.html), [Message](/elements/message.html), [Button](/elements/button.html), [Segment](/elements/segment.html), [Step](/elements/step.html), [Dropdown](/modules/dropdown.html), [Modal](/modules/modal.html), [Feed](/views/feed.html), [Statistic](/views/statistics.html), [Card](/views/card.html), [Item](/views/item.html) now use [flex](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Flexible_boxes) for positioning.

#### Complete Spectrum
Semantic now includes twelve named colors, enough for most languages to [distinguish between colors](https://en.wikipedia.org/wiki/Linguistic_relativity_and_the_color_naming_debate#Berlin_and_Kay). New in 2.0 are: olive, violet, brown and grey.
```html
<a class="ui grey label">Grey</a>
<a class="ui red pointing label">Red</a>
<a class="ui orange tag label">Orange</a>
<a class="ui yellow bottom pointing label">Yellow</a>
<a class="ui olive label">
  <i class="mail icon"></i>
  Olive
</a>
<a class="ui green right pointing label">Green</a>
<a class="ui teal label">
  Teal
  <div class="detail">Detail</div>
</a>
<a class="ui blue image label">
  <img src="/images/avatar2/small/elyse.png">
  Blue
</a>
<a class="ui violet label">
  Violet
</a>
<a class="ui purple label">
  Purple
  <i class="delete icon"></i>
</a>
<div class="ui horizontal segments">
  <div class="ui segment">
    <div class="ui pink top left ribbon label">Pink</div>
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
  <div class="ui segment">
    <div class="ui brown right ribbon label">Brown</div>
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
</div>
```

#### New Default Theme
All components have received a face-lift for 2.0. Styles give slightly more negative space and a few idiosyncratic design touches have been removed.

#### More Precise EM Values
EM sizing has been improved in 2.0, with all values rounding to exact pixel values. This helps common relative sizing pitfalls like rounding errors in vertical alignment.

Em variables now use new globally calculated em ratios, like `@relative4px`, to express pixel values in terms of root em size. This makes sure components don't include confusing decimal or fractional values when dealing with sizing.

## Grids

#### Flexbox Grid
Grids in 2.0 now use [flexbox](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Flexible_boxes) so columns are always equal height across rows.
```html
<div class="ui three column divided grid">
  <div class="row">
    <div class="column">
      <div class="ui segment">
        1
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        1
      </div>
      <div class="ui segment">
        2
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        1
      </div>
      <div class="ui segment">
        2
      </div>
      <div class="ui segment">
        3
      </div>
    </div>
  </div>
</div>
```

#### Grids Create Themselves
The new [equal width](/collections/grid.html#equal-width) variation adjusts column widths automatically splitting available width between columns.
```html
<div class="ui equal width grid">
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
</div>
```
> If a column has a specified width, other columns will adapt to take available space around it.
```html
<div class="ui equal width grid">
  <div class="column"></div>
  <div class="eight wide column"></div>
  <div class="column"></div>
</div>
```

#### Containers
[Containers](/elements/container.html) have been added as a simple way to limit content width.
```html
<div class="ui container">
  <div class="ui three column grid">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
</div>
```

#### Stretched rows
The new [stretched](/collections/grid.html#stretched) variation makes vertically aligning layouts much simpler. Columns will not only match heights, but stretch their contents to match heights.
```html
<div class="ui three column stretched grid">
  <div class="column">
    <div class="ui segment">
      1
    </div>
    <div class="ui segment">
      2
    </div>
  </div>
  <div class="column">
    <div class="ui segment">
      <img class="ui image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="column">
    <div class="ui segment">
      1
    </div>
    <div class="ui segment">
      2
    </div>
  </div>
</div>
```

## Dropdowns

#### Multiple Selection
Multiple select dropdowns are now available, and can generate automatically from standard HTML selects.

Dropdowns now all support advanced keyboard shortcuts like `pagedown`, `delete`, `shift+left` `ctrl+click`, and selection using first letter of item.

Additionally dropdowns will now automatically open `upward` if there is not enough space available in the viewport below a dropdown.
```html
<select class="ui fluid dropdown" multiple>
  <%- @partial('examples/single/state-options') %>
</select>
```

#### User Tagging
All dropdowns, single and multiple now support user tagging. Values can be automatically separated by a delimiter and placed in a hidden input, or extend an existing select element.
```javascript
$('.ui.dropdown')
  .dropdown({
    allowAdditions: true
  })
;
```
```html
<div class="ui form">
  <div class="two fields">
    <div class="field">
      <label>Primary Skill</label>
      <div class="ui search selection dropdown">
        <input name="primary-skill" type="hidden" />
        <i class="dropdown icon"></i>
        <div class="default text">Skills</div>
        <div class="menu">
          <%- @partial('examples/single/preset-menu') %>
        </div>
      </div>
    </div>
    <div class="field">
      <label>Skills</label>
      <div class="ui multiple search selection dropdown">
        <input name="all-skills" type="hidden" />
        <i class="dropdown icon"></i>
        <div class="default text">Skills</div>
        <div class="menu">
          <%- @partial('examples/single/preset-menu') %>
        </div>
      </div>
    </div>
  </div>
</div>
```

#### Remote Data
All dropdowns now support loading remote data. Selected name value pairs retrieved remotely are stored in [sessionStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage) so that selected values are repopulated correctly even after a page refresh.

Try refreshing the page and searching the same letter, results will appear instantly without a server roundtrip.
```javascript
// somewhere in app
$.api.settings.api = {
  queryTags: '//api.semantic-ui.com/tags/{query}'
};
$('.ui.dropdown')
  .dropdown({
    apiSettings: {
      action: 'queryTags'
    }
  })
;
```
```html
<div class="ui form">
  <div class="two fields">
    <div class="field">
      <label>Favorite Animal</label>
      <div class="ui search selection dropdown">
        <input type="hidden">
        <i class="dropdown icon"></i>
        <input type="text" class="search">
        <div class="default text">Select one...</div>
      </div>
    </div>
    <div class="field">
      <label>Favorite Animals</label>
      <div class="ui multiple search selection dropdown">
        <input type="hidden">
        <i class="dropdown icon"></i>
        <input type="text" class="search">
        <div class="default text">Select...</div>
      </div>
    </div>
  </div>
</div>
```

#### Scrolling Menus
[Scrolling menu](/modules/dropdown.html#scrolling) and nested menus are now supported.

Listing choices in a nested menu will still give all the same keyboard shortcuts and filtering as regular menus.
```html
<div class="ui floating dropdown labeled icon button">
  <i class="filter icon"></i>
  <span class="text">Filter Posts</span>
  <div class="menu">
    <div class="ui icon search input">
      <i class="search icon"></i>
      <input type="text" placeholder="Search tags...">
    </div>
    <div class="divider"></div>
    <div class="header">
      <i class="tags icon"></i>
      Tag Label
    </div>
    <div class="scrolling menu">
      <div class="item">
        <div class="ui violet empty circular label"></div>
        Already Fixed
      </div>
      <div class="item">
        <div class="ui blue empty circular label"></div>
        Announcement
      </div>
      <div class="item">
        <div class="ui black empty circular label"></div>
        Cannot Fix
      </div>
      <div class="item">
        <div class="ui green empty circular label"></div>
        Discussion
      </div>
      <div class="item">
        <div class="ui orange empty circular label"></div>
        Enhancement
      </div>
      <div class="item">
        <div class="ui red empty circular label"></div>
        Important
      </div>
      <div class="item">
        <div class="ui pink empty circular label"></div>
        Interesting
      </div>
      <div class="item">
        <div class="ui purple empty circular label"></div>
        News
      </div>
      <div class="item">
        <div class="ui yellow empty circular label"></div>
        Off Topic
      </div>
      <div class="item">
        <div class="ui brown empty circular label"></div>
        Up Next
      </div>
    </div>
  </div>
</div>
```

#### Advanced Shortcuts
Dropdowns now support advanced shortcuts like `page down` and `page up`, scrolling to selection on first letter press, i.e. "N" for New York, `shift+left/right` for group selection, and `ctrl+click` for modifying groups.
```html
<img class="ui image" src="/images/gif/multi-shortcuts.gif">
```

#### Much More
Dropdowns support many, many new features, including:

*   Maximum selection count is supported for multiple selects
*   Mutation observers will now watch for changes in menus or the elements they are generated from and will update choices automatically
*   Custom templated error messages are now supported with dropdowns

## API

#### Local Caching
API now supports [sessionStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage) caching. This setting makes repeated requests to a URL return results instantly across a user's session, drastically improving performance for components like [search](/modules/search.html).

Try refreshing the page and searching the same letter, results will appear instantly without a server roundtrip.
```javascript
$('.ui.dropdown')
  .dropdown({
    apiSettings: {
      cache : 'local',
      url: '//api.semantic-ui.com/tags/{query}'
    }
  })
;
```
```html
<div class="ui form">
  <div class="field">
    <label>Favorite Animal</label>
    <div class="ui search selection dropdown">
      <input type="hidden">
      <i class="dropdown icon"></i>
      <input type="text" class="search">
      <div class="default text">Select one...</div>
    </div>
  </div>
</div>
```

#### Translates Any API
[API](/behaviors/api.html) now lets you adjust a server's JSON response using a new callback, [onResponse](/behaviors/api.html#response-callbacks). This can let you restructure third party APIs to match your local data requirements.
```html
<div class="ui search">
  <div class="ui left icon input">
    <input class="prompt" type="text" placeholder="Search GitHub">
    <i class="github icon"></i>
  </div>
</div>
```
```javascript
$('.ui.search')
  .search({
    type          : 'category',
    minCharacters : 3,
    apiSettings   : {
      onResponse: function(githubResponse) {
        var
          response = {
            results : {}
          }
        ;
        // translate GitHub API response to work with search
        $.each(githubResponse.items, function(index, item) {
          var
            language   = item.language || 'Unknown',
            maxResults = 8
          ;
          if(index >= maxResults) {
            return false;
          }
          // create new language category
          if(response.results[language] === undefined) {
            response.results[language] = {
              name    : language,
              results : []
            };
          }
          // add result to category
          response.results[language].results.push({
            title       : item.name,
            description : item.description,
            url         : item.html_url
          });
        });
        return response;
      },
      url: '//api.github.com/search/repositories?q={query}'
    }
  })
;
```

#### Mocked Responses
[API](/behaviors/api.html) now supports mocked responses, letting you specify how responses are returned in advance.
