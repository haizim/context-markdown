# Transition

A transition is an animation usually used to move content in or out of view

## Transitions

#### Scale
An element can scale into or out of view
```javascript
$('.autumn.leaf')
  .transition('scale')
;
```

#### Zoom
An element can zoom into view from far away
```javascript
$('.autumn.leaf')
  .transition('zoom')
;
```

#### Fade
An element can fade into or out of view descending and ascending
```javascript
$('.autumn.leaf')
  .transition('fade')
;
```
```javascript
$('.autumn.leaf')
  .transition('fade up')
;
```
```javascript
$('.autumn.leaf')
  .transition('fade down')
;
```
```javascript
$('.autumn.leaf')
  .transition('fade left')
;
```
```javascript
$('.autumn.leaf')
  .transition('fade right')
;
```

#### Flip
An element can flip into or out of view vertically or horizontally
```javascript
$('.autumn.leaf')
  .transition('horizontal flip')
;
```
```javascript
$('.autumn.leaf')
  .transition('vertical flip')
;
```

#### Drop
An element can drop into view from above
```javascript
$('.autumn.leaf')
  .transition('drop')
;
```

#### Fly
An element can fly in from off canvas
```javascript
$('.autumn.leaf')
  .transition('fly left')
;
```
```javascript
$('.autumn.leaf')
  .transition('fly right')
;
```
```javascript
$('.autumn.leaf')
  .transition('fly up')
;
```
```javascript
$('.autumn.leaf')
  .transition('fly down')
;
```

#### Swing
An element can swing into view
```javascript
$('.autumn.leaf')
  .transition('swing left')
;
```
```javascript
$('.autumn.leaf')
  .transition('swing right')
;
```
```javascript
$('.autumn.leaf')
  .transition('swing up')
;
```
```javascript
$('.autumn.leaf')
  .transition('swing down')
;
```

#### Browse
An element can appear and disappear as part of a series
```javascript
$('.autumn.leaf')
  .transition('browse')
;
```
```javascript
$('.autumn.leaf')
  .transition('browse right')
;
```

#### Slide
An element can appear to slide in from above or below
```javascript
$('.autumn.leaf')
  .transition('slide down')
;
```
```javascript
$('.autumn.leaf')
  .transition('slide up')
;
```
```javascript
$('.autumn.leaf')
  .transition('slide left')
;
```
```javascript
$('.autumn.leaf')
  .transition('slide right')
;
```

## Static Animations

#### Jiggle
An element can jiggle to draw attention to its shape
```javascript
$('.autumn.leaf')
  .transition('jiggle')
;
```

#### Flash
An element can flash to draw attention to itself
```javascript
$('.autumn.leaf')
  .transition('flash')
;
```

#### Shake
An element can shake to draw attention to its position
```javascript
$('.autumn.leaf')
  .transition('shake')
;
```

#### Pulse
An element can pulse to draw attention to its visibility
```javascript
$('.autumn.leaf')
  .transition('pulse')
;
```

#### Tada
An element can give user positive feedback for an action
```javascript
$('.autumn.leaf')
  .transition('tada')
;
```

#### Bounce
An element can bounce to politely remind you of itself
```javascript
$('.autumn.leaf')
  .transition('bounce')
;
```

#### Glow
An element can glow to show its position in a page.
```javascript
$('.autumn.leaf')
  .transition('glow')
;
```

## Examples

### Visibility
After the animation queue finishes for an element, its final visibility state is determined. If an animation is an outward transition, the final visibility status will be hidden. If an animation is inward the element will be visible after the animation finishes.
```javascript
$('.long.leaf.image')
  .transition('scale')
;
```

### Specifying a direction
To force an animation direction, add either `in` or `out` to the animation name.
```javascript
$('.long.leaf.image')
  // if a direction if specified it will be obeyed
  .transition('horizontal flip in')
  .transition('vertical flip in')
;
```

### Automatic Direction

If an animation direction is not specified it will automatically be determined based on the elements current visibility. For example, if the element is visible the animation "fade out" will be called, if the animation is not visible "fade in".

```javascript
$('.long.leaf.image')
  // fade up out is used if available
  .transition('fade up')
  // this is now fade up in
  .transition('fade up')
;
```

### Grouped Transitions

#### Animation Intervals
When animating several different items in a group you may want to use an interval so that each item appears consecutively
```javascript
$('.jiggle.images .image')
  .transition({
    animation : 'jiggle',
    duration  : 800,
    interval  : 200
  })
;
```
```html
<div class="ui small jiggle images">
  <img src="/images/wireframe/image.png" class="ui wireframe image">
  <img src="/images/wireframe/image.png" class="ui wireframe image">
  <img src="/images/wireframe/image.png" class="ui wireframe image">
</div>
```

