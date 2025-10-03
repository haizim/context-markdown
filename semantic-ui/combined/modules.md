## === accordion.md ===

# Accordion

An accordion allows users to toggle the display of sections of content

## Definition

#### Accordion
A standard accordion
```html
<div class="ui accordion">
  <div class="active title">
    <i class="dropdown icon"></i>
    What is a dog?
  </div>
  <div class="active content">
    <p>A dog is a type of domesticated animal. Known for its loyalty and faithfulness, it can be found as a welcome guest in many households across the world.</p>
  </div>
  <div class="title">
    <i class="dropdown icon"></i>
    What kinds of dogs are there?
  </div>
  <div class="content">
    <p>There are many breeds of dogs. Each breed varies in size and temperament. Owners often select a breed of dog that they find to be compatible with their own lifestyle and desires from a companion.</p>
  </div>
  <div class="title">
    <i class="dropdown icon"></i>
    How do you acquire a dog?
  </div>
  <div class="content">
    <p>Three common ways for a prospective owner to acquire a dog is from pet shops, private owners, or shelters.</p>
    <p>A pet shop may be the most convenient way to buy a dog. Buying a dog from a private owner allows you to assess the pedigree and upbringing of your dog before choosing to take it home. Lastly, finding your dog from a shelter, helps give a good home to a dog who may not find one so readily.</p>
  </div>
</div>
```

#### Styled
A styled accordion adds basic formatting
```html
<div class="ui styled accordion">
  <div class="active title">
    <i class="dropdown icon"></i>
    What is a dog?
  </div>
  <div class="active content">
    <p>A dog is a type of domesticated animal. Known for its loyalty and faithfulness, it can be found as a welcome guest in many households across the world.</p>
  </div>
  <div class="title">
    <i class="dropdown icon"></i>
    What kinds of dogs are there?
  </div>
  <div class="content">
    <p>There are many breeds of dogs. Each breed varies in size and temperament. Owners often select a breed of dog that they find to be compatible with their own lifestyle and desires from a companion.</p>
  </div>
  <div class="title">
    <i class="dropdown icon"></i>
    How do you acquire a dog?
  </div>
  <div class="content">
    <p>Three common ways for a prospective owner to acquire a dog is from pet shops, private owners, or shelters.</p>
    <p>A pet shop may be the most convenient way to buy a dog. Buying a dog from a private owner allows you to assess the pedigree and upbringing of your dog before choosing to take it home. Lastly, finding your dog from a shelter, helps give a good home to a dog who may not find one so readily.</p>
  </div>
</div>
```

## Variations

#### Fluid
An accordion can take up the width of its container
```html
<div class="ui styled fluid accordion">
  <div class="active title">
    <i class="dropdown icon"></i>
    What is a dog?
  </div>
  <div class="active content">
    <p>A dog is a type of domesticated animal. Known for its loyalty and faithfulness, it can be found as a welcome guest in many households across the world.</p>
  </div>
  <div class="title">
    <i class="dropdown icon"></i>
    What kinds of dogs are there?
  </div>
  <div class="content">
    <p>There are many breeds of dogs. Each breed varies in size and temperament. Owners often select a breed of dog that they find to be compatible with their own lifestyle and desires from a companion.</p>
  </div>
  <div class="title">
    <i class="dropdown icon"></i>
    How do you acquire a dog?
  </div>
  <div class="content">
    <p>Three common ways for a prospective owner to acquire a dog is from pet shops, private owners, or shelters.</p>
    <p>A pet shop may be the most convenient way to buy a dog. Buying a dog from a private owner allows you to assess the pedigree and upbringing of your dog before choosing to take it home. Lastly, finding your dog from a shelter, helps give a good home to a dog who may not find one so readily.</p>
  </div>
</div>
```

#### Inverted
An accordion can be formatted to appear on dark backgrounds
```html
<div class="ui inverted segment">
  <div class="ui inverted accordion">
    <div class="active title">
      <i class="dropdown icon"></i>
      What is a dog?
    </div>
    <div class="active content">
      <p>A dog is a type of domesticated animal. Known for its loyalty and faithfulness, it can be found as a welcome guest in many households across the world.</p>
    </div>
    <div class="title">
      <i class="dropdown icon"></i>
      What kinds of dogs are there?
    </div>
    <div class="content">
      <p>There are many breeds of dogs. Each breed varies in size and temperament. Owners often select a breed of dog that they find to be compatible with their own lifestyle and desires from a companion.</p>
    </div>
    <div class="title">
      <i class="dropdown icon"></i>
      How do you acquire a dog?
    </div>
    <div class="content">
      <p>Three common ways for a prospective owner to acquire a dog is from pet shops, private owners, or shelters.</p>
      <p>A pet shop may be the most convenient way to buy a dog. Buying a dog from a private owner allows you to assess the pedigree and upbringing of your dog before choosing to take it home. Lastly, finding your dog from a shelter, helps give a good home to a dog who may not find one so readily.</p>
    </div>
  </div>
</div>
```

## Examples

#### Nested Accordions
An accordion can have multiple levels of nested content. This content can either be in a nested `accordion` or simply another level of `title` and `content`
```html
<div class="ui styled accordion">
  <div class="active title">
    <i class="dropdown icon"></i>
    Level 1
  </div>
  <div class="active content">
    Welcome to level 1
    <div class="accordion">
      <div class="active title">
          <i class="dropdown icon"></i>
          Level 1A
      </div>
      <div class="active content">
        <p>Level 1A Contents</p>
        <div class="accordion">
          <div class="title">
              <i class="dropdown icon"></i>
              Level 1A-A
          </div>
          <div class="content">
              Level 1A-A Contents
          </div>
          <div class="title">
              <i class="dropdown icon"></i>
              Level 1A-B
          </div>
          <div class="content">
              Level 1A-B Contents
          </div>
        </div>
      </div>
      <div class="title">
          <i class="dropdown icon"></i>
          Level 1B
      </div>
      <div class="content">
          Level 1B Contents
      </div>
      <div class="title">
          <i class="dropdown icon"></i>
          Level 1C
      </div>
      <div class="content">
          Level 1C Contents
      </div>
    </div>
  </div>
  <div class="title">
    <i class="dropdown icon"></i>
    Level 2
  </div>
  <div class="content">
    <p>Welcome to level 2</p>
    <div class="accordion">
      <div class="active title">
        <i class="dropdown icon"></i>
        Level 2A
      </div>
      <div class="active content">
        <p>Level 2A Contents</p>
        <div class="accordion">
          <div class="title">
              <i class="dropdown icon"></i>
              Level 2A-A
          </div>
          <div class="content">
              Level 2A-A Contents
          </div>
          <div class="title">
              <i class="dropdown icon"></i>
              Level 2A-B
          </div>
          <div class="content">
              Level 2A-B Contents
          </div>
        </div>
      </div>
      <div class="title">
          <i class="dropdown icon"></i>
          Level 2B
      </div>
      <div class="content">
          Level 2B Contents
      </div>
      <div class="title">
          <i class="dropdown icon"></i>
          Level 2C
      </div>
      <div class="content">
          Level 2C Contents
      </div>
    </div>
  </div>
</div>
```

#### Changing Trigger
An accordion normally triggers when its title is clicked. However you can change the trigger selector to specify an element inside a title to use as an activator
```javascript
$('.trigger.example .accordion')
  .accordion({
    selector: {
      trigger: '.title .icon'
    }
  })
;
```
```html
<div class="ui accordion">
  <div class="active title">
    <i class="dropdown icon"></i>
    What is a dog?
  </div>
  <div class="active content">
    <p>A dog is a type of domesticated animal. Known for its loyalty and faithfulness, it can be found as a welcome guest in many households across the world.</p>
  </div>
  <div class="title">
    <i class="dropdown icon"></i>
    What kinds of dogs are there?
  </div>
  <div class="content">
    <p>There are many breeds of dogs. Each breed varies in size and temperament. Owners often select a breed of dog that they find to be compatible with their own lifestyle and desires from a companion.</p>
  </div>
  <div class="title">
    <i class="dropdown icon"></i>
    How do you acquire a dog?
  </div>
  <div class="content">
    <p>Three common ways for a prospective owner to acquire a dog is from pet shops, private owners, or shelters.</p>
    <p>A pet shop may be the most convenient way to buy a dog. Buying a dog from a private owner allows you to assess the pedigree and upbringing of your dog before choosing to take it home. Lastly, finding your dog from a shelter, helps give a good home to a dog who may not find one so readily.</p>
  </div>
</div>
```

#### Form Fields
An accordion can be used anywhere where content can be shown or hidden. For example, to show optional form fields.
```html
<div class="ui segment">
  <div class="ui fluid form">
    <div class="two fields">
      <div class="field">
        <label>First Name</label>
        <input placeholder="First Name" type="text">
      </div>
      <div class="field">
        <label>Last Name</label>
        <input placeholder="Last Name" type="text">
      </div>
    </div>
    <div class="ui accordion field">
      <div class="title">
        <i class="icon dropdown"></i>
        Optional Details
      </div>
      <div class="content field">
        <label>Maiden Name</label>
        <input placeholder="Maiden Name" type="text">
      </div>
    </div>
    <div class="ui secondary submit button">Sign Up</div>
  </div>
</div>
```

#### Accordion Menu
An accordion can be used to create content drawers inside a menu
```html
<div class="ui vertical accordion menu">
  <div class="item">
    <a class="active title">
      <i class="dropdown icon"></i>
      Size
    </a>
    <div class="active content">
      <div class="ui form">
        <div class="grouped fields">
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="size" value="small" />
              <label>Small</label>
            </div>
          </div>
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="size" value="medium" />
              <label>Medium</label>
            </div>
          </div>
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="size" value="large" />
              <label>Large</label>
            </div>
          </div>
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="size" value="x-large" />
              <label>X-Large</label>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="item">
    <a class="title">
      <i class="dropdown icon"></i>
      Colors
    </a>
    <div class="content">
      <div class="ui form">
        <div class="grouped fields">
          <div class="field">
            <div class="ui checkbox">
              <input type="checkbox" name="small" />
              <label>Red</label>
            </div>
          </div>
          <div class="field">
            <div class="ui checkbox">
              <input type="checkbox" name="medium" />
              <label>Orange</label>
            </div>
          </div>
          <div class="field">
            <div class="ui checkbox">
              <input type="checkbox" name="large" />
              <label>Green</label>
            </div>
          </div>
          <div class="field">
            <div class="ui checkbox">
              <input type="checkbox" name="x-large" />
              <label>Blue</label>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
```

## Usage

### Initializing

#### Initializing an accordion
Accordion is initialized on pre-existing markup
```html
$('.ui.accordion')
  .accordion()
;
```

#### AJAX Content
Accordions use [DOM Mutation Observers](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver) and delegated events to allow for easy compatibility with AJAX content, or content added after initialization.

If the DOM tree changes the module will automatically call `module.refresh` and update the selector cache. Because events are bound on the parent module using delegated events, events will automatically fire on content added after initialization.

If you change other attributes of the module without DOM insertion and need to update the cache you can do so by calling this module's `refresh` behavior.
```javascript
$('.ui.accordion').accordion('refresh');
```

## Behavior

Behaviors are short english phrases used for accessing specific functionality in

Behaviors are accessible with Javascript using the syntax:
```javascript
$('.ui.accordion').accordion('behavior', argumentOne, argumentTwo...);
```

```html
<table class="ui definition celled table">
  <tr>
    <td>refresh</td>
    <td>Refreshes all cached selectors and data</td>
  </tr>
  <tr>
    <td>open (index)</td>
    <td>Opens accordion content at index</td>
  </tr>
  <tr>
    <td>close others</td>
    <td>Closes accordion content that are not active</td>
  </tr>
  <tr>
    <td>close (index)</td>
    <td>Closes accordion content at index</td>
  </tr>
  <tr>
    <td>toggle (index)</td>
    <td>Toggles accordion content at index</td>
  </tr>
</table>
```

## Settings

### Accordion

