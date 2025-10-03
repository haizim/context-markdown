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
