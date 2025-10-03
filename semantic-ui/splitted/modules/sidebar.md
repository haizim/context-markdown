# Sidebar

A sidebar hides additional content beside a page.

## Types

#### Sidebar
A sidebar
> Although sidebars can be used with any content, in most cases, sidebars are used with [inverted vertical menu](/collections/menu.html#vertical). Please see the [usage tab](#/usage) for more details.
```html
<body>
  <div class="ui sidebar inverted vertical menu">
    <a class="item">
      1
    </a>
    <a class="item">
      2
    </a>
    <a class="item">
      3
    </a>
  </div>
  <div class="pusher">
    <!-- Site content !-->
  </div>
</body>
```
```javascript
$('.ui.sidebar')
  .sidebar('toggle')
;
```
```html
<div class="ui left demo vertical inverted sidebar labeled icon menu">
  <a class="item">
    <i class="home icon"></i>
    Home
  </a>
  <a class="item">
    <i class="block layout icon"></i>
    Topics
  </a>
  <a class="item">
    <i class="smile icon"></i>
    Friends
  </a>
</div>
```
```javascript
$('.ui.labeled.icon.sidebar')
  .sidebar('toggle')
;
```

## States

### Sidebar

#### Visible
A sidebar can be visible on the page
> To have a sidebar appear on page load simply add the class `visible` to the sidebar.
```html
<div class="ui visible sidebar"></div>
```

### Pusher

#### Dimmed
A pusher can be dimmed
```html
<div class="dimmed pusher"></div>
```

## Variations

#### Direction
A sidebar can appear on different sides of the page

```html
<div class="ui top sidebar"></div>
<div class="ui right sidebar"></div>
<div class="ui bottom sidebar"></div>
<div class="ui left sidebar"></div>
```

#### Width
A sidebar can specify its width
```html
<div class="ui message">
  A sidebar will automatically adjust its animations to match any custom size specified in CSS
</div>
<div class="ui thin sidebar"></div>
<div class="ui very thin sidebar"></div>
<div class="ui sidebar"></div>
<div class="ui wide sidebar"></div>
<div class="ui very wide sidebar"></div>
```

## Usage

### Set-up

#### Page Structure
Using a sidebar requires a specific page structure. For optimal performance your page should be already set-up with this structure before initializing a sidebar.
> Sidebar will automatically add the correct layout on first load if it is not set-up, however fixing your page's layout on load **will reduce performance and is not recommended**.
```html
<body>
  <div class="ui sidebar">
    ...
  </div>
  <div class="pusher">
    Your site's actual content
  </div>
</body>
```

#### Using with Menu
Sidebars can be any content, however the most common type of content to display off-canvas is a [menu](/collections/menu.html). To understand the required structure for a menu, please refer to the [menu documentation](/collections/menu.html).
```html
<body>
  <div class="ui left vertical menu sidebar">
    <a class="item">
      Item 1
    </a>
    <a class="item">
      Item 2
    </a>
    <a class="item">
      Item 3
    </a>
  </div>
  <div class="pusher">
    <!-- Site content !-->
  </div>
</body>
```

#### Using Fixed Content
Any fixed position content that should move with page content when your sidebar is visible, should receive the class name `fixed` and exist as a sibling element to your sidebar.
> Fixed content that is not included adjacent to your `pusher` **will lose its positioning** when a sidebar is shown.
```html
<body>
  <div class="ui sidebar">
    ...
  </div>
  <div class="ui top fixed menu">
    ...
  </div>
  <div class="pusher">
    Your site's actual content
  </div>
</body>
```

#### iOS Sidebars
Sidebars use a special fix for iOS that are added using `userAgent` detection.

This should have no meaningful affect on your code, but will prevent the canvas from incorrectly autoresizing when a sidebar opens.
```css
html.ios {
  overflow-x: hidden;
  -webkit-overflow-scrolling: touch;
}
html.ios,
html.ios body {
  height: initial !important;
}
```

## Behavior

All the following behaviors can be called using the syntax:
```javascript
$('.your.element')
  .sidebar('behavior name', argumentOne, argumentTwo)
;
```

```html
<table class="ui definition celled sortable table segment">
  <thead>
    <tr>
      <th>Behavior</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>attach events(selector, event)</td>
      <td>Attaches sidebar action to given selector. Default event if none specified is toggle</td>
    </tr>
    <tr>
      <td>show</td>
      <td>Shows sidebar</td>
    </tr>
    <tr>
      <td>hide</td>
      <td>Hides sidebar</td>
    </tr>
    <tr>
      <td>toggle</td>
      <td>Toggles visibility of sidebar</td>
    </tr>
    <tr>
      <td>is visible</td>
      <td>Returns whether sidebar is visible</td>
    </tr>
    <tr>
      <td>is hidden</td>
      <td>Returns whether sidebar is hidden</td>
    </tr>
    <tr>
      <td>push page</td>
      <td>Pushes page content to be visible alongside sidebar</td>
    </tr>
    <tr>
      <td>get direction</td>
      <td>Returns direction of current sidebar</td>
    </tr>
    <tr>
      <td>pull page</td>
      <td>Returns page content to original position</td>
    </tr>
    <tr>
      <td>add body CSS</td>
      <td>Adds stylesheet to page head to trigger sidebar animations</td>
    </tr>
    <tr>
      <td>remove body CSS</td>
      <td>Removes any inline stylesheets for sidebar animation</td>
    </tr>
    <tr>
      <td>get transition event</td>
      <td>Returns vendor prefixed transition end event</td>
    </tr>
  </tbody>
</table>
```

## Examples

#### Transitions
Not all sidebar transitions are available for every sidebar direction, or when multiple sidebars are visible at a time.
```html
<table class="ui celled definition table">
  <thead>
    <tr>
      <th></th>
      <th>Multiple Visible <i class="help circle link icon" data-content="Whether multiple sidebars of this type can be visible at same time"></i></th>
      <th>Supports Vertical Sidebars</th>
      <th>Supports Horizontal Sidebars</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Overlay</td>
      <td><i class="green check icon"></i></td>
      <td><i class="green check icon"></i></td>
      <td><i class="green check icon"></i></td>
    </tr>
    <tr>
      <td>Push</td>
      <td><i class="green check icon"></i></td>
      <td><i class="green check icon"></i></td>
      <td><i class="green check icon"></i></td>
    </tr>
    <tr>
      <td>Scale Down</td>
      <td><i class="green check icon"></i></td>
      <td><i class="green check icon"></i></td>
      <td><i class="red cancel icon"></i></td>
    </tr>
    <tr>
      <td>Uncover</td>
      <td><i class="red cancel icon"></i></td>
      <td><i class="green check icon"></i></td>
      <td><i class="red cancel icon"></i></td>
    </tr>
    <tr>
      <td>Slide Along</td>
      <td><i class="red cancel icon"></i></td>
      <td><i class="green check icon"></i></td>
      <td><i class="red cancel icon"></i></td>
    </tr>
    <tr>
      <td>Slide Out</td>
      <td><i class="red cancel icon"></i></td>
      <td><i class="green check icon"></i></td>
      <td><i class="red cancel icon"></i></td>
    </tr>
  </tbody>
</table>
```

#### Displaying Multiple
Multiple sidebars can be displayed at the same time only when using a supported animation like `push` or `overlay`.
> You may need to manually set the z-index on elements to ensure the intended sidebar element appears on top.
> If you are triggering multiple sidebars at the same time, its recommended to set the transition to overlay.
```javascript
// showing multiple
$('.demo.sidebar')
  .sidebar('setting', 'transition', 'overlay')
  .sidebar('toggle')
;
```

#### Using a custom context
A sidebar can be initialized inside any element, not just a page's `body`.
> A sidebar's `context` cannot have any padding. You can solve this by padding its inner content, or using an additional containing element
```html
<div class="ui top attached demo menu">
  <a class="item">
    <i class="sidebar icon"></i>
    Menu
  </a>
</div>
<div class="ui bottom attached segment">
  <div class="ui inverted labeled icon left inline vertical sidebar menu">
    <a class="item">
      <i class="home icon"></i>
      Home
    </a>
    <a class="item">
      <i class="block layout icon"></i>
      Topics
    </a>
    <a class="item">
      <i class="smile icon"></i>
      Friends
    </a>
    <a class="item">
      <i class="calendar icon"></i>
      History
    </a>
  </div>
  <div class="pusher">
    <div class="ui basic segment">
      <h3 class="ui header">Application Content</h3>
      <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
      <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
      <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
      <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
    </div>
  </div>
</div>
```
```javascript
// using context
$('.context.example .ui.sidebar')
  .sidebar({
    context: $('.context.example .bottom.segment')
  })
  .sidebar('attach events', '.context.example .menu .item')
;
```

#### Triggering show/hide with other content
For convenience calling attach events will allow you to bind events. By default this will toggle the sidebar in and out of view on click
```javascript
$('.left.demo.sidebar').first()
  .sidebar('attach events', '.toggle.button')
;
$('.toggle.button')
  .removeClass('disabled')
;
```
```html
<div class="ui disabled secondary labeled icon toggle button">
  <i class="left arrow icon"></i>
  Trigger Sidebar
</div>
```

#### Triggering custom behavior with other content
You can also specify what behavior should occur when the element is clicked
```javascript
$('.left.demo.sidebar').first()
  .sidebar('attach events', '.open.button', 'show')
;
$('.open.button')
  .removeClass('disabled')
;
```
```html
<div class="ui disabled secondary labeled icon open button">
  <i class="left arrow icon"></i>
  Open Sidebar
</div>
```

#### Starting Visible
A sidebar can start visible by adding the class name `visible`
> You must include the class `pushable` on a sidebars containing element for it to appear correctly before Javascript initializes the element
> Although sidebars support any size content, sidebars that are visible on load only support standard, predefined sizes like `thin` or `wide`. This makes sure content can be positioned correctly before Javascript is available.
```html
<div class="ui bottom attached segment pushable">
  <div class="ui visible inverted left vertical sidebar menu">
    <a class="item">
      <i class="home icon"></i>
      Home
    </a>
    <a class="item">
      <i class="block layout icon"></i>
      Topics
    </a>
    <a class="item">
      <i class="smile icon"></i>
      Friends
    </a>
    <a class="item">
      <i class="calendar icon"></i>
      History
    </a>
  </div>
  <div class="pusher">
    <div class="ui basic segment">
      <h3 class="ui header">Application Content</h3>
      <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
      <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
      <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
      <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
    </div>
  </div>
</div>
```
```javascript
// showing multiple
$('.visible.example .ui.sidebar')
  .sidebar({
    context: '.visible.example .bottom.segment'
  })
  .sidebar('hide')
;
```

## Settings

### Sidebar

#### Behavior
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
      <td>context</td>
      <td>body</td>
      <td>Context which sidebar will appear inside</td>
    </tr>
    <tr>
      <td>exclusive</td>
      <td>false</td>
      <td>Whether multiple sidebars can be open at once</td>
    </tr>
    <tr>
      <td>closable</td>
      <td>true</td>
      <td>Whether sidebar can be closed by clicking on page</td>
    </tr>
    <tr>
      <td>dimPage</td>
      <td>true</td>
      <td>Whether to dim page contents when sidebar is visible</td>
    </tr>
    <tr>
      <td>scrollLock</td>
      <td>false</td>
      <td>Whether to lock page scroll when sidebar is visible</td>
    </tr>
    <tr>
      <td>returnScroll</td>
      <td>false</td>
      <td>Whether to return to original scroll position when sidebar is hidden, automatically occurs with `transition: scale`</td>
    </tr>
    <tr>
      <td>delaySetup</td>
      <td>false</td>
      <td>When sidebar is initialized without the proper HTML, using this option will defer creation of DOM to use `requestAnimationFrame`.</td>
    </tr>
  </tbody>
</table>
```

#### Animation
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <tr>
      <th>Setting</th>
      <th class="six wide">Default</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>transition</td>
      <td>auto</td>
      <td>Named transition to use when animating sidebar. Defaults to 'auto' which selects transition from `defaultTransition` based on direction.</td>
    </tr>
    <tr>
      <td>mobileTransition</td>
      <td>auto</td>
      <td>Named transition to use when animating when detecting mobile device. Defaults to 'auto' which selects transition from `defaultTransition` based on direction.</td>
    </tr>
    <tr>
      <td>defaultTransition</td>
      <td>
        <div class="code">
{
  computer: {
    left   : 'uncover',
    right  : 'uncover',
    top    : 'overlay',
    bottom : 'overlay'
  },
  mobile: {
    left   : 'uncover',
    right  : 'uncover',
    top    : 'overlay',
    bottom : 'overlay'
  }
}
        </div>
      </td>
      <td>Default transitions for each direction and screen size, used with `transition: auto`</td>
    </tr>
    <tr>
      <td>useLegacy</td>
      <td>false</td>
      <td>Whether Javascript animations should be used. Defaults to `false`. Setting to `auto` will use legacy animations only for browsers that do not support CSS transforms</td>
    </tr>
    <tr>
      <td>duration</td>
      <td>500</td>
      <td>Duration of sidebar animation when using legacy Javascript animation</td>
    </tr>
    <tr>
      <td>easing</td>
      <td>easeInOutQuint</td>
      <td>Easing to use when using legacy Javascript animation</td>
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
      <th class="four wide">Setting</th>
      <th>Context</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>onReposition</td>
      <td>$module</td>
      <td>Callback when element is repositioned from layout change</td>
    </tr>
    <tr>
      <td>onScroll</td>
      <td>$module</td>
      <td>Callback when `requestAnimationFrame` fires from scroll handler.</td>
    </tr>
    <tr>
      <td>onStick</td>
      <td>$module</td>
      <td>Callback when element is fixed to page</td>
    </tr>
    <tr>
      <td>onUnstick</td>
      <td>$module</td>
      <td>Callback when element is unfixed from page</td>
    </tr>
    <tr>
      <td>onTop</td>
      <td>$module</td>
      <td>Callback when element is bound to top of parent container</td>
    </tr>
    <tr>
      <td>onBottom</td>
      <td>$module</td>
      <td>Callback when element is bound to bottom of parent container</td>
    </tr>
  </tbody>
</table>
```

## Module

#### DOM Settings
```html
<table class="ui celled definition table segment">
  <thead>
    <tr>
      <th>Setting</th>
      <th class="six wide">Default</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>namespace</td>
      <td>sidebar</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
className         : {
  active    : 'active',
  animating : 'animating',
  dimmed    : 'dimmed',
  ios       : 'ios',
  pushable  : 'pushable',
  pushed    : 'pushed',
  right     : 'right',
  top       : 'top',
  left      : 'left',
  bottom    : 'bottom',
  visible   : 'visible'
}
        </div>
      </td>
    </tr>
    <tr>
      <td>regExp</td>
      <td>
        <div class="code">
regExp: {
  ios    : /(iPad|iPhone|iPod)/g,
  mobile : /Mobile|iP(hone|od|ad)|Android|BlackBerry|IEMobile|Kindle|NetFront|Silk-Accelerated|(hpw|web)OS|Fennec|Minimo|Opera M(obi|ini)|Blazer|Dolfin|Dolphin|Skyfire|Zune/g
}
        </div>
      </td>
    </tr>
    <tr>
      <td>selector</td>
      <td>
        <div class="code">
selector: {
  fixed   : '.fixed',
  omitted : 'script, link, style, .ui.modal, .ui.dimmer, .ui.nag, .ui.fixed',
  pusher  : '.pusher',
  sidebar : '.ui.sidebar'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```

#### Debug

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
      <td>Sidebar</td>
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
error   : {
  method       : 'The method you called is not defined.',
  pusher       : 'Had to add pusher element. For optimal performance make sure body content is inside a pusher element',
  movedSidebar : 'Had to move sidebar. For optimal performance make sure sidebar and pusher are direct children of your body tag',
  overlay      : 'The overlay setting is no longer supported, use animation: overlay',
  notFound     : 'There were no elements that matched the specified selector'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```
