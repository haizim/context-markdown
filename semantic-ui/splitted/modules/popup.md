# Popup

A popup displays additional information on top of a page

## Definition

### Types

### Javascript

> Popup includes both a javascript version (with a full featureset) and a limited CSS only version, which can be useful in pages that use many popups, or with libraries like React or Meteor to avoid handling DOM lifecycle.

#### Popup
An element can specify popup content to appear
```html
<div class="ui icon button" data-content="Add users to your feed">
  <i class="add icon"></i>
</div>
```

#### Titled
An element can specify popup content with a title
```html
<img src="/images/avatar/small/elliot.jpg" data-title="Elliot Fu" data-content="Elliot has been a member since July 2012" class="ui avatar image">
<img src="/images/avatar/small/stevie.jpg" data-title="Stevie Feliciano" data-content="Stevie has been a member since August 2013" class="ui avatar image">
<img src="/images/avatar/small/matt.jpg" data-title="Matt" data-content="Matt has been a member since July 2014" class="ui avatar image">
```

#### HTML
An element can specify HTML for a popup

```html
<div class="ui card" data-html="<div class='header'>User Rating</div><div class='content'><div class='ui star rating'><i class='active icon'></i><i class='active icon'></i><i class='active icon'></i><i class='active icon'></i><i class='active icon'></i></div></div>">
  <div class="image">
    <img src="/images/movies/totoro-horizontal.jpg">
  </div>
  <div class="content">
    <div class="header">My Neighbor Totoro</div>
    <div class="description">
      Two sisters move to the country with their father in order to be closer to their hospitalized mother, and discover the surrounding trees are inhabited by magical spirits.
    </div>
  </div>
  <div class="ui two bottom attached buttons">
    <div class="ui button">
      <i class="add icon"></i>
      Queue
    </div>
    <div class="ui primary button">
      <i class="play icon"></i>
      Watch
    </div>
  </div>
</div>
```

#### Pre-Existing
An element can display a popup that is already included in the page

```html
<div class="ui card">
  <div class="image">
    <img src="/images/movies/watchmen-horizontal.jpg">
  </div>
  <div class="content">
    <div class="header">Watchmen</div>
    <div class="description">
      In a gritty and alternate 1985 the glory days of costumed vigilantes have been brought to a close by a government crackdown, but after one of the masked veterans is brutally murdered an investigation into the killer is initiated.
    </div>
  </div>
  <div class="ui two bottom attached buttons">
    <div class="ui button">
      <i class="add icon"></i>
      Queue
    </div>
    <div class="ui primary button">
      <i class="play icon"></i>
      Watch
    </div>
  </div>
</div>
<div class="ui popup">
  <div class='header'>User Rating</div>
  <div class="ui star rating" data-rating="3"></div>
</div>
```

### No Javascript

#### Tooltip
An element can specify a simple tooltip that can appear without javascript
> Tooltips use an element's `:before` and `:after` pseudo classes. Elements like `icon` that already use these classes for styling will need to have the tooltips to a wrapping element, like a button, or a `span` to make sure tooltips work correctly.
```html
<div class="ui icon button" data-tooltip="Add users to your feed">
  <i class="add icon"></i>
</div>
<div class="ui icon button" data-tooltip="Add users to your feed" data-inverted>
  <i class="add icon"></i>
</div>
```
```html
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

## Variations

#### Basic
A popup can provide more basic formatting
```html
<div class="ui icon button" data-content="The default theme's basic popup removes the pointing arrow." data-variation="basic">
  <i class="add icon"></i>
</div>
```

#### Width
A popup can be extra wide to allow for longer content
```html
<i class="circular heart icon link" data-content="Hello. This is a wide pop-up which allows for lots of content with additional space. You can fit a lot of words here and the paragraphs will be pretty wide." data-variation="wide"></i>
<i class="circular heart icon link" data-content="Hello. This is a very wide pop-up which allows for lots of content with additional space. You can fit a lot of words here and the paragraphs will be pretty wide." data-variation="very wide"></i>
```

#### Fluid
A fluid popup will take up the entire width of its offset container
```html
<div class="ui button">Show fluid popup</div>
<div class="ui fluid popup">
  <div class="ui four column divided center aligned grid">
    <div class="column">1</div>
    <div class="column">2</div>
    <div class="column">3</div>
    <div class="column">4</div>
  </div>
