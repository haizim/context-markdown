# Visibility

Visibility provides a set of callbacks for when a content appears in the viewport

## Introduction

### Introduction
Visibility provides a set of callbacks that can be attached to any element and trigger when a specific visibility event occurs.

There are a variety of uses for attaching events to visibility. Here are some of the more common ones.

*   Infinite Scroll
    *   You want to start loading more content into a container when a user is partially finished scrolling through the content
*   Lazy Loading Images
    *   You want to start loading an image just before it is visible to a user
*   Reactive Content
    *   You want an element to change based on how far a user has scrolled
*   Sticky Headers
    *   You want an element to fix itself to the viewport when it is passed, and return to its original static position afterwards
*   Event Tracking
    *   You want to attach analytics events that match a users engagement with content, for example, to log to Google Analytics when a blog post is 30% read.

## Usage

#### How To Use
Visibility provides a set of callbacks which can be used to attach events to an element's position on screen.

Each scroll change will trigger an animation frame request that will fire callbacks for an element.

> The following examples use sticky columns to help display data alongside each example. Please consult the [sticky documentation](/modules/sticky.html) for usage examples.
```javascript
// some example callbacks
$('.demo.segment')
  .visibility({
    onTopVisible: function(calculations) {
      // top is on screen
    },
    onTopPassed: function(calculations) {
      // top of element passed
    },
    onUpdate: function(calculations) {
      // do something whenever calculations adjust
      updateTable(calculations);
    }
  })
;
```
```html
<div class="two column equal height ui grid">
  <div class="row">
    <div class="main column">
      <div class="ui first demo segment">
        <img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
    </div>
    <div class="column">
      <div class="ui sticky">
        <table class="ui basic celled sortable two column table">
          <thead>
            <th>Calculation</th>
            <th>Value</th>
          </thead>
          <tbody>
            <tr class="pixelsPassed">
              <td>pixelsPassed</td>
              <td></td>
            </tr>
            <tr class="percentagePassed">
              <td>percentagePassed</td>
              <td></td>
            </tr>
            <tr class="fits">
              <td>fits</td>
              <td></td>
            </tr>
            <tr class="width">
              <td>width</td>
              <td></td>
            </tr>
            <tr class="height">
              <td>height</td>
              <td></td>
            </tr>
            <tr class="onScreen">
              <td>onScreen</td>
              <td></td>
            </tr>
            <tr class="offScreen">
              <td>offScreen</td>
              <td></td>
            </tr>
            <tr class="passing">
              <td>passing</td>
              <td></td>
            </tr>
            <tr class="topVisible">
              <td>topVisible</td>
              <td></td>
            </tr>
            <tr class="bottomVisible">
              <td>bottomVisible</td>
              <td></td>
            </tr>
            <tr class="topPassed">
              <td>topPassed</td>
              <td></td>
            </tr>
            <tr class="bottomPassed">
              <td>bottomPassed</td>
              <td></td>
            </tr>
          </tr>
        </table>
      </div>
    </div>
  </div>
</div>
```

#### Changing Callback Frequency

Visibility's default settings will only have each callback occur **the first time** which the conditions are met. On subsequent occurences the event will not fire.

Setting `continuous: true` will make the callback fire **anytime the callback conditions are met**. So for example if you set a "top visible" callback, this callback will fire with each change in scroll when the top is visible on the page.

Setting `once: false` will make the callback fire each time a callback **becomes true**. So, using the same "top visible" example, the callback will fire each time the top of an element is passed. Even if you scroll back up and pass the element again

```html
<div class="two column equal height ui grid">
  <div class="row">
    <div class="main column">
      <div class="ui demo segment">
        <img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
    </div>
    <div class="column">
      <div class="ui sticky segments">
        <div class="ui segment">
          <div class="ui right floated compact clear button">
            Clear
          </div>
          <div class="ui toggle checkbox">
            <input type="checkbox" checked name="once" />
            <label>Once</label>
          </div>
          <div class="ui divider"></div>
          <div class="ui toggle checkbox">
            <input type="checkbox" name="continuous" />
            <label>Continuous</label>
          </div>
        </div>
        <div class="ui segment">
          Event Log
        </div>
        <div class="ui segment">
          <pre class="console"></pre>
        </div>
      </div>
    </div>
  </div>
</div>
```

