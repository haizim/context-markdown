# Step

A step shows the completion status of an activity in a series of activities

## Types

#### Step
A single step
```html
<div class="ui steps">
  <div class="step">
    Shipping
  </div>
</div>
```

## Groups

#### Steps
A set of steps
> Steps will automatically stack on mobile. To make steps automatically stack for tablet use the `tablet stackable` variation.
```html
<div class="ui steps">
  <div class="step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
      <div class="description">Choose your shipping options</div>
    </div>
  </div>
  <div class="active step">
    <i class="payment icon"></i>
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </div>
  <div class="disabled step">
    <i class="info icon"></i>
    <div class="content">
      <div class="title">Confirm Order</div>
    </div>
  </div>
</div>
```

#### Ordered
A step can show a ordered sequence of steps
```html
<div class="ui ordered steps">
  <div class="completed step">
    <div class="content">
      <div class="title">Shipping</div>
      <div class="description">Choose your shipping options</div>
    </div>
  </div>
  <div class="completed step">
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </div>
  <div class="active step">
    <div class="content">
      <div class="title">Confirm Order</div>
      <div class="description">Verify order details</div>
    </div>
  </div>
</div>
```

#### Vertical
A step can be displayed stacked vertically
```html
<div class="ui vertical steps">
  <div class="completed step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
      <div class="description">Choose your shipping options</div>
    </div>
  </div>
  <div class="completed step">
    <i class="credit card icon"></i>
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </div>
  <div class="active step">
    <i class="info icon"></i>
    <div class="content">
      <div class="title">Confirm Order</div>
      <div class="description">Verify order details</div>
    </div>
  </div>
</div>
```

## Content

#### Description
A step can contain a description
```html
<div class="ui steps">
  <div class="step">
    <div class="title">Shipping</div>
    <div class="description">Choose your shipping options</div>
  </div>
</div>
```

#### Icon
A step can contain an icon
```html
<div class="ui steps">
  <div class="step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
      <div class="description">Choose your shipping options</div>
    </div>
  </div>
</div>
```

#### Link
A step can link
```html
<div class="ui steps">
  <a class="active step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
      <div class="description">Choose your shipping options</div>
    </div>
  </a>
  <a class="step">
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </a>
</div>
```
```html
<div class="ui steps">
  <div class="link step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
      <div class="description">Choose your shipping options</div>
    </div>
  </div>
  <div class="link step">
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </div>
</div>
```

## States

#### Active
A step can be highlighted as active
```html
<div class="ui steps">
  <div class="active step">
    <i class="payment icon"></i>
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </div>
</div>
```

#### Completed
A step can show that a user has completed it
```html
<div class="ui steps">
  <div class="completed step">
    <i class="payment icon"></i>
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </div>
</div>
```
```html
<div class="ui ordered steps">
  <div class="completed step">
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </div>
</div>
```

#### Disabled
A step can show that it cannot be selected
```html
<div class="ui steps">
  <div class="disabled step">
    Billing
  </div>
</div>
```

## Variations

#### Stackable
A step can stack vertically only on smaller screens
```html
<div class="ui tablet stackable steps">
  <div class="step">
    <i class="plane icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
      <div class="description">Choose your shipping options</div>
    </div>
  </div>
  <div class="active step">
    <i class="dollar icon"></i>
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </div>
  <div class="disabled step">
    <i class="info circle icon"></i>
    <div class="content">
      <div class="title">Confirm Order</div>
      <div class="description">Verify order details</div>
    </div>
  </div>
</div>
```

#### Fluid
A fluid step takes up the width of its container
```html
<div class="ui two column grid">
  <div class="column">
    <div class="ui fluid vertical steps">
      <div class="completed step">
        <i class="truck icon"></i>
        <div class="content">
          <div class="title">Shipping</div>
          <div class="description">Choose your shipping options</div>
        </div>
      </div>
      <div class="active step">
        <i class="dollar icon"></i>
        <div class="content">
          <div class="title">Billing</div>
          <div class="description">Enter billing information</div>
        </div>
      </div>
    </div>
  </div>
  <div class="column">
    <p>The steps take up the entire column width</p>
  </div>
</div>
```

