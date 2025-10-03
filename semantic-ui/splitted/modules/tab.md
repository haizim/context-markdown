# Tab

A tab is a hidden section of content activated by a menu

## Definition

### Type

#### Tab
A basic tab
> A tab is hidden by default, and will only become visible when given the class name `active` or when activated with Javascript. For more information, see the usage section.
```html
<div class="ui top attached tabular menu">
  <div class="item">Tab</div>
</div>
<div class="ui bottom attached tab segment">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
```

## States

#### Active
A tab can be activated, and visible on the page
```html
<div class="ui top attached tabular menu">
  <div class="active item">Tab</div>
</div>
<div class="ui bottom attached active tab segment">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
```

#### Loading
A tab can display a loading indicator
```html
<div class="ui top attached tabular menu">
  <div class="active item">Tab</div>
</div>
<div class="ui bottom attached loading tab segment">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
```

## Examples

### Basic Examples

#### Basic Tabs
Tabs are connecting using paths specified in the `data-tab` attribute. Tab is then initialized in Javascript on the activating elements.
> To have a tab visible on page load, add the class `active` to both the initializing menu and the tab.
```html
<div class="ui top attached tabular menu">
  <a class="active item" data-tab="first">First</a>
  <a class="item" data-tab="second">Second</a>
  <a class="item" data-tab="third">Third</a>
</div>
<div class="ui bottom attached active tab segment" data-tab="first">
  First
</div>
<div class="ui bottom attached tab segment" data-tab="second">
  Second
</div>
<div class="ui bottom attached tab segment" data-tab="third">
  Third
</div>
```
```javascript
$('.menu .item')
  .tab()
;
```

#### Multiple Tab Groups
There are a several of ways to include independent tab groups on the same page, even with history. One of the easiest ways is provide a specific parent context for each tab group.
> If you are using tab contexts inside of tabs, you can also specify `childrenOnly: true` which will only look for tabs as the immediate children of the given context, or `context: 'parent'` a special keyword which avoids having to create unique selectors for each group.
```javascript
$('#context1 .menu .item')
  .tab({
    context: $('#context1')
  })
;
$('#context2 .menu .item')
  .tab({
    // special keyword works same as above
    context: 'parent'
  })
;
```
```html
<div id="context1">
  <div class="ui secondary menu">
    <a class="item" data-tab="first">First</a>
    <a class="item active" data-tab="second">Second</a>
    <a class="item" data-tab="third">Third</a>
  </div>
  <div class="ui tab segment" data-tab="first">
    <div class="ui top attached tabular menu">
      <a class="active item" data-tab="first/a">1A</a>
      <a class="item" data-tab="first/b">1B</a>
      <a class="item" data-tab="first/c">1C</a>
    </div>
    <div class="ui bottom attached active tab segment" data-tab="first/a">1A</div>
    <div class="ui bottom attached tab segment" data-tab="first/b">1B</div>
    <div class="ui bottom attached tab segment" data-tab="first/c">1C</div>
  </div>
  <div class="ui tab segment active" data-tab="second">
    <div class="ui top attached tabular menu">
      <a class="item" data-tab="second/a">2A</a>
      <a class="item" data-tab="second/b">2B</a>
      <a class="item active" data-tab="second/c">2C</a>
    </div>
    <div class="ui bottom attached tab segment" data-tab="second/a">2A</div>
    <div class="ui bottom attached tab segment" data-tab="second/b">2B</div>
    <div class="ui bottom attached tab segment active" data-tab="second/c">2C</div>
  </div>
  <div class="ui tab segment" data-tab="third">
    <div class="ui top attached tabular menu">
      <a class="item" data-tab="third/a">3A</a>
      <a class="item" data-tab="third/b">3B</a>
      <a class="item" data-tab="third/c">3C</a>
    </div>
    <div class="ui bottom attached tab segment" data-tab="third/a">3A</div>
    <div class="ui bottom attached tab segment" data-tab="third/b">3B</div>
    <div class="ui bottom attached tab segment" data-tab="third/c">3C</div>
  </div>
</div>
<div class="ui divider"></div>
<div id="context2">
  <div class="ui secondary menu">
    <a class="item" data-tab="fourth">Fourth</a>
    <a class="item active" data-tab="fifth">Fifth</a>
    <a class="item" data-tab="sixth">Sixth</a>
  </div>
  <div class="ui tab segment" data-tab="fourth">
    4
  </div>
  <div class="ui active tab segment" data-tab="fifth">
    5
  </div>
  <div class="ui tab segment" data-tab="sixth">
    6
  </div>
</div>
```

