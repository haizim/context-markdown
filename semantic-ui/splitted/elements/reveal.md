# Reveal

A reveal displays additional content in place of previous content when activated

## Types

#### Fade
An element can disappear to reveal content below
```html
<div class="ui fade reveal">
  <div class="visible content">
    <img src="/images/wireframe/square-image.png" class="ui small image">
  </div>
  <div class="hidden content">
    <img src="/images/avatar/large/ade.jpg" class="ui small image">
  </div>
</div>
```
```html
<div class="ui small fade reveal image">
  <img class="visible content" src="/images/wireframe/square-image.png">
  <img class="hidden content" src="/images/avatar/large/ade.jpg">
</div>
```

#### Move
An element can move in a direction to reveal content
```html
<div class="ui move reveal">
  <div class="visible content">
    <img src="/images/wireframe/square-image.png" class="ui small image">
  </div>
  <div class="hidden content">
    <img src="/images/avatar/large/chris.jpg" class="ui small image">
  </div>
</div>
```
```html
<div class="ui move right reveal">
  <div class="visible content">
    <img src="/images/wireframe/square-image.png" class="ui small image">
  </div>
  <div class="hidden content">
    <img src="/images/avatar/large/jenny.jpg" class="ui small image">
  </div>
</div>
```
```html
<div class="ui move up reveal">
  <div class="visible content">
    <img src="/images/wireframe/square-image.png" class="ui small image">
  </div>
  <div class="hidden content">
    <img src="/images/avatar/large/justen.jpg" class="ui small image">
  </div>
</div>
```
```html
<div class="ui move down reveal">
  <div class="visible content">
    <img src="/images/wireframe/square-image.png" class="ui small image">
  </div>
  <div class="hidden content">
    <img src="/images/avatar/large/nan.jpg" class="ui small image">
  </div>
</div>
```

#### Rotate
An element can rotate to reveal content below
```html
<div class="ui small circular rotate reveal image">
  <img src="/images/wireframe/square-image.png" class="visible content">
  <img src="/images/avatar/large/stevie.jpg" class="hidden content">
</div>
```
```html
<div class="ui small circular rotate left reveal image">
  <img src="/images/wireframe/square-image.png" class="visible content">
  <img src="/images/avatar/large/veronika.jpg" class="hidden content">
</div>
```

## Content

#### Visible Content
A reveal may contain content that is visible before interaction
> Visible and hidden content should be the same aspect ratio
```html
<div class="ui small fade reveal image">
  <img class="visible content" src="/images/avatar/large/ade.jpg">
  <img class="hidden content" src="/images/wireframe/square-image.png">
</div>
```

#### Hidden Content
A reveal may contain content that is hidden before user interaction
```html
<div class="ui small fade reveal image">
  <img class="visible content" src="/images/wireframe/square-image.png">
  <img class="hidden content" src="/images/avatar/large/ade.jpg">
</div>
```

## States

#### Active
An active reveal displays its hidden content
> Adding the class `active` can allow you to show the hidden contents programatically
```html
<div class="ui active move left reveal">
  <div class="visible content">
    <img src="/images/wireframe/square-image.png" class="ui small image">
  </div>
  <div class="hidden content">
    <img src="/images/avatar/large/nan.jpg" class="ui small image">
  </div>
</div>
```

## Variations

#### Instant
An element can show its content without delay
```html
<div class="ui instant move reveal">
  <div class="visible content">
    <img src="/images/wireframe/square-image.png" class="ui small image">
  </div>
  <div class="hidden content">
    <img src="/images/avatar/large/chris.jpg" class="ui small image">
  </div>
</div>
```

## States

#### Disabled
A disabled reveal will not animate when hovered
```html
<div class="ui disabled move reveal">
  <div class="visible content">
    <img src="/images/wireframe/square-image.png" class="ui small image">
  </div>
  <div class="hidden content">
    <img src="/images/avatar/large/chris.jpg" class="ui small image">
  </div>
</div>
```