## Callbacks

Callbacks are separated into two categories. Standard events will occur the first animation frame where the conditions evaluated to true.

#### Standard Events
```html
<table class="ui celled definition table">
  <thead>
    <tr>
      <th class="three wide">Event</th>
      <th class="six wide">Occurs</th>
      <th>Pseudocode</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        onOnScreen
      </td>
      <td>
        Any part of element is in current scroll viewport
      </td>
      <td>
        <div class="code" data-type="javascript">screen.bottom >= element.top && screen.bottom <= element.bottom</div>
      </td>
    </tr>
    <tr>
      <td>
        onOffScreen
      </td>
      <td>
        No part of element is in current scroll viewport
      </td>
      <td>
        <div class="code" data-type="javascript">screen.bottom <= element.top || screen.top >= element.bottom</div>
      </td>
    </tr>
    <tr>
      <td>
        onTopVisible
      </td>
      <td>
        Element's top edge has passed bottom of screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.bottom >= element.top</div>
      </td>
    </tr>
    <tr>
      <td>
        onTopPassed
      </td>
      <td>
        Element's top edge has passed top of the screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.top >= element.top</div>
      </td>
    </tr>
    <tr>
      <td>
        onBottomVisible
      </td>
      <td>
        Element's bottom edge has passed bottom of screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.bottom >= element.top</div>
      </td>
    </tr>
    <tr>
      <td>
        onPassing
      </td>
      <td>
        Any part of an element is visible on screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.bottom >= element.top && screen.top < element.bottom</div>
      </td>
    </tr>
    <tr>
      <td>
        onBottomPassed
      </td>
      <td>
        Element's bottom edge has passed top of screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.top >= element.bottom</div>
      </td>
    </tr>
  </tbody>
</table>
```

#### Grouped Events
`onPassed` allows you to specify a collection of callbacks that occur after different percentages or pixels of an element are passed
```html
<table class="ui celled definition table">
  <thead>
    <tr>
      <th class="three wide">Event</th>
      <th class="six wide">Occurs</th>
      <th>Example</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        onPassed {}
      </td>
      <td>
        A distance from the top of an element's content has been passed, either as a percentage or in pixels
      </td>
      <td>
        <div class="code" data-type="javascript">
        onPassed: {
          40: function() {
            // do something when having passed 40 pixels.
          },
          '80%': function() {
            // do something at 80%
          }
        }
        </div>
      </td>
    </tr>
  </tbody>
</table>
```

#### Reverse Events
Reverse events will occur under the same conditions but as a user scrolls back up the page.
```html
<table class="ui celled definition table">
  <thead>
    <tr>
      <th class="three wide">Event</th>
      <th class="six wide">Occurs</th>
      <th>Pseudocode</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        onTopVisibleReverse
      </td>
      <td>
        Element's top edge has not passed bottom of screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.bottom >= element.top</div>
      </td>
    </tr>
    <tr>
      <td>
        onTopPassedReverse
      </td>
      <td>
        Element's top edge has not passed top of the screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.top >= element.top</div>
      </td>
    </tr>
    <tr>
      <td>
        onBottomVisibleReverse
      </td>
      <td>
        Element's bottom edge has not passed bottom of screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.bottom >= element.top</div>
      </td>
    </tr>
    <tr>
      <td>
        onPassingReverse
      </td>
      <td>
        Element's top has not passed top of screen but bottom has
      </td>
      <td>
        <div class="code" data-type="javascript">screen.bottom >= element.top && screen.top < element.bottom</div>
      </td>
    </tr>
    <tr>
      <td>
        onBottomPassedReverse
      </td>
      <td>
        Element's bottom edge has not passed top of screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.top >= element.bottom</div>
      </td>
    </tr>
  </tbody>
</table>
```

## Behaviors