</div>
```

#### Size
A popup can vary in size
```html
<i class="circular heart icon link" data-content="Hello. This is a mini popup" data-variation="mini"></i>
<i class="circular heart icon link" data-content="Hello. This is a tiny popup" data-variation="tiny"></i>
<i class="circular heart icon link" data-content="Hello. This is a small popup" data-variation="small"></i>
<i class="circular heart icon link" data-content="Hello. This is a large popup" data-variation="large"></i>
<i class="circular heart icon link" data-content="Hello. This is a huge popup" data-variation="huge"></i>
```

#### Flowing
A popup can have no maximum width and continue to flow to fit its content
```html
<div class="ui button">Show flowing popup</div>
<div class="ui flowing popup">
  <div class="ui three column divided center aligned grid">
    <div class="column">
      <h4 class="ui header">Basic Plan</h4>
      <p><b>2</b> projects, $10 a month</p>
      <div class="ui button">Choose</div>
    </div>
    <div class="column">
      <h4 class="ui header">Business Plan</h4>
      <p><b>5</b> projects, $20 a month</p>
      <div class="ui button">Choose</div>
    </div>
    <div class="column">
      <h4 class="ui header">Premium Plan</h4>
      <p><b>8</b> projects, $25 a month</p>
      <div class="ui button">Choose</div>
    </div>
  </div>
</div>
```

#### Inverted
A popup can have its colors inverted
```html
<i class="circular heart icon link" data-content="Hello. This is an inverted popup" data-variation="inverted"></i>
<div class="ui icon button" data-tooltip="Hello. This is an inverted popup" data-position="top left" data-inverted>
  <i class="add icon"></i>
</div>
```

## Usage

### Initializing A Popup

A popup is initialized on an activating element
```javascript
$('.activating.element')
  .popup()
;
```

#### Using a Pre-existing Popup
Using a pre-existing popup allows for you to include complex HTML inside your popup.

If you include your popup on page load as an adjacent sibling element to your activating element it can be found automatically.

To instruct popup to look inline for your popup element you can initialize it with the `inline` parameter
```javascript
$('.button')
  .popup({
    inline: true
  })
;
```
```html
<div class="ui button">Activator</div>
<div class="ui special popup">
  <div class="header">Custom Header</div>
  <div class="ui button">Click Me</div>
</div>
```

#### Using a Pre-existing Popup Anywhere
If you cannot include your popup element as a sibling element, you can specify a custom selector to retrieve your popup
```javascript
$('.button')
  .popup({
    popup: '.special.popup'
  })
;
```

#### Specifying Content In Metadata
Frequently used settings like, title, content, HTML, or offset or variation, can be included in HTML metadata
> <i class="info icon"></i>
> <div class="content">
>   <div class="header">Specifying Content</div>
>   <p>Popups can specify content in three ways:
>   <ul class="list">
>     <li>Using HTML `title` attribute</li>
>     <li>Using `data-content` attribute</li>
>     <li>Using `data-html` for specific HTML</li>
>     <li>Using the content property in the initialization of the popup</li>
>   </ul>
>   <p>Popups can also specify some other frequently used settings using metadata
>   <ul class="list">
>     <li>`data-variation`: the popup variation to use </li>
>     <li>`data-offset`: a pixel offset correction for popup</li>
>     <li>`data-position`: the side to position popup on</li>
>   </ul>
> </div>
```html
<i class="heart icon" title="Hello I am a popup"></i>
```

#### Specifying Content In Javascript
```javascript
$('.ui.popup')
  .popup({
    title   : 'Popup Title',
    content : 'Hello I am a popup'
  })