#### Unstackable
A step can prevent itself from stacking on mobile
```html
<div class="ui unstackable steps">
  <div class="step">
    <i class="plane icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
      <div class="description">Choose your shipping options</div>
    </div>
  </div>
  <div class="active step">
    <i class="dollar icon"></i>
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </div>
  <div class="disabled step">
    <i class="info circle icon"></i>
    <div class="content">
      <div class="title">Confirm Order</div>
      <div class="description">Verify order details</div>
    </div>
  </div>
</div>
```

#### Attached
Steps can be attached to other elements
```html
<div class="ui three top attached steps">
  <div class="step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
      <div class="description">Choose your shipping options</div>
    </div>
  </div>
  <div class="active step">
    <i class="payment icon"></i>
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </div>
  <div class="disabled step">
    <i class="info icon"></i>
    <div class="content">
      <div class="title">Confirm Order</div>
      <div class="description">Verify order details</div>
    </div>
  </div>
</div>
<div class="ui attached segment">
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
</div>
<div class="ui three bottom attached steps">
  <div class="step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
      <div class="description">Choose your shipping options</div>
    </div>
  </div>
  <div class="active step">
    <i class="payment icon"></i>
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </div>
  <div class="disabled step">
    <i class="info icon"></i>
    <div class="content">
      <div class="title">Confirm Order</div>
      <div class="description">Verify order details</div>
    </div>
  </div>
</div>
```

#### Evenly Divided
Steps can be divided evenly inside their parent
```html
<div class="ui three steps">
  <div class="step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
    </div>
  </div>
  <div class="active step">
    <i class="payment icon"></i>
    <div class="content">
      <div class="title">Billing</div>
    </div>
  </div>
  <div class="disabled step">
    <i class="info icon"></i>
    <div class="content">
      <div class="title">Confirm Order</div>
    </div>
  </div>
</div>
```
```html
<div class="ui two steps">
  <div class="active step">
    <i class="payment icon"></i>
    <div class="content">
      <div class="title">Billing</div>
    </div>
  </div>
  <div class="disabled step">
    <i class="info icon"></i>
    <div class="content">
      <div class="title">Confirm Order</div>
    </div>
  </div>
</div>
```

#### Size
Steps can have different sizes
```html
<div class="ui mini steps">
  <div class="step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
      <div class="description">Choose your shipping options</div>
    </div>
  </div>
  <div class="active step">
    <i class="payment icon"></i>
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </div>
  <div class="disabled step">
    <i class="info icon"></i>
    <div class="content">
      <div class="title">Confirm Order</div>
      <div class="description">Verify order details</div>
    </div>
  </div>
</div>
```
```html
<div class="ui tiny steps">
  <div class="step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
      <div class="description">Choose your shipping options</div>
    </div>
  </div>
  <div class="active step">
    <i class="payment icon"></i>
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </div>
  <div class="disabled step">
    <i class="info icon"></i>
    <div class="content">
      <div class="title">Confirm Order</div>
      <div class="description">Verify order details</div>
    </div>
  </div>
</div>
```
```html
<div class="ui small steps">
  <div class="step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
      <div class="description">Choose your shipping options</div>
    </div>
  </div>
  <div class="active step">
    <i class="payment icon"></i>
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </div>
  <div class="disabled step">
    <i class="info icon"></i>
    <div class="content">
      <div class="title">Confirm Order</div>
      <div class="description">Verify order details</div>
    </div>
  </div>
</div>
```
```html
<div class="ui large steps">
  <div class="step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
    </div>
  </div>
  <div class="active step">
    <i class="payment icon"></i>
    <div class="content">
      <div class="title">Billing</div>
    </div>
  </div>
</div>
```
```html
<div class="ui big steps">
  <div class="step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
    </div>
  </div>
  <div class="active step">
    <i class="payment icon"></i>
    <div class="content">
      <div class="title">Billing</div>
    </div>
  </div>
</div>
```
```html
<div class="ui huge steps">
  <div class="step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
    </div>
  </div>
  <div class="active step">
    <i class="payment icon"></i>
    <div class="content">
      <div class="title">Billing</div>
    </div>
  </div>
</div>
```
```html
<div class="ui massive steps">
  <div class="step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
    </div>
  </div>
  <div class="active step">
    <i class="payment icon"></i>
    <div class="content">
      <div class="title">Billing</div>
    </div>
  </div>
</div>
```
