# Loader

A loader alerts a user to wait for an activity to complete

## Types

#### Loader
A loader
> Loaders are hidden unless `active` or inside an `active dimmer`.
```html
<div class="ui segment">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <div class="ui active dimmer">
    <div class="ui loader"></div>
  </div>
</div>
```

#### Text Loader
A loader can contain text
```html
<div class="ui segment">
  <div class="ui active dimmer">
    <div class="ui text loader">Loading</div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ui segment">
  <div class="ui active inverted dimmer">
    <div class="ui text loader">Loading</div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```

## States

#### Indeterminate
A loader can show it's unsure of how long a task will take
```html
<div class="ui segment">
  <div class="ui active dimmer">
    <div class="ui indeterminate text loader">Preparing Files</div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```

#### Active
A loader can be active or visible
> An active loader may not be clearly visible without using a `ui dimmer`
```html
<div class="ui segment">
  <div class="ui active loader"></div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```

#### Disabled
A loader can be disabled or hidden
```html
<div class="ui segment">
  <div class="ui disabled loader"></div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```

## Variations

#### Inline
Loaders can appear inline with content
```html
<div class="ui active inline loader"></div>
```

#### Inline Center
Loaders can appear inline centered with content
```html
<div class="ui active centered inline loader"></div>
```

#### Size
Loaders can have different sizes
```html
<div class="ui segment">
  <div class="ui active dimmer">
    <div class="ui mini text loader">Loading</div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ui segment">
  <div class="ui active dimmer">
    <div class="ui tiny text loader">Loading</div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ui segment">
  <div class="ui active dimmer">
    <div class="ui small text loader">Loading</div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ui segment">
  <div class="ui active dimmer">
    <div class="ui medium text loader">Loading</div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ui segment">
  <div class="ui active dimmer">
    <div class="ui large text loader">Loading</div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ui segment">
  <div class="ui active dimmer">
    <div class="ui big text loader">Loading</div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ui segment">
  <div class="ui active dimmer">
    <div class="ui huge text loader">Loading</div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ui segment">
  <div class="ui active dimmer">
    <div class="ui massive text loader">Loading</div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```

#### Inverted
Loaders can have their colors inverted.
```html
<div class="ui inverted segment">
  <div class="ui active inverted loader"></div>
  <br>
  <br>
  <br>
  <br>
</div>
```
> Loaders will automatically be inverted inside `inverted dimmer`
```html
<div class="ui segment">
  <div class="ui active inverted dimmer">
    <div class="ui mini text loader">Loading</div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ui segment">
  <div class="ui active inverted dimmer">
    <div class="ui small text loader">Loading</div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ui segment">
  <div class="ui active inverted dimmer">
    <div class="ui medium text loader">Loading</div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ui segment">
  <div class="ui active inverted dimmer">
    <div class="ui large text loader">Loading</div>
  </div>
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
```