;
```

## Behavior

All the following behaviors can be called using the syntax:
```javascript
$('.your.element')
  .popup('behavior name', argumentOne, argumentTwo)
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
      <td>show</td>
      <td>Shows popup</td>
    </tr>
    <tr>
      <td>hide</td>
      <td>Hides popup</td>
    </tr>
    <tr>
      <td>hide all</td>
      <td>Hides all visible pop ups on the page</td>
    </tr>
    <tr>
      <td>get popup</td>
      <td>Returns current popup dom element</td>
    </tr>
    <tr>
      <td>change content(html)</td>
      <td>Changes current popup content</td>
    </tr>
    <tr>
      <td>toggle</td>
      <td>Toggles visibility of popup</td>
    </tr>
    <tr>
      <td>is visible</td>
      <td>Returns whether popup is visible</td>
    </tr>
    <tr>
      <td>is hidden</td>
      <td>Returns whether popup is hidden</td>
    </tr>
    <tr>
      <td>exists</td>
      <td>Returns whether popup is created and inserted into the page</td>
    </tr>
    <tr>
      <td>reposition</td>
      <td>Adjusts popup when content size changes (only necessary for centered popups)</td>
    </tr>
    <tr>
      <td>set position(position)</td>
      <td>Repositions a popup</td>
    </tr>
    <tr>
      <td>destroy</td>
      <td>Removes popup from the page and removes all events</td>
    </tr>
    <tr>
      <td>remove popup</td>
      <td>Removes popup from the page</td>
    </tr>
  </tbody>
</table>
```

## Examples

#### Specifying Popup Boundaries
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

#### Wide Popup Menu
An easier way to display complex content, like a wide popup menu is to have the popup content as a pre-  existing part of your page's HTML.

Using the setting `inline: true` will let Semantic know to display the next sibling `ui  popup` element after the activator.

Tweaking settings like the delay for show, and hide, and making the menu hoverable will help it function   more like a dropdown menu

```javascript
$('.example .menu .browse')
  .popup({
    inline     : true,
    hoverable  : true,
    position   : 'bottom left',
    delay: {
      show: 300,
      hide: 800
    }
  })
;
```
```html
<div class="ui menu">
  <a class="browse item">
    Browse
    <i class="dropdown icon"></i>
  </a>
  <div class="ui fluid popup">
    <div class="ui four column relaxed divided grid">
      <div class="column">
        <h4 class="ui header">Fabrics</h4>
        <div class="ui link list">
          <a class="item">Cashmere</a>
          <a class="item">Linen</a>
          <a class="item">Cotton</a>
          <a class="item">Viscose</a>
        </div>
      </div>
      <div class="column">
        <h4 class="ui header">Size</h4>
        <div class="ui link list">
          <a class="item">Small</a>
          <a class="item">Medium</a>
          <a class="item">Large</a>
          <a class="item">Plus Sizes</a>
        </div>
      </div>
      <div class="column">
        <h4 class="ui header">Colors</h4>
        <div class="ui link list">
          <a class="item">Neutrals</a>
          <a class="item">Brights</a>
          <a class="item">Pastels</a>
        </div>
      </div>
      <div class="column">
        <h4 class="ui header">Types</h4>
        <div class="ui link list">
          <a class="item">Knitwear</a>
          <a class="item">Outerwear</a>
          <a class="item">Pants</a>
          <a class="item">Shoes</a>
        </div>
      </div>
    </div>
  </div>
  <a class="item">
    <i class="cart icon"></i>
    Checkout
  </a>
</div>
```

#### Specifying a selector for a popup
If its not possible to include the popup content as the next sibling, you can also specify a custom selector to help link the popup contents to its activator.
> Using an `inline` popup may require specifying a `min-width` on your popup, if your popup content will appear outside the boundaries of its parent element.
```javascript
$('.example .custom.button')
  .popup({
    popup : $('.custom.popup'),
    on    : 'click'
  })
;
```
```html
<div class="some-wrapping-div">
  <div class="ui custom button">Show custom popup</div>
</div>
<div class="ui custom popup">
  I'm not on the same level as the button, but i can still be found.
</div>
```

#### Specifying a trigger event
A popup trigger event can be specified
```javascript
$('.example .teal.button')
  .popup({
    on: 'click'
  })
