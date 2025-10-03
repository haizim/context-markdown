# Container

A container limits content to a maximum width

## Introduction

### When To Use

A container is an element designed to contain page elements to a reasonable maximum width based on the size of a user's screen. This is useful to couple with other UI elements like grid or menu to restrict their width to a reasonable size for display.

### Container Sizes

Containers are designed to responsively adjust their maximum width based on the size of the screen on which they are appearing.

| | Mobile | Tablet | Small Monitor | Large Monitor |
|---|---|---|---|---|
| Width | 100% | 723px | 933px | 1127px |
| Gutter Size | 1em | Fluid | Fluid | Fluid |
| Variable | `$largestMobileScreen` | `$mobileBreakpoint` | `$smallMonitorBreakpoint` | `$largeMonitorBreakpoint` |
| Device Width | below 768px | 768px - 991px | 992px - 1200px | above 1200px |

### Responsive Visibility

Since variations in Semantic UI are only assigned in the scope of components, there are no "free floating" responsive class names, however some components include responsive variations to help ease responsive design. Grid for example, includes responsive classes for hiding or showing `column`, `row` based on device type.

### Determining Maximum Widths

Containers appear at the same width at each device size. This size is calculated programmatically by determining the maximum device width available within a device breakpoint, given a desired minimum gutter size.

For example to determine tablet container size the following formula is used:

```less
/* In site.variables */
@tabletBreakpoint : 768px;
@scrollbarWidth : 17px; /* This is a constant */

/* In container.variables */
@tabletMinimumGutter : (@emSize  * 1); /* require 1em gutter */
@tabletWidth : @tabletBreakpoint - (@tabletMinimumGutter * 2) - @scrollbarWidth;
```

This is the same as `768px - (14px * 2) - 17px` or `723px`

Adjusting site breakpoints in `site.variables` to use custom values will automatically adjust container widths.

## Definition

### Types

#### Container

A standard container

```html
<div class="ui container">
  <p></p>
</div>
```

```html
<p>Lorem ipsum dolor sit amet, consectetuer adipiscing
elit. Aenean commodo ligula eget dolor. Aenean massa
<strong>strong</strong>. Cum sociis natoque penatibus
et magnis dis parturient montes, nascetur ridiculus
mus. Donec quam felis, ultricies nec, pellentesque
eu, pretium quis, sem. Nulla consequat massa quis
enim. Donec pede justo, fringilla vel, aliquet nec,
vulputate eget, arcu. In enim justo, rhoncus ut,
imperdiet a, venenatis vitae, justo. Nullam dictum
felis eu pede <a href="#">link</a>
mollis pretium. Integer tincidunt. Cras dapibus.
Vivamus elementum semper nisi. Aenean vulputate
eleifend tellus. Aenean leo ligula, porttitor eu,
consequat vitae, eleifend ac, enim. Aliquam lorem ante,
dapibus in, viverra quis, feugiat a, tellus. Phasellus
viverra nulla ut metus varius laoreet. Quisque rutrum.
Aenean imperdiet. Etiam ultricies nisi vel augue.
Curabitur ullamcorper ultricies nisi.</p>
```

#### Text Container

A container can reduce its maximum width to more naturally accomodate a single column of text

> A text container is a simpler markup alternative to using a grid with a single column, and is designed to have a reasonable maximum width for displaying flowing text

```html
<div class="ui text container">
</div>
```

