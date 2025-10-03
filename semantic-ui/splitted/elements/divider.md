# Divider

A divider visually segments content into groups

## Types

#### Divider
A standard divider
> To add a divider between parts of a grid use a `divided grid` variation.
```html
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
<div class="ui divider"></div>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
```

#### Vertical Divider
A divider can segment content vertically
> Vertical dividers requires `position: relative` on the element that you would like to contain the divider
> Due to a change in W3C implementation of absolutely positioned elements in flex containers vertical dividers now currently only support 50/50 splits automatically, and only if not positioned <b>as direct children of flex containers</b> (like grid).
```html
<div class="ui segment">
  <div class="ui two column very relaxed grid">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
      <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
      <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
      <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
      <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
      <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
      <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
    </div>
  </div>
  <div class="ui vertical divider">
    and
  </div>
</div>
```
> A vertical divider will automatically swap to a horizontal divider at mobile resolutions when used inside a `stackable grid`
```html
<div class="ui placeholder segment">
  <div class="ui two column very relaxed stackable grid">
    <div class="column">
      <div class="ui form">
        <div class="field">
          <label>Username</label>
          <div class="ui left icon input">
            <input type="text" placeholder="Username">
            <i class="user icon"></i>
          </div>
        </div>
        <div class="field">
          <label>Password</label>
          <div class="ui left icon input">
            <input type="password">
            <i class="lock icon"></i>
          </div>
        </div>
        <div class="ui blue submit button">Login</div>
      </div>
    </div>
    <div class="middle aligned column">
      <div class="ui big button">
        <i class="signup icon"></i>
        Sign Up
      </div>
    </div>
  </div>
  <div class="ui vertical divider">
    Or
  </div>
</div>
```

#### Horizontal Divider
A divider can segment content horizontally
> Horizontal dividers can also be used in combination with headers and icons to create different styles of dividers.
> Dividers will automatically vary the size of their dividing rules to match the length of your text
```html
<div class="ui center aligned basic segment">
  <div class="ui left icon action input">
    <i class="search icon"></i>
    <input type="text" placeholder="Order #">
    <div class="ui blue submit button">Search</div>
  </div>
  <div class="ui horizontal divider">
    Or
  </div>
  <div class="ui teal labeled icon button">
    Create New Order
    <i class="add icon"></i>
  </div>
</div>
```
```html
<h4 class="ui horizontal divider header">
  <i class="tag icon"></i>
  Description
</h4>
<p>Doggie treats are good for all times of the year. Proven to be eaten by 99.9% of all dogs worldwide.</p>
<h4 class="ui horizontal divider header">
  <i class="bar chart icon"></i>
  Specifications
</h4>
<table class="ui definition table">
  <tbody>
    <tr>
      <td class="two wide column">Size</td>
      <td>1" x 2"</td>
    </tr>
    <tr>
      <td>Weight</td>
      <td>6 ounces</td>
    </tr>
    <tr>
      <td>Color</td>
      <td>Yellowish</td>
    </tr>
    <tr>
      <td>Odor</td>
      <td>Not Much Usually</td>
    </tr>
  </tbody>
</table>
```

## Variations

#### Inverted
A divider can have its colors inverted
```html
<div class="ui inverted segment">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <div class="ui inverted divider"></div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <h4 class="ui horizontal inverted divider">
    Horizontal
  </h4>
</div>
```

#### Fitted
A divider can be fitted, without any space above or below it.
```html
<div class="ui segment">
  Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Donec odio. Quisque volutpat mattis eros. Nullam malesuada erat ut turpis. Suspendisse urna nibh, viverra non, semper suscipit, posuere a, pede.
  <div class="ui fitted divider"></div>
  Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Donec odio. Quisque volutpat mattis eros. Nullam malesuada erat ut turpis. Suspendisse urna nibh, viverra non, semper suscipit, posuere a, pede.
</div>
```

#### Hidden
A hidden divider divides content without creating a dividing line
```html
<h3 class="ui header">Section One</h3>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
<div class="ui hidden divider"></div>
<h3 class="ui header">Section Two</h3>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
```

#### Section
A divider can provide greater margins to divide sections of content
```html
<h3 class="ui header">Section One</h3>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
<div class="ui section divider"></div>
<h3 class="ui header">Section Two</h3>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
```

#### Clearing
A divider can clear the contents above it
```html
<div class="ui segment">
  <h2 class="ui right floated header">Floated Content</h2>
  <div class="ui clearing divider"></div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
