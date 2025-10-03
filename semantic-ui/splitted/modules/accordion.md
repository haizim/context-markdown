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
