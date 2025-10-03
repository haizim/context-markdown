# Form Validation

A form validation behavior checks data against a set of criteria before passing it along to the server

## Usage

#### Specifying Validation Rules
Form validation requires passing in a validation object with the rules required to validate your form.
> A validation object includes a list of form elements, and rules to validate each field against. Fields are matched by either the `id`, `name`, or `data-validate` property (in that order) matching the identifier specified in the settings object. Validation objects must use either shorthand or longhand exclusively.
```
// Shorthand Validation
$('.ui.form')
  .form({
    fields: {
      name     : 'empty',
      gender   : 'empty',
      username : 'empty',
      password : ['minLength[6]', 'empty'],
      skills   : ['minCount[2]', 'empty'],
      terms    : 'checked'
    }
  })
;
```

```
// Full Validation Settings
$('.ui.form')
  .form({
    fields: {
      name: {
        identifier: 'name',
        rules: [
          {
            type   : 'empty',
            prompt : 'Please enter your name'
          }
        ]
      },
      skills: {
        identifier: 'skills',
        rules: [
          {
            type   : 'minCount[2]',
            prompt : 'Please select at least two skills'
          }
        ]
      },
      gender: {
        identifier: 'gender',
        rules: [
          {
            type   : 'empty',
            prompt : 'Please select a gender'
          }
        ]
      },
      username: {
        identifier: 'username',
        rules: [
          {
            type   : 'empty',
            prompt : 'Please enter a username'
          }
        ]
      },
      password: {
        identifier: 'password',
        rules: [
          {
            type   : 'empty',
            prompt : 'Please enter a password'
          },
          {
            type   : 'minLength[6]',
            prompt : 'Your password must be at least {ruleValue} characters'
          }
        ]
      },
      terms: {
        identifier: 'terms',
        rules: [
          {
            type   : 'checked',
            prompt : 'You must agree to the terms and conditions'
          }
        ]
      }
    }
  })
;
```
```html
<form class="ui form segment">
  <p>Tell Us About Yourself</p>
  <div class="two fields">
    <div class="field">
      <label>Name</label>
      <input placeholder="First Name" name="name" type="text">
    </div>
    <div class="field">
      <label>Gender</label>
      <select class="ui dropdown" name="gender">
        <option value="">Gender</option>
        <option value="male">Male</option>
        <option value="female">Female</option>
      </select>
    </div>
  </div>
  <div class="two fields">
    <div class="field">
      <label>Username</label>
      <input placeholder="Username" name="username" type="text">
    </div>
    <div class="field">
      <label>Password</label>
      <input type="password" name="password">
    </div>
  </div>
  <div class="field">
    <label>Skills</label>
    <select name="skills" multiple class="ui dropdown">
      <option value="">Select Skills</option>
      <option value="css">CSS</option>
      <option value="html">HTML</option>
      <option value="javascript">Javascript</option>
      <option value="design">Graphic Design</option>
      <option value="plumbing">Plumbing</option>
      <option value="mech">Mechanical Engineering</option>
      <option value="repair">Kitchen Repair</option>
    </select>
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" name="terms" />
      <label>I agree to the terms and conditions</label>
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui error message"></div>
</div>
</form>
```

#### Passing Parameters to Rules
Typically rules that include a parameter are written `minLength[2]` with the value being passed in as brackets.

If passing in properties as a string is not ideal, or if you are pulling values from another javascript variable, it might make sense to consider using `value` to pass in the rule value.
```
$('.ui.form').form({
  fields: {
    color: {
      identifier: 'color',
      rules: [{
        type: 'regExp',
        value: /rgb\((\d{1,3}), (\d{1,3}), (\d{1,3})\)/i,
      }]
    }
  }
});
```
```html
<form class="ui form segment">
  <div class="field">
    <label>Color</label>
    <input placeholder="Enter rgb" name="color" type="text" value="rgb(255, 255, 255)">
  </div>
  <div class="ui primary submit button">Submit</div>
</form>
```

#### Customizing Prompts
Form validation includes default error prompts for most cases, however these can be quite generic. To specify custom personalized values for a validation prompt use the `prompt` property with a rule.
> Starting in <div class="ui teal label">2.3.1</div> you can specify prompts as a function. This may be useful when returning validation for fields that require dynamic validation messages.
> You can set default messages for each validation rule type by modifying `$.fn.form.settings.prompt`

Prompt also supports custom templating with the following values replaced

| **{name}** | The current text of a field's label, or if no label available its placeholder text |
|---|---|
| **{identifier}** | The identifier used to match the field |
| **{value}** | The current field value |
| **{ruleValue}** | The value passed to a rule, for example `minLength[100]` would set this value to 100 |

```
$('.ui.form')
  .form({
    fields: {
      field1: {
        rules: [
          {
            type   : 'empty'
          }
        ]
      },
      field2: {
        rules: [
          {
            type   : 'exactly[dog]',
            prompt : '{name} is set to "{value}" that is totally wrong. It should be {ruleValue}'
          }
        ]
      },
      field3: {
        rules: [
          {
            type   : 'exactly[cat]',
            prompt : function(value) {
              if(value == 'dog') {
                return 'I told you to put cat, not dog!';
              }
              return 'That is not cat';
            }
          }
        ],
      }
    }
  })
;
```
```html
<form class="ui form segment">
  <div class="two fields">
    <div class="field">
      <label>Field 1</label>
      <input type="text" name="field1">
    </div>
    <div class="field">
      <label>Field 2</label>
      <input type="text" name="field2">
    </div>
    <div class="field">
      <label>Field 3</label>
      <input type="text" name="field3">
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui error message">
  </div>
</form>
```

