# Rail

A rail is used to show accompanying content outside the boundaries of the main view of a site

## Introduction

### When to Use
Rails display optional accompanying content outside of the main viewport of your website. Sites often use rails with sticky content to fix additional—often optional—content to your viewport as you scroll through the page.

Semantic's default rail is `300px` wide, just large enough to fit many common ad unit sizes, and just wide enough for a sub-navigation menu or a prominent call-to-action.

### Adjusting Sizes
Railed content will most likely require arbitrary breakpoints that are specific to your site's content, to ensure they do not exceed the horizontal width of a user's browser.

Rails are generally used beside long, single-column containers with long-form content like blog posts, articles, or user profiles. Generally your main text container width should be set between around `600-800px` depending on your font size to optimize line length for readability.

This set-up means most tablet browsers can only accomodate a single rail. Ultrabooks and lower resolution computers two small rails, and larger monitors, usually two full-sized rails. The specifics of this implementation is left up to you in your project.

> The following examples do not use any breakpoints, so some railed content may appear outside your browser's viewport on smaller screens.

## Types

#### Rail
A rail can be presented on the left or right side of a container

```html
<div class="ui segment">
  <div class="ui left rail">
    <div class="ui segment">
      Left Rail Content
    </div>
  </div>
  <div class="ui right rail">
    <div class="ui segment">
      Right Rail Content
    </div>
  </div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
</div>
```

#### Internal
A rail can attach itself to the inside of a container

```html
<div class="ui segment" style="left: -150px; width: 960px;min-height: 300px;">
  <div class="ui left internal rail">
    <div class="ui segment">
      Left Rail Content
    </div>
  </div>
  <div class="ui right internal rail">
    <div class="ui segment">
      Right Rail Content
    </div>
  </div>
</div>
```

#### Dividing
A rail can create a division between itself and a container
```html
<div class="ui segment">
  <div class="ui left dividing rail">
    <div class="ui segment">
      Left Rail Content
    </div>
  </div>
  <div class="ui right dividing rail">
    <div class="ui segment">
      Right Rail Content
    </div>
  </div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
</div>
```

## Variations

#### Attached
A rail can appear attached to the main viewport
```html
<div class="ui segment">
  <div class="ui left attached rail">
    <div class="ui segment">
      Left Rail Content
    </div>
  </div>
  <div class="ui right attached rail">
    <div class="ui segment">
      Right Rail Content
    </div>
  </div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
</div>
```
```html
<div class="ui segment" style="left: -150px; width: 960px;min-height: 300px;">
  <div class="ui left internal attached rail">
    <div class="ui segment">
      Left Rail Content
    </div>
  </div>
  <div class="ui right internal attached rail">
    <div class="ui segment">
      Right Rail Content
    </div>
  </div>
</div>
```

#### Close
A rail can appear closer to the main viewport
```html
<div class="ui segment">
  <div class="ui left close rail">
    <div class="ui segment">
      Left Rail Content
    </div>
  </div>
  <div class="ui right close rail">
    <div class="ui segment">
      Right Rail Content
    </div>
  </div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
</div>
```
```html
<div class="ui segment">
  <div class="ui left very close rail">
    <div class="ui segment">
      Left Rail Content
    </div>
  </div>
  <div class="ui right very close rail">
    <div class="ui segment">
      Right Rail Content
    </div>
  </div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
</div>
```

#### Size
A rail can have different sizes
```html
<div class="ui segment">
  <div class="ui left mini rail">
    Mini
  </div>
  <div class="ui right tiny rail">
    Tiny
  </div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
</div>
```
```html
<div class="ui segment">
  <div class="ui left small rail">
    Small
  </div>
  <div class="ui right large rail">
    Large
  </div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
</div>
```
```html
<div class="ui segment">
  <div class="ui left big rail">
    Big
  </div>
  <div class="ui right huge rail">
    Huge
  </div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
</div>
```
```html
<div class="ui segment">
  <div class="ui right massive rail">
    Massive
  </div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
</div>
```