#### Animation Order
When hiding groups of elements, the default setting uses `reverse: 'auto'`. This will automatically reverse the order of animations from back-to-front when hiding elements to avoid layout reflows. When showing elements the order will return to its normal sequence.
```javascript
$('.sequenced.images .image')
  .transition({
    animation : 'scale',
    reverse   : 'auto', // default setting
    interval  : 200
  })
;
```
```html
<div class="ui small sequenced images">
  <img src="/images/wireframe/image.png" class="ui wireframe image">
  <img src="/images/wireframe/image.png" class="ui wireframe image">
  <img src="/images/wireframe/image.png" class="ui wireframe image">
  <img src="/images/wireframe/image.png" class="ui wireframe image">
  <img src="/images/wireframe/image.png" class="ui wireframe image">
  <img src="/images/wireframe/image.png" class="ui wireframe image">
</div>
```

#### Forcing Order
If you need to manually force reverse animations regardless of the animation direction, you can use `reverse: true`.
```javascript
$('.reverse.images .image')
  .transition({
    animation : 'pulse',
    reverse   : true,
    interval  : 200
  })
;
```
```html
<div class="ui small reverse images">
  <img src="/images/wireframe/image.png" class="ui wireframe image">
  <img src="/images/wireframe/image.png" class="ui wireframe image">
  <img src="/images/wireframe/image.png" class="ui wireframe image">
</div>
```

### Static Animations
Animations that do not have an in or out animation defined, will maintain their current visibility after running
```javascript
$('.long.leaf.image')
  .transition('pulse')
;
```

### Looping
Animation loops can be controlled by setting looping. Callbacks will occur after each loop cycle
```javascript
$('.long.leaf.image')
  .transition('set looping')
  .transition('bounce', '2000ms')
;
```
```javascript
$('.long.leaf.image')
  .transition('remove looping')
;
```

## Usage

### Introduction

UI Transitions provide a wrapper for using CSS transitions in Javascript providing cross-browser callbacks, advanced queuing, and feature detection.

Transitions are loosely coupled with other ui modules like [dropdowns](/modules/dropdown.html) and [modals](/modules/modal.html) to provide element transitions

### Types
Transitions are separated into three categories. **Inward transitions**, **outward transitions**, and **static transitions**. These three categories determine the visibility of the element after the animation completes.

## Usage

### Initializing

If a transition is called without any arguments all default settings will be used.

```javascript
$('.green.leaf')
  // default everything
  .transition()
;
```

