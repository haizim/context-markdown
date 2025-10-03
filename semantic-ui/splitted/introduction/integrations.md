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
