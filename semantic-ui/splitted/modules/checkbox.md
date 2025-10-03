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
