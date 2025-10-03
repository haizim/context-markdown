## === layout.md ===

# Layouts

Examples of using Semantic UI

## Starter
Examples to introduce components and their function

*   [Theming](/examples/theming.html)
    *   Examples of many common UI components, useful for testing custom themes.
*   [Responsive](/examples/responsive.html)
    *   Patterns for adjusting display for different devices.
*   [Grid](/examples/grid.html)
    *   An introduction to using Semantic UI grids.
*   [Attached Content](/examples/attached.html)
    *   Examples of content that can attach to other content.
*   [Bootstrap Migration](/examples/bootstrap.html)
    *   Examples of replacements for components found in Bootstrap.

## Pages
Starter page templates

*   [Homepage](/examples/homepage.html)
    *   A simple, responsive homepage design with sidebar.
*   [Sticky Menus](/examples/sticky.html)
    *   Using visibility APIs to fix content after passing position in page.
*   [Fixed Menu](/examples/fixed.html)
    *   Using a fixed menu with page content.
*   [Login Form](/examples/login.html)
    *   A full-screen login form.


## === theming.md ===

# Theming

An introduction to theming

## Preface

#### Progressive Truthfulness
> [Progressive truthfulness] is perhaps a better way to build models of physical objects...Start with a model that is fully detailed but only resembles what is wanted. Then, one adjusts one attribute after another, bringing the result ever closer to the mental vision of the new creation, or to the real properties of a real-world object
> ...Starting with exemplars that themselves have consistency of style ensures that such consistency is the designer's to lose.
> Frederick Brooks - [The Design of Design](http://www.amazon.com/gp/product/0201362988/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=0201362988&linkCode=as2&tag=seui-20&linkId=IUAKN3YQ7NNJ6IQ2)

Components in Semantic UI are designed to help developers adhere to [progressive truthfulness](https://books.google.com/books?id=0qG4TQi-e-4C&pg=PT234&lpg=PT234&dq=%22progressive+truthfulness%22+frederick+brooks&source=bl&ots=yrjNc6wnz8&sig=PJoYODuRku2A1kBoFOPfn4iGYnc&hl=en&sa=X&ved=0CCIQ6AEwAGoVChMImdSMpIOVxgIVCx-sCh3EQgBu#v=onepage&q=%22progressive%20truthfulness%22%20frederick%20brooks&f=false) in their development.

Instead of having to create components from a blank canvas, developers using Semantic UI only need to specify how their components should differ from the default theme using [CSS variables](http://lesscss.org/features/#variables-feature).

For developers who don't have time to hone a specific look-and-feel the default theme is elegant and neutral with a legible, open source sans-serif font `Lato`.

## Lead By Example

#### Recreating GitHub
Semantic UI includes an [example project](http://semantic-org.github.io/example-github/) designed to showcase theming. This project includes examples of creating a packaged theme, using component CSS overrides, and managing your themes with `theme.config`.

To get started click **the paint can** icon next to the notification button in the top right

The example project includes two HTML files, `index.html` is designed to swap themes using a sidebar, and uses precompiled CSS. `static.html` uses files outputted by Semantic UI and can be used alongside our [gulp pipeline](/introduction/build-tools.html) to try modifying themes hands on.

Some special things to note:

*   [Using site.variables](https://github.com/Semantic-Org/example-github/blob/master/semantic/src/themes/github/globals/site.variables) to modify page container sizes, default fonts, and colors
*   [Using overrides](https://github.com/Semantic-Org/example-github/blob/master/semantic/src/themes/github/collections/menu.overrides) with variables to add GitHub's specially formatted tab style
*   Combining multiple individual component themes together in one [theme.config](https://github.com/Semantic-Org/example-github/blob/master/semantic/src/theme.config)
*   Using a [custom icon font](https://github.com/Semantic-Org/example-github/blob/master/semantic/src/themes/github/elements/icon.overrides), and [modifying paths](https://github.com/Semantic-Org/example-github/blob/master/semantic/src/themes/github/elements/icon.variables) to assets.

[View Theming Demo](http://semantic-org.github.io/example-github/)

## Using Themes

#### Sitewide Defaults

Semantic UI includes twelve named colors. Components with color variations inherit these global variables when defining how colors should appear.

Each [level of inheritance](#theme-inheritance) includes a special file `site.variables` which defines theme-wide defaults that each component can extend.

Global variables use higher level abstractions, to avoid tedium in having to modify multiple properties to change the appearance of an element.

Other button shades like those used in `hover`, `active` and `focus` states are created by modifying the saturation and lightness of color variables, these derived variables will automatically adjust to your new color palette.

```less
/* In site.variables */
@primaryColor   : @pink;
@secondaryColor : @grey;
@red            : #B03060;
@orange         : #FE9A76;
@yellow         : #FFD700;
@olive          : #32CD32;
@green          : #016936;
@teal           : #008080;
@blue           : #0E6EB8;
@violet         : #EE82EE;
@purple         : #B413EC;
@pink           : #FF1493;
@brown          : #A52A2A;
@grey           : #A0A0A0;
@black          : #000000;
```

```html
<button class="ui primary button">
  Primary Button
</button>
<button class="ui secondary button">
  Secondary Button
</button>
<div class="ui horizontal divider">All Colors</div>
<button class="ui red button">Red</button>
<button class="ui orange button">Orange</button>
<button class="ui yellow button">Yellow</button>
<button class="ui olive button">Olive</button>
<button class="ui green button">Green</button>
<button class="ui teal button">Teal</button>
<button class="ui blue button">Blue</button>
<button class="ui violet button">Violet</button>
<button class="ui purple button">Purple</button>
<button class="ui pink button">Pink</button>
<button class="ui brown button">Brown</button>
<button class="ui grey button">Grey</button>
<button class="ui black button">Black</button>
```

#### Component Defaults
Components inherit default values from `site.variables` which they may redefine specifically for their component

For example, you could decide that instead of the boring default grey checkboxes, you want yours to include your site's branded colors. This can be accomplished in just a few variables.

```less
/* Checkbox */
@checkboxActiveBackground: @primaryColor;
@checkboxActiveBorderColor: @primaryColor;
@checkboxActiveCheckColor: @white;
/* Focused Checkbox */
@checkboxActiveFocusBackground: @primaryColorFocus;
@checkboxActiveFocusBorderColor: @primaryColorFocus;
@checkboxActiveFocusCheckColor: @white;
@checkboxTransition: none;
/* Radio */
@radioActiveBackground: @white;
@radioActiveBorderColor: @primaryColor;
@radioActiveBulletColor: @primaryColor;
/* Focused Radio */
@radioActiveFocusBackground: @white;
@radioActiveFocusBorderColor: @primaryColorFocus;
@radioActiveFocusBulletColor: @primaryColorFocus;
/* Slider */
@sliderOnLineColor: @primaryColor;
/* Focused Slider */
@sliderOnFocusLineColor: @primaryColorFocus;
```

```html
<div class="ui checkbox">
  <input type="checkbox" name="checkbox" checked >
  <label>Checkbox</label>
</div>

<div class="ui hidden divider"></div>
<div class="ui form">
  <div class="inline fields">
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="radio" checked />
        <label>A</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="radio" />
        <label>B</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="radio" />
        <label>C</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="radio" />
        <label>D</label>
      </div>
    </div>
  </div>
</div>

<div class="ui hidden divider"></div>
<div class="ui slider checkbox">
  <input type="checkbox" name="slider" checked>
  <label>Slider</label>
</div>
```

#### Using Packaged Themes
When you download Semantic UI all components will be set up to use the default theme. Semantic uses a special file `theme.config` for controlling your project's packaged theming configuration.

Packaged themes are applied per component, and not globally. This means you can specify individual themes for each component, mixing and matching from available themes.

The default `theme.config` will have all component values set to default. To choose a theme, simply change a component to match the theme name.

For example:
```
/*******************************
        Theme Selection
*******************************/

/* Global */
@site       : 'material';  /* Loads material site defaults */
@reset      : 'default';

/* Elements */
@button     : 'github'; /* But uses them with GitHub Buttons */
@container  : 'default';
@divider    : 'default';
@flag       : 'default';
@header     : 'default';
@icon       : 'default';
@image      : 'default';
@input      : 'default';
@label      : 'default';
@list       : 'default';
@loader     : 'default';
@rail       : 'default';
@reveal     : 'default';
@segment    : 'default';
@step       : 'default';

/* Collections */
@breadcrumb : 'default';
@form       : 'default';
@grid       : 'default';
@menu       : 'chubby'; /* Other UI can use different themes as well */
@message    : 'default';
@table      : 'default';

/* Modules */
@accordion  : 'default';
@checkbox   : 'default';
@dimmer     : 'default';
@dropdown   : 'default';
@embed      : 'default';
@modal      : 'default';
@nag        : 'default';
@popup      : 'default';
@progress   : 'default';
@rating     : 'default';
@search     : 'default';
@shape      : 'default';
@sidebar    : 'default';
@sticky     : 'default';
@tab        : 'default';
@transition : 'default';

/* Views */
@ad         : 'default';
@card       : 'default';
@comment    : 'default';
@feed       : 'default';
@item       : 'default';
@statistic  : 'default';
```

#### Browsing for Themes
Each UI definitions include a dropdown at the top of the page to preview themes included with the project.

Themes are **per component**, so although, for example, material themes are available for [menu](/collections/menu.html), [button](/elements/button.html), and [site](/globals/site.html), changing all values to "material" will produce an error for components which are not included in that theme.

## Composing a Component

#### Definition File
Each component includes a source CSS and Javascript file which declares how a components variables should affect its display on screen. Definition files are updated with each new release of Semantic UI, which may also include new variables.

Navigating definition files are a great way for developers who are comfortable with CSS to get an idea of how themes affect a components display.

Here's an abridged version of [button](/elements/button.html) with an explanation of each section of the file.

```less
/*******************************
                Theme
*******************************/

/* Define type and element to help locate theme files */
@type    : 'element';
@element : 'button';

/* Processes Variable Inheritance */
@import (multiple) '../../theme.config';

/* Create scope */
& {

/*******************************
               Button
*******************************/

/* Define Component */
.ui.button {
  cursor: pointer;
  display: inline-block;

  min-height: 1em;

  outline: none;
  border: none;
  vertical-align: @verticalAlign;
  background: @background;
  color: @textColor;

  font-family: @fontFamily;

  margin: 0em @horizontalMargin @verticalMargin 0em;
  padding: @verticalPadding @horizontalPadding (@verticalPadding + @shadowOffset);

  text-transform: @textTransform;
  text-shadow: @textShadow;
  font-weight: @fontWeight;
  line-height: @lineHeight;
  font-style: normal;
  text-align: center;
  text-decoration: none;

  border-radius: @borderRadius;
  box-shadow: @boxShadow;

  user-select: none;
  transition: @transition;
  will-change: @willChange;

  -webkit-tap-highlight-color: @tapColor;
}

/* Additional CSS removed for brevity */

/* Load CSS Overrides and Inline */
.loadUIOverrides();

}
```

#### Theme Files
Themes are made up of two files: a `.variables` file and a `.overrides` file. A theme can include both variables and overrides, or just either one alone.

#### Variables Files
A `.variables` file specifies variables which should be adjusted for a theme.

A theme's variable file only needs to include variables which are different for a theme.

#### Override Files
An .overrides file specifies additional CSS rules to be added to a definition for a theme. This file also has access to all inherited variables for a component.

## Cascading Inheritance

#### Theme Inheritance
Themes contain three separate levels of variable inheritance.

Each level of inheritance corresponds to a different level of permanence for a variable.

```html
<div class="ui fluid steps">
  <div class="step">
    <i class="lock icon"></i>
    <div class="content">
      <div class="title">Defaults</div>
      <div class="description">UI Defaults</div>
    </div>
  </div>
  <div class="step">
    <i class="download icon"></i>
    <div class="content">
      <div class="title">Packaged Theme</div>
      <div class="description">Distributable Packages</div>
    </div>
  </div>
<div class="step">
    <i class="user icon"></i>
    <div class="content">
      <div class="title">Site Theme</div>
      <div class="description">Site Specific Changes</div>
    </div>
  </div>
</div>
```

#### Default Theme
```html
<div class="ui breadcrumb">
  <div class="section">
    <i class="disabled folder icon"></i>
    src
  </div>
  <i class="right chevron icon divider"></i>
  <div class="section">
    <i class="disabled folder icon"></i>
    themes
  </div>
  <i class="right chevron icon divider"></i>
  <div class="active section">
    <i class="inverted circular teal folder icon"></i>
    default
  </div>
</div>
```
The default theme provides baseline variables for a component.

The best way to understand what variables are available for inclusion in a theme is to examine a component's default `.variables` file.

#### Packaged Theme
```html
<div class="ui breadcrumb">
  <div class="section">
    <i class="disabled folder icon"></i>
    src
  </div>
  <i class="right chevron icon divider"></i>
  <div class="section">
    <i class="disabled folder icon"></i>
    themes
  </div>
  <i class="right chevron icon divider"></i>
  <div class="active section">
    <i class="inverted circular teal folder icon"></i>
    theme-name
  </div>
</div>
```
Packaged themes are themes bundled together in a folder for distribution. These can be downloaded from the internet, or carried between projects.

Packaged themes can be used by modifying values in your [theme.config](#using-packaged-themes) file.

#### Site Theme
```html
<div class="ui breadcrumb">
  <div class="section">
    <i class="disabled folder icon"></i>
    src
  </div>
  <i class="right chevron icon divider"></i>
  <div class="active section">
    <i class="inverted circular teal folder icon"></i>
    site
  </div>
</div>
```
A site theme, not to be mistaken with `site.variables` a file located in every theme, is a special user theme that can be loaded on top of all other themes.

This is the best location to store changes that will be used on a single site. A site theme can be thought of as similar to a [child theme](https://codex.wordpress.org/Child_Themes) in Wordpress.

Site theme files **are optional includes** and can be safely removed if you do not need to add additional changes to a component on your project.