```html
<h2 class="ui header">Header</h2>
<p>Lorem ipsum dolor sit amet, consectetuer adipiscing
elit. Aenean commodo ligula eget dolor. Aenean massa
<strong>strong</strong>. Cum sociis natoque penatibus
et magnis dis parturient montes, nascetur ridiculus
mus. Donec quam felis, ultricies nec, pellentesque
eu, pretium quis, sem. Nulla consequat massa quis
enim. Donec pede justo, fringilla vel, aliquet nec,
vulputate eget, arcu. In enim justo, rhoncus ut,
imperdiet a, venenatis vitae, justo. Nullam dictum
felis eu pede <a href="#">link</a>
mollis pretium. Integer tincidunt. Cras dapibus.
Vivamus elementum semper nisi. Aenean vulputate
eleifend tellus. Aenean leo ligula, porttitor eu,
consequat vitae, eleifend ac, enim. Aliquam lorem ante,
dapibus in, viverra quis, feugiat a, tellus. Phasellus
viverra nulla ut metus varius laoreet. Quisque rutrum.
Aenean imperdiet. Etiam ultricies nisi vel augue.
Curabitur ullamcorper ultricies nisi.</p>
<p>Lorem ipsum dolor sit amet, consectetuer adipiscing
elit. Aenean commodo ligula eget dolor. Aenean massa
<strong>strong</strong>. Cum sociis natoque penatibus
et magnis dis parturient montes, nascetur ridiculus
mus. Donec quam felis, ultricies nec, pellentesque
eu, pretium quis, sem. Nulla consequat massa quis
enim. Donec pede justo, fringilla vel, aliquet nec,
vulputate eget, arcu. In enim justo, rhoncus ut,
imperdiet a, venenatis vitae, justo. Nullam dictum
felis eu pede <a href="#">link</a>
mollis pretium. Integer tincidunt. Cras dapibus.
Vivamus elementum semper nisi. Aenean vulputate
eleifend tellus. Aenean leo ligula, porttitor eu,
consequat vitae, eleifend ac, enim. Aliquam lorem ante,
dapibus in, viverra quis, feugiat a, tellus. Phasellus
viverra nulla ut metus varius laoreet. Quisque rutrum.
Aenean imperdiet. Etiam ultricies nisi vel augue.
Curabitur ullamcorper ultricies nisi.</p>
```

### Variations

#### Text Alignment

A container can specify its text alignment

```html
<div class="ui left aligned container">
  <p></p>
</div>
<div class="ui center aligned container">
  <p></p>
</div>
<div class="ui right aligned container">
  <p></p>
</div>
<div class="ui justified container">
  <p></p>
</div>
```

```html
Left Aligned
```

```html
Center Aligned
```

```html
Right Aligned
```

```html
<b>Justified</b>
<div class="ui divider"></div>
<p>Lorem ipsum dolor sit amet, consectetuer adipiscing
elit. Aenean commodo ligula eget dolor. Aenean massa
<strong>strong</strong>. Cum sociis natoque penatibus
et magnis dis parturient montes, nascetur ridiculus
mus. Donec quam felis, ultricies nec, pellentesque
eu, pretium quis, sem. Nulla consequat massa quis
enim. Donec pede justo, fringilla vel, aliquet nec,
vulputate eget, arcu. In enim justo, rhoncus ut,
imperdiet a, venenatis vitae, justo. Nullam dictum
felis eu pede <a href="#">link</a>
mollis pretium. Integer tincidunt. Cras dapibus.
Vivamus elementum semper nisi. Aenean vulputate
eleifend tellus. Aenean leo ligula, porttitor eu,
consequat vitae, eleifend ac, enim. Aliquam lorem ante,
dapibus in, viverra quis, feugiat a, tellus. Phasellus
viverra nulla ut metus varius laoreet. Quisque rutrum.
Aenean imperdiet. Etiam ultricies nisi vel augue.
Curabitur ullamcorper ultricies nisi.</p>
<p>Lorem ipsum dolor sit amet, consectetuer adipiscing
elit. Aenean commodo ligula eget dolor. Aenean massa
<strong>strong</strong>. Cum sociis natoque penatibus
et magnis dis parturient montes, nascetur ridiculus
mus. Donec quam felis, ultricies nec, pellentesque
eu, pretium quis, sem. Nulla consequat massa quis
enim. Donec pede justo, fringilla vel, aliquet nec,
vulputate eget, arcu. In enim justo, rhoncus ut,
imperdiet a, venenatis vitae, justo. Nullam dictum
felis eu pede <a href="#">link</a>
mollis pretium. Integer tincidunt. Cras dapibus.
Vivamus elementum semper nisi. Aenean vulputate
eleifend tellus. Aenean leo ligula, porttitor eu,
consequat vitae, eleifend ac, enim. Aliquam lorem ante,
dapibus in, viverra quis, feugiat a, tellus. Phasellus
viverra nulla ut metus varius laoreet. Quisque rutrum.
Aenean imperdiet. Etiam ultricies nisi vel augue.
Curabitur ullamcorper ultricies nisi.</p>
```