;
$('.example input')
  .popup({
    on: 'focus'
  })
;
```
```html
<div class="ui teal button" data-title="Using click events" data-content="Clicked popups will close if you click away, but not if you click inside the popup">Click Me</div>
<div class="ui icon input">
  <input type="text" placeholder="Focus me..." data-content="You can use me to enter data">
  <i class="search icon"></i>
</div>
```

#### Target Element
A popup can specify a different target element than itself to show a popup
```javascript
$('.test.button')
  .popup({
    position : 'right center',
    target   : '.test.image',
    title    : 'My favorite dog',
    content  : 'My favorite dog would like other dogs as much as themselves'
  })
;
```
```html
<div class="ui green test button">Hover Me</div>
<div class="ui divider"></div>
<img class="medium ui test image" src="/images/wireframe/image.png">
```

#### Inline or relative to page
A popup can either be inserted directly after an element, or added as a child element to the page's `body`.
> Using inline will allow your popups to go places other popups can't go, like inside `fixed` or `absolutely` positioned elements
> If you want to style each popup individually it makes sense to keep popup `inline: true`. If you are worried that your pop up might mistakingly inherit styles that it shouldn't, you should set `inline: false`.
```css
/* this will only style the popup if inline is true */
.example .popup {
  color: #FF0000;
}
```
```javascript
$('.inline.icon')
  .popup({
    inline: true
  })
;
```
```html
<i class="heart circular icon link" data-content="This is a child element to the page's body and will not be styled" ></i>
<i class="mail inline circular icon link" data-content="This popup was inserted inline and will be styled" ></i>
```

#### Positioning
A popup can be positioned to any side of an element. If space is not available, it will automatically search for a similar alternative position to use.
```html
<div class="ui segment">
  <i class="square inverted red heart icon link" data-content="Top Left" data-position="top left"></i>
  <i class="square inverted red heart icon link" data-content="Top Center" data-position="top center"></i>
  <i class="square inverted red heart icon link" data-content="Top Right" data-position="top right"></i>
  <i class="square inverted red heart icon link" data-content="Right Center" data-position="right center"></i>
  <i class="square inverted red heart icon link" data-content="Bottom Right" data-position="bottom right"></i>
  <i class="square inverted red heart icon link" data-content="Bottom Center" data-position="bottom center"></i>
  <i class="square inverted red heart icon link" data-content="Bottom Left" data-position="bottom left"></i>
  <i class="square inverted red heart icon link" data-content="Left Center" data-position="left center"></i>
</div>
```

#### Specifying an offset
A popup position can be adjusted manually by specifying an offset property using `data-offset="value"`

```html
<i class="heart circular icon link" data-offset="50" data-content="As expected this popup is way off to the right"></i>
```

#### Transitions
A popup can use any named ui transition.
```html
<i class="large demo home circular link icon" data-title="Home" data-content="The place where you keep your dog"></i> Home

<div class="ui divider"></div>

<div class="ui selection dropdown">
  <input type="hidden" name="transition">
  <i class="dropdown icon"></i>
  <div class="default text">Choose a transition</div>
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
$('.selection')
  .dropdown({
    onChange: function(value) {
      $('.demo.icon')
        .popup({
          transition: value
        })
        .popup('toggle')
      ;
    }
  })
