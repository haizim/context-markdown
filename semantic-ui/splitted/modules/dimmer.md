# Dimmer

A dimmer hides distractions to focus attention on particular content

## Definition

#### Dimmer
A simple dimmer displays no content
```javascript
// left button
$('.segment').dimmer('show');
// right button
$('.segment').dimmer('hide');
```
> A dimmer will automatically be created when a dimming behavior is triggered on an element.
```html
<div class="ui segment">
  <h3 class="ui header">
    Overlayable Section
  </h3>
  <div class="ui small images">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <img class="ui medium wireframe image" src="/images/wireframe/media-paragraph.png">
</div>
```
```html
<div class="ui segment">
  <!-- Dimmer Generated Automatically No Need to Include !-->
  <h3 class="ui header">
    Overlayable Section
  </h3>
  <div class="ui small images">
    <img>
    <img>
    <img>
  </div>
  <p></p>
</div>
```
```html
<div class="ui ignored ignored icon buttons">
  <div class="ui show button"><i class="plus icon"></i></div>
  <div class="ui hide button"><i class="minus icon"></i></div>
</div>
```

#### Content Dimmer
A dimmer can display content
> Since <div class="ui horizontal label">2.3</div> dimmers with content now only need a single wrapping `content` container.
```html
<div class="ui segment">
  <h3 class="ui header">
    Overlayable Section
  </h3>
  <div class="ui small images">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <img class="ui medium wireframe image" src="/images/wireframe/media-paragraph.png">
  <div class="ui dimmer">
    <div class="content">
      <h2 class="ui inverted icon header">
        <i class="heart icon"></i>
        Dimmed Message!
      </h2>
    </div>
  </div>
</div>
```
```html
<div class="ui ignored icon buttons">
  <div class="ui show button"><i class="plus icon"></i></div>
  <div class="ui hide button"><i class="minus icon"></i></div>
</div>
```

#### Page Dimmer
A dimmer can be formatted to be fixed to the page
```html
<div class="ui page dimmer">
  <div class="content">
    Hello
  </div>
</div>
```
```html
<div class="ui page button">
  <i class="plus icon"></i>Show
</div>
```

## States

#### Active
An active dimmer will dim its parent container
```html
<div class="ui segment">
  <div class="ui active dimmer"></div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```

#### Disabled
A disabled dimmer cannot be activated
```html
<div class="ui segment">
  <div class="ui disabled dimmer"></div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```

## Variations

### Dimmable

#### Blurring
A dimmable element can blur its contents
```html
<div class="ui blurring segment">
  <div class="ui dimmer"></div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ui ignored ignored icon buttons">
  <div class="ui show button"><i class="plus icon"></i></div>
  <div class="ui hide button"><i class="minus icon"></i></div>
</div>
```
```html
<div class="ui blurring segment">
  <div class="ui inverted dimmer"></div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ui ignored ignored icon buttons">
  <div class="ui show button"><i class="plus icon"></i></div>
  <div class="ui hide button"><i class="minus icon"></i></div>
</div>
```

### Alignment

#### Vertical Alignment
A dimmer can have its content top or bottom aligned.
```html
<div class="ui segment">
  <div class="ui top aligned dimmer">
    <div class="content">
      <h2 class="ui inverted header">Title</h2>
      <div class="ui primary button">Add</div>
      <div class="ui button">View</div>
    </div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ui ignored ignored icon buttons">
  <div class="ui show button"><i class="plus icon"></i></div>
  <div class="ui hide button"><i class="minus icon"></i></div>
</div>
```
```html
<div class="ui segment">
  <div class="ui bottom aligned dimmer">
    <div class="content">
      <h2 class="ui inverted header">Title</h2>
      <div class="ui primary button">Add</div>
      <div class="ui button">View</div>
    </div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ui ignored ignored icon buttons">
  <div class="ui show button"><i class="plus icon"></i></div>
  <div class="ui hide button"><i class="minus icon"></i></div>
</div>
```

### Dimmer

#### Simple Dimmer
A dimmer can be controlled without Javascript
> Having any parent element receive the class `ui dimmable dimmed` will trigger the dimmer to display.
```html
<div class="ui dimmable dimmed segment">
  <div class="ui simple dimmer"></div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```