Visibility includes several useful behaviors for interacting with the component
```html
<table class="ui celled definition table">
  <thead>
    <tr>
      <th class="three wide">Behavior</th>
      <th class="six wide">Usage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        disable callbacks
      </td>
      <td>
        Disable callbacks temporarily. This is useful if you need to adjust scroll position and do not want to trigger callbacks during the position change.
      </td>
    </tr>
    <tr>
      <td>
        enable callbacks
      </td>
      <td>
        Re-enable callbacks
      </td>
    </tr>
    <tr>
      <td>
        is on screen
      </td>
      <td>
        Returns whether element is on screen
      </td>
    </tr>
    <tr>
      <td>
        is off screen
      </td>
      <td>
        Returns whether element is off screen
      </td>
    </tr>
    <tr>
      <td>
        get pixels passed
      </td>
      <td>
        Returns number of pixels passed in current element from top of element
      </td>
    </tr>
    <tr>
      <td>
        get element calculations
      </td>
      <td>
        Returns element calculations as object
      </td>
    </tr>
    <tr>
      <td>
        get screen calculations
      </td>
      <td>
        Returns screen calculations as object
      </td>
    </tr>
    <tr>
      <td>
        get screen size
      </td>
      <td>
        Returns screen size as object
      </td>
    </tr>
  </tbody>
</table>
```

## Examples

#### Infinite Scroll
As an alternative to pagination you can use `onBottomVisible` to load content automatically when the bottom of a container is reached.

```javascript
$('.infinite.example .demo.segment')
  .visibility({
    once: false,
    // update size when new content loads
    observeChanges: true,
    // load content on bottom edge visible
    onBottomVisible: function() {
      // loads a max of 5 times
      window.loadFakeContent();
    }
  })
;
```
```html
<div class="ui demo segment">
  <h3 class="ui dividing center aligned header">Infinite Scroll Example</h3>
  <img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
  <div class="ui divider"></div>
  <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
  <div class="ui divider"></div>
  <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
  <div class="ui divider"></div>
  <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
  <div class="ui divider"></div>
  <div class="ui large centered inline text loader">
    Adding more content...
  </div>
</div>
```

#### Lazy Loading Images
Visibility includes several shortcuts for setting up common visibility events. Using the setting `type: 'image'` will automatically attach events to an images `topVisible` to load the contents of `data-src` as `src`.

You can specify a placeholder image as the current `src` to make sure content doesn't jump when an image loads, or you can specify no placeholder and have the image appear.

By default images will appear without animation, however you can also specify a named [transition](/modules/transition.html), and a duration that should be used for animating the image into view

```javascript
$('.demo.items .image img')
  .visibility({
    type       : 'image',
    transition : 'fade in',
    duration   : 1000
  })
;
```
```html
<div class="ui divided demo items">
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/elliot.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Elliot Fu</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/helen.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Helen Troy</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/jenny.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Jenny Hess</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/veronika.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Veronika Ossi</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/stevie.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Stevie</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/steve.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Steve Jobes</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/ade.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Ade</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/chris.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Chris</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/joe.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Joe Henderson</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/laura.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Laura</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
</div>
```

#### Gradual Changes
Each callback receives all calculated values as its first parameter, allowing you to adjust an element using

```javascript
$('.changing.example .demo.segment')
  .visibility({
    once       : false,
    continuous : true,
    onPassing  : function(calculations) {
      var newColor = 'rgba(0, 0, 0, ' + calculations.percentagePassed +')';
      $(this)
        .css('background-color', newColor)
      ;
    }
  })
;
```
```html
<div class="ui demo segment" style="height: 1000px;"></div>
```

#### Fixing Content To Viewport
Visibility provides a lightweight method for sticking content to a page's viewport. Using `type: fixed` will add the class `fixed` after an element is passed in the viewport. Using this class name you can assign special layout conditions to an item once it is passed.

Using the special visibility type `fixed` will automatically create a placeholder element, which will be shown or hidden after an element is passed, to ensure that the page's position does not change when the element is "fixed" and removed from normal layout flow.