;
```

## Settings

### Popup Settings
Settings to configure popup behavior
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th>Setting</th>
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>popup</td>
      <td>false</td>
      <td>Can specify a DOM element that should be used as the popup. This is useful for including a pre-formatted popup.</td>
    </tr>
    <tr>
      <td>exclusive</td>
      <td>false</td>
      <td>Whether all other popups should be hidden when this popup is opened</td>
    </tr>
    <tr>
      <td>movePopup</td>
      <td>true</td>
      <td>Whether to move popup to same offset container as target element when `popup` already exists on the page. Using a popup inside of an element without `overflow:visible`, like a sidebar, may require you to set this to `false`</td>
    </tr>
    <tr>
      <td>observeChanges</td>
      <td>true</td>
      <td>Whether popup should attach `mutationObservers` to automatically run `destroy` when the element is removed from the page's DOM.</td>
    </tr>
    <tr>
      <td>boundary</td>
      <td>window</td>
      <td>When the popup surpasses the boundary of this element, it will attempt to find another display position.</td>
    </tr>
    <tr>
      <td>context</td>
      <td>body</td>
      <td>Selector or jquery object specifying where the popup should be created.</td>
    </tr>
    <tr>
      <td>scrollContext</td>
      <td>window</td>
      <td>Will automatically hide a popup on scroll event in this context</td>
    </tr>
    <tr>
      <td>jitter</td>
      <td>2</td>
      <td>Number of pixels that a popup is allowed to appear outside the boundaries of its context. This allows for permissible rounding errors when an element is against the edge of its `context`.</td>
    </tr>
    <tr>
      <td>position</td>
      <td>top left</td>
      <td>Position that the popup should appear</td>
    </tr>
    <tr>
      <td>inline</td>
      <td>false</td>
      <td>If a popup is inline it will be created next to current element, allowing for local css rules to apply. It will not be removed from the DOM after being hidden. Otherwise popups will appended to body and removed after being hidden.</td>
    </tr>
    <tr>
      <td>preserve</td>
      <td>false</td>
      <td>Whether popup contents should be preserved in the page after being hidden, allowing it to re-appear slightly faster on subsequent loads.</td>
    </tr>
    <tr>
      <td>prefer</td>
      <td>adjacent</td>
      <td>Can be set to `adjacent` or `opposite` to prefer adjacent or opposite position if popup cannot fit on screen</td>
    </tr>
    <tr>
      <td>lastResort</td>
      <td>false</td>
      <td>When set to `false`, a popup will not appear and produce an error message if it cannot entirely fit on page. Setting this to a position like, `right center` forces the popup to use this position as a last resort even if it is partially offstage. Setting this to `true` will use the last attempted position.</td>
    </tr>
    <tr>
      <td>on</td>
      <td>hover</td>
      <td>Event used to trigger popup. Can be either **focus, click, hover, or manual**. Manual popups must be triggered with `$('.element').popup('show');`</td>
    </tr>
    <tr>
      <td>delay</td>
      <td>
        <div class="code">
delay: {
  show: 50,
  hide: 0
}
        </div>
      </td>
      <td>Delay in milliseconds before showing or hiding a popup on hover or focus</td>
    </tr>
    <tr>
      <td>transition</td>
      <td>
        slide down
      </td>
      <td>Named transition to use when animating menu in and out.</td>
    </tr>
    <tr>
      <td>duration</td>
      <td>
        200
      </td>
      <td>Duration of animation events</td>
    </tr>
    <tr>
      <td>arrowPixelsFromEdge <div class="ui teal label">New in 2.3</div></td>
      <td>20</td>
      <td>When a target element is less than 2x this amount, the popup will appear with the arrow centered on the target element, instead of with the popup edge matching the target's edge.</td>
    </tr>
    <tr>
      <td>setFluidWidth</td>
      <td>true</td>
      <td>Whether popup should set fluid popup variation width on load to avoid `width: 100%` including padding</td>
    </tr>
    <tr>
      <td>hoverable</td>
      <td>false</td>
      <td>Whether popup should not close on hover (useful for popup navigation menus)</td>
    </tr>
    <tr>
      <td>closable</td>
      <td>true</td>
      <td>When using `on: 'click'` specifies whether clicking the page should close the popup</td>
    </tr>
    <tr>
      <td>addTouchEvents</td>
      <td>true</td>
      <td>When using `on: 'hover'` whether `touchstart` events should be added to allow the popup to be triggered</td>
    </tr>
    <tr>
      <td>hideOnScroll</td>
      <td>auto</td>
      <td>Whether popup should hide on scroll or touchmove, `auto` only hides for popups without `on: 'click'`.<br>
      Set this to `false` to prevent mobile browsers from closing popups when you tap inside input fields.</td>
    </tr>
    <tr>
      <td>target</td>
      <td>false</td>
      <td>If a selector or jQuery object is specified this allows the popup to be positioned relative to that element.</td>
    </tr>
    <tr>
      <td>distanceAway</td>
      <td>0</td>
      <td>Offset for distance of popup from element</td>
    </tr>
    <tr>
      <td>offset</td>
      <td>0</td>
      <td>Offset in pixels from calculated position</td>
    </tr>
    <tr>
      <td>maxSearchDepth</td>
      <td>10</td>
      <td>Number of iterations before giving up search for popup position when a popup cannot fit on screen</td>
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
      <td>$module</td>
      <td>$popup</td>
      <td>Callback on popup element creation, with created popup</td>
    </tr>
    <tr>
      <td>onRemove</td>
      <td>$module</td>
      <td>$popup</td>
      <td>Callback immediately before Popup is removed from DOM</td>
    </tr>
    <tr>
      <td>onShow</td>
      <td>$module</td>
      <td>$popup</td>
      <td>Callback before popup is shown. Returning `false` from this callback will cancel the popup from showing.</td>
    </tr>
    <tr>
      <td>onVisible</td>
      <td>$module</td>
      <td>$popup</td>
      <td>Callback after popup is shown</td>
    </tr>
    <tr>
      <td>onHide</td>
      <td>$module</td>
      <td>$popup</td>
      <td>Callback before popup is hidden. Returning `false` from this callback will cancel the popup from hiding.</td>
    </tr>
    <tr>
      <td>onHidden</td>
      <td>$module</td>
      <td>$popup</td>
      <td>Callback after popup is hidden</td>
    </tr>
    <tr>
      <td>onUnplaceable</td>
      <td>$module</td>
      <td>$popup</td>
      <td>Callback after popup cannot be placed on screen</td>
    </tr>
  </tbody>
</table>
```