### Passing in settings
Transitions use similar argument shorthand as [animate](http://api.jquery.com/animate/). You can specify callback functions, animation duration, and other settings using the same arguments. Durations can be specified as strings with CSS shorthand, or with numbers.
```javascript
$('.green.leaf')
  .transition({
    animation  : 'scale',
    duration   : '2s',
    onComplete : function() {
      alert('done');
    }
  })
;
```

### Display Type

Animations can be used on any display type not just block level elements. For example you can animate a button while preserving its `inline-block` status.
```javascript
$('.test.button')
  .transition('horizontal flip', '500ms')
;
```
```html
<div class="ui divider"></div>
<div class="ui teal test labeled icon button">
  <i class="icon user"></i> Sign-up
</div>
```

### Queuing animations

Animations called in sequence will be queued. Any queued animation will automatically determine the transition direction if none is specified.
```javascript
$('.green.leaf')
  .transition('horizontal flip', '500ms')
  .transition('horizontal flip', 500, function() {
    alert('done!');
  })
;
```

### Stopping Animations

Animations can be stopped using three methods. `stop` will end the current animation, `stop all` will end animation and remove queued animations, and `clear queue` will continue the current playback but remove queued animations.

```javascript
// only first horizontal flip cancelled
$('.green.leaf')
  .transition('horizontal flip')
  .transition('horizontal flip')
  .transition('horizontal flip')
  .transition('stop')
  .transition('vertical flip')
;
```
```javascript
// all horizontal flip cancelled
$('.green.leaf')
  .transition('horizontal flip')
  .transition('horizontal flip')
  .transition('horizontal flip')
  .transition('stop all')
  .transition('vertical flip')
;
```
```javascript
// all queued animations cancelled
$('.green.leaf')
  .transition('horizontal flip')
  .transition('horizontal flip')
  .transition('vertical flip')
  .transition('clear queue')
;
```

### Hide/Show Without Transition

You can use transitions `show` and `hide` behavior to hide content without animation. This will preserve the display type, like `flex` or `table-cell` of an element just like animations.

> Transition only use inline styles when an element's final display state is not `block`, or when an element cannot be hidden without an inline override.

```javascript
$('.demo.table tr:last-child')
  .transition('toggle')
;
```
```javascript
$('.demo.table td:last-child')
  .transition('hide')
;
```

```html
<table class="ui demo table">
  <tbody>
    <tr>
      <td>John Lilki</td>
      <td>jhlilk22@yahoo.com</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Jamie Harington</td>
      <td>jamieharingonton@yahoo.com</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>Jill Lewis</td>
      <td>jilsewris22@yahoo.com</td>
      <td>Yes</td>
    </tr>
  </tbody>
</table>
```

### Behavior

All the following behaviors can be called using the syntax:
```javascript
$('.your.element')
  .transition('behavior name', argumentOne, argumentTwo)
;
```

```html
<table class="ui definition sortable celled table segment">
  <thead>
    <tr>
    <th>Behavior</th>
    <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>stop</td>
      <td>Stop current animation and preserve queue</td>
    </tr>
    <tr>
      <td>stop all</td>
      <td>Stop current animation and queued animations</td>
    </tr>
    <tr>
      <td>clear queue</td>
      <td>Clears all queued animations</td>
    </tr>
    <tr>
      <td>show</td>
      <td>Stop current animation and show element</td>
    </tr>
    <tr>
      <td>hide</td>
      <td>Stop current animation and hide element</td>
    </tr>
    <tr>
      <td>toggle</td>
      <td>Toggles between hide and show</td>
    </tr>
    <tr>
      <td>force repaint</td>
      <td>Forces reflow using a more expensive but stable method</td>
    </tr>
    <tr>
      <td>repaint</td>
      <td>Triggers reflow on element</td>
    </tr>
    <tr>
      <td>reset</td>
      <td>Resets all conditions changes during transition</td>
    </tr>
    <tr>
      <td>looping</td>
      <td>Enables animation looping</td>
    </tr>
    <tr>
      <td>remove looping</td>
      <td>Removes looping state from element</td>
    </tr>
    <tr>
      <td>disable</td>
      <td>Adds disabled state (stops ability to animate)</td>
    </tr>
    <tr>
      <td>enable</td>
      <td>Removes disabled state</td>
    </tr>
    <tr>
      <td>set duration(duration)</td>
      <td>Modifies element animation duration</td>
    </tr>
    <tr>
      <td>save conditions</td>
      <td>Saves all class names and styles to cache to be retrieved after animation</td>
    </tr>
    <tr>
      <td>restore conditions</td>
      <td>Adds back cached names and styles to element</td>
    </tr>
    <tr>
      <td>get animation name</td>
      <td>Returns vendor prefixed animation property for animationname</td>
    </tr>
    <tr>
      <td>get animation event</td>
      <td>Returns vendor prefixed animation property for animationend</td>
    </tr>
    <tr>
      <td>is visible</td>
      <td>Returns whether element is currently visible</td>
    </tr>
    <tr>
      <td>is animating</td>
      <td>Returns whether transition is currently occurring</td>
    </tr>
    <tr>
      <td>is looping</td>
      <td>Returns whether animation looping is set</td>
    </tr>
    <tr>
      <td>is supported</td>
      <td>Returns whether animations are supported</td>
    </tr>
  </tbody>
</table>
```

## Settings

### Transition Settings
Form settings modify the transition behavior
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
      <td>animation</td>
      <td>fade</td>
      <td>Named animation event to used. Must be defined in CSS.</td>
    </tr>
    <tr>
      <td>interval</td>
      <td>0</td>
      <td>Interval in MS between each elements transition</td>
    </tr>
    <tr>
      <td>reverse</td>
      <td>auto</td>
      <td>When an interval is specified, sets order of animations. `auto` reverses only animations that are hiding.</td>
    </tr>
    <tr>
      <td>displayType</td>
      <td>false</td>
      <td>Specify the final display type (block, inline-block etc) so that it doesn't have to be calculated.</td>
    </tr>
    <tr>
      <td>duration</td>
      <td>500ms</td>
      <td>Duration of the CSS transition animation</td>
    </tr>
    <tr>
      <td>useFailSafe</td>
      <td>true</td>
      <td>If enabled a `timeout` will be added to ensure `animationend` callback occurs even if element is hidden</td>
    </tr>
    <tr>
      <td>allowRepeats</td>
      <td>false</td>
      <td>If enabled will allow same animation to be queued while it is already occurring</td>
    </tr>
    <tr>
      <td>queue</td>
      <td>true</td>
      <td>Whether to automatically queue animation if another is occurring</td>
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
    <th class="four wide">Setting</th>
    <th>Context</th>
    <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>onShow</td>
      <td>transitioned element</td>
      <td>Callback on each transition that changes visibility to shown</td>
    </tr>
    <tr>
      <td>onHide</td>
      <td>transitioned element</td>
      <td>Callback on each transition that changes visibility to hidden</td>
    </tr>
    <tr>
      <td>onStart</td>
      <td>transitioned element</td>
      <td>Callback on animation start, useful for queued animations</td>
    </tr>
    <tr>
      <td>onComplete</td>
      <td>transitioned element</td>
      <td>Callback on each transition complete</td>
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
    <th class="six wide">Default</th>
    <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>namespace</td>
      <td>transition</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
  className   : {
    animating  : 'animating',
    disabled   : 'disabled',
    hidden     : 'hidden',
    inward     : 'in',
    loading    : 'loading',
    looping    : 'looping',
    outward    : 'out',
    transition : 'transition',
    visible    : 'visible'
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
      <td>Transition</td>
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
  errors   : {
    noAnimation : 'There is no CSS animation matching the one you specified.',
    method      : 'The method you called is not defined'
  }
        </div>
      </td>
    </tr>
  </tbody>
</table>
```
