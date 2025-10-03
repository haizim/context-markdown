# Embed

An embed displays content from other websites like YouTube videos or Google Maps

## Overview

### When to Use

#### Responsive Aspect Ratio
Embeds use an [instrinsic aspect ratio](http://alistapart.com/article/creating-intrinsic-ratios-for-video) which allows them to resize responsively based on their expected aspect ratio and not by using a single specified width or height.

#### Only Load After Interaction
Including an `iframe` embed directly will automatically load all iframe contents on page load which can drastically reduce the responsiveness of a page.

Semantic's embed combats this by not  loading iframe content until a user has interacted with your embed's placeholder content.

To give you an idea of how much file size including an embed will add to your page load see the chart below
> The following are download estimates taken from firebug and a single sample embed. Individual results may vary.

| Network | Embed Size |
|---|---|
| Google Maps | 237kb |
| YouTube | 380kb |
| Vimeo | 81kb |

## Definition

### Types

#### YouTube
An embed can be used to display [YouTube](http://www.youtube.com) Content

```html
<div class="ui embed"
  data-source="youtube"
  data-id="O6Xo21L0ybE"
  data-placeholder="/images/image-16by9.png">
</div>
```

#### Vimeo
An embed can be used to display [Vimeo](http://www.vimeo.com) content.

```html
<div class="ui embed"
  data-source="vimeo"
  data-id="125292332"
  data-placeholder="/images/vimeo-example.jpg">
</div>
```

#### Custom Content
An embed can display any web content
> Embeds use an intrinsic aspect ratios to embed content responsively. Content will preserve their intrinsic aspect ratio for all browser sizes responsively
```html
<div class="ui embed"
  data-url="http://www.myfav.es/jack"
  data-placeholder="/images/image-16by9.png"
  data-icon="right circle arrow"
>
</div>
```

## Variations

#### Aspect Ratio
An embed can specify an alternative aspect ratio
```html
<div class="ui 4:3 embed"
  data-source="youtube"
  data-id="HTZudKi36bo"
  data-placeholder="/images/4by3.jpg">
</div>
```

## Usage

### Initializing

#### Specifying a URL
Specifying a url will automatically match to an embed source using the domain of the url.
```javascript
$('.url.example .ui.embed').embed();
```
```html
<div class="ui embed"
  data-url="https://www.youtube.com/embed/O6Xo21L0ybE"
  data-placeholder="/images/bear-waving.jpg"
></div>
```

#### Using Content IDs
Embed is designed to automatically generate urls from content ids. This way your site's backend can store meaningful content metadata and not worry about generating urls.
```javascript
$('.content.example .ui.embed').embed();
```
```html
<div class="ui embed"
  data-source="youtube"
  data-id="O6Xo21L0ybE"
></div>
```

#### Specifying Metadata
Other settings like icons and placeholder images can be specified in metadata overriding presets for a site.
```javascript
$('.metadata.example .ui.embed').embed();
```
```html
<div class="ui embed"
  data-source="youtube"
  data-id="O6Xo21L0ybE"
  data-icon="video"
  data-placeholder="/images/bear-waving.jpg"
></div>
```

#### Specifying Programmatically
You can also specify embed settings at run-time in the settings object.
```javascript
$('.custom.example .ui.embed').embed({
  source      : 'youtube',
  id          : 'O6Xo21L0ybE',
  placeholder : '/images/bear-waving.jpg'
});
```
```html
<div class="ui embed"></div>
```

#### Specifying New Sources
Embed comes with two predefined embed sources, but can be extended with custom sources. Each source specifies default parameters and their mappings to settings, a templated url, and what icon should be used for overlays

Extending `$.fn.embed.settings.sources` allows you to use other proprietary embeds.
```javascript
// built in
$.fn.embed.settings.sources = {
  youtube: {
    name   : 'youtube',
    type   : 'video',
    icon   : 'video play',
    domain : 'youtube.com',
    url    : '//www.youtube.com/embed/{id}',
    parameters: function(settings) {
      return {
        autohide       : !settings.showUI,
        autoplay       : settings.autoplay,
        color          : settings.colors || undefined,
        hq             : settings.hd,
        jsapi          : settings.api,
        modestbranding : 1
      };
    }
  },
  vimeo: {
    name   : 'vimeo',
    type   : 'video',
    icon   : 'video play',
    domain : 'vimeo.com',
    url    : '//www.youtube.com/embed/{id}',
    parameters: function(settings) {
      return {
        api      : settings.api,
        autoplay : settings.autoplay,
        byline   : settings.showUI,
        color    : settings.colors || undefined,
        portrait : settings.showUI,
        title    : settings.showUI
      };
    }
  }
};
```

## Behaviors
All the following behaviors can be called using the syntax:
```javascript
$('.your.element')
  .embed('behavior name', argumentOne, argumentTwo)
;
```

```html
<table class="ui definition celled sortable table segment">
  <thead>
    <th>Behavior</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>change(source, id, url)</td>
      <td>Changes iframe to a new content source</td>
    </tr>
    <tr>
      <td>reset</td>
      <td>Removes embed and shows placeholder content if available</td>
    </tr>
    <tr>
      <td>show</td>
      <td>Shows embed content</td>
    </tr>
    <tr>
      <td>hide</td>
      <td>Hides embed content and shows placeholder content</td>
    </tr>
    <tr>
      <td>get id</td>
      <td>Returns current content id</td>
    </tr>
    <tr>
      <td>get placeholder</td>
      <td>Returns placeholder image url</td>
    </tr>
    <tr>
      <td>get sources</td>
      <td>Returns source name</td>
    </tr>
    <tr>
      <td>get type</td>
      <td>Returns source type</td>
    </tr>
    <tr>
      <td>get url</td>
      <td>Returns URL with all parameters added</td>
    </tr>
    <tr>
      <td>has placeholder</td>
      <td>Returns whether embed content has placeholder</td>
    </tr>
    <tr>
      <td>destroy</td>
      <td>Destroys instance and removes all events</td>
    </tr>
  </tbody>
</table>
```

## Settings

### Embed Settings
Settings to configure video behavior
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th>Setting</th>
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>icon</td>
      <td>false</td>
      <td>Specifies an icon to use with placeholder content</td>
    </tr>
    <tr>
      <td>source</td>
      <td>false</td>
      <td>Specifies a source to use, if no source is provided it will be determined from the domain of a specified url.</td>
    </tr>
    <tr>
      <td>url</td>
      <td>false</td>
      <td>Specifies a url to use for embed</td>
    </tr>
    <tr>
      <td>id</td>
      <td>false</td>
      <td>Specifies an id value to replace with the `{id}` value found in templated urls</td>
    </tr>
    <tr>
      <td>parameters</td>
      <td>false</td>
      <td>Specify an object containing key/value pairs to add to the iframes GET parameters</td>
    </tr>
  </tbody>
</table>
```

### Video Settings
Settings to configure video behavior

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th>Setting</th>
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>autoplay</td>
      <td>auto</td>
      <td>Default setting `auto` will only autoplay content when a placeholder is specified. Setting to true or false will force autoplay.</td>
    </tr>
    <tr>
      <td>color</td>
      <td>#444444</td>
      <td>Specifies a default chrome color with Vimeo or YouTube.</td>
    </tr>
    <tr>
      <td>url</td>
      <td>false</td>
      <td>Specifies a url to use for embed</td>
    </tr>
    <tr>
      <td>hd</td>
      <td>true</td>
      <td>Whether to prefer HD content</td>
    </tr>
    <tr>
      <td>brandedUI</td>
      <td>false</td>
      <td>Whether to show networks branded UI like title cards, or after video calls to action.</td>
    </tr>
  </tbody>
</table>
```

#### Callbacks
Callbacks specify a function to occur after a specific behavior.

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <tr>
      <th class="four wide"></th>
      <th class="four wide">Parameters</th>
      <th>Context</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>onCreate</td>
      <td>url</td>
      <td>$module</td>
      <td>Callback when iframe is generated</td>
    </tr>
    <tr>
      <td>onDisplay</td>
      <td></td>
      <td>$module</td>
      <td>Whenever an iframe contents is shown</td>
    </tr>
    <tr>
      <td>onPlaceholderDisplay</td>
      <td></td>
      <td>$module</td>
      <td>Callback immediately before Embed is removed from DOM</td>
    </tr>
    <tr>
      <td>onEmbed</td>
      <td>parameters</td>
      <td>$module</td>
      <td>Callback when module parameters are determined. Allows you to adjust parameters at run time by returning a new parameters object.</td>
    </tr>
  </tbody>
</table>
```

### DOM Settings
DOM settings specify how this module should interface with the DOM
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th>Setting</th>
    <th class="six wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>namespace</td>
      <td>embed</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>selector</td>
      <td>
        <div class="code">
selector : {
  embed       : '.embed',
  placeholder : '.placeholder',
  play        : '.play'
}
        </div>
      </td>
      <td>DOM Selectors used internally</td>
    </tr>
    <tr>
      <td>metadata</td>
      <td>
        <div class="code">
metadata    : {
  id          : 'id',
  icon        : 'icon',
  placeholder : 'placeholder',
  source      : 'source',
  url         : 'url'
}
        </div>
      </td>
      <td>HTML Data attributes used to store data</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
className : {
  active : 'active',
  embed  : 'embed'
}
        </div>
      </td>
      <td>Class names used to attach style to state</td>
    </tr>
    <tr>
      <td>templates</td>
      <td colspan="2">
        <div class="code">
$.fn.embed.settings.templates = {
  iframe: function(url, parameters) {
    // returns html for iframe
  },
  placeholder: function(image, icon) {
   // returns html for placeholder element
  }
}
        </div>
      </td>
    </tr>
    <tr>
      <td>metadata</td>
      <td colspan="2">
        <div class="code">
metadata    : {
  id          : 'id',
  icon        : 'icon',
  placeholder : 'placeholder',
  source      : 'source',
  url         : 'url'
}
        </div>
      </td>
    </tr>
    <tr>
      <td>errors</td>
      <td colspan="2">
        <div class="code">
error : {
  noURL  : 'No URL specified',
  method : 'The method you called is not defined'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```

### Debug Settings
Debug settings controls debug output to the console

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th>Setting</th>
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>Embed</td>
      <td>Name used in debug logs</td>
    </tr>
    <tr>
      <td>silent</td>
      <td>False</td>
      <td>Silences all console output including error messages, regardless of other debug settings.</td>
    </tr>
    <tr>
      <td>debug</td>
      <td>False</td>
      <td>Provides standard debug output to console</td>
    </tr>
    <tr>
      <td>performance</td>
      <td>True</td>
      <td>Provides standard debug output to console</td>
    </tr>
    <tr>
      <td>verbose</td>
      <td>True</td>
      <td>Provides ancillary debug output to console</td>
    </tr>
  </tbody>
</table>
```
