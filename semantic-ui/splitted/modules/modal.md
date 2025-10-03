# Modal

A modal displays content that temporarily blocks interactions with the main view of a site

## Types

#### Modal
A standard modal
```javascript
$('.ui.modal')
  .modal('show')
;
```
```html
<div class="ui modal">
  <i class="close icon"></i>
  <div class="header">
    Profile Picture
  </div>
  <div class="image content">
    <div class="ui medium image">
      <img src="/images/avatar/large/chris.jpg">
    </div>
    <div class="description">
      <div class="ui header">We've auto-chosen a profile image for you.</div>
      <p>We've grabbed the following image from the <a href="https://www.gravatar.com" target="_blank">gravatar</a> image associated with your registered e-mail address.</p>
      <p>Is it okay to use this photo?</p>
    </div>
  </div>
  <div class="actions">
    <div class="ui black deny button">
      Nope
    </div>
    <div class="ui positive right labeled icon button">
      Yep, that's me
      <i class="checkmark icon"></i>
    </div>
  </div>
</div>
```

#### Basic
A modal can reduce its complexity
```javascript
$('.ui.basic.modal')
  .modal('show')
;
```
```html
<div class="ui basic modal">
  <div class="ui icon header">
    <i class="archive icon"></i>
    Archive Old Messages
  </div>
  <div class="content">
    <p>Your inbox is getting full, would you like us to enable automatic archiving of old messages?</p>
  </div>
  <div class="actions">
    <div class="ui red basic cancel inverted button">
      <i class="remove icon"></i>
      No
    </div>
    <div class="ui green ok inverted button">
      <i class="checkmark icon"></i>
      Yes
    </div>
  </div>
</div>
```

## Content

#### Header
A modal can have a header
```html
<div class="ui modal">
  <div class="header">Header</div>
</div>
```

#### Content
A modal can contain content
```html
<div class="ui modal">
  <div class="header">Header</div>
  <div class="content">
    <p></p>
    <p></p>
    <p></p>
  </div>
</div>
```

#### Image Content
A modal can contain image content
> Modals with image content must use the `image content` class in `2.0`. This is to make sure flex-box rules do not affect regular content.
```html
<div class="ui modal">
  <div class="header">Header</div>
  <div class="image content">
    <img class="image">
    <div class="description">
      <p></p>
    </div>
  </div>
</div>
```

#### Actions
A modal can contain a row of actions
> Close actions are applied by default to all button actions, in addition an `onApprove` or `onDeny` callback will fire if the elements match either selector.
```css
approve  : '.positive, .approve, .ok',
deny     : '.negative, .deny, .cancel'
```
> To prevent a modal action from causing the modal to close, you can `return false;` from either callback.
```html
<div class="ui modal">
  <div class="header">Header</div>
  <div class="content">
    <p></p>
  </div>
  <div class="actions">
    <div class="ui approve button">Approve</div>
    <div class="ui button">Neutral</div>
    <div class="ui cancel button">Cancel</div>
  </div>
</div>
```

## Variations

#### Full Screen
A modal can use the entire size of the screen
```javascript
$('.fullscreen.modal')
  .modal('show')
;
```

#### Size
A modal can vary in size
```javascript
$('.mini.modal')
  .modal('show')
;
```
```javascript
$('.tiny.modal')
  .modal('show')
;
```
```javascript
$('.small.modal')
  .modal('show')
;
```
```javascript
$('.large.modal')
  .modal('show')
;
```

#### Scrolling Content
A modal can use the entire size of the screen
```html
<div class="ui modal">
  <div class="header">Header</div>
  <div class="scrolling content">
    <p>Very long content goes here</p>
  </div>
</div>
```
```javascript
$('.ui.longer.modal')
  .modal('show')
;
```

## States

#### Active
An active modal is visible on the page
```html
<div class="ui active modal"></div>
```

## Examples

#### Disabling Vertical Centering
When your modal has dynamic content, or multiple steps, it can make sense to disable centering so content doesn't jump around vertically when its height changes.
```javascript
$('.special.modal')
  .modal({
    centered: false
  })
  .modal('show')
;
```

#### Scrolling Modal
When your modal content exceeds the height of the browser the scrollable area will automatically expand to include just enough space for scrolling, without scrolling the page below.
```javascript
$('.long.modal')
  .modal('show')
;
```

#### Internally Scrolling Content
You may prefer to have the content of your modal scroll itself, you can do this by using the `scrolling content` variation.
```javascript
$('.longer.modal')
  .modal('show')
;
```