#### Default Paths
When you specify a path like `first/` after opening the tab it will look for the any child paths and open the first. In this example even if the path is `first/`, the tab corresponding with `first/a` will automatically also be open because it is the default child tab. This will work recursively for as many additional child tab groups as you include.
> Each of these examples is initialized with a context to prevent contamination with other tab examples on this page. This is not necessary unless using multiple tab systems on a single page.
```javascript
$('.paths.example .menu .item')
  .tab({
    context: '.paths.example'
  })
;
```
```html
<div class="ui pointing secondary menu">
  <a class="active item" data-tab="first">First</a>
  <a class="item" data-tab="second">Second</a>
  <a class="item" data-tab="third">Third</a>
</div>
<div class="ui active tab segment" data-tab="first">
  <div class="ui top attached tabular menu">
    <a class="active item" data-tab="first/a">1A</a>
    <a class="item" data-tab="first/b">1B</a>
    <a class="item" data-tab="first/c">1C</a>
  </div>
  <div class="ui bottom attached active tab segment" data-tab="first/a">1A</div>
  <div class="ui bottom attached tab segment" data-tab="first/b">1B</div>
  <div class="ui bottom attached tab segment" data-tab="first/c">1C</div>
</div>
<div class="ui tab segment" data-tab="second">
  <div class="ui top attached tabular menu">
    <a class="item" data-tab="second/a">2A</a>
    <a class="item" data-tab="second/b">2B</a>
    <a class="item" data-tab="second/c">2C</a>
  </div>
  <div class="ui bottom attached tab segment" data-tab="second/a">2A</div>
  <div class="ui bottom attached tab segment" data-tab="second/b">2B</div>
  <div class="ui bottom attached tab segment" data-tab="second/c">2C</div>
</div>
<div class="ui tab segment" data-tab="third">
  <div class="ui top attached tabular menu">
    <a class="item" data-tab="third/a">3A</a>
    <a class="item" data-tab="third/b">3B</a>
    <a class="item" data-tab="third/c">3C</a>
  </div>
  <div class="ui bottom attached tab segment" data-tab="third/a">3A</div>
  <div class="ui bottom attached tab segment" data-tab="third/b">3B</div>
  <div class="ui bottom attached tab segment" data-tab="third/c">3C</div>
</div>
```

### Remote Examples