#### Fluid

A fluid container has no maximum width

> Fluid containers are useful for setting text alignment, or other variations on unstyled content

```html
<div class="ui fluid container">
  Fluid
</div>
```

```html
<h2 class="ui header">Dogs Roles with Humans</h2>
<p>Domestic dogs inherited complex behaviors, such as bite inhibition, from their wolf ancestors, which would have been pack hunters with complex body language. These sophisticated forms of social cognition and communication may account for their trainability, playfulness, and ability to fit into human households and social situations, and these attributes have given dogs a relationship with humans that has enabled them to become one of the most successful species on the planet today.</p>
<p>The dogs' value to early human hunter-gatherers led to them quickly becoming ubiquitous across world cultures. Dogs perform many roles for people, such as hunting, herding, pulling loads, protection, assisting police and military, companionship, and, more recently, aiding handicapped individuals. This impact on human society has given them the nickname "man's best friend" in the Western world. In some cultures, however, dogs are also a source of meat.</p>
```

## Examples

#### Containers Using Grids

A container can be combined with a grid allowing you to use all of the layout and alignment available for grids including responsive patterns.

```html
<div class="ui four column doubling stackable grid container">
  <div class="column">
    <p></p>
    <p></p>
  </div>
  <div class="column">
    <p></p>
    <p></p>
  </div>
  <div class="column">
    <p></p>
    <p></p>
  </div>
  <div class="column">
    <p></p>
    <p></p>
  </div>
</div>
```

```html
<div class="column">
  <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
  <div class="ui hidden divider"></div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  <div class="ui hidden divider"></div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
</div>
<div class="column">
  <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
  <div class="ui hidden divider"></div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  <div class="ui hidden divider"></div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
</div>
<div class="column">
  <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
  <div class="ui hidden divider"></div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  <div class="ui hidden divider"></div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
</div>
<div class="column">
  <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
  <div class="ui hidden divider"></div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  <div class="ui hidden divider"></div>
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
</div>
```

#### Centered Menu

A container can be used inside of a menu to make sure menu items appear inline with page contents. Using responsive variations like stackable menu can help make contents adjust to different device sizes.

```html
<div class="ui attached stackable menu">
  <div class="ui container">
    <a class="item">
      <i class="home icon"></i> Home
    </a>
    <a class="item">
      <i class="grid layout icon"></i> Browse
    </a>
    <a class="item">
      <i class="mail icon"></i> Messages
    </a>
    <div class="ui simple dropdown item">
      More
      <i class="dropdown icon"></i>
      <div class="menu">
        <a class="item"><i class="edit icon"></i> Edit Profile</a>
        <a class="item"><i class="globe icon"></i> Choose Language</a>
        <a class="item"><i class="settings icon"></i> Account Settings</a>
      </div>
    </div>
    <div class="right item">
      <div class="ui input"><input type="text" placeholder="Search..."></div>
    </div>
  </div>
</div>
```

#### Container Segment

A container can be used with a segment

```html
<div class="ui raised very padded text container segment">
  <h2 class="ui header">Dogs Roles with Humans</h2>
  <p></p>
  <p></p>
</div>
```

```html
<h2 class="ui header">Dogs Roles with Humans</h2>
<p>Domestic dogs inherited complex behaviors, such as bite inhibition, from their wolf ancestors, which would have been pack hunters with complex body language. These sophisticated forms of social cognition and communication may account for their trainability, playfulness, and ability to fit into human households and social situations, and these attributes have given dogs a relationship with humans that has enabled them to become one of the most successful species on the planet today.</p>
<p>The dogs' value to early human hunter-gatherers led to them quickly becoming ubiquitous across world cultures. Dogs perform many roles for people, such as hunting, herding, pulling loads, protection, assisting police and military, companionship, and, more recently, aiding handicapped individuals. This impact on human society has given them the nickname "man's best friend" in the Western world. In some cultures, however, dogs are also a source of meat.</p>
```