#### Inverted Dimmer
A dimmer can be formatted to have its colors inverted
```html
<div class="ui segment">
  <div class="ui inverted dimmer"></div>
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
```
```html
<div class="ignored ui icon buttons">
  <div class="ui show button"><i class="plus icon"></i></div>
  <div class="ui hide button"><i class="minus icon"></i></div>
</div>
```

## Examples

#### Dimmer Events
A dimmer can trigger a visibility change on an event
```javascript
$('.event.example .image')
  .dimmer({
    on: 'hover'
  })
;
```
```html
<div class="ui medium image">
  <div class="ui dimmer">
    <div class="content">
      <h2 class="ui inverted header">Title</h2>
      <div class="ui primary button">Add</div>
      <div class="ui button">View</div>
    </div>
  </div>
  <img class="ui image" src="/images/wireframe/image.png">
</div>
<div class="ui circular image">
  <div class="ui dimmer">
    <div class="content">
      <div class="ui small primary button">Add</div>
      <div class="ui small button">View</div>
    </div>
  </div>
  <img src="/images/wireframe/square-image.png">
</div>
```

#### Loaders inside Dimmers
Any loader inside a dimmer will automatically use an appropriate color to match
```html
<div class="ui segment">
  <div class="ui inverted dimmer">
    <div class="ui text loader">Loading</div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ignored ui icon buttons">
  <div class="ui show button"><i class="plus icon"></i></div>
  <div class="ui hide button"><i class="minus icon"></i></div>
</div>
```

## Usage

### Display
You can display a dimmer by either invoking .dimmer('show') on a section or a dimmer itself. If you choose to  dim a dimmable section, a dimmer will automatically be created.
```html
// these two are the same
$('.ui.dimmable')
  .dimmer('show')
;
$('.ui.dimmable .dimmer')
  .dimmer('show')
;
```

#### Creating Dimmers
If a dimmer does not exist inside the element it will be created on first use.
```javascript
$('h4')
  .dimmer('toggle')
;
```

#### Showing a Specific Dimmer
If a dimmer is already inside an element, you can call behavior on the dimmable section or the dimmer itself.
```javascript
// If a dimmer exists on a page, you can make it appear by calling it directly
$('.page.dimmer:first')
  .dimmer('toggle')
;
```

## Behavior

All the following behaviors can be called using the syntax:

> Behaviors must be called on the same content which you originally initialize the dimmer, whether it is the `dimmable` context, or the `ui dimmer`

```javascript
$('.your.element')
  .dimmer('behavior name', argumentOne, argumentTwo)
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
      <td>add content (element)</td>
      <td>Detaches a given element from DOM and reattaches element inside dimmer</td>
    </tr>
    <tr>
      <td>show</td>
      <td>Shows dimmer</td>
    </tr>
    <tr>
      <td>hide</td>
      <td>Hides dimmer</td>
    </tr>
    <tr>
      <td>toggle</td>
      <td>Toggles current dimmer visibility</td>
    </tr>
    <tr>
      <td>set opacity(opacity)</td>
      <td>Changes dimmer opacity</td>
    </tr>
    <tr>
      <td>create</td>
      <td>Creates a new dimmer in dimmable context</td>
    </tr>
    <tr>
      <td>get duration</td>
      <td>Returns current duration for show or hide event depending on current visibility</td>
    </tr>
    <tr>
      <td>get dimmer</td>
      <td>Returns DOM element for dimmer</td>
    </tr>
    <tr>
      <td>has dimmer</td>
      <td>Returns whether current dimmable has a dimmer</td>
    </tr>
    <tr>
      <td>is active</td>
      <td>Whether section's dimmer is active</td>
    </tr>
    <tr>
      <td>is animating</td>
      <td>Whether dimmer is animating</td>
    </tr>
    <tr>
      <td>is dimmer</td>
      <td>Whether current element is a dimmer</td>
    </tr>
    <tr>
      <td>is dimmable</td>
      <td>Whether current element is a dimmable section</td>
    </tr>
    <tr>
      <td>is disabled</td>
      <td>Whether dimmer is disabled</td>
    </tr>
    <tr>
      <td>is enabled</td>
      <td>Whether dimmer is not disabled</td>
    </tr>
    <tr>
      <td>is page</td>
      <td>Whether dimmable section is `body`</td>
    </tr>
    <tr>
      <td>is page dimmer</td>
      <td>Whether dimmer is a page dimmer</td>
    </tr>
    <tr>
      <td>set active</td>
      <td>Sets page dimmer to active</td>
    </tr>
    <tr>
      <td>set dimmable</td>
      <td>Sets an element as a dimmable section</td>
    </tr>
    <tr>
      <td>set dimmed</td>
      <td>Sets a dimmable section as dimmed</td>
    </tr>
    <tr>
      <td>set page dimmer</td>
      <td>Sets current dimmer as a page dimmer</td>
    </tr>
    <tr>
      <td>set disabled</td>
      <td>Sets a dimmer as disabled</td>
    </tr>
  </tbody>
</table>
```