#### Multiple Modals
A modal can open a second modal. If you use `allowMultiple: true` parameter the second modal will  be opened on top of the first modal. Otherwise the modal will be closed before the second modal is opened.
```javascript
// initialize all modals
$('.coupled.modal')
  .modal({
    allowMultiple: true
  })
;
// open second modal on first modal buttons
$('.second.modal')
  .modal('attach events', '.first.modal .button')
;
// show first immediately
$('.first.modal')
  .modal('show')
;
```
```javascript
$('.coupled.modal')
  .modal({
    allowMultiple: false
  })
;
// attach events to buttons
$('.second.modal')
  .modal('attach events', '.first.modal .button')
;
// show first now
$('.first.modal')
  .modal('show')
;
```

#### Forcing a Choice
You can disable a modal's dimmer from being closed by click to force a user to make a choice
```javascript
$('.basic.test.modal')
  .modal('setting', 'closable', false)
  .modal('show')
;
```

#### Approve / Deny Callbacks
Modals will automatically tie approve deny callbacks to any positive/approve, negative/deny or ok/cancel buttons.
> If `onDeny`, `onApprove` or `onHide` returns false it will prevent the modal from closing
```javascript
$('.ui.basic.test.modal')
  .modal({
    closable  : false,
    onDeny    : function(){
      window.alert('Wait not yet!');
      return false;
    },
    onApprove : function() {
      window.alert('Approved!');
    }
  })
  .modal('show')
;
```

#### Attach events
A modal can attach events to another element
```javascript
$('.test.modal')
  .modal('attach events', '.test.button', 'show')
;
```
```html
<div class="ui primary test button">Launch modal</div>
```

#### Transitions
A modal can use any named ui transition.
```html
<div class="ui animation selection dropdown">
  <input type="hidden" name="transition">
  <div class="default text">Choose transition</div>
  <i class="dropdown icon"></i>
  <div class="menu">
    <div class="item">Horizontal Flip</div>
    <div class="item">Vertical Flip</div>
    <div class="item">Fade Up</div>
    <div class="item">Fade</div>
    <div class="item">Scale</div>
  </div>
</div>
<div class="ui clearing divider"></div>
```
```javascript
$('.selection.dropdown')
  .dropdown({
    onChange: function(value) {
      $('.test.modal')
        .modal('setting', 'transition', value)
        .modal('show')
      ;
    }
  })
;
```

#### Dimmer Variations
Modals can specify additional variations like `blurring` or `inverted` which adjust how the dimmer displays.
> Full screen blurring modals are not performant for current-gen computers at widescreen resolutions with integrated graphics.
```javascript
$('.ui.inverted.modal')
  .modal({
    inverted: true
  })
  .modal('show')
;
```
```javascript
$('.ui.standard.modal')
  .modal({
    blurring: true
  })
  .modal('show')
;
```

## Usage

### Initializing a modal
A modal can be included anywhere on the page. On initialization a modal's current size will be cached, and the element will be detached from the DOM and moved inside a dimmer.
> <div class="header">Why move modal content?</div>
> <p>Having a modal inside the page dimmer allows for 3D animations without having the 3D perspective settings alter the rest of the page content. Additionally, content outside the dimmer can be blurred or altered without affecting the modal's content.</p>
> <p>If you need to have your modal stay in its current location you can preserve its position using the setting `detachable: false`</p>
```javascript
$('.ui.modal')
  .modal()
;
```
```html
<div class="ui modal">
  <i class="close icon"></i>
  <div class="header">
    Modal Title
  </div>
  <div class="image content">
    <div class="image">
      An image can appear on left or an icon
    </div>
    <div class="description">
      A description can appear on the right
    </div>
  </div>
  <div class="actions">
    <div class="ui button">Cancel</div>
    <div class="ui button">OK</div>
  </div>
</div>
```

## Behavior

All the following behaviors can be called using the syntax:
```javascript
$('.ui.modal')
  .modal('behavior name', argumentOne, argumentTwo)
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
      <td>show</td>
      <td>Shows the modal</td>
    </tr>
    <tr>
      <td>hide</td>
      <td>Hides the modal</td>
    </tr>
    <tr>
      <td>toggle</td>
      <td>Toggles the modal</td>
    </tr>
    <tr>
      <td>refresh</td>
      <td>Refreshes centering of modal on page</td>
    </tr>
    <tr>
      <td>show dimmer</td>
      <td>Shows associated page dimmer</td>
    </tr>
    <tr>
      <td>hide dimmer</td>
      <td>Hides associated page dimmer</td>
    </tr>
    <tr>
      <td>hide others</td>
      <td>Hides all modals not selected modal in a dimmer</td>
    </tr>
    <tr>
      <td>hide all</td>
      <td>Hides all visible modals in the same dimmer</td>
    </tr>
    <tr>
      <td>cache sizes</td>
      <td>Caches current modal size</td>
    </tr>
    <tr>
      <td>can fit</td>
      <td>Returns whether the modal can fit on the page</td>
    </tr>
    <tr>
      <td>is active</td>
      <td>Returns whether the modal is active</td>
    </tr>
    <tr>
      <td>set active</td>
      <td>Sets modal to active</td>
    </tr>
  </tbody>
</table>
```

