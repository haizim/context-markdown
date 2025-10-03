# Message

A message displays information that explains nearby content

## Types

#### Message
A basic message
```html
<div class="ui message">
  <div class="header">
    Changes in Service
  </div>
  <p>We just updated our privacy policy here to better service our customers. We recommend reviewing the changes.</p>
</div>
```

#### List Message
A message with a list
```html
<div class="ui message">
  <div class="header">
    New Site Features
  </div>
  <ul class="list">
    <li>You can now have cover images on blog pages</li>
    <li>Drafts will now auto-save while writing</li>
  </ul>
</div>
```

#### Icon Message
A message can contain an icon.
```html
<div class="ui icon message">
  <i class="inbox icon"></i>
  <div class="content">
    <div class="header">
      Have you heard about our mailing list?
    </div>
    <p>Get the best news in your e-mail every day.</p>
  </div>
</div>
```
```html
<div class="ui icon message">
  <i class="notched circle loading icon"></i>
  <div class="content">
    <div class="header">
      Just one second
    </div>
    <p>We're fetching that content for you.</p>
  </div>
</div>
```

#### Dismissable Block
A message that the user can choose to hide
```html
<div class="ui message">
  <i class="close icon"></i>
  <div class="header">
    Welcome back!
  </div>
  <p>This is a special notification which you can dismiss if you're bored with it.</p>
</div>
```
> Dismissable blocks do not automatically close when using the close icon, this behavior must be defined using Javascript, for example:
> ```javascript
> $('.message .close')
>   .on('click', function() {
>     $(this)
>       .closest('.message')
>       .transition('fade')
>     ;
>   })
> ;
> ```

## States

#### Hidden
A message can be hidden
```html
<div class="ui hidden message">
  <p>You can't see me</p>
</div>
```

#### Visible
A message can be set to visible to force itself to be shown.
```html
<div class="ui visible message">
  <p>You can always see me</p>
</div>
```

## Variations

#### Floating
A message can float above content that it is related to
```html
<div class="ui floating message">
  <p>Way to go!</p>
</div>
```

#### Compact
A message can only take up the width of its content.
```html
<div class="ui compact message">
  <p>Get all the best inventions in your e-mail every day. Sign up now!</p>
</div>
```

#### Attached
A message can be formatted to attach itself to other content
```html
<div class="ui attached message">
  <div class="header">
    Welcome to our site!
  </div>
  <p>Fill out the form below to sign-up for a new account</p>
</div>
<form class="ui form attached fluid segment">
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
  <div class="field">
    <label>Username</label>
    <input placeholder="Username" type="text">
  </div>
  <div class="field">
    <label>Password</label>
    <input type="password">
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" id="terms" />
      <label for="terms">I agree to the terms and conditions</label>
    </div>
  </div>
  <div class="ui blue submit button">Submit</div>
</form>
<div class="ui bottom attached warning message">
  <i class="icon help"></i>
  Already signed up? <a href="#">Login here</a> instead.
</div>
```

#### Warning
A message may be formatted to display warning messages.
```html
<div class="ui warning message">
  <i class="close icon"></i>
  <div class="header">
    You must register before you can do that!
  </div>
  Visit our registration page, then try again
</div>
```

#### Info
A message may be formatted to display information.
```html
<div class="ui info message">
  <i class="close icon"></i>
  <div class="header">
    Was this what you wanted?
  </div>
  <ul class="list">
    <li>It's good to see you again.</li>
    <li>Did you know it's been a while?</li>
  </ul>
</div>
```

#### Positive / Success
A message may be formatted to display a positive message.
> Positive/Success and Negative/Error messages by default use similar colors, but each has their own color  variables that can be distinguished in your theme.
```html
<div class="ui positive message">
  <i class="close icon"></i>
  <div class="header">
    You are eligible for a reward
  </div>
  <p>Go to your <b>special offers</b> page to see now.</p>
</div>
```
```html
<div class="ui success message">
  <i class="close icon"></i>
  <div class="header">
    Your user registration was successful.
  </div>
  <p>You may now log-in with the username you have chosen</p>
</div>
```

#### Negative / Error
A message may be formatted to display a negative message.
```html
<div class="ui negative message">
  <i class="close icon"></i>
  <div class="header">
    We're sorry we can't apply that discount
  </div>
  <p>That offer has expired
</div>
```
```html
<div class="ui error message">
  <i class="close icon"></i>
  <div class="header">
    There were some errors with your submission
  </div>
  <ul class="list">
    <li>You must include both a upper and lower case letters in your password.</li>
    <li>You need to select your home country.</li>
  </ul>
</div>
```

#### Colored
A message can be formatted to be different colors
```html
<div class="ui red message">Red</div>
<div class="ui orange message">Orange</div>
<div class="ui yellow message">Yellow</div>
<div class="ui olive message">Olive</div>
<div class="ui green message">Green</div>
<div class="ui teal message">Teal</div>
<div class="ui blue message">Blue</div>
<div class="ui violet message">Violet</div>
<div class="ui purple message">Purple</div>
<div class="ui pink message">Pink</div>
<div class="ui brown message">Brown</div>
<div class="ui black message">Black</div>
```

#### Size
A message can have different sizes
```html
<div class="ui mini message">
  This is a mini message.
</div>
<div class="ui tiny message">
  This is a tiny message.
</div>
<div class="ui small message">
  This is a small message.
</div>
<div class="ui large message">
  This is large
</div>
<div class="ui big message">
  This is big
</div>
<div class="ui huge message">
  This is huge
</div>
<div class="ui massive message">
  This is massive
</div>
```