In this example, when an element is passed we fix it to the viewport, add a background color and box shadow so that it can float above other content. We also show an adjacent placeholder element which makes sure that content stays offset the same as if the menu was still in content flow

> You may need to adjust your fixed content's `z-index` to ensure it appears above other page content.
```javascript
$('.overlay.example .overlay')
  .visibility({
    type   : 'fixed',
    offset : 15 // give some space from top of screen
  })
;
```
```css
.visibility.example .overlay {
  background-color: #FFFFFF;
  padding: 0em;
  box-shadow: 0px 0px 0px rgba(0, 0, 0, 0);
  transition: all 0.5s ease;
  background: transparent;
}
/* change style */
.visibility.example .fixed.overlay {
  position: fixed;
  padding: 1em;
  box-shadow: 0px 0px 6px rgba(0, 0, 0, 0.2);
}
```
```html
<div class="overlay">
  <div class="ui secondary menu">
    <a class="item">
      <i class="sidebar icon"></i> Menu
    </a>
    <a class="item">Option 1</a>
    <a class="item">Option 2</a>
    <a class="item">Option 3</a>
  </div>
</div>
<div class="ui clearing divider"></div>
<img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
<div class="ui divider"></div>
<img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
<div class="ui divider"></div>
<img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
<div class="ui divider"></div>
<img src="/images/wireframe/paragraph.png" class="ui wireframe image">
<div class="ui divider"></div>
<img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
<div class="ui divider"></div>
<img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
<div class="ui divider"></div>
<img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
<div class="ui divider"></div>
<img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
<div class="ui divider"></div>
<img src="/images/wireframe/paragraph.png" class="ui wireframe image">
```

## Settings

#### Functionality
Settings to configure visibility behavior
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th>Setting</th>
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>once</td>
      <td>true</td>
      <td>When set to false a callback will occur each time an element **passes the threshold** for a condition.</td>
    </tr>
    <tr>
      <td>continuous</td>
      <td>false</td>
      <td>When set to true a callback will occur anytime an element **passes a condition**  not just immediately after the threshold is met.</td>
    </tr>
    <tr>
      <td>type</td>
      <td>false</td>
      <td>Set to `image` to load images when on screen. Set to `fixed` to add class name `fixed` when passed.</td>
    </tr>
    <tr>
      <td>initialCheck</td>
      <td>true</td>
      <td>Whether visibility conditions should be checked immediately on init</td>
    </tr>
    <tr>
      <td>context</td>
      <td>window</td>
      <td>The scroll context visibility should use.</td>
    </tr>
    <tr>
      <td>refreshOnLoad</td>
      <td>true</td>
      <td>Whether visibility conditions should be checked on window `load`. This ensures that after images load content positions will be updated correctly.</td>
    </tr>
    <tr>
      <td>refreshOnResize</td>
      <td>true</td>
      <td>Whether visibility conditions should be checked on window `resize`. Useful when content resizes causes continuous changes in position</td>
    </tr>
    <tr>
      <td>checkOnRefresh</td>
      <td>true</td>
      <td>Whether visibility conditions should be checked on calls to `refresh`. These calls can be triggered from either `resize`, `load` or manually calling `$('.foo').visibility('refresh')`</td>
    </tr>
    <tr>
      <td>zIndex</td>
      <td>1</td>
      <td>Specify a z-index when using `type: 'fixed'`. <div class="ui teal horizontal label">New in 2.2</div></td>
    </tr>
    <tr>
      <td>offset</td>
      <td>0</td>
      <td>Value that context `scrollTop` should be adjusted in pixels. Useful for making content appear below content fixed to the page.</td>
    </tr>
    <tr>
      <td>includeMargin</td>
      <td>false</td>
      <td>Whether element calculations should include its margin</td>
    </tr>
    <tr>
      <td>throttle</td>
      <td>false</td>
      <td>When set to an integer, scroll position will be debounced using this ms value. `false` will debounce with `requestAnimationFrame`.</td>
    </tr>
    <tr>
      <td>observeChanges</td>
      <td>true</td>
      <td>Whether to automatically refresh content when changes are made to the element's DOM subtree </td>
    </tr>
    <tr>
      <td>transition</td>
      <td>false</td>
      <td>When using `type: image` allows you to specify transition when showing a loaded image</td>
    </tr>
    <tr>
      <td>duration</td>
      <td>1000</td>
      <td>When using `type: image` allows you to specify transition duration</td>
    </tr>
  </tbody>
