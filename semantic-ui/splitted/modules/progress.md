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