#### Retreiving Remote Content
Using `auto: true` will load the tab's path from your server with additional headers to specify an in-page request. When [cache: true](#settings) is set, re-opening a tab will be loaded from cache without a server request.
> API requests for the following example have been faked using [mockResponse](/behaviors/api.html#using-custom-backends) API setting to avoid network overhead.
```javascript
$('.dynamic.example .menu .item')
  .tab({
    cache: false,
    // faking API request
    apiSettings: {
      loadingDuration : 300,
      mockResponse    : function(settings) {
        var response = {
          first  : 'AJAX Tab One',
          second : 'AJAX Tab Two',
          third  : 'AJAX Tab Three'
        };
        return response[settings.urlData.tab];
      }
    },
    context : 'parent',
    auto    : true,
    path    : '/'
  })
;
```
```html
<div class="ui pointing secondary menu">
  <a class="active item" data-tab="first">First</a>
  <a class="item" data-tab="second">Second</a>
  <a class="item" data-tab="third">Third</a>
</div>
<div class="ui active tab segment" data-tab="first">
  <h3 class="ui header">AJAX Tab One</h3>
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
<div class="ui tab segment" data-tab="second">
</div>
<div class="ui tab segment" data-tab="third">
</div>
```

#### Evaluating Scripts in HTML
By default, `script` tags included in HTML will only be evaluated on first load. To change this behavior you can adjust the `evaluateScripts` setting.
```javascript
$('.eval.example .menu .item')
  .tab({
    evaluateScripts : 'once',
    context         : 'parent',
    auto            : true,
    path            : '/'
  })
;
```
```html
<div class="ui pointing secondary menu">
  <a class="active item" data-tab="first">First</a>
  <a class="item" data-tab="second">Second</a>
  <a class="item" data-tab="third">Third</a>
</div>
<div class="ui active tab segment" data-tab="first">
  <h3 class="ui header">AJAX Tab One</h3>
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
<div class="ui tab segment" data-tab="second">
</div>
<div class="ui tab segment" data-tab="third">
</div>
```

### History Examples

#### Using Hash History
For static sites, or sites that only require simple history, in-page links can be used to trigger different local tab states
```javascript
$('.history.example .menu .item')
  .tab({
    context : '.history.example',
    history : true
  })
;
```
```html
<div class="ui pointing secondary menu">
  <a class="active item" data-tab="first">First</a>
  <a class="item" data-tab="second">Second</a>
  <a class="item" data-tab="third">Third</a>
</div>
<div class="ui active tab segment" data-tab="first">
  <div class="ui top attached tabular menu">
    <a class="active item" data-tab="first/a">1A</a>
    <a class="item" data-tab="first/b">1B</a>
    <a class="item" data-tab="first/c">1C</a>
  </div>
  <div class="ui bottom attached active tab segment" data-tab="first/a">1A</div>
  <div class="ui bottom attached tab segment" data-tab="first/b">1B</div>
  <div class="ui bottom attached tab segment" data-tab="first/c">1C</div>
</div>
<div class="ui tab segment" data-tab="second">
  <div class="ui top attached tabular menu">
    <a class="item" data-tab="second/a">2A</a>
    <a class="item" data-tab="second/b">2B</a>
    <a class="item" data-tab="second/c">2C</a>
  </div>
  <div class="ui bottom attached tab segment" data-tab="second/a">2A</div>
  <div class="ui bottom attached tab segment" data-tab="second/b">2B</div>
  <div class="ui bottom attached tab segment" data-tab="second/c">2C</div>
</div>
<div class="ui tab segment" data-tab="third">
  <div class="ui top attached tabular menu">
    <a class="item" data-tab="third/a">3A</a>
    <a class="item" data-tab="third/b">3B</a>
    <a class="item" data-tab="third/c">3C</a>
  </div>
  <div class="ui bottom attached tab segment" data-tab="third/a">3A</div>
  <div class="ui bottom attached tab segment" data-tab="third/b">3B</div>
  <div class="ui bottom attached tab segment" data-tab="third/c">3C</div>
</div>
```

#### Using HTML5 State
For sites that are able to replicate change on the server, tab can automatically map changes in tab navigation to [html5 state.](http://diveintohtml5.info/history.html)
> Since these docs are statically hosted on GitHub Pages, html5 state tabs are not demonstrable from the docs. You will need to try this example in your own code.
```javascript
$('.ui.menu .item')
  .tab({
    history : true,
    historyType : 'state',
    // base url for all other path changes
    path        : '/my/base/url'
  })
;
```

#### Setting Paths
Using `historyType: state` requires specifying a **base URL without any internal state**. This cannot be set automatically to `window.location` because all tabs with html5 state will appear as normal page urls, and route accordingly.

HTML5 state will only work with dynamic site back-ends because it requires each tab path to correctly route on the server to the appropriate content.
```javascript
$('.ui.menu .item')
  .tab({
    history: true,
    historyType: 'state'
    path: '/modules/tab.html'
  })
;
```
> Using an incorrect base path is a common error when using HTML5 state, and can cause unusual behaviors.

### AJAX Content

#### ...with automatic routing

Specifying the setting `auto: true`, will automatically retrieve content at a remote url matching the url set in the browser.

So for example the tab `inbox` will retrieve content from the URL `base-url/inbox/`

The URL will receive an addition HTTP Header `'X-Remote': true`. You can use this on your server's back-end to determine whether a request is an AJAX request from a tab, or a full page request.

Queries with `'X-Remote': true` should refresh only the tabbed content, while queries without are normal resources and should refresh **the entire page contents**

This uses a similar technique to [pJax](https://github.com/defunkt/jquery-pjax) or Rail's [turbolinks](https://github.com/rails/turbolinks/).

> There are a variety of settings for configuring dynamic content behavior. Visit the tab settings section for more information
```javascript
$('.dynamic.example .menu .item')
  .tab({
    context : '.dynamic.example',
    auto    : true,
    path    : '/modules/tab.html'
  })
;
```

#### ...with an API Behavior
Tabs provide an optional coupling with API which allow you to specify a templated API endpoint that a tab can query

Tabs will automatically pass the url variable `{$tab}` which can be replaced for RESTful API links.

To learn more about API behaviors built into semantic check out the API docs

[View API Docs](/behaviors/api.html)

## Behavior

All the following behaviors can be called using the syntax `$('.foo').tab('behavior name', argumentOne, argumentTwo)`

```html
<table class="ui definition celled table segment">
  <tr>
    <td>attach events(selector, event)</td>
    <td>Attaches tab action to given selector. Default event if none specified is toggle</td>
  </tr>
  <tr>
    <td>change tab(path)</td>
    <td>Changes tab to path</td>
  </tr>
  <tr>
    <td>set state(path)</td>
    <td>Sets current path to state</td>
  </tr>
  <tr>
    <td>get path</td>
    <td>Returns current path</td>
  </tr>
  <tr>
    <td>is tab</td>
    <td>Returns whether tab exists</td>
  </tr>
  <tr>
    <td>cache read(path)</td>
    <td>Returns cached HTML for path</td>
  </tr>
  <tr>
    <td>cache add(path, html)</td>
    <td>Sets cached HTML for path</td>
  </tr>
  <tr>
    <td>cache remove(path)</td>
    <td>Removes cached HTML for path</td>
  </tr>
</table>
```

## Settings

### Tab Settings
Form settings modify the tab behavior
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <tr>
      <th>Setting</th>
      <th class="four wide">Default</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>auto</td>
      <td>false</td>
      <td>Whether tab should load remote content as same url as history</td>
    </tr>
    <tr>
      <td>deactivate</td>
      <td>'siblings'</td>
      <td>When set to `siblings` will only deactivate elements that are DOM siblings with the activated element. When set to `all` the component will deactivate all other elements initialized at the same time.</td>
    </tr>
    <tr>
      <td>history</td>
      <td>false</td>
      <td>Whether to record history events for tab changes</td>
    </tr>
    <tr>
      <td>ignoreFirstLoad</td>
      <td>false</td>
      <td>Do not load content remotely on first tab load. Useful when open tab is rendered on server.</td>
    </tr>
    <tr>
      <td>evaluateScripts</td>
      <td>once</td>
      <td>Whether inline scripts in tab HTML should be parsed on tab load. Defaults to `once`, parsing only on first load. Can also be set to `true` or `false` to always parse or never parse inline scripts.</td>
    </tr>
    <tr>
      <td>alwaysRefresh</td>
      <td>false</td>
      <td>Tab should reload content every time it is opened</td>
    </tr>
    <tr>
      <td>deactivate <div class="ui horizontal label">2.2</div></td>
      <td>siblings</td>
      <td>Can be set to either `siblings` or `all`. Siblings will only de-activate tab activators that are `siblings` of the clicked element when a tab is selected. `All` will deactivate all other tab activators initialized at the same time.</td>
    </tr>
    <tr>
      <td>cacheType <div class="ui horizontal label">2.2</div></td>
      <td>response</td>
      <td>Can be set to either `response`, `DOM` or `html`. Using `DOM` will cache the a clone of the DOM tree, preserving all events as they existed on render. `response` will cache the original response on load, this way callbacks always receive the same content. Using `html` will cache the resulting html after all callbacks, making sure any changes to content are preserved.</td>
    </tr>
    <tr>
      <td>cache</td>
      <td>true</td>
      <td>Tab should reload content every time it is opened</td>
    </tr>
    <tr>
      <td>apiSettings</td>
      <td>false</td>
      <td>Settings object for [$.api](/behaviors/api.html) call</td>
    </tr>
    <tr>
      <td>historyType</td>
      <td>hash</td>
      <td>Can be set to **hash** or **state**. Hash will use an in-page link to create history events. State will use [DOM History](https://developer.mozilla.org/en-US/docs/Web/Guide/API/DOM/Manipulating_the_browser_history) and load pages from server on refresh.</td>
    </tr>
    <tr>
      <td>path</td>
      <td>false</td>
      <td>When using historyType `state` you must specify the base URL for all internal links.</td>
    </tr>
    <tr>
      <td>context</td>
      <td>false</td>
      <td>Tabs are limited to those found inside this context</td>
    </tr>
    <tr>
      <td>childrenOnly</td>
      <td>false</td>
      <td>If enabled limits tabs to children of passed context</td>
    </tr>
    <tr>
      <td>maxDepth</td>
      <td>25</td>
      <td>Maximum amount of nested tabs allowed (avoids recursion)</td>
    </tr>
  </tbody>
</table>
```

### Callbacks
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
      <td>onFirstLoad</td>
      <td>tabPath, parameterArray, historyEvent</td>
      <td>Tab</td>
      <td>Callback only the first time a tab is loaded</td>
    </tr>
    <tr>
      <td>onLoad</td>
      <td>tabPath, parameterArray, historyEvent</td>
      <td>Tab</td>
      <td>Callback every time a tab is loaded</td>
    </tr>
    <tr>
      <td>onRequest</td>
      <td>tabPath</td>
      <td>Tab</td>
      <td>Called when a tab begins loading remote content</td>
    </tr>
    <tr>
      <td>onVisible</td>
      <td>tabPath</td>
      <td>Tab</td>
      <td>Called after a tab becomes visible</td>
    </tr>
  </tbody>
</table>
```

### DOM Settings
DOM settings specify how this module should interface with the DOM
```html
<table class="ui celled definition table segment">
  <thead>
    <tr>
      <th>Setting</th>
      <th class="six wide">Default</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>namespace</td>
      <td>tab</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>templates</td>
      <td>
        <div class="code">
templates    : {
  // returns page title
  determineTitle: function(tabArray) {}
}
        </div>
      </td>
      <td>Functions used to return content</td>
    </tr>
    <tr>
      <td>selector</td>
      <td>
        <div class="code">
selector    : {
  tabs : '.ui.tab',
  parent : '.ui:not(.menu)'
}
        </div>
      </td>
      <td>Selectors used by module</td>
    </tr>
    <tr>
      <td>metadata</td>
      <td>
        <div class="code">
metadata : {
  tab    : 'tab',
  loaded : 'loaded',
  promise: 'promise'
}
        </div>
      </td>
      <td>DOM metadata used by module</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
className   : {
  loading : 'loading',
  active  : 'active'
}
        </div>
      </td>
      <td>Class names used to attach style to state</td>
    </tr>
  </tbody>
</table>
```

### Debug Settings
Debug settings controls debug output to the console

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <tr>
      <th>Setting</th>
      <th class="four wide">Default</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>Tab</td>
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
    <tr>
      <td>errors</td>
      <td colspan="2">
        <div class="code">
error: {
  api        : 'You attempted to load content without API module',
  method     : 'The method you called is not defined',
  missingTab : 'Activated tab cannot be found for this context.',
  noContent  : 'The tab you specified is missing a content url.',
  path       : 'History enabled, but no path was specified',
  recursion  : 'Max recursive depth reached',
  state      : 'The state library has not been initialized'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```