</table>
```

#### Visibility Callbacks
Callbacks that occur on named visibility events
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <tr>
      <th class="four wide"></th>
      <th>Context</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>onTopVisible</td>
      <td>$element</td>
      <td>Element's top edge has passed bottom of screen</td>
    </tr>
    <tr>
      <td>onTopPassed</td>
      <td>$element</td>
      <td>Element's top edge has passed top of the screen</td>
    </tr>
    <tr>
      <td>onBottomVisible</td>
      <td>$element</td>
      <td>Element's bottom edge has passed bottom of screen</td>
    </tr>
    <tr>
      <td>onPassing</td>
      <td>$element</td>
      <td>Any part of an element is visible on screen</td>
      </td>
    </tr>
    <tr>
      <td>onBottomPassed</td>
      <td>$element</td>
      <td>Element's bottom edge has passed top of screen</td>
    </tr>
    <tr>
      <td>onTopVisibleReverse</td>
      <td>$element</td>
      <td>Element's top edge has not passed bottom of screen</td>
    </tr>
    <tr>
      <td>onTopPassedReverse</td>
      <td>$element</td>
      <td>Element's top edge has not passed top of the screen</td>
    </tr>
    <tr>
      <td>onBottomVisibleReverse</td>
      <td>$element</td>
      <td>Element's bottom edge has not passed bottom of screen</td>
    </tr>
    <tr>
      <td>onPassingReverse</td>
      <td>$element</td>
      <td>Element's top has not passed top of screen but bottom has</td>
      </td>
    </tr>
    <tr>
      <td>onBottomPassedReverse</td>
      <td>$element</td>
      <td>Element's bottom edge has not passed top of screen</td>
    </tr>
  </tbody>
</table>
```

#### Image Callbacks
Callbacks that occur only when using [type: 'fixed'](#lazy-loading-images)

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <tr>
      <th class="four wide"></th>
      <th>Context</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>onLoad</td>
      <td>img</td>
      <td>Occurs after an image has completed loading</td>
    </tr>
    <tr>
      <td>onAllLoaded</td>
      <td>last loaded img</td>
      <td>Occurs after all `img` initialized at the same time have loaded.</td>
    </tr>
  </tbody>
</table>
```

#### Fixed Callbacks
Callbacks that occur only when using [type: 'fixed'](#fixing-content-to-viewport)

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <tr>
      <th class="four wide"></th>
      <th>Context</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>onFixed</td>
      <td>$element</td>
      <td>Occurs after element has been assigned position fixed</td>
    </tr>
    <tr>
      <td>onUnfixed</td>
      <td>$element</td>
      <td>Occurs after element has been removed from fixed position</td>
    </tr>
  </tbody>
</table>
```

#### Utility Callbacks
Callbacks that occur on named visibility events

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <tr>
      <th class="four wide"></th>
      <th>Context</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>onUpdate(calculations)</td>
      <td>$element</td>
      <td>Occurs each time an elements calculations are updated</td>
    </tr>
    <tr>
      <td>onRefresh</td>
      <td>$element</td>
      <td>Occurs whenever element's visibility is refreshed</td>
    </tr>
  </tbody>
</table>
```

#### DOM Settings
DOM settings specify how this module should interface with the DOM
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th class="three wide">Setting</th>
    <th class="six wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>namespace</td>
      <td>visibility</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
className : {
  fixed     : 'fixed',
}
        </div>
      </td>
      <td>Class names used to attach style to state</td>
    </tr>
  </tbody>
</table>
```

#### Debug Settings
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
      <td>Visibility</td>
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
error : {
  method : 'The method you called is not defined.',
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```