## Settings

### Modal Settings
Modal settings modify the modal's behavior
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
      <td>detachable</td>
      <td>true</td>
      <td>If set to false will prevent the modal from being moved to inside the dimmer</td>
    </tr>
    <tr>
      <td>useFlex</td>
      <td>'auto'</td>
      <td>Auto will automatically use flex in browsers that support absolutely positioned elements inside flex containers. Setting to true/false will force this setting for all browsers.</td>
    </tr>
    <tr>
      <td>autofocus</td>
      <td>true</td>
      <td>When true, the first form input inside the modal will receive focus when shown.  Set this to false to prevent this behavior.</td>
    </tr>
    <tr>
      <td>observeChanges</td>
      <td>false</td>
      <td>Whether any change in `modal` DOM should automatically refresh cached positions</td>
    </tr>
    <tr>
      <td>allowMultiple</td>
      <td>false</td>
      <td>If set to true will not close other visible modals when opening a new one</td>
    </tr>
    <tr>
      <td>keyboardShortcuts</td>
      <td>true</td>
      <td>Whether to automatically bind keyboard shortcuts</td>
    </tr>
    <tr>
      <td>offset</td>
      <td>0</td>
      <td>A vertical offset to allow for content outside of modal, for example a close button, to be centered.</td>
    </tr>
    <tr>
      <td>context</td>
      <td>
      body
      </td>
      <td>Selector or jquery object specifying the area to dim</td>
    </tr>
    <tr>
      <td>closable</td>
      <td>
      true
      </td>
      <td>Setting to false will not allow you to close the modal by clicking on the dimmer</td>
    </tr>
    <tr>
      <td>dimmerSettings</td>
      <td>
      <div class="code">
      {
        closable : false,
        useCSS   : true
      }
      </div>
      </td>
      <td>You can specify custom settings to extend [UI dimmer](/modules/dimmer.html)</td>
    </tr>
    <tr>
      <td>transition</td>
      <td>
        scale
      </td>
      <td>Named transition to use when animating menu in and out, full list can be found in [ui transitions](/modules/transition.html) docs.</td>
    </tr>
    <tr>
      <td>duration</td>
      <td>
        400
      </td>
      <td>Duration of animation</td>
    </tr>
    <tr>
      <td>queue</td>
      <td>
        false
      </td>
      <td>Whether additional animations should queue</td>
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
      <td>onShow</td>
      <td>Modal</td>
      <td>Is called when a modal starts to show.</td>
    </tr>
    <tr>
      <td>onVisible</td>
      <td>Modal</td>
      <td>Is called after a modal has finished showing animating.</td>
    </tr>
    <tr>
      <td>onHide($element)</td>
      <td>Modal</td>
      <td>Is called after a modal starts to hide. If the function returns `false`, the modal will not hide.</td>
    </tr>
    <tr>
      <td>onHidden</td>
      <td>Modal</td>
      <td>Is called after a modal has finished hiding animation.</td>
    </tr>
    <tr>
      <td>onApprove($element)</td>
      <td>Click</td>
      <td>Is called after a positive, approve or ok button is pressed. If the function returns `false`, the modal will not hide.</td>
    </tr>
    <tr>
      <td>onDeny($element)</td>
      <td>Modal</td>
      <td>Is called after a negative, deny or cancel button is pressed. If the function returns `false` the modal will not hide.</td>
    </tr>
  </tbody>
</table>
```

### DOM Settings
DOM settings specify how this module should interface with the DOM
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <tr>
    <th>Setting</th>
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>namespace</td>
      <td>modal</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>selector</td>
      <td colspan="2">
        <div class="code">
selector    : {
  close    : '.close, .actions .button',
  approve  : '.actions .positive, .actions .approve, .actions .ok',
  deny     : '.actions .negative, .actions .deny, .actions .cancel'
},
        </div>
      </td>
    </tr>
    <tr>
      <td>className</td>
      <td colspan="2">
        <div class="code">
className : {
  active    : 'active',
  scrolling : 'scrolling'
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
    <tr>
      <th>Setting</th>
      <th class="four wide">Default</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>Modal</td>
      <td>Name used in debug logs</td>
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
      <td>error</td>
      <td colspan="2">
        <div class="code">
error   : {
  method    : 'The method you called is not defined.'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```
