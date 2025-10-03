# Breadcrumb

A breadcrumb is used to show hierarchy between content

## Types

#### Breadcrumb
A standard breadcrumb
```html
<div class="ui breadcrumb">
  <a class="section">Home</a>
  <div class="divider"> / </div>
  <a class="section">Store</a>
  <div class="divider"> / </div>
  <div class="active section">T-Shirt</div>
</div>
```
```html
<div class="ui breadcrumb">
  <a class="section">Home</a>
  <i class="right angle icon divider"></i>
  <a class="section">Store</a>
  <i class="right angle icon divider"></i>
  <div class="active section">T-Shirt</div>
</div>
```

## Content

#### Divider
A breadcrumb can contain a divider to show the relationship between sections, this can be formatted as an icon or text.
```html
<div class="ui breadcrumb">
  <a class="section">Home</a>
  <span class="divider">/</span>
  <a class="section">Registration</a>
  <span class="divider">/</span>
  <div class="active section">Personal Information</div>
</div>
```
```html
<div class="ui breadcrumb">
  <a class="section">Home</a>
  <i class="right chevron icon divider"></i>
  <a class="section">Registration</a>
  <i class="right arrow icon divider"></i>
  <div class="active section">Personal Information</div>
</div>
```

#### Section
A breadcrumb can contain sections that can either be formatted as a link or text
```html
<div class="ui breadcrumb">
  <div class="section">Home</div>
  <div class="divider"> / </div>
  <div class="active section">Search</div>
</div>
```

#### Link
A section may be linkable or contain a link
```html
<div class="ui breadcrumb">
  <a class="section">Home</a>
  <div class="divider"> / </div>
  <div class="active section">Search for: <a href="#">paper towels</a></div>
</div>
```

## States

#### Active
A section can be active
```html
<div class="ui breadcrumb">
  <a class="section">Products</a>
  <div class="divider"> / </div>
  <div class="active section">Paper Towels</div>
</div>
```

## Variations

#### Size
A breadcrumb can vary in size
```html
<div class="ui mini breadcrumb">
  <a class="section">Home</a>
  <i class="right chevron icon divider"></i>
  <a class="section">Registration</a>
  <i class="right chevron icon divider"></i>
  <div class="active section">Personal Information</div>
</div>
```
```html
<div class="ui tiny breadcrumb">
  <a class="section">Home</a>
  <i class="right chevron icon divider"></i>
  <a class="section">Registration</a>
  <i class="right chevron icon divider"></i>
  <div class="active section">Personal Information</div>
</div>
```
```html
<div class="ui small breadcrumb">
  <a class="section">Home</a>
  <i class="right chevron icon divider"></i>
  <a class="section">Registration</a>
  <i class="right chevron icon divider"></i>
  <div class="active section">Personal Information</div>
</div>
```
```html
<div class="ui large breadcrumb">
  <a class="section">Home</a>
  <i class="right chevron icon divider"></i>
  <a class="section">Registration</a>
  <i class="right chevron icon divider"></i>
  <div class="active section">Personal Information</div>
</div>
```
```html
<div class="ui big breadcrumb">
  <a class="section">Home</a>
  <i class="right chevron icon divider"></i>
  <a class="section">Registration</a>
  <i class="right chevron icon divider"></i>
  <div class="active section">Personal Information</div>
</div>
```
```html
<div class="ui huge breadcrumb">
  <a class="section">Home</a>
  <i class="right chevron icon divider"></i>
  <a class="section">Registration</a>
  <i class="right chevron icon divider"></i>
  <div class="active section">Personal Information</div>
</div>
```
```html
<div class="ui massive breadcrumb">
  <a class="section">Home</a>
  <i class="right chevron icon divider"></i>
  <a class="section">Registration</a>
  <i class="right chevron icon divider"></i>
  <div class="active section">Personal Information</div>
</div>
```