#### Matching Fields
By default the property name used in the validation object will match against the `id`, `name`, or `data-validate` property of each input to find the corresponding field to match validation rules against.

If you need to specify a different identifier you can use the `identifier` property on each validation rule
```
$('.ui.form')
  .form({
    fields: {
      name: {
        identifier : 'special-name',
        rules: [
          {
            type   : 'empty'
          }
        ]
      }
    }
  })
;
```
```html
<form class="ui form segment">
  <div class="field">
    <label>Special Field</label>
    <input type="text" name="special-name">
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui error message">
  </div>
</form>
```

#### Validating Programmatically
Form validation provides additional behaviors to programmatically trigger validation for either the form or an individual field, and check validation on the form or individual fields.

Please see the [behaviors section](#behaviors) for an explanation on syntax.

| **validate form** | Validates entire form and displays errors if necessary |
|---|---|
| **is valid** | Returns whether a form is valid |
| **is valid(fieldName)** | Returns whether a field in a form is valid (does not update UI) |
| **validate field(fieldName)** | Validates a particular field and displays errors if necessary |

```
$('.ui.form')
  .form({
    fields: {
     email: 'empty',
     name: 'empty'
    }
  })
;
if( $('.ui.form').form('is valid', 'email')) {
  // email is valid
}
if( $('.ui.form').form('is valid')) {
  // form is valid (both email and name)
}
```

## Rules

#### Validation Rules
Validation rules are a set of conditions required to validate a field
> Validation rules are found in `$.fn.form.settings.rules`, to add new global validation rules, modify `$.fn.form.settings.rules` to include your function.
> To pass parameters to a rule, use bracket notation in your settings object. For example `type: 'not[dog]'`

### Empty

| empty | A field is empty |
|---|---|
| checked | A checkbox field is checked |

### Content Type

| email | A field is a valid email address | |
|---|---|---|
| url | A field is a url | |
| integer | A field is an integer value, or matches an integer range | `integer` or `integer[1..10]` |
| decimal | A field must be a decimal number | |
| number | A field is any number decimal or non-decimal | |
| regExp[expression] | Matches against a regular expression, when using bracketed notation RegExp values must be escaped. | `regExp[/^[a-z0-9_-]{3,16}$/gi]]` Or `regExp[/^[a-z0-9_-]{3,16}$/]]` |

### Payment

| creditCard | A field is a valid credit card | `creditCard` |
|---|---|---|
| creditCard[types] | A field matches a specified array of card types | `creditCard[visa,mastercard,unionpay]` |

### Specified Content

| contains | A field contains text (case insensitive) | `contains[foo]` |
|---|---|
| containsExactly | A field contains text (case sensitive) | `containsExactly[foo]` |
| doesntContain | A field doesn't contain text (case insensitive) | `doesntContain[foo]` |
| doesntContainExactly | A field doesn't contain text (case sensitive) | `doesntContainExactly[foo]` |
| is | A field is a value (case insensitive) | `is[foo]` |
| isExactly | A field is a value (case-sensitive) | `isExactly[foo]` |
| not | A field is not a value (case insensitive) | `not[foo]` |
| notExactly | A field is not a value (case sensitive) | `notExactly[foo]` |

### Length

| minLength | A field is less than a min length | `minLength[5]` |
|---|---|
| exactLength | A field is exactly length | `exactLength[16]` |
| maxLength | A field is less than a max length | `maxLength[50]` |

### Matching Fields

| match | A field should match the value of another validation field, for example to confirm passwords | `match[password]` |
|---|---|
| different | A field should be different than another specified field | `different[choice]` |

### Selection Count

| minCount | A multiple select field contains at minimum (count) selections | `minCount[count]` |
|---|---|
| exactCount | A multiple select field contains exactly (count) selections | `exactCount[count]` |
| maxCount | A multiple select field contains at maximum (count) selections | `maxCount[count]` |

#### Adding Custom Rules
You can extend form validation to include your own rules. Keep in mind these will need to be executed synchronously.
```
// some arbitrary business-logic
window.user = {
  name       : 'Simon',
  adminLevel : 1
};
// custom form validation rule
$.fn.form.settings.rules.adminLevel = function(value, adminLevel) {
  return (window.user.adminLevel >= adminLevel)
};
$('.ui.form')
  .form({
    fields: {
      dog: {
        identifier: 'dog',
        rules: [
          {
            type: 'adminLevel[2]',
            prompt: 'You must be at least a level-2 admin to add a dog'
          }
        ]
      }
    }
  })
;
```
```html
<form class="ui form segment">
  <p>Let's go ahead and get you signed up.</p>
  <div class="field">
    <label>Dog</label>
    <input placeholder="Dog" name="dog" type="text">
  </div>
  <div class="ui primary submit button">
    <i class="add icon"></i>
    Add Dog
  </div>
  <div class="ui error message"></div>
</form>
```

#### Built-in Events

Form will automatically attach events to specially labeled form fields

*   Fields will blur on `escape` key press
*   Fields will submit form on `enter`
*   Submit events will be attached to `click` on any element inside the form with class `submit`
*   Reset events will be attached to `click` on any element inside the form with class `reset`
*   Clear events will be attached to `click` on any element inside the form with class `clear`

```html
<form class="ui form segment">
  <div class="field">
    <label>Test Field</label>
    <input placeholder="Test Field" name="name" type="text">
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui reset button">Reset</div>
  <div class="ui clear button">Clear</div>
</form>
```

## Manipulating Forms

#### Reset / Clear Fields

Calling `$('form').form('reset')`, or clicking any reset element will return all form values to their *default value*. This is the value the form fields were set to when the page loaded.

Calling `$('form').form('clear')` will remove all values from form fields and reset dropdowns to placeholder text

> Form `reset` works by caching default values on page load. For this to work correctly any form that uses reset will need to initialize on page load.
> Reset and clear will modify all form fields, not just those which have validation rules
```html
<form class="ui form segment">
  <div class="two fields">
    <div class="field">
      <label>Name</label>
      <input placeholder="First Name" name="name" type="text">
    </div>
    <div class="field">
      <label>Gender</label>
      <div class="ui selection dropdown">
        <input name="gender" type="hidden">
        <div class="default text">Gender</div>
        <i class="dropdown icon"></i>
        <div class="menu">
          <div class="item" data-value="male">Male</div>
          <div class="item" data-value="female">Female</div>
        </div>
      </div>
    </div>
  </div>
  <div class="field">
    <label>Username</label>
    <input placeholder="Username" name="username" type="text">
  </div>
  <div class="field">
    <label>Password</label>
    <input name="password" type="password">
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input name="terms" type="checkbox">
      <label>I agree to the terms and conditions</label>
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui reset button">Reset</div>
  <div class="ui clear button">Clear</div>
</form>
```

#### Writing Values

Form includes behaviors for reading from and writing to form fields.

```javascript
$('.writing.example form')
  // set one value
  .form('set value', 'name', 'Jack')

  // set several values
  .form('set values', {
    name     : 'Jack',
    gender   : 'male',
    colors   : ['red', 'grey'],
    username : 'jlukic',
    password : 'youdliketoknow',
    terms    : true
  })
;
```
```html
<form class="ui form segment">
  <div class="two fields">
    <div class="field">
      <label>Name</label>
      <input placeholder="First Name" name="name" type="text">
    </div>
    <div class="field">
      <label>Gender</label>
      <div class="ui selection dropdown">
        <input name="gender" type="hidden">
        <div class="default text">Gender</div>
        <i class="dropdown icon"></i>
        <div class="menu">
          <div class="item" data-value="male">Male</div>
          <div class="item" data-value="female">Female</div>
        </div>
      </div>
    </div>
  </div>
  <div class="field">
    <label>Username</label>
    <input placeholder="Username" name="username" type="text">
  </div>
  <div class="field">
    <label>Password</label>
    <input name="password" type="password">
  </div>
  <div class="inline fields">
    <label for="colors">Favorite Colors</label>
    <div class="field">
      <div class="ui checkbox">
        <input type="checkbox" name="colors[]" value="red" />
        <label>Red</label>
      </div>
    </div>
    <div class="field">
      <div class="ui checkbox">
        <input type="checkbox" name="colors[]" value="blue" />
        <label>Blue</label>
      </div>
    </div>
    <div class="field">
      <div class="ui checkbox">
        <input type="checkbox" name="colors[]" value="green" />
        <label>Green</label>
      </div>
    </div>
    <div class="field">
      <div class="ui checkbox">
        <input type="checkbox" name="colors[]" value="grey" />
        <label>Grey</label>
      }
    </div>
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input name="terms" type="checkbox">
      <label>I agree to the terms and conditions</label>
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui clear button">Clear</div>
</form>
```

#### Getting Values

You can also read values from form fields using `get value` and `get values`

> Although `get values` allows you to use any matching identifier, returned values will always use the corresponding `name` attribute of the element.
```javascript
var
  $form = $('.get.example form'),
  // get one value
  colors = $form.form('get value', 'colors'),
  // get list of values
  fields = $form.form('get values', ['name', 'colors']),
  // get all values
  allFields = $form.form('get values')
;
console.log(colors);
console.log(fields);
console.log(allFields);
```
```html
<form class="ui form segment">
  <div class="two fields">
    <div class="field">
      <label>Name</label>
      <input placeholder="First Name" name="name" type="text">
    </div>
    <div class="field">
      <label>Gender</label>
      <div class="ui selection dropdown">
        <input name="gender" type="hidden">
        <div class="default text">Gender</div>
        <i class="dropdown icon"></i>
        <div class="menu">
          <div class="item" data-value="male">Male</div>
          <div class="item" data-value="female">Female</div>
        </div>
      </div>
    </div>
  </div>
  <div class="field">
    <label>Username</label>
    <input placeholder="Username" name="username" type="text">
    </div>
  <div class="field">
    <label>Password</label>
    <input name="password" type="password">
  </div>
  <div class="inline fields">
    <label for="colors">Favorite Colors</label>
    <div class="field">
      <div class="ui checkbox">
        <input type="checkbox" name="colors[]" value="red" />
        <label>Red</label>
      </div>
    </div>
    <div class="field">
      <div class="ui checkbox">
        <input type="checkbox" name="colors[]" value="blue" />
        <label>Blue</label>
      </div>
    </div>
    <div class="field">
      <div class="ui checkbox">
        <input type="checkbox" name="colors[]" value="green" />
        <label>Green</label>
      </div>
    </div>
    <div class="field">
      <div class="ui checkbox">
        <input type="checkbox" name="colors[]" value="grey" />
        <label>Grey</label>
      </div>
    </div>
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input name="terms" type="checkbox">
      <label>I agree to the terms and conditions</label>
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
</form>
```

## Examples

### Rule Examples

#### Empty
The following shows examples of validating different types of empty or unchecked content.
```html
<form class="ui form">
  <div class="field">
    <label>Empty</label>
    <input name="empty" type="text">
  </div>
  <div class="field">
    <label>Dropdown</label>
    <select class="ui dropdown" name="dropdown">
      <option value="">Select</option>
      <option value="male">Choice 1</option>
      <option value="female">Choice 2</option>
    </select>
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" name="checkbox" />
      <label>Checkbox</label>
    </div>
  </div>
  <div class="ui submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```
```javascript
$('.field.example form')
  .form({
    on: 'blur',
    fields: {
      empty: {
        identifier  : 'empty',
        rules: [
          {
            type   : 'empty',
            prompt : 'Please enter a value'
          }
        ]
      },
      dropdown: {
        identifier  : 'dropdown',
        rules: [
          {
            type   : 'empty',
            prompt : 'Please select a dropdown value'
          }
        ]
      },
      checkbox: {
        identifier  : 'checkbox',
        rules: [
          {
            type   : 'checked',
            prompt : 'Please check the checkbox'
          }
        ]
      }
    }
  })
;
```

#### Content Type
Inputs can match against common content types, or your own custom [regular expressions](http://www.regular-expressions.info/).
```html
<form class="ui form">
  <div class="two fields">
    <div class="field">
      <label>Integer</label>
      <input name="integer" type="text" value="101">
    </div>
    <div class="field">
      <label>E-mail</label>
      <input name="email" type="text" value="jack">
    </div>
  </div>
  <div class="two fields">
    <div class="field">
      <label>Decimal</label>
      <input name="decimal" type="text" value="1.1.1">
    </div>
    <div class="field">
      <label>Number</label>
      <input name="number" type="text" value="+200">
    </div>
  </div>
  <div class="two fields">
    <div class="field">
      <label>URL</label>
      <input name="url" type="text" value="ww.fakeurl.com">
    </div>
    <div class="field">
      <label>RegEx</label>
      <input name="regex" type="text" value="joe">
    </div>
  </div>
  <div class="ui submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```
```javascript
$('.type.example form')
  .form({
    on: 'blur',
    fields: {
      integer: {
        identifier  : 'integer',
        rules: [
          {
            type   : 'integer[1..100]',
            prompt : 'Please enter an integer value'
          }
        ]
      },
      decimal: {
        identifier  : 'decimal',
        rules: [
          {
            type   : 'decimal',
            prompt : 'Please enter a valid decimal'
          }
        ]
      },
      number: {
        identifier  : 'number',
        rules: [
          {
            type   : 'number',
            prompt : 'Please enter a valid number'
          }
        ]
      },
      email: {
        identifier  : 'email',
        rules: [
          {
            type   : 'email',
            prompt : 'Please enter a valid e-mail'
          }
        ]
      },
      url: {
        identifier  : 'url',
        rules: [
          {
            type   : 'url',
            prompt : 'Please enter a url'
          }
        ]
      },
      regex: {
        identifier  : 'regex',
        rules: [
          {
            type   : 'regExp[/^[a-z0-9_-]{4,16}$/]'
            prompt : 'Please enter a 4-16 letter username'
          }
        ]
      }
    }
  })
;
```

#### Payment
Inputs can validate credit cards and other payment types.

| Card Name | Validation Name | Test Card Number |
|---|---|---|
| Visa | `visa` | 4565340519181845 |
| American Express | `amex` | 378282246310005 |
| Mastercard | `mastercard` | 5200828282828210 |
| Discover | `discover` | 6011111111111117 |
| Unionpay | `unionpay` | 6240008631401148 |
| JCB | `jcb` | 3530111333300000 |
| Diner's Club | `dinersClub` | 38520000023237 |
| Maestro | `maestro` | 6799990100000000019 |
| Laser | `laser` | 630490017740292441 |
| Visa Electron | `visaElectron` | 4917300800000000 |

```html
<form class="ui form segment">
  <div class="two fields">
    <div class="field">
      <label>Credit Card</label>
      <input name="card" type="text" value="4444444444444444">
    </div>
    <div class="field">
      <label>Certain Type</label>
      <input name="exact-card" type="text" value="4444444444444444">
    </div>
  </div>
  <div class="ui submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```
```javascript
$('.payment.example form')
  .form({
    on: 'blur',
    fields: {
      card: {
        identifier  : 'card',
        rules: [
          {
            type   : 'creditCard',
            prompt : 'Please enter a valid credit card'
          }
        ]
      },
      exactCard: {
        identifier  : 'exact-card',
        rules: [
          {
            type   : 'creditCard[visa,amex]',
            prompt : 'Please enter a visa or amex card'
          }
        ]
      }
    }
  })
;
```

#### Matching Fields
Fields can be required to match, or not match other fields. You may consider using this with [optional fields](#optional-fields).
```html
<form class="ui form">
  <div class="two fields">
    <div class="field">
      <label>Match 1</label>
      <input name="match1" type="text" value="same">
    </div>
    <div class="field">
      <label>Match 2</label>
      <input name="match2" type="text" value="different">
    }
  </div>
  <div class="two fields">
    <div class="field">
      <label>Different 1</label>
      <input name="different1" type="text" value="same">
    </div>
    <div class="field">
      <label>Different 2</label>
      <input name="different2" type="text" value="same">
    </div>
  </div>
  <div class="ui submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```
```javascript
$('.match.example form')
  .form({
    on: 'blur',
    fields: {
      match: {
        identifier  : 'match2',
        rules: [
          {
            type   : 'match[match1]',
            prompt : 'Please put the same value in both fields'
          }
        ]
      },
      different: {
        identifier  : 'different2',
        rules: [
          {
            type   : 'different[different1]',
            prompt : 'Please put different values for each field'
          }
        ]
      }
    }
  })
;
```

#### Length
Inputs can match against length of content
```html
<form class="ui form">
  <div class="field">
    <label>minLength</label>
    <textarea name="minLength" cols="5"></textarea>
  </div>
  <div class="field">
    <label>Exact Length</label>
    <input name="exactLength" type="text" value="12345">
  </div>
  <div class="field">
    <label>maxLength</label>
    <textarea name="maxLength" cols="5">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla metus leo, scelerisque quis pretium non, ultricies in dolor. Vivamus pulvinar odio at nisl egestas tempor. Quisque nec diam gravida, convallis massa et, aliquam purus. Nunc eget aliquet leo. Morbi sodales mi placerat volutpat rhoncus. Pellentesque sed leo eu risus rutrum suscipit ut dapibus est. Curabitur lacus diam, viverra mollis purus ut, facilisis consectetur dui. Etiam molestie suscipit ligula, vitae lacinia mi tempor ac. Pellentesque accumsan porttitor nisi. Sed ac metus ac arcu feugiat posuere. Curabitur eget pharetra felis. Donec consectetur felis sed iaculis vulputate. Sed mollis ultrices consequat.</textarea>
  </div>
  <div class="ui submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```
```javascript
$('.length.example form')
  .form({
    on: 'blur',
    fields: {
      minLength: {
        identifier  : 'minLength',
        rules: [
          {
            type   : 'minLength[100]',
            prompt : 'Please enter at least 100 characters'
          }
        ]
      },
      exactLength: {
        identifier  : 'exactLength',
        rules: [
          {
            type   : 'exactLength[6]',
            prompt : 'Please enter exactly 6 characters'
          }
        ]
      },
      maxLength: {
        identifier  : 'maxLength',
        rules: [
          {
            type   : 'maxLength[100]',
            prompt : 'Please enter at most 100 characters'
          }
        ]
      },
    }
  })
;
```

#### Specified Content
Validation rules can specify content that should or should not appear inside an input
```html
<form class="ui form">
  <div class="two fields">
    <div class="field">
      <label>is</label>
      <input name="is" type="text" value="dogs">
    </div>
    <div class="field">
      <label>isExactly</label>
      <input name="isExactly" type="text" value="Dog">
    </div>
  </div>
  <div class="two fields">
    <div class="field">
      <label>not</label>
      <input name="not" type="text" value="Dog">
    </div>
    <div class="field">
      <label>notExactly</label>
      <input name="notExactly" type="text" value="dog">
    </div>
  </div>
  <div class="two fields">
    <div class="field">
      <label>contains</label>
      <input name="contains" type="text" value="poodle">
    </div>
    <div class="field">
      <label>containsExactly</label>
      <input name="containsExactly" type="text" value="Dogbert">
    </div>
  </div>
  <div class="two fields">
    <div class="field">
      <label>doesntContain</label>
      <input name="doesntContain" type="text" value="Dogtown">
    </div>
    <div class="field">
      <label>doesntContainExactly</label>
      <input name="doesntContainExactly" type="text" value="dognapper">
    </div>
  </div>
  <div class="ui submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```
```javascript
$('.content.example form')
  .form({
    on: 'blur',
    fields: {
      is: {
        identifier  : 'is',
        rules: [
          {
            type   : 'is[dog]',
            prompt : 'Please enter exactly "dog"'
          }
        ]
      },
      isExactly: {
        identifier  : 'isExactly',
        rules: [
          {
            type   : 'isExactly[dog]',
            prompt : 'Please enter exactly "dog"'
          }
        ]
      },
      not: {
        identifier  : 'not',
        rules: [
          {
            type   : 'not[dog]',
            prompt : 'Please enter a value, but not "dog"'
          }
        ]
      },
      notExactly: {
        identifier  : 'notExactly',
        rules: [
          {
            type   : 'notExactly[dog]',
            prompt : 'Please enter a value, but not exactly "dog"'
          }
        ]
      },
      contains: {
        identifier  : 'contains',
        rules: [
          {
            type   : 'contains[dog]',
            prompt : 'Please enter a value containing "dog"'
          }
        ]
      },
      containsExactly: {
        identifier  : 'containsExactly',
        rules: [
          {
            type   : 'containsExactly[dog]',
            prompt : 'Please enter a value containing exactly "dog"'
          }
        ]
      },
      doesntContain: {
        identifier  : 'doesntContain',
        rules: [
          {
            type   : 'doesntContain[dog]',
            prompt : 'Please enter a value not containing "dog"'
          }
        ]
      },
      doesntContainExactly: {
        identifier  : 'doesntContainExactly',
        rules: [
          {
            type   : 'doesntContainExactly[dog]',
            prompt : 'Please enter a value not containing exactly "dog"'
          }
        ]
      }
    }
  })
;
```

#### Selection Count
Multiple selects can specify how many options should be allowed.
```html
<form class="ui form">
  <div class="three fields">
    <div class="field">
      <label>Exact Count</label>
      <select name="exactCount" multiple class="ui dropdown">
        <option value="">Select Values</option>
        <option value="1" selected>1</option>
        <option value="2">2</option>
        <option value="3">3</option>
        <option value="4">4</option>
        <option value="5">5</option>
      </select>
    </div>
    <div class="field">
      <label>Minimum Count</label>
      <select name="minCount" multiple class="ui dropdown">
        <option value="">Select Values</option>
        <option value="1" selected>1</option>
        <option value="2">2</option>
        <option value="3">3</option>
        <option value="4">4</option>
        <option value="5">5</option>
      </select>
    </div>
    <div class="field">
      <label>Maximum Count</label>
      <select name="maxCount" multiple class="ui dropdown">
        <option value="">Select Values</option>
        <option value="1" selected>1</option>
        <option value="2" selected>2</option>
        <option value="3" selected>3</option>
        <option value="4">4</option>
        <option value="5">5</option>
      </select>
    </div>
  </div>
  <div class="ui submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```
```javascript
$('.multi.example form')
  .form({
    on: 'blur',
    fields: {
      minCount: {
        identifier  : 'minCount',
        rules: [
          {
            type   : 'minCount[2]',
            prompt : 'Please select at least 2 values'
          }
        ]
      },
      maxCount: {
        identifier  : 'maxCount',
        rules: [
          {
            type   : 'maxCount[2]',
            prompt : 'Please select a max of 2 values'
          }
        ]
      },
      exactCount: {
        identifier  : 'exactCount',
        rules: [
          {
            type   : 'exactCount[2]',
            prompt : 'Please select 2 values'
          }
        ]
      }
    }
  })
```

### Form Examples

#### Adding Rules Programmatically
You can use the special behaviors `add field/rule`, `remove rule` and `remove field` to dynamically add or remove fields or rules.
> <div class="ui header">Adding Multiple Rules and Complex Rules</div>
> You can specify shorthand or full rule objects when adding rules. You can also specifiy fields as an array to modify multiple fields.
```javascript
// lets only validate username to start
$('.add.example .ui.form')
  .form({
    username: ['empty', 'minLength[5]']
  })
;
```
```javascript
// lets toggle some validation based on button
$('.add.example .ui.positive.button')
  .on('click', function() {
    $('.add.example .ui.form')
      // adding longform
      .form('add rule', 'gender', {
        rules: [
          {
            type   : 'empty',
            prompt : 'Entering your gender is necessary'
          }
        ]
      })
      // adding shorthand
      .form('add rule', 'password', ['empty', 'minLength[5]'])
    ;
  })
;
```
```javascript
$('.add.example .ui.negative.button')
  .on('click', function() {
    $('.add.example .ui.form')
      // removing multiple at once
      .form('remove fields', ['gender', 'password'])
    ;
  })
;
```
```html
<div class="ui positive button">Add Additional Validation</div>
<div class="ui negative button">Remove Additional Validation</div>
<form class="ui form segment">
  <div class="two fields">
    <div class="field">
      <label>Username</label>
      <input type="text" name="username">
    </div>
    <div class="field">
      <label>Password</label>
      <input type="password" name="password">
    </div>
  </div>
  <div class="two fields">
    <div class="field">
      <label>Gender</label>
      <div class="ui fluid selection dropdown">
        <input type="hidden" name="gender">
        <div class="default text">Gender</div>
        <i class="dropdown icon"></i>
        <div class="menu">
          <div class="item" data-value="1">Male</div>
          <div class="item" data-value="0">Female</div>
        </div>
      </div>
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui clear button">Clear</div>
  <div class="ui error message"></div>
</form>
```

#### Validating Dropdowns
[Dropdowns](/modules/dropdown.html) can also be validated like other form fields. Simply match the validation rule to the `input` or `select` associated with the dropdown
```
$('.ui.dropdown')
  .dropdown()
;
$('.ui.form')
  .form({
    fields: {
      gender: 'empty',
      name: 'empty'
    }
  })
;
```
```html
<form class="ui form segment">
  <div class="two fields">
    <div class="field">
      <label>Name</label>
      <input type="text" name="name">
    </div>
    <div class="field">
      <label>Gender</label>
      <div class="ui fluid selection dropdown">
        <input type="hidden" name="gender">
        <div class="default text">Gender</div>
        <i class="dropdown icon"></i>
        <div class="menu">
          <div class="item" data-value="1">Male</div>
          <div class="item" data-value="0">Female</div>
        </div>
      </div>
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
</form>
```

#### Using Server Name Attributes
Sometimes an integration requires you to use a specific value for `name`, or `id`. In these cases, you can match a form field using the `data-validate` property.
```
$('.ui.form')
  .form(
    fields: {
      name: 'empty'
    }
  })
;
```
```html
<form class="ui form segment">
  <div class="field">
    <label>Name</label>
    <input type="text" name="SERVER_REQUIRED_NAME" data-validate="name">
  </div>
  <div class="ui primary submit button">Submit</div>
</form>
```

#### Dependent Fields
You can specify validation fields to only be used when other fields are present. Simply add `depends: 'id'` with the ID of the field that must be non-blank for this rule to evaluate.
```
$('.ui.form')
  .form({
    fields: {
      yearsPracticed: {
        identifier : 'yearsPracticed',
        depends    : 'isDoctor',
        rules      : [
          {
            type   : 'empty',
            prompt : 'Please enter the number of years you have been a doctor'
          }
        ]
      }
    }
  })
;
```
```html
<form class="ui form segment">
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" name="isDoctor" />
      <label>Are you a doctor?</label>
    </div>
  </div>
  <div class="field">
    <label>How long have you been a medical professional</label>
    <input type="text" name="yearsPracticed">
  </div>
  <div class="ui divider"></div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```

#### Optional Fields
Adding the parameter `optional: true` will only add your validation rules when the field is **not empty**.
```
$('.ui.form')
  .form({
    fields: {
      email: {
        identifier : 'email',
        rules: [
          {
            type   : 'email',
            prompt : 'Please enter a valid e-mail'
          }
        ]
      },
      ccEmail: {
        identifier : 'cc-email',
        optional   : true,
        rules: [
          {
            type   : 'email',
            prompt : 'Please enter a valid second e-mail'
          }
        ]
      }
    }
  })
;
```
```html
<form class="ui form segment">
  <p>Your tickets are all ready to print. Where would you like to send a receipt?</p>
  <div class="fields">
    <div class="ten wide field">
      <label>E-mail</label>
      <input type="text" name="email">
    </div>
    <div class="six wide field">
      <label>Additional E-mail</label>
      <input type="text" name="cc-email">
    </div>
  </div>
  <div class="ui divider"></div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```

#### Setting Site Defaults
You can specify site wide validation settings by modifying `$.fn.form.settings.defaults` that will apply on any form validation if the field appears in the form**.
```javascript
$.fn.form.settings.defaults = {
  email: {
    identifier : 'email',
    rules: [
      {
        type   : 'email',
        prompt : 'Please enter a valid e-mail'
      }
    ]
  },
  // this form doesn't have a cc email but it will not produce an error
  ccEmail: {
    identifier : 'cc-email',
    optional   : true,
    rules: [
      {
        type   : 'email',
        prompt : 'Please enter a valid second e-mail'
      }
    ]
  },
};
```
```html
<form class="ui form segment">
  <p>Your tickets are all ready to print. Where would you like to send a receipt?</p>
  <div class="ten wide field">
    <label>E-mail</label>
    <input type="text" name="email">
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```

#### Displaying Error Messages
Forms that contain a [ui message](/collections/message.html) error block will automatically be filled in with form validation information.
> The template for error messages can be modified by adjusting settings.template.error
```html
<form class="ui form segment">
  <p>Let's go ahead and get you signed up.</p>
  <div class="two fields">
    <div class="field">
      <label>First Name</label>
      <input placeholder="First Name" name="first-name" type="text">
    </div>
    <div class="field">
      <label>Last Name</label>
      <input placeholder="Last Name" name="last-name" type="text">
    </div>
  </div>
  <div class="field">
    <label>Username</label>
    <input placeholder="Username" name="username" type="text">
  </div>
  <div class="field">
    <label>Password</label>
    <input type="password" name="password">
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" name="terms" />
      <label>I agree to the Terms and Conditions</label>
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```

#### Validating on Blur and other Events
Validation messages can also appear inline. UI Forms automatically format [labels](/elements/label.html) with the class name `prompt`. These validation prompts are also set to appear on input change instead of form submission.
> This example also uses a different validation event. Each element will be validated on input blur instead of the default form submit.
```javascript
$('.ui.form')
  .form({
    fields : validationRules,
    inline : true,
    on     : 'blur'
  })
;
```
```html
<form class="ui form segment">
  <p>Let's go ahead and get you signed up.</p>
  <div class="two fields">
    <div class="field">
      <label>First Name</label>
      <input placeholder="First Name" name="first-name" type="text">
    </div>
    <div class="field">
      <label>Last Name</label>
      <input placeholder="Last Name" name="last-name" type="text">
    </div>
  </div>
  <div class="field">
    <label>Username</label>
    <input placeholder="Username" name="username" type="text">
  </div>
  <div class="field">
    <label>Password</label>
    <input type="password" name="password">
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" name="terms" />
      <label>I agree to the Terms and Conditions</label>
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
</form>
```

#### Creating Custom Validation
You can use multiple arbitrary rules to validate a form
```
$('.ui.form')
  .form({
    fields: {
      dog: {
        identifier: 'dog',
        rules: [
          {
            type: 'empty',
            prompt: 'You must have a dog to add'
          },
          {
            type: 'contains[fluffy]',
            prompt: 'I only want you to add fluffy dogs!'
          },
          {
            type: 'not[mean]',
            prompt: 'Why would you add a mean dog to the list?'
          }
        ]
      }
    }
  })
;
```
```html
<form class="ui form segment">
  <p>Let's go ahead and get you signed up.</p>
  <div class="field">
    <label>Dog</label>
    <input placeholder="Dog" name="dog" type="text">
  </div>
  <div class="ui primary submit button">
    <i class="add icon"></i>
    Add Dog
  </div>
  <div class="ui error message"></div>
</form>
```

## Behaviors

All the following behaviors can be called using the syntax

```javascript
$('.foo').form('behavior name', argumentOne, argumentTwo)
```

```html
<table class="ui definition celled table">
  <tr>
    <td>submit</td>
    <td>Submits selected form</td>
  </tr>
  <tr>
    <td>is valid</td>
    <td>Returns true/false whether a form passes its validation rules</td>
  </tr>
  <tr>
    <td>add rule(field, rules)<div class="ui label">New in 2.2.11</div></td>
    <td>Adds rule to existing rules for field, also aliased as `add field`</td>
  </tr>
  <tr>
    <td>add fields(fields) <div class="ui label">New in 2.2.11</div></td>
    <td>Adds fields object to existing fields</td>
  </tr>
  <tr>
    <td>remove rule(field, rules)<div class="ui label">New in 2.2.11</div></td>
    <td>Removes specific rule from field leaving other rules</td>
  </tr>
  <tr>
    <td>remove field(field)<div class="ui label">New in 2.2.11</div></td>
    <td>Remove all validation for a field</td>
  </tr>
  <tr>
    <td>add prompt(identifier, errors)</td>
    <td>Adds error prompt to the field with the given identifier</td>
  </tr>
  <tr>
    <td>is valid(fieldName)</td>
    <td>Returns true/false whether a field passes its validation rules</td>
  </tr>
  <tr>
    <td>validate form</td>
    <td>Validates form, updates UI, and calls onSuccess or onFailure</td>
  </tr>
  <tr>
    <td>validate field(fieldName)</td>
    <td>Validates field, updates UI, and calls onSuccess or onFailure</td>
  </tr>
  <tr>
    <td>get field(id)</td>
    <td>Returns element with matching name, id, or data-validate metadata to ID</td>
  </tr>
  <tr>
    <td>get value(id)</td>
    <td>Returns value of element with id</td>
  </tr>
  <tr>
    <td>get values(ids)</td>
    <td>Returns object of element values that match array of ids. If no IDS are passed will return all fields</td>
  </tr>
  <tr>
    <td>set value(id)</td>
    <td>Sets value of element with id</td>
  </tr>
  <tr>
    <td>set values(values)</td>
    <td>Sets key/value pairs from passed values object to matching ids</td>
  </tr>
  <tr>
    <td>get validation(element)</td>
    <td>Returns validation rules for a given jQuery-referenced input field</td>
  </tr>
  <tr>
    <td>has field(identifier)</td>
    <td>Returns whether a field exists</td>
  </tr>
  <tr>
    <td>add errors(errors)</td>
    <td>Adds errors to form, given an array errors</td>
  </tr>
  <tr>
    <td>add prompt(id, prompt)</td>
    <td>Adds a custom user prompt for a given element with id</td>
  </tr>
</table>
```

## Settings

#### Form Settings
Form settings modify the form validation behavior

```html
<table class="ui celled sortable definition table">
  <thead>
    <th>Setting</th>
    <th class="six wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>keyboardShortcuts</td>
      <td>true</td>
      <td>Adds keyboard shortcuts for enter and escape keys to submit form and blur fields respectively</td>
    </tr>
    <tr>
      <td>on</td>
      <td>submit</td>
      <td>Event used to trigger validation. Can be either **submit**, **blur** or **change**.</td>
    </tr>
    <tr>
      <td>revalidate</td>
      <td>true</td>
      <td>If set to true will revalidate fields with errors on input change</td>
    </tr>
    <tr>
      <td>delay</td>
      <td>true</td>
      <td>Delay from last typed letter to validate a field when using `on: change` or when revalidating a field.</td>
    </tr>
    <tr>
      <td>inline</td>
      <td>false</td>
      <td>Adds inline error on field validation error</td>
    </tr>
    <tr>
      <td>transition</td>
      <td>
        scale
      </td>
      <td>Named transition to use when animating validation errors. Fade and slide down are available without including [ui transitions](/modules/transition.html)</td>
    </tr>
    <tr>
      <td>duration</td>
      <td>150</td>
      <td>Animation speed for inline prompt</td>
    </tr>
  </tbody>
</table>
```

#### Form Prompts
Settings to modify default form prompts

```html
<table class="ui celled sortable definition table">
  <thead>
    <th class="collapsing">Setting</th>
    <th>Default</th>
  </thead>
  <tbody>
    <tr>
      <td>text</td>
      <td>
        <div class="code">
text: {
  unspecifiedRule  : 'Please enter a valid value',
  unspecifiedField : 'This field'
}
        </div>
      </td>
    </tr>
    <tr>
      <td>prompt</td>
      <td>
        <div class="code">
prompt: {
  empty                : '{name} must have a value',
  checked              : '{name} must be checked',
  email                : '{name} must be a valid e-mail',
  url                  : '{name} must be a valid url',
  regExp               : '{name} is not formatted correctly',
  integer              : '{name} must be an integer',
  decimal              : '{name} must be a decimal number',
  number               : '{name} must be a number',
  is                   : '{name} must be '\'{ruleValue}\'',
  isExactly            : '{name} must be exactly '\'{ruleValue}\'',
  not                  : '{name} cannot be set to '\'{ruleValue}\'',
  notExactly           : '{name} cannot be set to exactly '\'{ruleValue}\'',
  contain              : '{name} cannot contain '\'{ruleValue}\'',
  containExactly       : '{name} cannot contain exactly '\'{ruleValue}\'',
  doesntContain        : '{name} must contain  '\'{ruleValue}\'',
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```