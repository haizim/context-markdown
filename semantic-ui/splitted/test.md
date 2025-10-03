# Layout Page

This page can be used to help make adjustments to the global docs layout partials

## Types

#### Page Headers
Headers may be oriented to give the hierarchy of a section in the context of the page
> Page headings are sized using `rem` and are not affected by surrounding content size.
```html
<h1 class="ui header">First header</h1>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
<h2 class="ui header">Second header</h2>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
<h3 class="ui header">Third header</h3>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
<h4 class="ui header">Fourth header</h4>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
<h5 class="ui header">Fifth header</h5>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
```

#### Ordinality
A button can be formatted to show different levels of emphasis
> Setting your brand colors to primary and secondary color variables in `site.variables` will allow you to use your color theming for UI elements
```html
<button class="ui primary button">
  Save
</button>
<button class="ui button">
  Discard
</button>
```
```html
<button class="ui secondary button">
  Okay
</button>
<button class="ui button">
  Cancel
</button>
```

#### Animated
A button can animate to show hidden content
> The button will be automatically sized according to the visible content size. Make sure there is enough room for the hidden content to show
```html
<div class="ui animated button" tabindex="0">
  <div class="visible content">Next</div>
  <div class="hidden content">
    <i class="right arrow icon"></i>
  </div>
</div>
<div class="ui vertical animated button" tabindex="0">
  <div class="hidden content">Shop</div>
  <div class="visible content">
    <i class="shop icon"></i>
  </div>
</div>
<div class="ui animated fade button" tabindex="0">
  <div class="visible content">Sign-up for a Pro account</div>
  <div class="hidden content">
    $12.99 a month
  </div>
</div>
```

#### Icon
A button can have only an icon
```html
<button class="ui icon button">
  <i class="cloud icon"></i>
</button>
```

#### Labeled Icon
A button can have an icon and a label
```html
<button class="ui labeled icon button">
  <i class="pause icon"></i>
  Pause
</button>
<button class="ui right labeled icon button">
  <i class="right arrow icon"></i>
  Next
</button>
```

#### Basic
A basic button is less pronounced
```html
<button class="ui basic button">
  <i class="icon user"></i>
  Add Friend
</button>
```
```html
<button class="ui red basic button">Red</button>
<button class="ui orange basic button">Orange</button>
<button class="ui yellow basic button">Yellow</button>
<button class="ui olive basic button">Olive</button>
<button class="ui green basic button">Green</button>
<button class="ui teal basic button">Teal</button>
<button class="ui blue basic button">Blue</button>
<button class="ui violet basic button">Violet</button>
<button class="ui purple basic button">Purple</button>
<button class="ui pink basic button">Pink</button>
<button class="ui brown basic button">Brown</button>
<button class="ui grey basic button">Grey</button>
<button class="ui black basic button">Black</button>
```