## Settings

### Dimmer

#### Behavior
```html
<table class="ui sortable celled definition table">
  <thead>
    <th></th>
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>useFlex</td>
      <td class="six wide">true</td>
      <td>Whether dimmers should use flex or legacy positioning</td>
    </tr>
    <tr>
      <td>variation</td>
      <td class="six wide">false</td>
      <td>Specify a variation to add when generating dimmer, like `inverted`</td>
    </tr>
    <tr>
      <td>dimmerName</td>
      <td class="six wide">false</td>
      <td>If initializing a dimmer on a `dimmable` context, you can use `dimmerName` to distinguish between multiple dimmers in that context.</td>
    </tr>
    <tr>
      <td>closable</td>
      <td class="six wide">auto</td>
      <td>Whether clicking on the dimmer should hide the dimmer (Defaults to `auto`, closable only when `settings.on` is not `hover`</td>
    </tr>
    <tr>
      <td>on</td>
      <td class="six wide">false</td>
      <td>Can be set to `hover` or `click` to show/hide dimmer on dimmable event</td>
    </tr>
    <tr>
      <td>useCSS</td>
      <td class="six wide">true</td>
      <td>Whether to dim dimmers using CSS transitions.</td>
    </tr>
    <tr>
      <td>duration</td>
      <td>
        <div class="code">
duration    : {
  show : 500,
  hide : 500
}
        </div>
      </td>
      <td>Animation duration of dimming. If an integer is used, that value will apply to both show and hide animations.</td>
    </tr>
    <tr>
      <td>transition</td>
      <td>
        Fade
      </td>
      <td>Named transition to use when animating menu in and out. Fade and slide down are available without including [ui transitions](/modules/transition.html)</td>
    </tr>
  </tbody>
</table>
```

#### Callbacks

```html
<table class="ui sortable celled definition table">
  <thead>
    <th class="three wide"></th>
    <th class="three wide">Context</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>onShow</td>
      <td>dimmable</td>
      <td>Callback on element show</td>
    </tr>
    <tr>
      <td>onHide</td>
      <td>dimmable</td>
      <td>Callback on element hide</td>
    </tr>
    <tr>
      <td>onChange</td>
      <td>dimmable</td>
      <td>Callback on element show or hide</td>
    </tr>
  </tbody>
</table>
```

## Module

These settings are native to all modules, and define how the component ties content to DOM attributes, and debugging settings for the module.

```html
<table class="ui sortable celled definition table">
  <thead>
    <th></th>
    <th class="eight wide">Default</th>
    <th>Description</th>
  </thead>

  <tbody>
    <tr>
      <td>namespace</td>
      <td>dimmer</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>selector</td>
      <td>
        <div class="code">
selector: {
  dimmable : '.dimmable',
  dimmer   : '.ui.dimmer',
  content  : '.ui.dimmer > .content, .ui.dimmer > .content > .center'
}
        </div>
      </td>
      <td>Object containing selectors used by module.</td>
    </tr>
    <tr>
      <td>template</td>
      <td>
        <div class="code">
template : {
  dimmer: function() {
   return $('<div />').attr('class', 'ui dimmer');
  }
}
        </div>
      </td>
      <td>Templates used to generate dimmer content</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
className : {
  active     : 'active',
  dimmable   : 'dimmable',
  dimmed     : 'dimmed',
  disabled   : 'disabled',
  pageDimmer : 'page',
  hide       : 'hide',
  show       : 'show',
  transition : 'transition'
}
        </div>
      </td>
      <td>Class names used to attach style to state</td>
    </tr>
    <tr>
      <td>name</td>
      <td>Dimmer</td>
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
      <td>
        <div class="code">
error   : {
  method   : 'The method you called is not defined.'
}
        </div>
      </td>
      <td>Error messages displayed to console</td>
    </tr>
  </tbody>
</table>
```