#### Behavior
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th class="three wide"></th>
    <th class="three wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>exclusive</td>
      <td>true</td>
      <td>Only allow one section open at a time</td>
    </tr>
    <tr>
      <td>on</td>
      <td>click</td>
      <td>Event on `title` that will cause accordion to open</td>
    </tr>
    <tr>
      <td>animateChildren</td>
      <td>true</td>
      <td>Whether child content opacity should be animated (may cause performance issues with many child elements)</td>
    </tr>
    <tr>
      <td>closeNested</td>
      <td>true</td>
      <td>Close open nested accordion content when an element closes</td>
    </tr>
    <tr>
      <td>collapsible</td>
      <td>true</td>
      <td>Allow active sections to collapse</td>
    </tr>
    <tr>
      <td>duration</td>
      <td>500</td>
      <td>Duration in ms of opening animation</td>
    </tr>
    <tr>
      <td>easing</td>
      <td>easeInOutQuint</td>
      <td>Easing of opening animation. EaseInOutQuint is included with accordion, for additional options you must include [easing equations](http://gsgd.co.uk/sandbox/jquery/easing/).</td>
    </tr>
  </tbody>
</table>
```

#### Callbacks

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th class="three wide"></th>
    <th class="three wide">Context</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>onOpening</td>
      <td>active content</td>
      <td>Callback before element opens</td>
    </tr>
    <tr>
      <td>onOpen</td>
      <td>active content</td>
      <td>Callback after element is open</td>
    </tr>
    <tr>
      <td>onClosing</td>
      <td>active content</td>
      <td>Callback before element closes</td>
    </tr>
    <tr>
      <td>onClose</td>
      <td>active content</td>
      <td>Callback after element is closed</td>
    </tr>
    <tr>
      <td>onChanging</td>
      <td>active content</td>
      <td>Callback before element opens or closes</td>
    </tr>
    <tr>
      <td>onChange</td>
      <td>active content</td>
      <td>Callback on element open or close</td>
    </tr>
  </tbody>
</table>
```

## Module

These settings are native to all modules, and define how the component ties content to DOM attributes, and debugging settings for the module.

```html
<table class="ui sortable celled definition table segment">
  <thead>
    <th></th>
    <th class="six wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>Accordion</td>
      <td>Name used in log statements</td>
    </tr>
    <tr>
      <td>namespace</td>
      <td>accordion</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>selector</td>
      <td>
        <div class="code">
selector    : {
  accordion : '.accordion',
  title     : '.title',
  trigger   : '.title',
  content   : '.content'
}
        </div>
      </td>
      <td>Selectors used to find parts of a module</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
className   : {
  active    : 'active',
  animating : 'animating'
}
        </div>
      </td>
      <td>Class names used to determine element state</td>
    </tr>
    <tr>
      <td>silent</td>
      <td>False</td>
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
      <td>Show `console.table` output with performance metrics</td>
    </tr>
    <tr>
      <td>verbose</td>
      <td>false</td>
      <td>Provides ancillary debug output to console</td>
    </tr>
    <tr>
      <td>errors</td>
      <td colspan="2">
        <div class="code">
error   : {
  method   : 'The method you called is not defined.'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```


## === checkbox.md ===

# Checkbox

A checkbox allows a user to select a value from a small set of options, often binary

## Definition

#### Checkbox
A standard checkbox
```html
<div class="ui checkbox">
  <input type="checkbox" name="example" />
  <label>Make my profile visible</label>
</div>
```

#### Radio
A checkbox can be formatted as a radio element. This means it is an exclusive option.

```html
<div class="ui radio checkbox">
  <input type="radio" name="radio" checked="checked" />
  <label>Radio choice</label>
</div>
```
```html
<div class="ui form">
  <div class="inline fields">
    <label>How often do you use checkboxes?</label>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="frequency" checked="checked" />
        <label>Once a week</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="frequency" />
        <label>2-3 times a week</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="frequency" />
        <label>Once a day</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="frequency" />
        <label>Twice a day</label>
      </div>
    </div>
  </div>
</div>
```
```html
<div class="ui form">
  <div class="grouped fields">
    <label>How often do you use checkboxes?</label>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="example2" checked="checked" />
        <label>Once a week</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="example2" />
        <label>2-3 times a week</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="example2" />
        <label>Once a day</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="example2" />
        <label>Twice a day</label>
      </div>
    </div>
  </div>
</div>
```

#### Slider
A checkbox can be formatted to emphasize the current selection state
```html
<div class="ui slider checkbox">
  <input type="checkbox" name="newsletter" />
  <label>Accept terms and conditions</label>
</div>
```
```html
<div class="ui form">
  <div class="grouped fields">
    <label>Outbound Throughput</label>
    <div class="field">
      <div class="ui slider checkbox">
        <input type="radio" name="throughput" checked="checked">
        <label>20 mbps max</label>
      </div>
    </div>
    <div class="field">
      <div class="ui slider checkbox">
        <input type="radio" name="throughput">
        <label>10mbps max</label>
      </div>
    </div>
    <div class="field">
      <div class="ui slider checkbox">
        <input type="radio" name="throughput">
        <label>5mbps max</label>
      </div>
    </div>
    <div class="field">
      <div class="ui slider checkbox checked">
        <input type="radio" name="throughput">
        <label>Unmetered</label>
      </div>
    </div>
  </div>
</div>
```

#### Toggle
A checkbox can be formatted to show an on or off choice
```html
<div class="ui toggle checkbox">
  <input type="checkbox" name="public" />
  <label>Subscribe to weekly newsletter</label>
</div>
```

## States

#### Read-only
A checkbox can be read-only and unable to change states
```html
<div class="ui read-only checkbox">
  <input type="checkbox" />
  <label>Read Only</label>
</div>
```

#### Checked
A checkbox can be checked
```html
<div class="ui checked checkbox">
  <input type="checkbox" checked />
  <label>Active</label>
</div>
```

#### Indeterminate
A checkbox can be indeterminate
> An indeterminate state can only be set in Javascript, see examples section
```html
<div class="ui checkbox">
  <input type="checkbox" />
  <label>Indeterminate</label>
</div>
```

#### Disabled
A checkbox can be read-only and unable to change states
> A checkbox can be disabled by either setting the disabled attribute on the hidden input, or class `disabled` on the `ui checkbox`
```html
<div class="ui disabled checkbox">
  <input type="checkbox" disabled="disabled" />
  <label>Disabled</label>
</div>
<br>
<br>
<div class="ui toggle checkbox">
  <input type="checkbox" disabled="disabled" />
  <label>Disabled</label>
</div>
```

## Variations

#### Fitted
A fitted checkbox does not leave padding for a label
```html
<div class="ui left floated compact segment">
  <div class="ui fitted checkbox">
    <input type="checkbox"/>
    <label></label>
  </div>
</div>
<div class="ui left floated compact segment">
  <div class="ui fitted slider checkbox">
    <input type="checkbox"/>
    <label></label>
  </div>
</div>
<div class="ui left floated compact segment">
  <div class="ui fitted toggle checkbox">
    <input type="checkbox"/>
    <label></label>
  </div>
</div>
```

## Examples

#### Using Callbacks
Checkbox has two versions of each state change behavior to let you determine whether the call should trigger checkbox callbacks.

Calling a behavior like `check` will trigger an elements callbacks, however using `set checked` will adjust the checkbox state *without triggering callbacks*

This differentiation is important to differentiate between programmatic changes, and user-invoked changes to state.
```html
<div class="ui equal width stretched grid">
  <div class="column">
    <div class="ui segment">
      <div class="ui top right attached label">
        Example
      </div>
      <div class="ui checkbox">
        <input type="checkbox" />
        <label>Checkbox</label>
      </div>
      <div class="ui divider"></div>
      <div class="ui radio checkbox">
        <input type="radio" />
        <label>Radio</label>
      </div>
    </div>
  </div>
  <div class="column">
    <div class="ui console segment">
      <div class="ui top right attached label">
        Console
      </div>
    </div>
  </div>
  <div class="column">
    <div class="ui vertical buttons">
      <div class="ui button" data-method="toggle">Toggle</div>
      <div class="ui button" data-method="check">Check</div>
      <div class="ui button" data-method="uncheck">Uncheck</div>
      <div class="ui button" data-method="indeterminate">Indeterminate</div>
      <div class="ui button" data-method="determinate">Determinate</div>
      <div class="ui button" data-method="enable">Enable</div>
      <div class="ui button" data-method="disable">Disable</div>
    </div>
    <div class="ui divider"></div>
    <div class="ui vertical buttons">
      <div class="ui button" data-method="set checked">Set Checked</div>
      <div class="ui button" data-method="set unchecked">Set Unchecked</div>
      <div class="ui button" data-method="set indeterminate">Set Indeterminate</div>
      <div class="ui button" data-method="set determinate">Set Determinate</div>
      <div class="ui button" data-method="set enabled">Set Enabled</div>
      <div class="ui button" data-method="set disabled">Set Disabled</div>
    </div>
  </div>
</div>
```
```javascript
var
  $console = $('.callback .console')
;
$('.callback.example .checkbox')
  .checkbox()
  .first().checkbox({
    onChecked: function() {
      $console.append('onChecked called<br>');
    },
    onUnchecked: function() {
      $console.append('onUnchecked called<br>');
    },
    onEnable: function() {
      $console.append('onEnable called<br>');
    },
    onDisable: function() {
      $console.append('onDisable called<br>');
    },
    onDeterminate: function() {
      $console.append('onDeterminate called<br>');
    },
    onIndeterminate: function() {
      $console.append('onIndeterminate called<br>');
    },
    onChange: function() {
      $console.append('onChange called<br>');
    }
  })
;
// bind events to buttons
$('.callback.example .button')
  .on('click', function() {
    $('.callback .checkbox').checkbox( $(this).data('method') );
  })
;
```

#### Grouped Checkboxes
The [indeterminate](https://developer.mozilla.org/en-US/docs/Web/CSS/%3Aindeterminate) state can be used to represent a value that is neither checked or unchecked.

This can be useful with groups where a "master" checkbox, should display the selections of several other checkboxes

```html
<div class="ui celled relaxed list">
  <div class="item">
    <div class="ui master checkbox">
      <input type="checkbox" name="fruits" />
      <label>Fruits</label>
    </div>
    <div class="list">
      <div class="item">
        <div class="ui child checkbox">
          <input type="checkbox" name="apple" />
          <label>Apple</label>
        </div>
      </div>
      <div class="item">
        <div class="ui child checkbox">
          <input type="checkbox" name="orange" />
          <label>Orange</label>
        </div>
      </div>
      <div class="item">
        <div class="ui child checkbox">
          <input type="checkbox" name="pear" />
          <label>Pear</label>
        </div>
      </div>
    </div>
  </div>
  <div class="item">
    <div class="ui master checkbox">
      <input type="checkbox" name="vegetables" />
      <label>Vegetables</label>
    </div>
    <div class="list">
      <div class="item">
        <div class="ui child checkbox">
          <input type="checkbox" name="lettuce" />
          <label>Lettuce</label>
        </div>
      </div>
      <div class="item">
        <div class="ui child checkbox">
          <input type="checkbox" name="carrot" />
          <label>Carrot</label>
        </div>
      </div>
      <div class="item">
        <div class="ui child checkbox">
          <input type="checkbox" name="spinach" />
          <label>Spinach</label>
        </div>
      </div>
    </div>
  </div>
</div>
```
```javascript
$('.list .master.checkbox')
  .checkbox({
    // check all children
    onChecked: function() {
      var
        $childCheckbox  = $(this).closest('.checkbox').siblings('.list').find('.checkbox')
      ;
      $childCheckbox.checkbox('check');
    },
    // uncheck all children
    onUnchecked: function() {
      var
        $childCheckbox  = $(this).closest('.checkbox').siblings('.list').find('.checkbox')
      ;
      $childCheckbox.checkbox('uncheck');
    }
  })
;
```
```javascript
$('.list .child.checkbox')
  .checkbox({
    // Fire on load to set parent value
    fireOnInit : true,
    // Change parent state on each child checkbox change
    onChange   : function() {
      var
        $listGroup      = $(this).closest('.list'),
        $parentCheckbox = $listGroup.closest('.item').children('.checkbox'),
        $checkbox       = $listGroup.find('.checkbox'),
        allChecked      = true,
        allUnchecked    = true
      ;
      // check to see if all other siblings are checked or unchecked
      $checkbox.each(function() {
        if( $(this).checkbox('is checked') ) {
          allUnchecked = false;
        }
        else {
          allChecked = false;
        }
      });
      // set parent checkbox state, but dont trigger its onChange callback
      if(allChecked) {
        $parentCheckbox.checkbox('set checked');
      }
      else if(allUnchecked) {
        $parentCheckbox.checkbox('set unchecked');
      }
      else {
        $parentCheckbox.checkbox('set indeterminate');
      }
    }
  })
;
```

#### Checking Conditions
[Checkboxes](/modules/checkbox.html) include four new callbacks `beforeChecked`, `beforeUnchecked`, `beforeDeterminate`, and `beforeIndeterminate`, returning `false` from these callbacks will cancel the action from occuring before the input value is updated.
```html
<div class="ui checkbox">
  <input type="checkbox" name="example" />
  <label>Maybe this will work</label>
</div>
```
```javascript
$('.cancel.example .ui.checkbox')
  .checkbox({
    beforeChecked: function() {
      var
        luckyPerson = (Math.random() < 0.5)
      ;
      return luckyPerson;
    }
  })
;
```

#### One-Way Choices
> To make a user able to check a box, but unable to uncheck it, use the `uncheckable` setting.
> To always disable a checkbox, add the property `disabled` to your input.
> To make a checkbox read-only do not initialize it, or include the `read-only` class which will not allow events.
```javascript
$('.state.example .checkbox')
  .last()
  .checkbox({
    uncheckable: false
  })
;
```
```html
<div class="ui form">
  <div class="field">
    <div class="ui checkbox" id="demo1">
      <input type="checkbox" disabled="disabled" checked="checked" />
      <label>Disabled</label>
    </div>
  </div>
  <div class="field">
    <div class="ui read-only checkbox" id="demo2">
      <input type="checkbox" checked="checked" />
      <label>Read-only</label>
    </div>
  </div>
  <div class="field">
    <div class="ui checkbox" id="demo3">
      <input type="checkbox" />
      <label>Uncheckable</label>
    </div>
  </div>
</div>
```

#### Attaching Events to other Elements
Checkbox can use the `attach events` behavior to attach events easily to other activating elements. This defaults to toggling, but other behaviors can be used as well.
```javascript
$('.test.checkbox').checkbox('attach events', '.toggle.button');
$('.test.checkbox').checkbox('attach events', '.check.button', 'check');
$('.test.checkbox').checkbox('attach events', '.uncheck.button', 'uncheck');
```
```html
<div class="ui toggle button">Toggle</div>
<div class="ui positive check button">Check</div>
<div class="ui negative uncheck button">Uncheck</div>
<div class="ui six column center aligned stackable divided grid segment">
  <div class="column">
    <div class="ui test slider checkbox">
      <input type="checkbox" />
      <label>1</label>
    </div>
  </div>
  <div class="column">
    <div class="ui test toggle checkbox">
      <input type="checkbox" checked="checked" />
      <label>2</label>
    </div>
  </div>
  <div class="column">
    <div class="ui test checkbox">
      <input type="checkbox" />
      <label>3</label>
    </div>
  </div>
  <div class="column">
    <div class="ui test slider checkbox">
      <input type="checkbox" checked="checked" />
      <label>4</label>
    </div>
  </div>
  <div class="column">
    <div class="ui test toggle checkbox">
      <input type="checkbox" />
      <label>5</label>
    </div>
  </div>
  <div class="column">
    <div class="ui test checkbox">
      <input type="checkbox" />
      <label>6</label>
    </div>
  </div>
</div>
```

## Usage

### Initializing

#### Checkbox
A checkbox does not require Javascript to function.
```html
<div class="ui checkbox">
  <input type="checkbox">
  <label>Label</label>
</div>
```
```html
<div class="ui checkbox">
  <input type="checkbox">
  <label>Label</label>
</div>
```

#### Full Featured Checkboxes
Using Javascript with checkboxes will automatically make the checkbox's label trigger a change in the input and provide callback functions. Additionally, some states like `indeterminate` can only be triggered with Javascript.
```html
<div class="ui checkbox">
  <input type="checkbox">
  <label>Label</label>
</div>
```
```html
<div class="ui checkbox">
  <input type="checkbox">
  <label>Label</label>
</div>
```

#### Linked Labels
If you just need labels to link without any other features of Javascript checkboxes, you can match the `for` attribute of the label to an input's id.
```html
<div class="ui checkbox">
  <input id="example-id" type="checkbox">
  <label for="example-id">Label</label>
</div>
```
```html
<div class="ui checkbox">
  <input id="example-id" type="checkbox">
  <label for="example-id">Label</label>
</div>
```

## Behavior

Behaviors are accessible with Javascript using the syntax:
```javascript
$('.ui.checkbox').checkbox(behavior, argumentOne, argumentTwo...);
```

```html
<table class="ui definition celled table segment">
  <tr>
    <td>toggle</td>
    <td>Switches a checkbox from current state</td>
  </tr>
  <tr>
    <td>check</td>
    <td>Set a checkbox state to checked</td>
  </tr>
  <tr>
    <td>uncheck</td>
    <td>Set a checkbox state to unchecked</td>
  </tr>
  <tr>
    <td>indeterminate</td>
    <td>Set as indeterminate checkbox</td>
  </tr>
  <tr>
    <td>determinate</td>
    <td>Set as determinate checkbox</td>
  </tr>
  <tr>
    <td>enable</td>
    <td>Enable interaction with a checkbox</td>
  </tr>
  <tr>
    <td>set checked</td>
    <td>Set a checkbox state to checked without callbacks</td>
  </tr>
  <tr>
    <td>set unchecked</td>
    <td>Set a checkbox state to unchecked without callbacks</td>
  </tr>
  <tr>
    <td>set indeterminate</td>
    <td>Set as indeterminate checkbox without callbacks</td>
  </tr>
  <tr>
    <td>set determinate</td>
    <td>Set as determinate checkbox without callbacks</td>
  </tr>
  <tr>
    <td>set enabled</td>
    <td>Enable interaction with a checkbox without callbacks</td>
  </tr>
  <tr>
    <td>set disabled</td>
    <td>Disable interaction with a checkbox without callbacks</td>
  </tr>
  <tr>
    <td>attach events(selector, behavior)</td>
    <td>Attach checkbox events to another element</td>
  </tr>
  <tr>
    <td>is radio</td>
    <td>Returns whether element is radio selection</td>
  </tr>
  <tr>
    <td>is checked</td>
    <td>Returns whether element is currently checked</td>
  </tr>
  <tr>
    <td>is unchecked</td>
    <td>Returns whether element is not checked</td>
  </tr>
  <tr>
    <td>can change</td>
    <td>Returns whether element is able to be changed</td>
  </tr>
  <tr>
    <td>should allow check</td>
    <td>Returns whether element can be checked (checking if already checked or `beforeChecked` would cancel)</td>
  </tr>
  <tr>
    <td>should allow uncheck</td>
    <td>Returns whether element can be unchecked (checking if already unchecked or `beforeUnchecked` would cancel)</td>
    </tr>
  <tr>
    <td>should allow determinate</td>
    <td>Returns whether element can be determinate (checking if already determinate or `beforeDeterminate` would cancel)</td>
  </tr>
  <tr>
    <td>should allow indeterminate</td>
    <td>Returns whether element can be indeterminate (checking if already indeterminate or `beforeIndeterminate` would cancel)</td>
  </tr>
  <tr>
    <td>can uncheck</td>
    <td>Returns whether element is able to be unchecked</td>
  </tr>
</table>
```

## Settings

### Checkbox

These settings are specific to checkbox, and determine the parameters of its behavior

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th class="three wide"></th>
    <th class="three wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>uncheckable</td>
      <td>auto</td>
      <td>Setting to true/false will determine whether an input will allow no selection. Auto will set disallow this behavior only for radio boxes</td>
    </tr>
    <tr>
      <td>fireOnInit</td>
      <td>false</td>
      <td>Whether callbacks for checked status should be fired on init as well as change</td>
    </tr>
  </tbody>
</table>
```

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th class="three wide"></th>
    <th class="three wide">Context</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>onChange</td>
      <td>HTML input element</td>
      <td>Callback after a checkbox is either checked or unchecked.</td>
    </tr>
    <tr>
      <td>onChecked</td>
      <td>HTML input element</td>
      <td>Callback after a checkbox is checked.</td>
    </tr>
    <tr>
      <td>onIndeterminate</td>
      <td>HTML input element</td>
      <td>Callback after a checkbox is set to undeterminate.</td>
    </tr>
    <tr>
      <td>onDeterminate</td>
      <td>HTML input element</td>
      <td>Callback after a checkbox is set to determinate.</td>
    </tr>
    <tr>
      <td>onUnchecked</td>
      <td>HTML input element</td>
      <td>Callback after a checkbox is unchecked.</td>
    </tr>
    <tr>
      <td>beforeChecked</td>
      <td>HTML input element</td>
      <td>Callback before a checkbox is checked. Can cancel change by returning `false`</td>
    </tr>
    <tr>
      <td>beforeIndeterminate</td>
      <td>HTML input element</td>
      <td>Callback before a checkbox is set to undeterminate. Can cancel change by returning `false`</td>
    </tr>
    <tr>
      <td>beforeDeterminate</td>
      <td>HTML input element</td>
      <td>Callback before a checkbox is set to determinate. Can cancel change by returning `false`</td>
    </tr>
    <tr>
      <td>beforeUnchecked</td>
      <td>HTML input element</td>
      <td>Callback before a checkbox is unchecked. Can cancel change by returning `false`</td>
    </tr>
    <tr>
      <td>onEnable</td>
      <td>HTML input element</td>
      <td>Callback after a checkbox is enabled.</td>
    </tr>
    <tr>
      <td>onDisable</td>
      <td>HTML input element</td>
      <td>Callback after a checkbox is disabled.</td>
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
    <th class="six wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>Checkbox</td>
      <td>Name used in log statements</td>
    </tr>
    <tr>
      <td>namespace</td>
      <td>checkbox</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>selector</td>
      <td>
        <div class="code">
selector : {
  input  : 'input[type=checkbox], input[type=radio]',
  label  : 'label'
}
        </div>
      </td>
      <td>Selectors used to find parts of a module</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
className   : {
  checked  : 'checked',
  disabled : 'disabled',
  radio    : 'radio',
  readOnly : 'read-only'
}
        </div>
      </td>
      <td>Class names used to determine element state</td>
    </tr>
    <tr>
      <td>silent</td>
      <td>False</td>
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
      <td>Show `console.table` output with performance metrics</td>
    </tr>
    <tr>
      <td>verbose</td>
      <td>false</td>
      <td>Debug output includes all internal behaviors</td>
    </tr>
    <tr>
      <td>errors</td>
      <td colspan="2">
        <div class="code">
error   : {
  method   : 'The method you called is not defined.'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```


## === dimmer.md ===

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


## === dropdown.md ===

# Semantic UI

User Interface is the language of the web

## Design Beautiful Websites Quickly

Semantic is a development framework that helps create beautiful, responsive layouts using human-friendly HTML.

## Concise HTML
Semantic UI treats words and classes as exchangeable concepts.

Classes use syntax from natural languages like noun/modifier relationships, word order, and plurality to link concepts intuitively.

Get the same benefits as [BEM](https://en.bem.info) or [SMACSS](https://smacss.com), but without the tedium.

```html
<div class="ui three buttons">
  <button class="ui active button">One</button>
  <button class="ui button">Two</button>
  <button class="ui button">Three</button>
</div>
```

## Intuitive Javascript
Semantic uses simple phrases called behaviors that trigger functionality.

Any arbitrary decision in a component is included as a setting that developers can modify.

```javascript
$('select.dropdown')
  .dropdown('set selected', ['meteor', 'ember'])
;
```
```html
<select name="skills" multiple class="ui fluid dropdown">
  <option value="">Skills</option>
  <option value="angular">Angular</option>
  <option value="css">CSS</option>
  <option value="ember">Ember</option>
  <option value="html">HTML</option>
  <option value="javascript">Javascript</option>
  <option value="meteor">Meteor</option>
  <option value="node">NodeJS</option>
</select>
```

## Simplified Debugging
Performance logging lets you track down bottlenecks without digging through stack traces.

> Don't have access to development tools right now? Check out [this short clip](http://t.co/GOUQx8iCyG).

```javascript
$('.sequenced.images .image')
  .transition({
    debug     : true,
    animation : 'jiggle',
    duration  : 500,
    interval  : 200
  })
;
```
```html
<div class="ui small sequenced images">
  <img src="/images/avatar2/large/elyse.png" class="ui circular image">
  <img src="/images/avatar2/large/matthew.png" class="ui circular image">
  <img src="/images/avatar2/large/kristy.png" class="ui circular image">
</div>
```

## Semantic is growing fast. Want to see just how much? Sign up and we'll let you know

```html
<form class="ui form" method="post" action="https://semantic-ui.clients.ubivox.com/handlers/post/">
  <input type="hidden" name="action" value="subscribe" />
  <input type="hidden" name="lists" value="29450" />
  <div class="field">
    <div class="ui huge input">
      <input type="text" name="email_address" data-validate="email" placeholder="E-mail">
    </div>
    <button type="submit" value="Subscribe" class="ui huge secondary submit button">
      Sign-up
    </button>
  </div>
</form>
```

## Unbelievable Theming

Semantic comes equipped with an intuitive inheritance system and high level theming variables that let you have complete design freedom.

Develop your UI once, then deploy with the same code everywhere.

```html
<div data-type="element" data-element="button" class="ui large floating dropdown theme button">
  <span class="text">Select Theme</span>
  <i class="dropdown icon"></i>
  <div class="menu ui transition hidden" tabindex="-1">
    <div data-value="Default" class="item">Semantic UI</div>
    <div data-value="Amazon" class="item">Amazon</div>
    <div data-value="Material" class="item">Google Material</div>
    <div data-value="GitHub" class="item">GitHub</div>
    <div data-value="Bootstrap3" class="item">Bootstrap</div>
    <div data-value="Twitter" class="item">Twitter</div>
    <div class="divider"></div>
    <div data-value="Raised" class="item">Raised</div>
    <div data-value="Chubby" class="item">Chubby</div>
    <div data-value="Classic" class="item">Classic</div>
  </div>
</div>
<div class="ui divider"></div>
<div class="ui button">
  View
</div>
<div class="ui primary button">
  <i class="shop icon"></i> Add to Cart
</div>
<div class="ui secondary button">
  <i class="save icon"></i> Save for Later
</div>
<div class="ui labeled icon button">
  <i class="star icon"></i>
  Rate
</div>
<div class="ui demo buttons">
  <div class="ui active button">1</div>
  <div class="ui button">2</div>
  <div class="ui button">3</div>
</div>
```

### Variable File
```html
<div class="variable code" data-type="less" data-preserve="true">
</div>
```

### Override File
```html
<div class="override code" data-type="less" data-preserve="true">
</div>
```

## Unbelievable Breadth

Definitions aren't limited to just buttons on a page. Semantic's components allow several distinct types of definitions: elements, collections, views, modules and behaviors which cover the gamut of interface design.

[See Layout Examples](/usage/layout.html)

### Menu
```html
<div class="ui vertical demo menu">
  <a class="active teal item">
    Inbox
    <div class="ui teal label">1</div>
  </a>
  <a class="item">
    Trash
    <div class="ui label">1</div>
  </a>
  <div class="item">
    <div class="ui transparent icon input">
      <input type="text" placeholder="Search mail...">
      <i class="search icon"></i>
    </div>
  </div>
</div>
<div class="ui fluid demo tabular menu">
  <a class="active item">
    Tab
  </a>
  <a class="item">
    Tab
  </a>
</div>
<div class="ui secondary vertical demo menu">
  <a class="active item">
    Inbox
  </a>
  <a class="item">
    Starred
  </a>
  <a class="item">
    Trash
  </a>
</div>
<div class="ui secondary pointing vertical demo menu">
  <a class="active item">
    Inbox
  </a>
  <a class="item">
    Starred
  </a>
  <a class="item">
    Trash
  </a>
</div>
```

### Divider
```html
<div class="ui two column stackable center aligned grid segment">
  <div class="column">
    <div class="ui button">A</div>
  </div>
  <div class="ui vertical divider">or</div>
  <div class="column">
    <div class="teal ui button">B</div>
  </div>
</div>
```

### Accordion
```html
<div class="ui vertical fluid accordion menu">
  <div class="item">
    <a class="active title">
      <i class="dropdown icon"></i>
      Size
    </a>
    <div class="active content">
      <div class="ui form">
        <div class="grouped fields">
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="size" value="small">
              <label>Small</label>
            </div>
          </div>
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="size" value="medium">
              <label>Medium</label>
            </div>
            </div>
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="size" value="large">
              <label>Large</label>
            </div>
          </div>
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="size" value="x-large">
              <label>X-Large</label>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="item">
    <a class="title">
      <i class="dropdown icon"></i>
      Colors
    </a>
    <div class="content">
      <div class="ui form">
        <div class="grouped fields">
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="color">
              <label>Red</label>
            </div>
          </div>
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="color">
              <label>Orange</label>
            </div>
          </div>
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="color">
              <label>Green</label>
            </div>
          </div>
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="color">
              <label>Blue</label>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
```

### Message
```html
<div class="ui message">
  <i class="close icon"></i>
  This site uses cookies
</div>
<div class="ui warning icon message">
  <div class="content">
    <div class="header">Looking for help? </div>
    <ul class="list">
      <li>Use our <a href="#">help center</a></li>
      <li>Check our <a href"#"="">FAQ</a></li>
    </ul>
  </div>
</div>
<div class="ui info message">
  <div class="header">We're creating your profile page</div>
  <p>It will be ready in just a second.</p>
</div>
```

### Card
```html
<div class="ui card">
  <div class="blurring dimmable image">
    <div class="ui dimmer">
      <div class="content">
        <div class="center">
          <div class="ui inverted button">Add Friend</div>
        </div>
      </div>
    </div>
    <img src="/images/avatar2/large/rachel.png">
  </div>
  <div class="content">
    <div class="header">Rachel Maddaw</div>
    <div class="meta">
      <a class="group">Pundit</a>
    </div>
  </div>
  <div class="extra content">
    <a class="right floated created">
      Joined in 1998
    </a>
    <a class="friends">
      <i class="user icon"></i>
      22 Friends
    </a>
  </div>
</div>
```

### Feed
```html
<div class="ui feed">
  <div class="event">
    <div class="label">
      <img src="/images/avatar2/small/mark.png">
    </div>
    <div class="content">
      <div class="summary">
        <a class="user">
          Mark
        </a> added you as a friend
      </div>
    </div>
  </div>
  <div class="event">
    <div class="label">
      <img src="/images/avatar2/small/lena.png">
    </div>
    <div class="content">
      You added Lena to the group <a>Close Friends</a>
    </div>
  </div>
  <div class="event">
    <div class="label">
      <img src="/images/avatar2/small/eve.png">
    </div>
    <div class="content">
      Eve just <a>posted on your page</a>
    </div>
  </div>
</div>
```

### Label
```html
<div class="ui image label">
  <img src="/images/avatar2/small/molly.png">
  molly@thebears.com
  <i class="delete icon"></i>
</div>
<a class="ui teal label">
  <i class="mail icon"></i> 23 New
</a>
<a class="ui tag label">Dresses</a>
```

### Step
```html
<div class="ui fluid vertical steps">
  <a class="step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
      <div class="description">Choose your shipping options</div>
    </div>
  </a>
  <a class="active step">
    <i class="payment icon"></i>
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </a>
  <a class="disabled step">
    <i class="info icon"></i>
    <div class="content">
      <div class="title">Confirm Order</div>
      <div class="description">Verify order details</div>
    </div>
  </a>
</div>
```

### Dropdown
```html
<div class="ui fluid search selection dropdown">
  <input type="hidden" name="country">
  <i class="dropdown icon"></i>
  <input class="search" tabindex="0"><div class="default text">Select Country</div>
  <div class="menu" tabindex="-1">
    <div class="item" data-value="ad"><i class="ad flag"></i>Andorra</div>
    <div class="item" data-value="ae"><i class="ae flag"></i>United Arab Emirates</div>
    <div class="item" data-value="af"><i class="af flag"></i>Afghanistan</div>
    <div class="item" data-value="ag"><i class="ag flag"></i>Antigua</div>
    <div class="item" data-value="ai"><i class="ai flag"></i>Anguilla</div>
    <div class="item" data-value="al"><i class="al flag"></i>Albania</div>
    <div class="item" data-value="am"><i class="am flag"></i>Armenia</div>
    <div class="item" data-value="an"><i class="an flag"></i>Netherlands Antilles</div>
    <div class="item" data-value="ao"><i class="ao flag"></i>Angola</div>
    <div class="item" data-value="ar"><i class="ar flag"></i>Argentina</div>
    <div class="item" data-value="as"><i class="as flag"></i>American Samoa</div>
    <div class="item" data-value="at"><i class="at flag"></i>Austria</div>
    <div class="item" data-value="au"><i class="au flag"></i>Australia</div>
    <div class="item" data-value="aw"><i class="aw flag"></i>Aruba</div>
    <div class="item" data-value="ax"><i class="ax flag"></i>Aland Islands</div>
    <div class="item" data-value="az"><i class="az flag"></i>Azerbaijan</div>
    <div class="item" data-value="ba"><i class="ba flag"></i>Bosnia</div>
    <div class="item" data-value="bb"><i class="bb flag"></i>Barbados</div>
    <div class="item" data-value="bd"><i class="bd flag"></i>Bangladesh</div>
    <div class="item" data-value="be"><i class="be flag"></i>Belgium</div>
    <div class="item" data-value="bf"><i class="bf flag"></i>Burkina Faso</div>
    <div class="item" data-value="bg"><i class="bg flag"></i>Bulgaria</div>
    <div class="item" data-value="bh"><i class="bh flag"></i>Bahrain</div>
    <div class="item" data-value="bi"><i class="bi flag"></i>Burundi</div>
    <div class="item" data-value="bj"><i class="bj flag"></i>Benin</div>
    <div class="item" data-value="bm"><i class="bm flag"></i>Bermuda</div>
    <div class="item" data-value="bn"><i class="bn flag"></i>Brunei</div>
    <div class="item" data-value="bo"><i class="bo flag"></i>Bolivia</div>
    <div class="item" data-value="br"><i class="br flag"></i>Brazil</div>
    <div class="item" data-value="bs"><i class="bs flag"></i>Bahamas</div>
    <div class="item" data-value="bt"><i class="bt flag"></i>Bhutan</div>
    <div class="item" data-value="bv"><i class="bv flag"></i>Bouvet Island</div>
    <div class="item" data-value="bw"><i class="bw flag"></i>Botswana</div>
    <div class="item" data-value="by"><i class="by flag"></i>Belarus</div>
    <div class="item" data-value="bz"><i class="bz flag"></i>Belize</div>
    <div class="item" data-value="ca"><i class="ca flag"></i>Canada</div>
    <div class="item" data-value="cc"><i class="cc flag"></i>Cocos Islands</div>
    <div class="item" data-value="cd"><i class="cd flag"></i>Congo</div>
    <div class="item" data-value="cf"><i class="cf flag"></i>Central African Republic</div>
    <div class="item" data-value="cg"><i class="cg flag"></i>Congo Brazzaville</div>
    <div class="item" data-value="ch"><i class="ch flag"></i>Switzerland</div>
    <div class="item" data-value="ci"><i class="ci flag"></i>Cote Divoire</div>
    <div class="item" data-value="ck"><i class="ck flag"></i>Cook Islands</div>
    <div class="item" data-value="cl"><i class="cl flag"></i>Chile</div>
    <div class="item" data-value="cm"><i class="cm flag"></i>Cameroon</div>
    <div class="item" data-value="cn"><i class="cn flag"></i>China</div>
    <div class="item" data-value="co"><i class="co flag"></i>Colombia</div>
    <div class="item" data-value="cr"><i class="cr flag"></i>Costa Rica</div>
    <div class="item" data-value="cs"><i class="cs flag"></i>Serbia</div>
    <div class="item" data-value="cu"><i class="cu flag"></i>Cuba</div>
    <div class="item" data-value="cv"><i class="cv flag"></i>Cape Verde</div>
    <div class="item" data-value="cx"><i class="cx flag"></i>Christmas Island</div>
    <div class="item" data-value="cy"><i class="cy flag"></i>Cyprus</div>
    <div class="item" data-value="cz"><i class="cz flag"></i>Czech Republic</div>
    <div class="item" data-value="de"><i class="de flag"></i>Germany</div>
    <div class="item" data-value="dj"><i class="dj flag"></i>Djibouti</div>
    <div class="item" data-value="dk"><i class="dk flag"></i>Denmark</div>
    <div class="item" data-value="dm"><i class="dm flag"></i>Dominica</div>
    <div class="item" data-value="do"><i class="do flag"></i>Dominican Republic</div>
    <div class="item" data-value="dz"><i class="dz flag"></i>Algeria</div>
    <div class="item" data-value="ec"><i class="ec flag"></i>Ecuador</div>
    <div class="item" data-value="ee"><i class="ee flag"></i>Estonia</div>
    <div class="item" data-value="eg"><i class="eg flag"></i>Egypt</div>
    <div class="item" data-value="eh"><i class="eh flag"></i>Western Sahara</div>
    <div class="item" data-value="er"><i class="er flag"></i>Eritrea</div>
    <div class="item" data-value="es"><i class="es flag"></i>Spain</div>
    <div class="item" data-value="et"><i class="et flag"></i>Ethiopia</div>
    <div class="item" data-value="eu"><i class="eu flag"></i>European Union</div>
    <div class="item" data-value="fi"><i class="fi flag"></i>Finland</div>
    <div class="item" data-value="fj"><i class="fj flag"></i>Fiji</div>
    <div class="item" data-value="fk"><i class="fk flag"></i>Falkland Islands</div>
    <div class="item" data-value="fm"><i class="fm flag"></i>Micronesia</div>
    <div class="item" data-value="fo"><i class="fo flag"></i>Faroe Islands</div>
    <div class="item" data-value="fr"><i class="fr flag"></i>France</div>
    <div class="item" data-value="ga"><i class="ga flag"></i>Gabon</div>
    <div class="item" data-value="gb"><i class="gb flag"></i>England</div>
    <div class="item" data-value="gd"><i class="gd flag"></i>Grenada</div>
    <div class="item" data-value="ge"><i class="ge flag"></i>Georgia</div>
    <div class="item" data-value="gf"><i class="gf flag"></i>French Guiana</div>
    <div class="item" data-value="gh"><i class="gh flag"></i>Ghana</div>
    <div class="item" data-value="gi"><i class="gi flag"></i>Gibraltar</div>
    <div class="item" data-value="gl"><i class="gl flag"></i>Greenland</div>
    <div class="item" data-value="gm"><i class="gm flag"></i>Gambia</div>
    <div class="item" data-value="gn"><i class="gn flag"></i>Guinea</div>
    <div class="item" data-value="gp"><i class="gp flag"></i>Guadeloupe</div>
    <div class="item" data-value="gq"><i class="gq flag"></i>Equatorial Guinea</div>
    <div class="item" data-value="gr"><i class="gr flag"></i>Greece</div>
    <div class="item" data-value="gs"><i class="gs flag"></i>Sandwich Islands</div>
    <div class="item" data-value="gt"><i class="gt flag"></i>Guatemala</div>
    <div class="item" data-value="gu"><i class="gu flag"></i>Guam</div>
    <div class="item" data-value="gw"><i class="gw flag"></i>Guinea-Bissau</div>
    <div class="item" data-value="gy"><i class="gy flag"></i>Guyana</div>
    <div class="item" data-value="hk"><i class="hk flag"></i>Hong Kong</div>
    <div class="item" data-value="hm"><i class="hm flag"></i>Heard Island</div>
    <div class="item" data-value="hn"><i class="hn flag"></i>Honduras</div>
    <div class="item" data-value="hr"><i class="hr flag"></i>Croatia</div>
    <div class="item" data-value="ht"><i class="ht flag"></i>Haiti</div>
    <div class="item" data-value="hu"><i class="hu flag"></i>Hungary</div>
    <div class="item" data-value="id"><i class="id flag"></i>Indonesia</div>
    <div class="item" data-value="ie"><i class="ie flag"></i>Ireland</div>
    <div class="item" data-value="il"><i class="il flag"></i>Israel</div>
    <div class="item" data-value="in"><i class="in flag"></i>India</div>
    <div class="item" data-value="io"><i class="io flag"></i>Indian Ocean Territory</div>
    <div class="item" data-value="iq"><i class="iq flag"></i>Iraq</div>
    <div class="item" data-value="ir"><i class="ir flag"></i>Iran</div>
    <div class="item" data-value="is"><i class="is flag"></i>Iceland</div>
    <div class="item" data-value="it"><i class="it flag"></i>Italy</div>
    <div class="item" data-value="jm"><i class="jm flag"></i>Jamaica</div>
    <div class="item" data-value="jo"><i class="jo flag"></i>Jordan</div>
    <div class="item" data-value="jp"><i class="jp flag"></i>Japan</div>
    <div class="item" data-value="ke"><i class="ke flag"></i>Kenya</div>
    <div class="item" data-value="kg"><i class="kg flag"></i>Kyrgyzstan</div>
    <div class="item" data-value="kh"><i class="kh flag"></i>Cambodia</div>
    <div class="item" data-value="ki"><i class="ki flag"></i>Kiribati</div>
    <div class="item" data-value="km"><i class="km flag"></i>Comoros</div>
    <div class="item" data-value="kn"><i class="kn flag"></i>Saint Kitts and Nevis</div>
    <div class="item" data-value="kp"><i class="kp flag"></i>North Korea</div>
    <div class="item" data-value="kr"><i class="kr flag"></i>South Korea</div>
    <div class="item" data-value="kw"><i class="kw flag"></i>Kuwait</div>
    <div class="item" data-value="ky"><i class="ky flag"></i>Cayman Islands</div>
    <div class="item" data-value="kz"><i class="kz flag"></i>Kazakhstan</div>
    <div class="item" data-value="la"><i class="la flag"></i>Laos</div>
    <div class="item" data-value="lb"><i class="lb flag"></i>Lebanon</div>
    <div class="item" data-value="lc"><i class="lc flag"></i>Saint Lucia</div>
    <div class="item" data-value="li"><i class="li flag"></i>Liechtenstein</div>
    <div class="item" data-value="lk"><i class="lk flag"></i>Sri Lanka</div>
    <div class="item" data-value="lr"><i class="lr flag"></i>Liberia</div>
    <div class="item" data-value="ls"><i class="ls flag"></i>Lesotho</div>
    <div class="item" data-value="lt"><i class="lt flag"></i>Lithuania</div>
    <div class="item" data-value="lu"><i class="lu flag"></i>Luxembourg</div>
    <div class="item" data-value="lv"><i class="lv flag"></i>Latvia</div>
    <div class="item" data-value="ly"><i class="ly flag"></i>Libya</div>
    <div class="item" data-value="ma"><i class="ma flag"></i>Morocco</div>
    <div class="item" data-value="mc"><i class="mc flag"></i>Monaco</div>
    <div class="item" data-value="md"><i class="md flag"></i>Moldova</div>
    <div class="item" data-value="me"><i class="me flag"></i>Montenegro</div>
    <div class="item" data-value="mg"><i class="mg flag"></i>Madagascar</div>
    <div class="item" data-value="mh"><i class="mh flag"></i>Marshall Islands</div>
    <div class="item" data-value="mk"><i class="mk flag"></i>MacEdonia</div>
    <div class="item" data-value="ml"><i class="ml flag"></i>Mali</div>
    <div class="item" data-value="ar"><i class="ar flag"></i>Burma</div>
    <div class="item" data-value="mn"><i class="mn flag"></i>Mongolia</div>
    <div class="item" data-value="mo"><i class="mo flag"></i>MacAu</div>
    <div class="item" data-value="mp"><i class="mp flag"></i>Northern Mariana Islands</div>
    <div class="item" data-value="mq"><i class="mq flag"></i>Martinique</div>
    <div class="item" data-value="mr"><i class="mr flag"></i>Mauritania</div>
    <div class="item" data-value="ms"><i class="ms flag"></i>Montserrat</div>
    <div class="item" data-value="mt"><i class="mt flag"></i>Malta</div>
    <div class="item" data-value="mu"><i class="mu flag"></i>Mauritius</div>
    <div class="item" data-value="mv"><i class="mv flag"></i>Maldives</div>
    <div class="item" data-value="mw"><i class="mw flag"></i>Malawi</div>
    <div class="item" data-value="mx"><i class="mx flag"></i>Mexico</div>
    <div class="item" data-value="my"><i class="my flag"></i>Malaysia</div>
    <div class="item" data-value="mz"><i class="mz flag"></i>Mozambique</div>
    <div class="item" data-value="na"><i class="na flag"></i>Namibia</div>
    <div class="item" data-value="nc"><i class="nc flag"></i>New Caledonia</div>
    <div class="item" data-value="ne"><i class="ne flag"></i>Niger</div>
    <div class="item" data-value="nf"><i class="nf flag"></i>Norfolk Island</div>
    <div class="item" data-value="ng"><i class="ng flag"></i>Nigeria</div>
    <div class="item" data-value="ni"><i class="ni flag"></i>Nicaragua</div>
    <div class="item" data-value="nl"><i class="nl flag"></i>Netherlands</div>
    <div class="item" data-value="no"><i class="no flag"></i>Norway</div>
    <div class="item" data-value="np"><i class="np flag"></i>Nepal</div>
    <div class="item" data-value="nr"><i class="nr flag"></i>Nauru</div>
    <div class="item" data-value="nu"><i class="nu flag"></i>Niue</div>
    <div class="item" data-value="nz"><i class="nz flag"></i>New Zealand</div>
    <div class="item" data-value="om"><i class="om flag"></i>Oman</div>
    <div class="item" data-value="pa"><i class="pa flag"></i>Panama</div>
    <div class="item" data-value="pe"><i class="pe flag"></i>Peru</div>
    <div class="item" data-value="pf"><i class="pf flag"></i>French Polynesia</div>
    <div class="item" data-value="pg"><i class="pg flag"></i>New Guinea</div>
    <div class="item" data-value="ph"><i class="ph flag"></i>Philippines</div>
    <div class="item" data-value="pk"><i class="pk flag"></i>Pakistan</div>
    <div class="item" data-value="pl"><i class="pl flag"></i>Poland</div>
    <div class="item" data-value="pm"><i class="pm flag"></i>Saint Pierre</div>
    <div class="item" data-value="pn"><i class="pn flag"></i>Pitcairn Islands</div>
    <div class="item" data-value="pr"><i class="pr flag"></i>Puerto Rico</div>
    <div class="item" data-value="ps"><i class="ps flag"></i>Palestine</div>
    <div class="item" data-value="pt"><i class="pt flag"></i>Portugal</div>
    <div class="item" data-value="pw"><i class="pw flag"></i>Palau</div>
    <div class="item" data-value="py"><i class="py flag"></i>Paraguay</div>
    <div class="item" data-value="qa"><i class="qa flag"></i>Qatar</div>
    <div class="item" data-value="re"><i class="re flag"></i>Reunion</div>
    <div class="item" data-value="ro"><i class="ro flag"></i>Romania</div>
    <div class="item" data-value="rs"><i class="rs flag"></i>Serbia</div>
    <div class="item" data-value="ru"><i class="ru flag"></i>Russia</div>
    <div class="item" data-value="rw"><i class="rw flag"></i>Rwanda</div>
    <div class="item" data-value="sa"><i class="sa flag"></i>Saudi Arabia</div>
    <div class="item" data-value="sb"><i class="sb flag"></i>Solomon Islands</div>
    <div class="item" data-value="sc"><i class="sc flag"></i>Seychelles</div>
    <div class="item" data-value="sd"><i class="sd flag"></i>Sudan</div>
    <div class="item" data-value="se"><i class="se flag"></i>Sweden</div>
    <div class="item" data-value="sg"><i class="sg flag"></i>Singapore</div>
    <div class="item" data-value="sh"><i class="sh flag"></i>Saint Helena</div>
    <div class="item" data-value="si"><i class="si flag"></i>Slovenia</div>
    <div class="item" data-value="sj"><i class="sj flag"></i>Svalbard, I Flag Jan Mayen</div>
    <div class="item" data-value="sk"><i class="sk flag"></i>Slovakia</div>
    <div class="item" data-value="sl"><i class="sl flag"></i>Sierra Leone</div>
    <div class="item" data-value="sm"><i class="sm flag"></i>San Marino</div>
    <div class="item" data-value="sn"><i class="sn flag"></i>Senegal</div>
    <div class="item" data-value="so"><i class="so flag"></i>Somalia</div>
    <div class="item" data-value="sr"><i class="sr flag"></i>Suriname</div>
    <div class="item" data-value="st"><i class="st flag"></i>Sao Tome</div>
    <div class="item" data-value="sv"><i class="sv flag"></i>El Salvador</div>
    <div class="item" data-value="sy"><i class="sy flag"></i>Syria</div>
    <div class="item" data-value="sz"><i class="sz flag"></i>Swaziland</div>
    <div class="item" data-value="tc"><i class="tc flag"></i>Caicos Islands</div>
    <div class="item" data-value="td"><i class="td flag"></i>Chad</div>
    <div class="item" data-value="tf"><i class="tf flag"></i>French Territories</div>
    <div class="item" data-value="tg"><i class="tg flag"></i>Togo</div>
    <div class="item" data-value="th"><i class="th flag"></i>Thailand</div>
    <div class="item" data-value="tj"><i class="tj flag"></i>Tajikistan</div>
    <div class="item" data-value="tk"><i class="tk flag"></i>Tokelau</div>
    <div class="item" data-value="tl"><i class="tl flag"></i>Timorleste</div>
    <div class="item" data-value="tm"><i class="tm flag"></i>Turkmenistan</div>
    <div class="item" data-value="tn"><i class="tn flag"></i>Tunisia</div>
    <div class="item" data-value="to"><i class="to flag"></i>Tonga</div>
    <div class="item" data-value="tr"><i class="tr flag"></i>Turkey</div>
    <div class="item" data-value="tt"><i class="tt flag"></i>Trinidad</div>
    <div class="item" data-value="tv"><i class="tv flag"></i>Tuvalu</div>
    <div class="item" data-value="tw"><i class="tw flag"></i>Taiwan</div>
    <div class="item" data-value="tz"><i class="tz flag"></i>Tanzania</div>
    <div class="item" data-value="ua"><i class="ua flag"></i>Ukraine</div>
    <div class="item" data-value="ug"><i class="ug flag"></i>Uganda</div>
    <div class="item" data-value="um"><i class="um flag"></i>Us Minor Islands</div>
    <div class="item" data-value="us"><i class="us flag"></i>United States</div>
    <div class="item" data-value="uy"><i class="uy flag"></i>Uruguay</div>
    <div class="item" data-value="uz"><i class="uz flag"></i>Uzbekistan</div>
    <div class="item" data-value="va"><i class="va flag"></i>Vatican City</div>
    <div class="item" data-value="vc"><i class="vc flag"></i>Saint Vincent</div>
    <div class="item" data-value="ve"><i class="ve flag"></i>Venezuela</div>
    <div class="item" data-value="vg"><i class="vg flag"></i>British Virgin Islands</div>
    <div class="item" data-value="vi"><i class="vi flag"></i>Us Virgin Islands</div>
    <div class="item" data-value="vn"><i class="vn flag"></i>Vietnam</div>
    <div class="item" data-value="vu"><i class="vu flag"></i>Vanuatu</div>
    <div class="item" data-value="wf"><i class="wf flag"></i>Wallis and Futuna</div>
    <div class="item" data-value="ws"><i class="ws flag"></i>Samoa</div>
    <div class="item" data-value="ye"><i class="ye flag"></i>Yemen</div>
    <div class="item" data-value="yt"><i class="yt flag"></i>Mayotte</div>
    <div class="item" data-value="za"><i class="za flag"></i>South Africa</div>
    <div class="item" data-value="zm"><i class="zm flag"></i>Zambia</div>
    <div class="item" data-value="zw"><i class="zw flag"></i>Zimbabwe</div>
  </div>
</div>
```

## Settings

### Dropdown Settings
Settings to configure dropdown behavior
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th>Setting</th>
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>action</td>
      <td>activate</td>
      <td>When an item is selected, the default action to take. Can be set to `activate`, `select`, `hide`, `auto`, `combo`, `nothing`.</td>
    </tr>
    <tr>
      <td>minCharacters</td>
      <td>1</td>
      <td>Minimum characters to query for results when creating a searchable dropdown</td>
    </tr>
    <tr>
      <td>apiSettings</td>
      <td>false</td>
      <td>Settings object for [$.api](/behaviors/api.html) call</td>
    </tr>
    <tr>
      <td>fields</td>
      <td>
        <div class="code">
fields: {
  remoteValues : 'results',
  values       : 'values',
  name         : 'name',
  value        : 'value',
  text         : 'text'
}
        </div>
      </td>
      <td>Mapping of standard properties to element attributes.</td>
    </tr>
    <tr>
      <td>saveRemoteData</td>
      <td>true</td>
      <td>When using a remote query, whether to automatically store remote results in a dropdown's cache after the initial search.</td>
    </tr>
    <tr>
      <td>filterRemoteData</td>
      <td>false</td>
      <td>When using a remote query, whether to filter results with current query after the initial search.</td>
    </tr>
    <tr>
      <td>hideOnScroll</td>
      <td>auto</td>
      <td>Whether dropdown should hide on scroll or touchmove, `auto` only hides for dropdowns without `on: 'click'`.<br>
      Set this to `false` to prevent mobile browsers from closing dropdowns when you tap inside input fields.</td>
    </tr>
    <tr>
      <td>forceSelection</td>
      <td>true</td>
      <td>When using search selection, whether the selected result must match a value from the existing menu.</td>
    </tr>
    <tr>
      <td>allowAdditions</td>
      <td>false</td>
      <td>When using a search dropdown, whether a user can add a new item to a previous selection.</td>
    </tr>
    <tr>
      <td>allowCategorySelection</td>
      <td>false</td>
      <td>When using a multi-level menu, whether a user can select a category that has sub-menus.</td>
    </tr>
    <tr>
      <td>maxSelections</td>
      <td>false</td>
      <td>When using a multiple select, the maximum number of selections a user may make.</td>
    </tr>
    <tr>
      <td>useLabels</td>
      <td>true</td>
      <td>When using a multiple select, whether to show currently selected options as labels.</td>
    </tr>
    <tr>
      <td>delimiter</td>
      <td>,</td>
      <td>When using a multiple select, the character to use to delimit values in the hidden input.</td>
    </tr>
    <tr>
      <td>showOnFocus</td>
      <td>true</td>
      <td>Whether dropdown should show menu on focus</td>
    </tr>
    <tr>
      <td>allowReselection</td>
      <td>false</td>
      <td>When set to `true` a user can reselect the currently selected menu item to close a dropdown.</td>
    </tr>
    <tr>
      <td>match</td>
      <td>both</td>
      <td>When using a search dropdown, specifies how search queries should match against menu values. Can be set to `both`, `value`, or `text`.</td>
    </tr>
    <tr>
      <td>placeholder</td>
      <td>auto</td>
      <td>When set to `auto` will use the text content of the first `option` element in a `select` as a placeholder. Can also be set to a string or `false`.</td>
    </tr>
    <tr>
      <td>direction</td>
      <td>auto</td>
      <td>Direction of dropdown. Can be set to `auto`, `upward`, `downward`.</td>
    </tr>
    <tr>
      <td>transition</td>
      <td>
        slide down
      </td>
      <td>Named transition to use when animating menu in and out. Fade and slide down are available without including <a href="/modules/transition.html">ui transitions</a></td>
    </tr>
    <tr>
      <td>duration</td>
      <td>
        200
      </td>
      <td>Duration of animation events</td>
    </tr>
    <tr>
      <td>fullTextSearch</td>
      <td>false</td>
      <td>Whether search should include all content when searching, not just values.</td>
    </tr>
    <tr>
      <td>sortSelect</td>
      <td>false</td>
      <td>Whether to sort values when creating a dropdown from a select element.</td>
    </tr>
    <tr>
      <td>values</td>
      <td>false</td>
      <td>An array of objects that will be used to create a dropdown menu.</td>
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
      <td>onChange(value, text, $choice)</td>
      <td>module</td>
      <td>Is called after a value is selected and menu is closed. Receives the name and value of selection.</td>
    </tr>
    <tr>
      <td>onAdd(value, text, $choice)</td>
      <td>module</td>
      <td>Is called after a value is added to a multiple select dropdown. Receives the name and value of selection.</td>
    </tr>
    <tr>
      <td>onRemove(value, text, $choice)</td>
      <td>module</td>
      <td>Is called after a value is removed from a multiple select dropdown. Receives the name and value of selection.</td>
    </tr>
    <tr>
      <td>onLabelCreate(value, text, $label)</td>
      <td>module</td>
      <td>Is called after a label is created in a multiple select dropdown. Receives the value and text and the created label element. Should return a W3C compliant element.</td>
    </tr>
    <tr>
      <td>onLabelRemove(value, text, $label)</td>
      <td>module</td>
      <td>Is called after a label is removed in a multiple select dropdown. Receives the value and text and the removed label element. Should return `false` to prevent default label removal.</td>
    </tr>
    <tr>
      <td>onLabelSelect($labels)</td>
      <td>module</td>
      <td>Is called after a label is selected. Receives the selected labels.</td>
    </tr>
    <tr>
      <td>onNoResults(searchTerm)</td>
      <td>module</td>
      <td>Is called after a search or filter returns no results. Receives the search term that was entered.</td>
    </tr>
    <tr>
      <td>onShow</td>
      <td>module</td>
      <td>Is called before a dropdown is shown. Returning `false` from this callback will cancel the show action.</td>
    </tr>
    <tr>
      <td>onVisible</td>
      <td>module</td>
      <td>Is called after a dropdown is shown.</td>
    </tr>
    <tr>
      <td>onHide</td>
      <td>module</td>
      <td>Is called before a dropdown is hidden. Returning `false` from this callback will cancel the hide action.</td>
    </tr>
    <tr>
      <td>onHidden</td>
      <td>module</td>
      <td>Is called after a dropdown is hidden.</td>
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
      <td>dropdown</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>selector</td>
      <td>
        <div class="code">
selector    : {
  menu        : '.menu',
  item        : '.menu > .item',
  uiSelect    : 'select.ui.dropdown',
  dropdown    : '.ui.dropdown',
  text        : '.text:not(.icon)',
  input       : 'input[type="hidden"]',
  icon        : '.dropdown.icon',
  clear       : '.clear.icon',
  search      : 'input.search',
  sizer       : '.sizer',
  label       : '.ui.label',
  active      : '.active',
  message     : '.message'
}
        </div>
      </td>
      <td>Selectors used to find parts of a module</td>
    </tr>
    <tr>
      <td>metadata</td>
      <td>
        <div class="code">
metadata    : {
  defaultText : 'defaultText',
  defaultValue: 'defaultValue',
  placeholder : 'placeholder',
  text        : 'text',
  value       : 'value'
}
        </div>
      </td>
      <td>HTML5 metadata attributes used internally</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
className   : {
  active      : 'active',
  addition    : 'addition',
  animating   : 'animating',
  disabled    : 'disabled',
  hidden      : 'hidden',
  item        : 'item',
  label       : 'ui label',
  loading     : 'loading',
  menu        : 'menu',
  message     : 'message',
  multiple    : 'multiple',
  placeholder : 'placeholder',
  search      : 'search',
  selected    : 'selected',
  selection   : 'selection',
  upward      : 'upward',
  visible     : 'visible'
}
        </div>
      </td>
      <td>Class names used to determine element state</td>
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
      <td>Dropdown</td>
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
errors: {
  action     : 'You called a dropdown action that was not defined',
  combo      : 'Combo menu items must have both a text and value property to set',
  invalidType: 'Dropdown input type is not supported.',
  noAPICall  : 'The API module is not enabled for this dropdown',
  noResults  : 'There were no results that matched your query',
  noSearch   : 'The search process was unable to calculate and update values correctly.',
  server     : 'There was an error contacting the server',
  show       : 'Errors already visible, cannot show new errors',
  text       : 'The text you specified is not an allowed value',
  values     : 'Values must be contained in a stringified JS array for this type of dropdown',
  method     : 'The method you called is not defined.'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```

## === embed.md ===

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


## === modal.md ===

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


## === nag.md ===

# Nag

A nag is an important message that persists until dismissed by a user

## Current Progress
```html
<div class="ui indicating progress">
  <div class="bar" style="width: 60%;">
    <div class="progress">60%</div>
  </div>
  <div class="label">Needs Documentation / Re-coding</div>
</div>
```

## Usage

Nags are used to present a user with a one time message which will persist until a user acknowledges the message. This can be used for providing notices like the site's use of cookies, an important change to a site like a security breach.

Semantic's nag component provides built in options for ensuring a nag is only displayed once. You can trigger an API endpoint on dismissal, in order to store a value in your database, or you can use localstorage or cookie value to make sure that a particular computer does not receive the nag again.

## Example

```javascript
// Wont re-appear unless cleared
$('.cookie.nag')
  .nag('show')
;
```
```javascript
// Clears cookie so nag shows again
$('.cookie.nag')
  .nag('clear')
;
```
```html
<div class="ui inline cookie nag">
  <span class="title">
    We use cookies to ensure you get the best experience on our website
  </span>
  <i class="close icon"></i>
</div>
```
```javascript
// Automatically shows on init if cookie isnt set
$('.cookie.nag')
  .nag({
    key      : 'accepts-cookies',
    value    : true
  })
;
```

## Support Development

You can help support the future development of the Semantic UI project, and help boost the priority of this component by donating to Semantic UI development.

Please be sure to leave a note in the comments to indicate that you are interested in the development of this particular component.


## === popup.md ===

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


## === progress.md ===

# Progress

A progress bar shows the progression of a task

## Definition

#### Standard
A standard progress bar
```html
<div class="ui progress">
  <div class="bar">
    <div class="progress"></div>
  </div>
  <div class="label">Uploading Files</div>
</div>
```
```html
<div class="ignored">
  <div class="ui icon buttons">
    <div class="decrement ui basic red button icon"><i class="minus icon"></i></div>
    <div class="increment ui basic green button icon"><i class="plus icon"></i></div>
  </div>
</div>
```

#### Indicating
An indicating progress bar visually indicates the current level of progress of a task
```html
<div class="ui indicating progress">
  <div class="bar"></div>
  <div class="label">Funding</div>
</div>
```
```html
<div class="ignored">
  <div class="ui icon buttons">
    <div class="decrement ui basic red button icon"><i class="minus icon"></i></div>
    <div class="increment ui basic green button icon"><i class="plus icon"></i></div>
  </div>
</div>
```

## Content

#### Bar
A progress element can contain a bar visually indicating progress
```html
<div class="ui progress">
  <div class="bar"></div>
</div>
```

#### Progress
A progress bar can contain a text value indicating current progress
```html
<div class="ui progress">
  <div class="bar">
    <div class="progress"></div>
  </div>
</div>
```

#### Label
A progress element can contain a label
```html
<div class="ui progress">
  <div class="bar">
    <div class="progress"></div>
  </div>
  <div class="label">Uploading Files</div>
</div>
```

## States

#### Active
A progress bar can show activity
```html
<div class="ui active progress">
  <div class="bar">
    <div class="progress"></div>
  </div>
  <div class="label">Uploading Files</div>
</div>
```

#### Success
A progress bar can show a success state
```html
<div class="ui progress success">
  <div class="bar">
    <div class="progress"></div>
  </div>
  <div class="label">Everything worked, your file is all ready.</div>
</div>
```

#### Warning
A progress bar can show a warning state
```html
<div class="ui progress warning">
  <div class="bar">
    <div class="progress"></div>
  </div>
  <div class="label">Your file didn't meet the minimum resolution requirements.</div>
</div>
```

#### Error
A progress bar can show an error state
```html
<div class="ui progress error">
  <div class="bar">
    <div class="progress"></div>
  </div>
  <div class="label">There was an error.</div>
</div>
```

#### Disabled
A progress bar can be disabled
```html
<div class="ui disabled progress">
  <div class="bar"></div>
</div>
```

## Variations

#### Inverted
A progress bar can have its colors inverted
```html
<div class="ui inverted segment">
  <div class="ui inverted progress">
    <div class="bar">
      <div class="progress"></div>
    </div>
    <div class="label">Uploading Files</div>
  </div>
  <div class="ui inverted progress success">
    <div class="bar">
      <div class="progress"></div>
    </div>
    <div class="label">Success</div>
  </div>
  <div class="ui inverted progress warning">
    <div class="bar">
      <div class="progress"></div>
    </div>
    <div class="label">Warning</div>
  </div>
  <div class="ui inverted progress error">
    <div class="bar">
      <div class="progress"></div>
    </div>
    <div class="label">Error</div>
  </div>
</div>
```
```html
<div class="ignored">
  <div class="ui icon buttons">
    <div class="increment ui basic green button icon"><i class="plus icon"></i></div>
  </div>
</div>
```

#### Attached
A progress bar can show progress of an element
```html
<div class="ui segment">
  <div class="ui top attached progress">
    <div class="bar"></div>
  </div>
  <p>La la la la</p>
  <div class="ui bottom attached progress">
    <div class="bar"></div>
  </div>
</div>
```
```html
<div class="ignored">
  <div class="ui icon buttons">
    <div class="decrement ui basic red button icon"><i class="minus icon"></i></div>
    <div class="increment ui basic green button icon"><i class="plus icon"></i></div>
  </div>
</div>
```
```html
<div class="ui card">
  <div class="image">
    <img src="/images/wireframe/image.png">
  </div>
  <div class="content">
    <a class="header">Project</a>
    <div class="meta">
      <span class="date">Started in 2014</span>
    </div>
  </div>
  <div class="extra content">
    <a>
      <i class="user icon"></i>
      22 Friends
    </a>
  </div>
  <div class="ui bottom attached progress">
    <div class="bar"></div>
  </div>
</div>
```
```html
<div class="ignored">
  <div class="ui icon buttons">
    <div class="decrement ui basic red button icon"><i class="minus icon"></i></div>
    <div class="increment ui basic green button icon"><i class="plus icon"></i></div>
  </div>
</div>
```

#### Size
A progress bar can vary in size
> Some small sizes may not be able to fit an inlined label
```html
<div class="ui tiny progress">
  <div class="bar"></div>
  <div class="label">Tiny</div>
</div>
<div class="ui small progress">
  <div class="bar"></div>
  <div class="label">Small</div>
</div>
<div class="ui progress">
  <div class="bar"></div>
  <div class="label">Standard</div>
</div>
<div class="ui large progress">
  <div class="bar"></div>
  <div class="label">Large</div>
</div>
<div class="ui big progress">
  <div class="bar"></div>
  <div class="label">Big</div>
</div>
```
```html
<div class="ignored">
  <div class="ui icon buttons">
    <div class="decrement ui basic red button icon"><i class="minus icon"></i></div>
    <div class="increment ui basic green button icon"><i class="plus icon"></i></div>
  </div>
</div>
```

#### Color
Can have different colors:
```html
<div class="ui red progress">
  <div class="bar"></div>
</div>
<div class="ui orange progress">
  <div class="bar"></div>
</div>
<div class="ui yellow progress">
  <div class="bar"></div>
</div>
<div class="ui olive progress">
  <div class="bar"></div>
</div>
<div class="ui green progress">
  <div class="bar"></div>
</div>
<div class="ui teal progress">
  <div class="bar"></div>
</div>
<div class="ui blue progress">
  <div class="bar"></div>
</div>
<div class="ui violet progress">
  <div class="bar"></div>
</div>
<div class="ui purple progress">
  <div class="bar"></div>
</div>
<div class="ui pink progress">
  <div class="bar"></div>
</div>
<div class="ui brown progress">
  <div class="bar"></div>
</div>
<div class="ui grey progress">
  <div class="bar"></div>
</div>
<div class="ui black progress">
  <div class="bar"></div>
</div>
```
```html
<div class="ignored">
  <div class="ui icon buttons">
    <div class="decrement ui basic red button icon"><i class="minus icon"></i></div>
    <div class="increment ui basic green button icon"><i class="plus icon"></i></div>
  </div>
</div>
```

#### Inverted Color
These colors can also be inverted for improved contrast on dark backgrounds
```html
<div class="ui inverted segment">
  <div class="ui red inverted progress">
    <div class="bar">
      <div class="progress"></div>
    </div>
  </div>
  <div class="ui orange inverted progress">
    <div class="bar">
      <div class="progress"></div>
    </div>
  </div>
  <div class="ui yellow inverted progress">
    <div class="bar">
      <div class="progress"></div>
    </div>
  </div>
  <div class="ui olive inverted progress">
    <div class="bar">
      <div class="progress"></div>
    </div>
  </div>
  <div class="ui green inverted progress">
    <div class="bar">
      <div class="progress"></div>
    </div>
  </div>
  <div class="ui teal inverted progress">
    <div class="bar">
      <div class="progress"></div>
    </div>
  </div>
  <div class="ui blue inverted progress">
    <div class="bar">
      <div class="progress"></div>
    </div>
  </div>
  <div class="ui violet inverted progress">
    <div class="bar">
      <div class="progress"></div>
    </div>
  </div>
  <div class="ui purple inverted progress">
    <div class="bar">
      <div class="progress"></div>
    </div>
  </div>
  <div class="ui pink inverted progress">
    <div class="bar">
      <div class="progress"></div>
    </div>
  </div>
  <div class="ui brown inverted progress">
    <div class="bar">
      <div class="progress"></div>
    </div>
  </div>
  <div class="ui grey inverted progress">
    <div class="bar">
      <div class="progress"></div>
    </div>
  </div>
  <div class="ui black inverted progress">
    <div class="bar">
      <div class="progress"></div>
    </div>
  </div>
```
```html
<div class="ignored">
  <div class="ui icon buttons">
    <div class="decrement ui basic inverted red button icon"><i class="minus icon"></i></div>
    <div class="increment ui basic inverted green button icon"><i class="plus icon"></i></div>
  </div>
</div>
```

## Usage

### Initializing a progress bar

#### With metadata
A progress bar can be initialized with metadata
```javascript
$('#example1').progress();
```
```html
<div class="ui teal progress" data-percent="74" id="example1">
  <div class="bar"></div>
  <div class="label">74% Funded</div>
</div>
```

#### With Javascript
A progress bar can be initialized with a Javascript settings object
```javascript
$('#example2').progress({
  percent: 22
});
```
```html
<div class="ui teal progress" id="example2">
  <div class="bar"></div>
  <div class="label">22% Earned</div>
</div>
```

## Task Completion Percent

#### Adding a Total Value
A progress bar can keep track of the current value as a ratio of a total value. This is useful for tracking the progress of a series of events with a known quantity, for example "uploading 1 of 20" photos.

Each call to increment will increase the value by 1, or the value specified as the second parameter
```javascript
$('#example3')
  .progress('increment')
;
```
```html
<div class="ui teal progress" id="example3">
  <div class="bar">
    <div class="progress"></div>
  </div>
  <div class="label">Adding Photos</div>
</div>
```
```javascript
$('#example3')
  .progress({
    total: 3
  })
;
```

#### Initializing with Metadata
A progress bar can keep track of the current value as a ratio of a total value. This is useful for tracking the progress of a series of events with a known quantity, for example "uploading 1 of 20" photos.

Each call to increment will increase the value by 1, or the value specified as the second parameter

In addition you can pass in templates text for each state available to your progress bar which will automatically be updated when your progress bar reaches that state
```javascript
$('#example4')
  .progress('increment')
;
```
```html
<div class="ui indicating progress" data-value="1" data-total="20" id="example4">
  <div class="bar">
    <div class="progress"></div>
  </div>
  <div class="label">Adding Photos</div>
</div>
```

#### Adding Custom Labels
You can pass in templates text for each state available to your progress bar which will automatically be updated when your progress bar reaches that state

You can use `label` setting to change progress bar labels between two preset messages. In addition you can customize the messages themselves by specifying the templated text in `text`. Templated strings will replace three values on render

| {percent} | Current percentage |
|---|---|
| {value} | Current value |
| {total} | Total value |
| {left} | Distance to total, or % progress left |

```javascript
$('#example5')
  .progress('increment')
;
```
```html
<div class="ui indicating progress" data-value="1" data-total="20" id="example5">
  <div class="bar"></div>
  <div class="label">Adding Photos</div>
</div>
```
```javascript
$('#example5')
  .progress({
    text: {
      active  : 'Adding {value} of {total} photos',
      success : '{total} Photos Uploaded!'
    }
  })
;
```

#### Translation
You can also adjust text labels to help strings appear translated
```javascript
$('#example6')
  .progress('increment')
;
```
```html
<div class="ui progress" data-value="15" data-total="20" id="example6">
  <div class="bar">
    <div class="progress"></div>
  </div>
  <div class="label">Carga de archivos</div>
</div>
```
```javascript
$('#example6')
  .progress({
    label: 'ratio',
    text: {
      ratio: '{value} de {total}'
    }
  })
;
```

## Behavior

All the following behaviors can be called using the syntax:
```javascript
$('.your.element')
  .progress('behavior name', argumentOne, argumentTwo)
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
      <td>set percent(percent)</td>
      <td>Sets current percent of progress to value. If using a total will convert from percent to estimated value.</td>
    </tr>
    <tr>
      <td>set progress(value)</td>
      <td>Sets progress to specified value. Will automatically calculate percent from total.</td>
    </tr>
    <tr>
      <td>increment(incrementValue)</td>
      <td>Increments progress by increment value, if not passed a value will use random amount specified in settings</td>
    </tr>
    <tr>
      <td>decrement(decrementValue)</td>
      <td>Decrements progress by decrement value, if not passed a value will use random amount specified in settings</td>
    </tr>
    <tr>
      <td>update progress(value)</td>
      <td>Immediately updates progress to value, ignoring progress animation interval delays</td>
    </tr>
    <tr>
      <td>complete</td>
      <td>Finishes progress and sets loaded to 100%</td>
    </tr>
    <tr>
      <td>reset</td>
      <td>Resets progress to zero</td>
    </tr>
    <tr>
      <td>set total(total)</td>
      <td>Set total to a new value</td>
    </tr>
    <tr>
      <td>get text(text)</td>
      <td>Replaces templated string with value, total, percent left and percent.</td>
    </tr>
    <tr>
      <td>get normalized value(value)</td>
      <td>Returns normalized value inside acceptable range specified by total.</td>
    </tr>
    <tr>
      <td>get percent</td>
      <td>Returns percent as last specified</td>
    </tr>
    <tr>
      <td>get value</td>
      <td>Returns current progress value</td>
    </tr>
    <tr>
      <td>get total</td>
      <td>Returns total</td>
    </tr>
    <tr>
      <td>is complete</td>
      <td>Returns whether progress is completed</td>
    </tr>
    <tr>
      <td>is success</td>
      <td>Returns whether progress was a success</td>
    </tr>
    <tr>
      <td>is warning</td>
      <td>Returns whether progress is in warning state</td>
    </tr>
    <tr>
      <td>is error</td>
      <td>Returns whether progress is in error state</td>
    </tr>
    <tr>
      <td>is active</td>
      <td>Returns whether progress is in active state</td>
    </tr>
    <tr>
      <td>set active</td>
      <td>Sets progress to active state</td>
    </tr>
    <tr>
      <td>set warning</td>
      <td>Sets progress to warning state</td>
    </tr>
    <tr>
      <td>set success</td>
      <td>Sets progress to success state</td>
    </tr>
    <tr>
      <td>set error</td>
      <td>Sets progress to error state</td>
    </tr>
    <tr>
      <td>set duration(value)</td>
      <td>Changes progress animation speed</td>
    </tr>
    <tr>
      <td>set label(text)</td>
      <td>Sets progress exterior label to text</td>
    </tr>
    <tr>
      <td>set bar label(text)</td>
      <td>Sets progress bar label to text</td>
    </tr>
    <tr>
      <td>remove active</td>
      <td>Removes progress to active state</td>
    </tr>
    <tr>
      <td>remove warning</td>
      <td>Removes progress to warning state</td>
    </tr>
    <tr>
      <td>remove success</td>
      <td>Removes progress to success state</td>
    </tr>
    <tr>
      <td>remove error</td>
      <td>Removes progress to error state</td>
    </tr>
  </tbody>
</table>
```

## Examples

#### Frequently Updated Progress
Progress bar will automatically poll for the last progress value after completing an animation, so that animation easing continues to work smoothly, even if update events occur much more frequently than UI updates.
```html
<a class="ui button" data-url="/images/large-pdf.pdf">
  Rapidly Update
</a>
<div class="code" data-type="html" data-preview="true">
  <div class="ui indicating progress" data-value="1" data-total="200" id="example5">
    <div class="bar">
      <div class="progress"></div>
    </div>
    <div class="label">Waiting for you to press button</div>
  </div>
</div>
```
```javascript
$('.rapid.example .ui.button')
  .on('click', function() {
    var
      $progress       = $('.rapid.example .ui.progress'),
      $button         = $(this),
      updateEvent
    ;
    // restart to zero
    clearInterval(window.fakeProgress)
    $progress.progress('reset');

    // updates every 10ms until complete
    window.fakeProgress = setInterval(function() {
      $progress.progress('increment');
      $button.text( $progress.progress('get value') );
      // stop incrementing when complete
      if($progress.progress('is complete')) {
        clearInterval(window.fakeProgress)
      }
    }, 10);
  })
;
$('.rapid.example .ui.progress')
  .progress({
    duration : 200,
    total    : 200,
    text     : {
      active: '{value} of {total} done'
    }
  })
;
```

## Settings

### Progress Settings
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
      <td>autoSuccess</td>
      <td>true</td>
      <td>Whether success state should automatically trigger when progress completes</td>
    </tr>
    <tr>
      <td>showActivity</td>
      <td>true</td>
      <td>Whether progress should automatically show activity when incremented</td>
    </tr>
    <tr>
      <td>limitValues</td>
      <td>true</td>
      <td>When set to true, values that calculate to above 100% or below 0% will be adjusted. When set to false, inappropriate values will produce an error.</td>
    </tr>
    <tr>
      <td>label</td>
      <td>percent</td>
      <td>Can be set to either to display progress as **percent** or **ratio**. Matches up to corresponding text template with the same name.</td>
    </tr>
    <tr>
      <td>random</td>
      <td>
      <div class="code">
        className : {
          active  : 'active',
          error   : 'error',
          success : 'success',
          warning : 'warning'
        }
      </div>
      </td>
      <td>When incrementing without value, sets range for random increment value</td>
    </tr>
    <tr>
      <td>precision</td>
      <td>1</td>
      <td>Decimal point precision for calculated progress</td>
    </tr>
    <tr>
      <td>total</td>
      <td>false</td>
      <td>Setting a total value will make each call to increment get closer to this total (i.e. 1/20, 2/20 etc)</td>
    </tr>
    <tr>
      <td>value</td>
      <td>false</td>
      <td>Sets current value, when total is specified, this is used to calculate a ratio of the total, with percent this should be the overall percent</td>
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
      <td>onChange</td>
      <td>percent, value, total</td>
      <td>Progress</td>
      <td>Callback on percentage change</td>
    </tr>
    <tr>
      <td>onSuccess</td>
      <td>total</td>
      <td>Progress</td>
      <td>Callback on success state</td>
    </tr>
    <tr>
      <td>onActive</td>
      <td>value, total</td>
      <td>Progress</td>
      <td>Callback on active state</td>
    </tr>
    <tr>
      <td>onError</td>
      <td>value, total</td>
      <td>Progress</td>
      <td>Callback on error state</td>
    </tr>
    <tr>
      <td>onWarning</td>
      <td>value, total</td>
      <td>Progress</td>
      <td>Callback on warning state</td>
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
      <td>progress</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>text</td>
      <td>
        <div class="code">
        text : {
          active  : false,
          error   : false,
          success : false,
          warning : false,
          percent : '{percent}%',
          ratio   : '{value} of {total}'
        }
        </div>
      </td>
      <td>Text content for each state, uses simple templating with {percent}, {value}, {total}</td>
    </tr>
    <tr>
      <td>regExp</td>
      <td>
        <div class="code">
        regExp: {
          variable: /\{\$*[A-z0-9]+\}/g
        }
        </div>
      </td>
      <td>Regular expressions used by module</td>
    </tr>
    <tr>
      <td>selector</td>
      <td>
        <div class="code">
        selector : {
          bar      : '> .bar',
          label    : '> .label',
          progress : '.bar > .progress'
        }
        </div>
      </td>
      <td>Selectors used by module</td>
    </tr>
    <tr>
      <td>metadata</td>
      <td>
        <div class="code">
        metadata: {
          percent : 'percent',
          total   : 'total',
          value   : 'value'
        }
        </div>
      </td>
      <td>DOM metadata used by module</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
        className : {
          active  : 'active',
          error   : 'error',
          success : 'success',
          warning : 'warning'
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
      <td>Progress</td>
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
        error    : {
          method     : 'The method you called is not defined.',
          nonNumeric : 'Progress value is non numeric'
        }
        </div>
      </td>
    </tr>
  </tbody>
</table>
```


## === rating.md ===

# Rating

A rating indicates user interest in content

## Definition

#### Rating
A basic rating
```html
<div class="ui rating" data-max-rating="1"></div>
```

#### Star
A rating can use a set of star icons

Rating
```html
<div class="ui star rating" data-rating="3"></div>
```

#### Heart
A rating can use a set of heart icons
```html
<div class="ui heart rating" data-rating="1" data-max-rating="3"></div>
```

## Variations

#### Size
A rating can vary in size
```html
<div class="ui mini star rating"></div>
<br><br>
<div class="ui tiny star rating"></div>
<br><br>
<div class="ui small star rating"></div>
<br><br>
<div class="ui star rating"></div>
<br><br>
<div class="ui large star rating"></div>
<br><br>
<div class="ui huge star rating"></div>
<br><br>
<div class="ui massive star rating"></div>
```

## Examples

#### Setting existing values
The starting rating can be set either using metadata value `data-rating` or the setting `initialRating`.

The maximum rating can be be set using the metadata value `data-max-rating` or the settings `maxRating`, or you can just include the icon HTML yourself on initialization to avoid the overhead of the `DOM template insertions`.

> If a metadata rating is specified it will automatically override the default value specified in Javascript.
```javascript
$('.toggle.example .rating')
  .rating({
    initialRating: 2,
    maxRating: 4
  })
;
```
```html
<div class="ui very relaxed celled list">
  <div class="item">
    <img class="ui wireframe image" src="/images/wireframe/square-image.png">
    <div class="content">
      <div class="header">
        New York Dog Fair
        <div class="ui heart rating" data-rating="2"></div>
      </div>
      A fun day at the fair
    </div>
  </div>
  <div class="item">
    <img class="ui wireframe image" src="/images/wireframe/square-image.png">
    <div class="content">
      <div class="header">
        Dog Appreciation Day
        <div class="ui heart rating" data-rating="2"></div>
      </div>
      I'd like to tell your dog he's great
    </div>
  </div>
</div>
```

#### Read-Only Ratings
You can disable or enable interactive rating
```javascript
$('.toggle.example .rating')
  .rating('disable')
;
```
```javascript
$('.toggle.example .rating')
  .rating('enable')
;
```
```html
<div class="ui heart demo rating" data-rating="3">
  <i class="icon"></i>
  <i class="icon"></i>
  <i class="icon"></i>
  <i class="icon"></i>
  <i class="icon"></i>
</div>
```

#### Clearing Ratings
When clearable is set to `true` you can clear the rating by clicking on the current start rating.
```javascript
$('.clearing.example .rating')
  .rating('setting', 'clearable', true)
;
```
```html
<div class="ui heart demo rating" data-rating="3">
  <i class="icon"></i>
  <i class="icon"></i>
  <i class="icon"></i>
  <i class="icon"></i>
  <i class="icon"></i>
</div>
```

## Usage

### Initializing

#### Metadata
You can specify the starting rating, and max rating in metadata.
```javascript
$('.ui.rating')
  .rating()
;
```
```html
<div class="ui rating" data-rating="3" data-max-rating="5"></div>
```

#### Javascript
You can specify the rating values in Javascript
```javascript
$('.ui.rating')
  .rating({
    initialRating: 3,
    maxRating: 5
  })
;
```
```html
<div class="ui rating"></div>
```

## Behaviors

All the following behaviors can be called using the syntax:
```javascript
$('.ui.rating')
  .rating('behavior name', argumentOne, argumentTwo)
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
      <td>set rating(rating)</td>
      <td>Sets rating programmatically</td>
    </tr>
    <tr>
      <td>get rating</td>
      <td>Gets current rating</td>
    </tr>
    <tr>
      <td>disable</td>
      <td>Disables interactive rating mode</td>
    </tr>
    <tr>
      <td>enable</td>
      <td>Enables interactive rating mode</td>
    </tr>
    <tr>
      <td>clear rating</td>
      <td>Clears current rating</td>
    </tr>
  </tbody>
</table>
```

## Settings

### Rating Settings
Rating settings modify the rating's behavior
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th>Setting</th>
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>initialRating</td>
      <td>0</td>
      <td>A number representing the default rating to apply</td>
    </tr>
    <tr>
      <td>fireOnInit</td>
      <td>false</td>
      <td>Whether callbacks like `onRate` should fire immediately after initializing with the current value.</td>
    </tr>
    <tr>
      <td>clearable</td>
      <td>auto</td>
      <td>By default a rating will be only clearable if there is 1 icon. Setting to true/false will allow or disallow a user to clear their rating</td>
    </tr>
    <tr>
      <td>interactive</td>
      <td>true</td>
      <td>Whether to enable user's ability to rate</td>
    </tr>
  </tbody>
</table>
```

### Callbacks
Callbacks specify a function to occur after a specific behavior.
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th class="four wide">Setting</th>
    <th>Context</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>onRate(value)</td>
      <td>Rating</td>
      <td>Is called after user selects a new rating</td>
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
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>namespace</td>
      <td>rating</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>selector</td>
      <td colspan="2">
        <div class="code">
selector  : {
  icon : '.icon'
}
        </div>
      </td>
    </tr>
    <tr>
      <td>className</td>
      <td colspan="2">
        <div class="code">
className : {
  active     : 'active',
  hover      : 'hover',
  loading    : 'loading'
},
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
      <td>Rating</td>
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
      <td>error</td>
      <td colspan="2">
        <div class="code">
error   : {
  action    : 'You called a rating action that was not defined'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```


## === search.md ===

# Search

A search module allows a user to query for results from a selection of data

## Definition

#### Standard
A search can display a set of results
```html
<div class="ui search">
  <input class="prompt" type="text" placeholder="Common passwords...">
  <div class="results"></div>
</div>
```
> Using a [ui input](/elements/input.html) allows you to use additional input types, like this icon input
```html
<div class="ui search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Common passwords...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```

#### Category
A search can display results from remote content ordered by categories
```html
<div class="ui category search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search animals...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```

#### Local Search
A search can look for results inside a static local source.
> By default, results will return content first that begin with the query text, but also afterward content that matches the query anywhere inside. To disable full text search you can specify in settings `fullTextSearch: false`.
```html
<div class="ui search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search countries...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```
```javascript
$('.ui.search')
  .search({
    source: content
  })
;
```
```javascript
var content = [
  { title: 'Andorra' },
  { title: 'United Arab Emirates' },
  { title: 'Afghanistan' },
  { title: 'Antigua' },
  { title: 'Anguilla' },
  { title: 'Albania' },
  { title: 'Armenia' },
  { title: 'Netherlands Antilles' },
  { title: 'Angola' },
  { title: 'Argentina' },
  { title: 'American Samoa' },
  { title: 'Austria' },
  { title: 'Australia' },
  { title: 'Aruba' },
  { title: 'Aland Islands' },
  { title: 'Azerbaijan' },
  { title: 'Bosnia' },
  { title: 'Barbados' },
  { title: 'Bangladesh' },
  { title: 'Belgium' },
  { title: 'Burkina Faso' },
  { title: 'Bulgaria' },
  { title: 'Bahrain' },
  { title: 'Burundi' }
  // etc
];
```

#### Local Category Search
A search can look for category results inside a static local source.
> By default, results will return content first that begin with the query text, but also afterward content that matches the query anywhere inside. To disable full text search you can specify in settings `fullTextSearch: false`.
```html
<div class="ui search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search countries...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```
```javascript
$('.ui.search')
  .search({
    type: 'category',
    source: categoryContent
  })
;
```
```javascript
var categoryContent = [
  { category: 'South America', title: 'Brazil' },
  { category: 'South America', title: 'Peru' },
  { category: 'North America', title: 'Canada' },
  { category: 'Asia', title: 'South Korea' },
  { category: 'Asia', title: 'Japan' },
  { category: 'Asia', title: 'China' },
  { category: 'Europe', title: 'Denmark' },
  { category: 'Europe', title: 'England' },
  { category: 'Europe', title: 'France' },
  { category: 'Europe', title: 'Germany' },
  { category: 'Africa', title: 'Ethiopia' },
  { category: 'Africa', title: 'Nigeria' },
  { category: 'Africa', title: 'Zimbabwe' },
];
```

## States

#### Loading
A search can show a loading indicator
```html
<div class="ui loading search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```

## Variations

#### Disabled
A search can show it is currently unable to be interacted with
```html
<div class="ui disabled category search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search animals...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```

#### Fluid
A search can have its results take up the width of its container
```html
<div class="ui fluid category search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search animals...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```

#### Aligned
A search can have its results aligned to its left or right container edge
```html
<div class="ui right aligned category search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search animals...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```

## Usage

### Initializing

> Search is built ontop of Semantic [API](/behaviors/api.html) behaviors to allow for URL templating, and UI state management. Please check out the API documentation for more information on adjusting API settings.

#### Automatic Routing
By default search will automatically route to the named [API endpoint](/behaviors/api.html) 'search'
```javascript
// initializes with default endpoint /search/{query}
$('.ui.search')
  .search({
    type: 'category'
  })
;
```

#### Named URL
You can specify custom API settings to adjust the url, callback settings, or specify a different API action.
```javascript
$('.ui.search')
  .search({
    // change search endpoint to a custom endpoint by manipulating apiSettings
    apiSettings: {
      url: 'custom-search/?q={query}'
    },
    type: 'category'
  })
;
```

#### Local Object
Local search results allow you to search across specified properties of a javacript object literal looking for matching values

You can set which fields are searchable using the `searchFields` setting. Local object search can only display standard search results (not categories).

```javascript
// searches across any array/object of searchable objects
var
  content = [
    {
      title: 'Horse',
      description: 'An Animal',
    },
    {
      title: 'Cow',
      description: 'Another Animal',
    }
  ]
;
$('.ui.search')
  .search({
    source : content,
    searchFields   : [
      'title'
    ],
    fullTextSearch: false
  })
;
```

## Server Responses

> You may also consider adding a top level property like `success: true` and using API's `successTest` parameter to determine whether a server response is actually succesful, even if it returns the correct HTTP code

#### Standard
```
{
  "results": [
    {
      "title": "Result Title",
      "url": "/optional/url/on/click",
      "image": "optional-image.jpg",
      "price": "Optional Price",
      "description": "Optional Description"
    },
    {
      "title": "Result Title",
      "description": "Result Description"
    }
  ],
  // optional action below results
  "action": {
    "url": '/path/to/results',
    "text": "View all 202 results"
  }
}
```

#### Category
```
{
  "results": {
    "category1": {
      "name": "Category 1",
      "results": [
        {
          "title": "Result Title",
          "url": "/optional/url/on/click",
          "image": "optional-image.jpg",
          "price": "Optional Price",
          "description": "Optional Description"
        },
        {
          "title": "Result Title",
          "url": "/optional/url/on/click",
          "image": "optional-image.jpg",
          "price": "Optional Price",
          "description": "Optional Description"
        }
      ]
    },
    "category2": {
      "name": "Category 2",
      "results": [
        {
          "title": "Result Title",
          "url": "/optional/url/on/click",
          "image": "optional-image.jpg",
          "price": "Optional Price",
          "description": "Optional Description"
        }
      ]
    }
  },
  // optional action below results
  "action": {
    "url": '/path/to/results',
    "text": "View all 202 results"
  }
}
```

## Retreiving Results

#### Unique IDs
If no `id` property is included on a result, a key will automatically be generated when your results are returned for each result.

IDs are generated using the position in the results, for example the first element will receive the id `1`, and the first category result will receive the id `a1`.

An `id` or search result title can then be used with `get result(value)` to return the result object.

```javascript
// get result from current query results with the title cat
$('.ui.search')
  .search('get result', 'cat')
;
// get first result from first category with category search
$('.ui.search')
  .search('get result', 'a1')
;
// get first result from standard search
$('.ui.search')
  .search('get result', '1')
;
```

## Behaviors

All the following behaviors can be called using the syntax:
```javascript
$('.your.element')
  .search('behavior name', argumentOne, argumentTwo)
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
      <td>query (callback)</td>
      <td>Search for value currently set in search input</td>
    </tr>
    <tr>
      <td>display message(text, type)</td>
      <td>Displays message in search results with text, using template matching type</td>
    </tr>
    <tr>
      <td>cancel query</td>
      <td>Cancels current remote search query</td>
    </tr>
    <tr>
      <td>search local(query)</td>
      <td>Search local object for specified query and display results</td>
    </tr>
    <tr>
      <td>has minimum characters</td>
      <td>Whether has minimum characters</td>
    </tr>
    <tr>
      <td>search remote(query, callback)</td>
      <td>Search remote endpoint for specified query and display results</td>
    </tr>
    <tr>
      <td>search object(query, object, searchFields)</td>
      <td>Search object for specified query and return results</td>
    </tr>
    <tr>
      <td>cancel query</td>
      <td>Cancels current remote search request</td>
    </tr>
    <tr>
      <td>is focused</td>
      <td>Whether search is currently focused</td>
    </tr>
    <tr>
      <td>is visible</td>
      <td>Whether search results are visible</td>
    </tr>
    <tr>
      <td>is empty</td>
      <td>Whether search results are empty</td>
    </tr>
    <tr>
      <td>get value</td>
      <td>Returns current search value</td>
    </tr>
    <tr>
      <td>get result(value)</td>
      <td>Returns JSON object matching searched title or id (see above)</td>
    </tr>
    <tr>
      <td>set value(value)</td>
      <td>Sets search input to value</td>
    </tr>
    <tr>
      <td>read cache(query)</td>
      <td>Reads cached results for query</td>
    </tr>
    <tr>
      <td>clear cache(query)</td>
      <td>Clears value from cache, if no parameter passed clears all cache</td>
    </tr>
    <tr>
      <td>write cache(query)</td>
      <td>Writes cached results for query</td>
    </tr>
    <tr>
      <td>add results(html)</td>
      <td>Adds HTML to results and displays</td>
    </tr>
    <tr>
      <td>show results(callback)</td>
      <td>Shows results container</td>
    </tr>
    <tr>
      <td>hide results(callback)</td>
      <td>Hides results container</td>
    </tr>
    <tr>
      <td>generate results(response)</td>
      <td>Generates results using parser specified by `settings.template`</td>
    </tr>
    <tr>
      <td>destroy</td>
      <td>Removes all events</td>
    </tr>
  </tbody>
</table>
```

## Examples

#### Using Different Response Fields
Search expects a very specific API response, however you can easily modify the mapping of server response to displayed field using the `fields` parameter.
```html
<div class="ui search">
  <div class="ui left icon input">
    <input class="prompt" type="text" placeholder="Search GitHub">
    <i class="github icon"></i>
  </div>
</div>
```
```javascript
$('.ui.search')
  .search({
    apiSettings: {
      url: '//api.github.com/search/repositories?q={query}'
    },
    fields: {
      results : 'items',
      title   : 'name',
      url     : 'html_url'
    },
    minCharacters : 3
  })
;
```

#### Using API Settings
[API](/behaviors/api.html) provides a callback [onResponse](/behaviors/api.html#response-callbacks) that can be used to restructure third party APIs to match the expected server response for search.

You can also use [mockResponseAsync](/behaviors/api.html#mocking-responses) to use a custom backend for fullfilling searches.
```html
<div class="ui search">
  <div class="ui left icon input">
    <input class="prompt" type="text" placeholder="Search GitHub">
    <i class="github icon"></i>
  </div>
</div>
```
```javascript
$('.ui.search')
  .search({
    type          : 'category',
    minCharacters : 3,
    apiSettings   : {
      onResponse: function(githubResponse) {
        var
          response = {
            results : {}
          }
        ;
        // translate GitHub API response to work with search
        $.each(githubResponse.items, function(index, item) {
          var
            language   = item.language || 'Unknown',
            maxResults = 8
          ;
          if(index >= maxResults) {
            return false;
          }
          // create new language category
          if(response.results[language] === undefined) {
            response.results[language] = {
              name    : language,
              results : []
            };
          }
          // add result to category
          response.results[language].results.push({
            title       : item.name,
            description : item.description,
            url         : item.html_url
          });
        });
        return response;
      },
      url: '//api.github.com/search/repositories?q={query}'
    }
  })
;
```

## Settings

### Search

#### Behavior
```html
<table class="ui sortable celled definition table">
  <thead>
    <th class="three wide"></th>
    <th class="five wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>apiSettings</td>
      <td>
      <div class="code">
      {
        action: 'search'
      }
      </div>
      </td>
      <td>Settings for [API](/behaviors/api.html#/usage) call.</td>
    </tr>
    <tr>
      <td>minCharacters</td>
      <td>1</td>
      <td>Minimum characters to query for results</td>
    </tr>
    <tr>
      <td>searchOnFocus</td>
      <td>true</td>
      <td>Whether search should show results on focus (must also match min character length)</td>
    </tr>
    <tr>
      <td>transition</td>
      <td>
        fade
      </td>
      <td>Named transition to use when animating menu in and out. Fade and slide down are available without including [ui transitions](/modules/transition.html)</td>
    </tr>
    <tr>
      <td>duration</td>
      <td>
        300
      </td>
      <td>Duration of animation events</td>
    </tr>
    <tr>
      <td>maxResults</td>
      <td>7</td>
      <td>Maximum results to display when using local and simple search, maximum category count for category search</td>
    </tr>
    <tr>
      <td>cache</td>
      <td>true</td>
      <td>Caches results locally to avoid requerying server</td>
    </tr>
    <tr>
      <td>source</td>
      <td>false</td>
      <td>Specify a Javascript object which will be searched locally</td>
    </tr>
    <tr>
      <td>selectFirstResult</td>
      <td>false</td>
      <td>Whether the search should automatically select the first search result after searching</td>
    </tr>
    <tr>
      <td>showNoResults</td>
      <td>false</td>
      <td>Whether a "no results" message should be shown if no results are found. (These messages can be modified using the `template` object specified below)</td>
    </tr>
    <tr>
      <td>fullTextSearch</td>
      <td>'exact'</td>
      <td>Specifying to "true" will use a fuzzy full text search, setting to "exact" will force the exact search to be matched somewhere in the string, setting to `false` will only match to start of string. (This setting was previously called `searchFullText`.)</td>
    </tr>
    <tr>
      <td>fields</td>
      <td>
        <div class="code">
fields: {
  categories      : 'results',     // array of categories (category view)
  categoryName    : 'name',        // name of category (category view)
  categoryResults : 'results',     // array of results (category view)
  description     : 'description', // result description
  image           : 'image',       // result image
  price           : 'price',       // result price
  results         : 'results',     // array of results (standard)
  title           : 'title',       // result title
  action          : 'action',      // "view more" object name
  actionText      : 'text',        // "view more" text
  actionURL       : 'url'
}
        </div>
      </td>
      <td>List mapping display content to JSON property, either with API or `source`.</td>
    </tr>
    <tr>
      <td>searchFields</td>
      <td>
        <div class="code">
          [
            'title',
            'description'
          ]
        </div>
      </td>
      <td>Specify object properties inside local source object which will be searched</td>
    </tr>
    <tr>
      <td>hideDelay</td>
      <td>0</td>
      <td>Delay before hiding results after search blur</td>
    </tr>
    <tr>
      <td>searchDelay</td>
      <td>100</td>
      <td>Delay before querying results on inputchange</td>
    </tr>
    <tr>
      <td>easing</td>
      <td>
        easeOutExpo
      </td>
      <td>Easing equation when using fallback Javascript animation</td>
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
      <td>onSelect(result, response)</td>
      <td>module</td>
      <td>Callback on element selection by user. The first parameter includes the filtered response results for that element. The function should return false to prevent default action (closing search results and selecting value).</td>
    </tr>
    <tr>
      <td>onResultsAdd(html)</td>
      <td>module</td>
      <td>Callback after processing element template to add HTML to results. Function should return false to prevent default actions.</td>
    </tr>
    <tr>
      <td>onSearchQuery(query)</td>
      <td>module</td>
      <td>Callback on search query</td>
    </tr>
    <tr>
      <td>onResults(response)</td>
      <td>module</td>
      <td>Callback on server response</td>
    </tr>
    <tr>
      <td>onResultsOpen</td>
      <td>results element</td>
      <td>Callback when results are opened</td>
    </tr>
    <tr>
      <td>onResultsClose</td>
      <td>results element</td>
      <td>Callback when results are closed</td>
    </tr>
  </tbody>
</table>
```

## Templates

These templates are used to generate the HTML structures for search results

> By specifying a search as `type: 'customType'`, and a custom template under `$.fn.search.settings.templates.customType` you can create custom search results. Keep in mind that `.title` will be used for matching results `onSelect`
```html
<table class="ui sortable celled definition table">
  <thead>
    <th></th>
    <th class="twelve wide">Functions</th>
  </thead>
    <tr>
      <td>templates</td>
      <td>
        <div class="code">
        $.fn.search.settings.templates : {
          escape: function(string) {
            // returns escaped string for injected results
          },
          message: function(message, type) {
           // returns html for message with given message and type
          },
          category: function(response) {
           // returns results html for category results
          },
          standard: function(response) {
           // returns results html for standard results
          }
        }
        </div>
      </td>
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
    <th class="six wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>Search</td>
      <td>Name used in log statements</td>
    </tr>
    <tr>
      <td>namespace</td>
      <td>search</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>regExp</td>
      <td>
        <div class="code">
regExp: {
  escape     : /[\-\[\]\/\{\}\(\)\*\+\?\.\\\^\$\|]/g,
  beginsWith : '(?:\s|^)'
}
        </div>
      </td>
      <td>Regular expressions used for matching</td>
    </tr>
    <tr>
      <td>selector</td>
      <td>
        <div class="code">
selector : {
  prompt       : '.prompt',
  searchButton : '.search.button',
  results      : '.results',
  category     : '.category',
  result       : '.result'
}
        </div>
      </td>
      <td>Selectors used to find parts of a module</td>
    </tr>
    <tr>
      <td>metadata</td>
      <td>
        <div class="code">
metadata: {
  cache   : 'cache',
  results : 'results'
}
        </div>
      </td>
      <td>HTML5 metadata attributes used internally</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
className: {
  active  : 'active',
  empty   : 'empty',
  focus   : 'focus',
  loading : 'loading',
  pressed : 'down'
}
        </div>
      </td>
      <td>Class names used to determine element state</td>
    </tr>
    <tr>
      <td>silent</td>
      <td>False</td>
      <td>Silences all console output including error messages, regardless of other debug settings.</td>
    </tr>
    <tr>
      <td>debug</td>
      <td>false</td>
      <td>Debug output to console</td>
    </tr>
    <tr>
      <td>performance</td>
      <td>true</td>
      <td>Show `console.table` output with performance metrics</td>
    </tr>
    <tr>
      <td>verbose</td>
      <td>false</td>
      <td>Debug output includes all internal behaviors</td>
    </tr>
    <tr>
      <td>errors</td>
      <td colspan="2">
        <div class="code">
error : {
  source      : 'Cannot search. No source used, and Semantic API module was not included',
  noResults   : 'Your search returned no results',
  logging     : 'Error in debug logging, exiting.',
  noTemplate  : 'A valid template name was not specified.',
  serverError : 'There was an issue with querying the server.',
  maxResults  : 'Results must be an array to use maxResults setting',
  method      : 'The method you called is not defined.'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```

## === shape.md ===

# Shape

A shape is a three dimensional object displayed on a two dimensional plane

## Definition

#### Shape
A shape is a three dimensional object including any flat content as a side.
```html
<div class="ui people shape">
  <div class="sides">
    <div class="active side">
      <div class="ui card">
        <div class="image">
          <img src="/images/avatar/large/steve.jpg">
        </div>
        <div class="content">
          <div class="header">Steve Jobes</div>
          <div class="meta">
            <a>Acquaintances</a>
          </div>
          <div class="description">
            Steve Jobes is a fictional character designed to resemble someone familiar to readers.
          </div>
        </div>
        <div class="extra content">
          <span class="right floated">
            Joined in 2014
          </span>
          <span>
            <i class="user icon"></i>
            151 Friends
          </span>
        </div>
      </div>
    </div>
    <div class="side">
      <div class="ui card">
        <div class="image">
          <img src="/images/avatar/large/stevie.jpg">
        </div>
        <div class="content">
          <a class="header">Stevie Feliciano</a>
          <div class="meta">
            <span class="date">Joined in 2014</span>
          </div>
          <div class="description">
            Stevie Feliciano is a library scientist living in New York City. She likes to spend her time reading, running, and writing.
          </div>
        </div>
        <div class="extra content">
          <a>
            <i class="user icon"></i>
            22 Friends
          </a>
        </div>
      </div>
    </div>
  </div>
</div>
<div class="ui ignored divider"></div>
<div class="ui ignored icon direction buttons">
  <div class="ui button" data-animation="flip" title="Flip Left" data-direction="left"><i class="left long arrow icon"></i></div>
  <div class="ui button" data-animation="flip" title="Flip Up" data-direction="up"><i class="up long arrow icon"></i></div>
  <div class="ui icon button" data-animation="flip" title="Flip Down" data-direction="down"><i class="down long arrow icon"></i></div>
  <div class="ui icon button" data-animation="flip" title="Flip Right" data-direction="right"><i class="right long arrow icon"></i></div>
</div>
<div class="ui ignored icon direction buttons">
  <div class="ui button" title="Flip Over" data-animation="flip" data-direction="over"><i class="retweet icon"></i></div>
  <div class="ui button" title="Flip Back" data-animation="flip" data-direction="back"><i class="flipped retweet icon"></i></div>
</div>
```

#### Cube
A cube shape is formatted so that each side is the face of a cube
```html
<div class="ui cube shape">
  <div class="sides">
    <div class="active side">
      <div class="content">
        <div class="center">
          1
        </div>
      </div>
    </div>
    <div class="side">
      <div class="content">
        <div class="center">
          2
        </div>
      </div>
    </div>
    <div class="side">
      <div class="content">
        <div class="center">
          3
        </div>
      </div>
    </div>
    <div class="side">
      <div class="content">
        <div class="center">
          4
        </div>
      </div>
    </div>
    <div class="side">
      <div class="content">
        <div class="center">
          5
        </div>
      </div>
    </div>
    <div class="side">
      <div class="content">
        <div class="center">
          6
        </div>
      </div>
    </div>
  </div>
</div>

<div class="ui ignored divider"></div>
<div class="ui ignored icon direction buttons">
  <div class="ui button" data-animation="flip" title="Flip Left" data-direction="left"><i class="left long arrow icon"></i></div>
  <div class="ui button" data-animation="flip" title="Flip Up" data-direction="up"><i class="up long arrow icon"></i></div>
  <div class="ui icon button" data-animation="flip" title="Flip Down" data-direction="down"><i class="down long arrow icon"></i></div>
  <div class="ui icon button" data-animation="flip" title="Flip Right" data-direction="right"><i class="right long arrow icon"></i></div>
</div>
<div class="ui ignored icon direction buttons">
  <div class="ui button" title="Flip Over" data-animation="flip" data-direction="over"><i class="retweet icon"></i></div>
  <div class="ui button" title="Flip Back" data-animation="flip" data-direction="back"><i class="flipped retweet icon"></i></div>
</div>
```

#### Text
A text shape is formatted to allow for sides of text to be displayed
> <i class="info letter icon"></i>
> <div class="content">
>   <div class="header">Using Shapes</div>
>   <ul class="list">
>     <li>A shape must have defined width and heights for each side or else text flow may change during animation</li>
>     <li>The module uses 3D transformations which are currently only supported in modern versions of Chrome, Safari, and Firefox.</li>
>   </ul>
> </div>
```html
<div class="ui text shape">
  <div class="sides">
    <div class="active ui header side">Did you know? This side starts visible.</div>
    <div class="ui header side">Help, its another side!</div>
    <div class="ui header side">This is the last side</div>
  </div>
</div>

<div class="ui ignored divider"></div>
<div class="ui ignored icon direction buttons">
  <div class="ui button" data-animation="flip" title="Flip Left" data-direction="left"><i class="left long arrow icon"></i></div>
  <div class="ui button" data-animation="flip" title="Flip Up" data-direction="up"><i class="up long arrow icon"></i></div>
  <div class="ui icon button" data-animation="flip" title="Flip Down" data-direction="down"><i class="down long arrow icon"></i></div>
  <div class="ui icon button" data-animation="flip" title="Flip Right" data-direction="right"><i class="right long arrow icon"></i></div>
</div>
<div class="ui ignored icon direction buttons">
  <div class="ui button" title="Flip Over" data-animation="flip" data-direction="over"><i class="retweet icon"></i></div>
  <div class="ui button" title="Flip Back" data-animation="flip" data-direction="back"><i class="flipped retweet icon"></i></div>
</div>
```

## Examples

### Examples

#### Shape Types
Shapes do not have to be regular or have its sides match up in length and width to animate correctly.

### Shape
```html
<div class="ui type buttons">
  <div class="active ui button" data-shape="auto">Auto</div>
  <div class="ui button" data-shape="square">Square</div>
  <div class="ui button" data-shape="irregular">Irregular</div>
</div>
<div class="ui divider"></div>
<div class="demo auto ui shape">
  <div class="sides">
    <div class="active first side">
      <img src="/images/leaves/1.png" class="ui medium image">
    </div>
    <div class="second side">
      <img src="/images/leaves/3.png" class="ui medium image">
    </div>
    <div class="third side">
      <img src="/images/leaves/5.png" class="ui medium image">
    </div>
  </div>
</div>

<div class="ui ignored divider"></div>
<div class="ui ignored icon direction buttons">
  <div class="ui button" data-animation="flip" title="Flip Left" data-direction="left"><i class="left long arrow icon"></i></div>
  <div class="ui button" data-animation="flip" title="Flip Up" data-direction="up"><i class="up long arrow icon"></i></div>
  <div class="ui icon button" data-animation="flip" title="Flip Down" data-direction="down"><i class="down long arrow icon"></i></div>
  <div class="ui icon button" data-animation="flip" title="Flip Right" data-direction="right"><i class="right long arrow icon"></i></div>
</div>
<div class="ui ignored icon direction buttons">
  <div class="ui button" title="Flip Over" data-animation="flip" data-direction="over"><i class="retweet icon"></i></div>
  <div class="ui button" title="Flip Back" data-animation="flip" data-direction="back"><i class="flipped retweet icon"></i></div>
</div>
```

## Usage

### Getting Started

#### Required Markup
Shapes can have any arbitrary content, just wrap each side in `side`
```html
<div class="ui shape">
  <div class="sides">
    <div class="active side">This side starts visible.</div>
    <div class="side">This is yet another side</div>
    <div class="side">This is the last side</div>
  </div>
</div>
```

#### Animating with Javascript
Animations use CSS3 transitions and Javascript to set-up the correct conditions.

Initializing a shape
```javascript
$('.shape').shape();
```

Transitions automatically assume next side is the next sibling (or first if last element)
```javascript
$('.shape').shape('flip up');
```

To manually set the next side to appear use a selector or jQuery object
```javascript
$('.shape')
  .shape('set next side', '.second.side')
  .shape('flip up')
;
```

Any internal method can be invoked programmatically
```javascript
$('.shape').shape('repaint');
```

## Behavior

All the following behaviors can be called using the syntax:
```javascript
$('.your.element')
  .shape('behavior name', argumentOne, argumentTwo)
;
```

```html
<table class="ui definition sortable celled table segment">
  <thead>
    <th>Behavior</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>flip up</td>
      <td>Flips the shape upward</td>
    </tr>
    <tr>
      <td>flip down</td>
      <td>Flips the shape downward</td>
    </tr>
    <tr>
      <td>flip right</td>
      <td>Flips the shape right</td>
    </tr>
    <tr>
      <td>flip left</td>
      <td>Flips the shape left</td>
    </tr>
    <tr>
      <td>flip over</td>
      <td>Flips the shape over clock-wise</td>
    </tr>
    <tr>
      <td>flip back</td>
      <td>Flips the shape over counter-clockwise</td>
    </tr>
    <tr>
      <td>set next side(selector)</td>
      <td>Set the next side to a specific selector</td>
    </tr>
    <tr>
      <td>is animating</td>
      <td>Returns whether shape is currently animating</td>
    </tr>
    <tr>
      <td>reset</td>
      <td>Removes all inline styles</td>
    </tr>
    <tr>
      <td>queue(animation)</td>
      <td>Queues an animationtill after current animation</td>
    </tr>
    <tr>
      <td>repaint</td>
      <td>Forces a reflow on element</td>
    </tr>
    <tr>
      <td>set default side</td>
      <td>Set the next side to next sibling to active element</td>
    </tr>
    <tr>
      <td>set stage size</td>
      <td>Sets shape to the content size of the next side</td>
    </tr>
    <tr>
      <td>refresh</td>
      <td>Refreshes the selector cache for element sides</td>
    </tr>
    <tr>
      <td>get transform down</td>
      <td>Returns translation for next side staged below</td>
    </tr>
    <tr>
      <td>get transform left</td>
      <td>Returns translation for next side staged left</td>
    </tr>
    <tr>
      <td>get transform right</td>
      <td>Returns translation for next side staged right</td>
    </tr>
    <tr>
      <td>get transform up</td>
      <td>Returns translation for next side staged up</td>
    </tr>
    <tr>
      <td>get transform down</td>
      <td>Returns translation for next side staged down</td>
    </tr>
  </tbody>
</table>
```

## Settings

### Shape Settings
Shape settings modify the shape's behavior
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th>Setting</th>
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>duration</td>
      <td>700ms</td>
      <td>Duration of side change animation</td>
    </tr>
    <tr>
      <td>width <div class="ui horizontal teal label">2.2</div></td>
      <td>initial</td>
      <td>
        <div class="ui bulleted list">
          <div class="item">When set to `next` will use the width of the next `side` during the shape's animation.</div>
          <div class="item">When set to `initial` it will use the width of the shape at initialization.</div>
          <div class="item">When set to a specifix pixel height, will force the width to that height.</div>
        </div>
      </td>
    </tr>
    <tr>
      <td>height <div class="ui horizontal teal label">2.2</div></td>
      <td>initial</td>
      <td>
        <div class="ui bulleted list">
          <div class="item">When set to `next` will use the height of the next `side` during the shape's animation.</div>
          <div class="item">When set to `initial` it will use the height of the shape at initialization.</div>
          <div class="item">When set to a specifix pixel height, will force the height to that height.</div>
        </div>
      </td>
    </tr>
  </tbody>
</table>
```

### Callbacks
Callbacks specify a function to occur after a specific behavior.

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th class="four wide">Setting</th>
    <th>Context</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>beforeChange</td>
      <td>Next Side</td>
      <td>Is called before side change</td>
    </tr>
    <tr>
      <td>onChange</td>
      <td>Active Side</td>
      <td>Is called after visible side change</td>
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
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>namespace</td>
      <td>shape</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>selector</td>
      <td colspan="2">
        <div class="code">
selector    : {
  sides : '.sides',
  side  : '.side'
}
        </div>
      </td>
    </tr>
    <tr>
      <td>className</td>
      <td colspan="2">
        <div class="code">
className   : {
  animating : 'animating',
  hidden    : 'hidden',
  loading   : 'loading',
  active    : 'active'
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
      <td>Shape</td>
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
      <td>error</td>
      <td colspan="2">
        <div class="code">
error: {
  side   : 'You tried to switch to a side that does not exist.',
  method : 'The method you called is not defined'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```


## === sidebar.md ===

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


## === sticky.md ===

# Sticky

Sticky content fixes itself to the browser viewport as content is scrolled

## Examples

### Introduction

Sticky content stays fixed to the browser viewport while another column of content is visible on the page.

Although sticky content can be used inside any container, sticky pairs well with [ui rail](/elements/rail.html) because often "stuck" content is used to occupy additional canvas space outside of the main content of a website, making sure follow up links, ads, and other ancillary content remains on screen while engaging the sites main content.

> The following examples may be hidden on small screen sizes. For the best experience, view these examples on a large resolution display.

## Examples

#### Sticking to Adjacent Context
Sticky content attaches itself to the viewport when it is passed, and remains fixed to the viewport until this fixed content collides with the bottom edge of the passed `context`. Additional static content can exist above `sticky` content without affecting its position.

```javascript
$('.ui.sticky')
  .sticky({
    context: '#example1'
  })
;
```
```html
<div class="ui segment" id="example1">
  <div class="left ui rail">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <div class="ui sticky">
      <h3 class="ui header">Stuck Content</h3>
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="right ui rail">
    <div class="ui sticky">
      <h3 class="ui header">Stuck Content</h3>
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
</div>
```

#### Pushing
Specifying `pushing: true` will have the viewport "push" the sticky content depending on the scroll direction. When scrolling down content will be stuck to the top of the viewport, but in the opposite direction content is stuck to the bottom of the viewport.
```javascript
$('.ui.sticky')
  .sticky({
    context: '#example2',
    pushing: true
  })
;
```
```html
<div class="ui segment" id="example2">
  <div class="left ui rail">
    <div class="ui sticky">
      <h3 class="ui header">Stuck Content</h3>
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="right ui rail">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <div class="ui sticky">
      <h3 class="ui header">Stuck Content</h3>
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
</div>
```

#### Oversized Content

Sticky content that is larger than the viewport will automatically scroll independently from the context, shifting scroll direction at any time will also immediately adjust the scroll position of the fixed content.

This behavior makes sure users aren't required to navigate all the way to the top of the context element to see content that can't fit on-screen inside the sticky element.

```javascript
$('.ui.sticky')
  .sticky({
    context: '#example3'
  })
;
```
```html
<div class="ui segment" id="example3">
  <div class="left ui rail">
    <div class="ui sticky">
      <h3 class="ui header">Long Stuck Content</h3>
      <div class="ui divided items">
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="right ui rail">
      <div class="ui sticky">
        <h3 class="ui header">Short Stuck Content</h3>
        <img class="ui wireframe image" src="/images/wireframe/image.png">
      </div>
    </div>
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
</div>
```

#### Sticking to Own Context

Sticky content without a specified context can also stick itself to its current context, although this may cause overlap issues with content.

Content that sticks to its own context will adjust its own layout when being "stuck". You can fix layout issues caused by this reflow by adding styles to the next element after a `ui fixed sticky`

```css
.ui.fixed.sticky + p {
  margin-top: 39px;
}
```

```javascript
$('.ui.sticky')
  .sticky()
;
```
```html
<div class="ui segment">
  <div class="ui sticky">
    <div class="ui fluid three item tabular menu">
      <a class="active item">Tab 1</a>
      <a class="item">Tab 2</a>
      <a class="item">Tab 3</a>
    </div>
  </div>
  <div class="ui active tab">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  </div>
</div>
```

## Usage

### Initializing

Sticky is initialized on content that should be stuck to viewport. Most instances require specifying a secondary `context` which will define the top and bottom bounds of the sticky element. Sticky content must be included inside a containing element. This container can be a [ui rail](/elements/rail.html) or your own arbitrary container, but should exist parallel to your context.

> Sticky does not work in tables without using `table-layout: fixed` to prevent automatic resizing with content
```html
<div class="ui rail">
  <div class="ui sticky">
    <!-- Any arbitrary content !-->
  </div>
</div>
<div id="context">
  <!-- Long flowing text content !-->
</div>
```
```javascript
$('.ui.sticky')
  .sticky({
    context: '#context'
  })
;
```

#### Refreshing Cached Values
Sticky content caches its current offset on the page and other crucial values on initialization. This prevents it from having to query the DOM on each browser scroll which would drastically reduce performance.

Sticky uses [mutation observers](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver) to adjust its position when content is added to the context, and also will automatically recalculate on browser `resize`, but any other changes to your page that adjust the elements context require you to refresh the sticky's position

Examples of changes that might affect sticky elements are:

*   Loading images without specified size
*   Setting CSS which adjusts the layout of the page
*   Hiding elements using Javascript

Refreshing cached values just requires calling the `refresh` behavior.
```javascript
// recalculates offsets
$('.ui.sticky')
  .sticky('refresh')
;
```

#### Sticky Conditions
Sticky content is required to be inside its own `position: relative` container that is either the sticky context, or **shares vertical positioning with the context element**.

You can use `ui rail` or `ui grid` column that are in the same row to provide this set-up, or your own custom CSS

Sticky elements swap between being bound to the edges of their container, or fixed to the edges of the browser viewport
```html
<table class="ui ignored celled definition table">
  <thead>
    <tr>
      <th></th>
      <th>Class</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Fixed Top</td>
      <td>ui fixed top sticky</td>
      <td>Element is fixed to top of viewport</td>
    </tr>
    <tr>
      <td>Fixed Bottom</td>
      <td>ui fixed bottom sticky</td>
      <td>Element is fixed to bottom of viewport</td>
    </tr>
    <tr>
      <td>Bound Top</td>
      <td>ui bound top sticky</td>
      <td>Element is bound to the top of its containing element (usually rail or column)</td>
    </tr>
    <tr>
      <td>Bound Bottom</td>
      <td>ui bound bottom sticky</td>
      <td>Element is bound to the bottom of its containing element (usually rail or column)</td>
    </tr>
  </tbody>
</table>
```

#### Adjusting Offset and Padding
If you have content fixed to the viewport it might make sense to include a top or bottom offset. An `offset` will adjust all values so that content does not overlap any content between the top of the browser and the specified value. A `bottomOffset` will do the same thing for content fixed to the bottom of the viewport.
```javascript
$('.ui.sticky')
  .sticky({
    offset       : 50,
    bottomOffset : 50,
    context      : '#element-to-follow'
  })
;
```

## Settings

### Sticky Settings
Settings to configure sticky behavior
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th>Setting</th>
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>pushing</td>
      <td>false</td>
      <td>Whether element should be "pushed" by the viewport, attaching to the bottom of the screen when scrolling up</td>
    </tr>
    <tr>
      <td>setSize</td>
      <td>true <div class="ui label">New in 2.2.11</div></td>
      <td>Sets size of `fixed` content to match its width before fixing to screen dynamically. This is used because fixed may display block or 100% width content differently than it appears before sticking.</td>
    </tr>
    <tr>
      <td>jitter</td>
      <td>5</td>
      <td>Sticky container height will only be set if the difference between heights of container and context is larger than this jitter value.</td>
    </tr>
    <tr>
      <td>observeChanges</td>
      <td>false</td>
      <td>Whether any change in `context` DOM should automatically refresh cached sticky positions</td>
    </tr>
    <tr>
      <td>context</td>
      <td>false</td>
      <td>Context which sticky element should stick to</td>
    </tr>
    <tr>
      <td>scrollContext</td>
      <td>window</td>
      <td>Context which sticky should attach `onscroll` events.</td>
    </tr>
    <tr>
      <td>offset</td>
      <td>0</td>
      <td>Offset in pixels from the top of the screen when fixing element to viewport</td>
    </tr>
    <tr>
      <td>bottomOffset</td>
      <td>0</td>
      <td>Offset in pixels from the bottom of the screen when fixing element to viewport</td>
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
      <td>sticky</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
className : {
  bound     : 'bound',
  fixed     : 'fixed',
  supported : 'native',
  top       : 'top',
  bottom    : 'bottom'
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
      <td>Sticky</td>
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
error         : {
  container      : 'Sticky element must be inside a relative container',
  visible        : 'Element is hidden, you must call refresh after element becomes visible',
  method         : 'The method you called is not defined.',
  invalidContext : 'Context specified does not exist',
  elementSize    : 'Sticky element is larger than its container, cannot create sticky.'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```


## === tab.md ===

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


## === transition.md ===

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