### Content Settings
Settings to specify popup contents
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th>Setting</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>variation</td>
      <td>Popup variation to use, can use multiple variations with a space delimiter</td>
    </tr>
    <tr>
      <td>content</td>
      <td>Content to display</td>
    </tr>
    <tr>
      <td>title</td>
      <td>Title to display alongside content</td>
    </tr>
    <tr>
      <td>html</td>
      <td>HTML content to display instead of preformatted title and content</td>
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
      <td>popup</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>selector</td>
      <td>
        <div class="code">
selector    : {
  popup    : '.ui.popup'
}
        </div>
      </td>
      <td>DOM Selectors used internally</td>
    </tr>
    <tr>
      <td>metadata</td>
      <td>
        <div class="code">
metadata: {
  content   : 'content',
  html      : 'html',
  offset    : 'offset',
  position  : 'position',
  title     : 'title',
  variation : 'variation'
}
        </div>
      </td>
      <td>HTML Data attributes used to store data</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
className   : {
  loading     : 'loading',
  popup       : 'ui popup',
  position    : 'top left center bottom right',
  visible     : 'visible'
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
    <th>Setting</th>
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>Popup</td>
      <td>Name used in debug logs</td>
    </tr>
    <tr>
      <td>silent</td>
      <td>false</td>
      <td>Silences all console output including error messages, regardless of other debug settings.</td>
    </tr>
    <tr>
      <td>debug</td>
      <td>false</td>
      <td>Provides standard debug output to console</td>
    </tr>
    <tr>
      <td>performance</td>
      <td>true</td>
      <td>Provides standard debug output to console</td>
    </tr>
    <tr>
      <td>verbose</td>
      <td>true</td>
      <td>Provides ancillary debug output to console</td>
    </tr>
    <tr>
      <td>errors</td>
      <td colspan="2">
        <div class="code">
error: {
  invalidPosition : 'The position you specified is not a valid position',
  cannotPlace     : 'Popup does not fit within the boundaries of the viewport',
  method          : 'The method you called is not defined.',
  noTransition    : 'This module requires ui transitions <https://github.com/Semantic-Org/UI-Transition>',
  notFound        : 'The target or popup you specified does not exist on the page'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```
