## === button.md ===

# Button

A button indicates a possible user action

## Types

#### Button
A standard button
```html
<button class="ui button">
  Follow
</button>
```
> Although any tag can be used for a button, it will only be keyboard focusable if you use a `<button>` tag or you add the property `tabindex="0"`. Keyboard accessible buttons will preserve focus styles after click, which may be visually jarring.
```html
<button class="ui button">
  Button
</button>
<div class="ui button" tabindex="0">
  Focusable
</div>
```

#### Emphasis
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

#### Labeled
A button can appear alongside a label
```html
<div class="ui labeled button" tabindex="0">
  <div class="ui button">
    <i class="heart icon"></i> Like
  </div>
  <a class="ui basic label">
    2,048
  </a>
</div>
<div class="ui left labeled button" tabindex="0">
  <a class="ui basic right pointing label">
    2,048
  </a>
  <div class="ui button">
    <i class="heart icon"></i> Like
  </div>
</div>
<div class="ui left labeled button" tabindex="0">
  <a class="ui basic label">
    1,048
  </a>
  <div class="ui icon button">
    <i class="fork icon"></i>
  </div>
</div>
```
```html
<div class="ui labeled button" tabindex="0">
  <div class="ui red button">
    <i class="heart icon"></i> Like
  </div>
  <a class="ui basic red left pointing label">
    1,048
  </a>
</div>
<div class="ui labeled button" tabindex="0">
  <div class="ui basic blue button">
    <i class="fork icon"></i> Forks
  </div>
  <a class="ui basic left pointing blue label">
    1,048
  </a>
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
A button can use an icon as a label
```html
<button class="ui labeled icon button">
  <i class="pause icon"></i>
  Pause
</button>
<button class="ui right labeled icon button">
  <i class="right arrow icon"></i>
  Next
</button>
<button class="ui labeled icon button">
  <i class="loading spinner icon"></i>
  Loading
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
<button class="ui primary basic button">Primary</button>
<button class="ui secondary basic button">Secondary</button>
<button class="ui positive basic button">Positive</button>
<button class="ui negative basic button">Negative</button>
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

#### Inverted
A button can be formatted to appear on dark backgrounds
```html
<div class="ui inverted segment">
  <button class="ui inverted button">Standard</button>
  <button class="ui inverted primary button">Primary</button>
  <button class="ui inverted secondary button">Secondary</button>
  <button class="ui inverted red button">Red</button>
  <button class="ui inverted orange button">Orange</button>
  <button class="ui inverted yellow button">Yellow</button>
  <button class="ui inverted olive button">Olive</button>
  <button class="ui inverted green button">Green</button>
  <button class="ui inverted teal button">Teal</button>
  <button class="ui inverted blue button">Blue</button>
  <button class="ui inverted violet button">Violet</button>
  <button class="ui inverted purple button">Purple</button>
  <button class="ui inverted pink button">Pink</button>
  <button class="ui inverted brown button">Brown</button>
  <button class="ui inverted grey button">Grey</button>
  <button class="ui inverted black button">Black</button>
</div>
```
```html
<div class="ui inverted segment">
  <button class="ui inverted basic button">Basic</button>
  <button class="ui inverted primary basic button">Primary</button>
  <button class="ui inverted secondary basic button">Secondary</button>
  <button class="ui inverted red basic button">Basic Red</button>
  <button class="ui inverted orange basic button">Basic Orange</button>
  <button class="ui inverted yellow basic button">Basic Yellow</button>
  <button class="ui inverted olive basic button">Basic Olive</button>
  <button class="ui inverted green basic button">Basic Green</button>
  <button class="ui inverted teal basic button">Basic Teal</button>
  <button class="ui inverted blue basic button">Basic Blue</button>
  <button class="ui inverted violet basic button">Basic Violet</button>
  <button class="ui inverted purple basic button">Basic Purple</button>
  <button class="ui inverted pink basic button">Basic Pink</button>
  <button class="ui inverted brown basic button">Basic Brown</button>
  <button class="ui inverted grey basic button">Basic Grey</button>
  <button class="ui inverted black basic button">Basic Black</button>
</div>
```

## Groups

#### Buttons
Buttons can exist together as a group
```html
<div class="ui buttons">
  <button class="ui button">One</button>
  <button class="ui button">Two</button>
  <button class="ui button">Three</button>
</div>
```

#### Icon Buttons
Button groups can show groups of icons
```html
<div class="ui icon buttons">
  <button class="ui button"><i class="align left icon"></i></button>
  <button class="ui button"><i class="align center icon"></i></button>
  <button class="ui button"><i class="align right icon"></i></button>
  <button class="ui button"><i class="align justify icon"></i></button>
</div>
<div class="ui icon buttons">
  <button class="ui button"><i class="bold icon"></i></button>
  <button class="ui button"><i class="underline icon"></i></button>
  <button class="ui button"><i class="text width icon"></i></button>
</div>
```

## Content

#### Conditionals
Button groups can contain conditionals
```html
<div class="ui buttons">
  <button class="ui button">Cancel</button>
  <div class="or"></div>
  <button class="ui positive button">Save</button>
</div>
```
> Or buttons can have their text localized, or adjusted by using the `data-text` attribute. If the size of the conditional changes you will need to adjust `@orCircleSize`
```html
<div class="ui buttons">
  <button class="ui button">un</button>
  <div class="or" data-text="ou"></div>
  <button class="ui positive button">deux</button>
</div>
```

## States

#### Active
A button can show it is currently the active user selection
```html
<button class="ui active button">
  <i class="user icon"></i>
  Follow
</button>
```

#### Disabled
A button can show it is currently unable to be interacted with
```html
<button class="ui disabled button">
  <i class="user icon"></i>
  Followed
</button>
```

#### Loading
A button can show a loading indicator
```html
<button class="ui loading button">Loading</button>
<button class="ui basic loading button">Loading</button>
<button class="ui primary loading button">Loading</button>
<button class="ui secondary loading button">Loading</button>
```

## Variations

#### Social
A button can be formatted to link to a social website
```html
<button class="ui facebook button">
  <i class="facebook icon"></i>
  Facebook
</button>
<button class="ui twitter button">
  <i class="twitter icon"></i>
  Twitter
</button>
<button class="ui google plus button">
  <i class="google plus icon"></i>
  Google Plus
</button>
<button class="ui vk button">
  <i class="vk icon"></i>
  VK
</button>
<button class="ui linkedin button">
  <i class="linkedin icon"></i>
  LinkedIn
</button>
<button class="ui instagram button">
  <i class="instagram icon"></i>
  Instagram
</button>
<button class="ui youtube button">
  <i class="youtube icon"></i>
  YouTube
</button>
```

#### Size
A button can have different sizes
```html
<button class="mini ui button">
  Mini
</button>
<button class="tiny ui button">
  Tiny
</button>
<button class="small ui button">
  Small
</button>
<button class="medium ui button">
  Medium
</button>
<button class="large ui button">
  Large
</button>
<button class="big ui button">
  Big
</button>
<button class="huge ui button">
  Huge
</button>
<button class="massive ui button">
  Massive
</button>
```

#### Floated
A button can be aligned to the left or right of its container
```html
<button class="ui right floated button">Right Floated</button>
<button class="ui left floated button">Left Floated</button>
```

#### Colored
A button can have different colors
```html
<button class="ui red button">Red</button>
<button class="ui orange button">Orange</button>
<button class="ui yellow button">Yellow</button>
<button class="ui olive button">Olive</button>
<button class="ui green button">Green</button>
<button class="ui teal button">Teal</button>
<button class="ui blue button">Blue</button>
<button class="ui violet button">Violet</button>
<button class="ui purple button">Purple</button>
<button class="ui pink button">Pink</button>
<button class="ui brown button">Brown</button>
<button class="ui grey button">Grey</button>
<button class="ui black button">Black</button>
```

#### Compact
A button can reduce its padding to fit into tighter spaces
```html
<button class="compact ui button">
  Hold
</button>
<button class="ui compact icon button">
  <i class="pause icon"></i>
</button>
<button class="ui compact labeled icon button">
  <i class="pause icon"></i>
  Pause
</button>
```

#### Toggle
A button can be formatted to toggle on and off
```html
<button class="ui toggle button">
  Vote
</button>
```

#### Positive
A button can hint towards a positive consequence
```html
<button class="positive ui button">Positive Button</button>
```

#### Negative
A button can hint towards a negative consequence
```html
<button class="negative ui button">Negative Button</button>
```

#### Fluid
A button can take the width of its container
```html
<button class="fluid ui button">Fits container</button>
```

#### Circular
A button can be circular
```html
<button class="circular ui icon button">
  <i class="icon settings"></i>
</button>
```
```html
<button class="ui circular facebook icon button">
  <i class="facebook icon"></i>
</button>
<button class="ui circular twitter icon button">
  <i class="twitter icon"></i>
</button>
<button class="ui circular linkedin icon button">
  <i class="linkedin icon"></i>
</button>
<button class="ui circular google plus icon button">
  <i class="google plus icon"></i>
</button>
```

#### Vertically Attached
A button can be attached to the top or bottom of other content
```html
<div class="ui top attached button" tabindex="0">Top</div>
<div class="ui attached segment">
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
</div>
<div class="ui bottom attached button" tabindex="0">Bottom</div>
```
```html
<div class="ui two top attached buttons">
    <div class="ui button">One</div>
    <div class="ui button">Two</div>
</div>
<div class="ui attached segment">
  <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
</div>
<div class="ui two bottom attached buttons">
    <div class="ui button">One</div>
    <div class="ui button">Two</div>
</div>
```

#### Horizontally Attached
A button can be attached to the left or right of other content
```html
<button class="ui left attached button">Left</button>
<button class="right attached ui button">Right</button>
```

## Group Variations

#### Vertical Buttons
Groups can be formatted to appear vertically
```html
<div class="ui vertical buttons">
  <button class="ui button">Feed</button>
  <button class="ui button">Messages</button>
  <button class="ui button">Events</button>
  <button class="ui button">Photos</button>
</div>
```

#### Icon Buttons
Groups can be formatted as icons
```html
<div class="ui icon buttons">
  <button class="ui button">
    <i class="play icon"></i>
  </button>
  <button class="ui button">
    <i class="pause icon"></i>
  </button>
  <button class="ui button">
    <i class="shuffle icon"></i>
  </button>
</div>
```

#### Labeled Icon Buttons
Groups can be formatted as labeled icons
```html
<div class="ui vertical labeled icon buttons">
  <button class="ui button">
    <i class="pause icon"></i>
    Pause
  </button>
  <button class="ui button">
    <i class="play icon"></i>
    Play
  </button>
  <button class="ui button">
    <i class="shuffle icon"></i>
    Shuffle
  </button>
</div>
```

#### Mixed Group
Groups can be formatted to use multiple button types together
```html
<div class="ui buttons">
  <button class="ui labeled icon button">
    <i class="left chevron icon"></i>
    Back
  </button>
  <button class="ui button">
    <i class="stop icon"></i>
    Stop
  </button>
  <button class="ui right labeled icon button">
    Forward
    <i class="right chevron icon"></i>
  </button>
</div>
```

#### Equal Width
Groups can have their widths divided evenly
```html
<div class="five ui buttons">
  <button class="ui button">Overview</button>
  <button class="ui button">Specs</button>
  <button class="ui button">Warranty</button>
  <button class="ui button">Reviews</button>
  <button class="ui button">Support</button>
</div>
<div class="three ui buttons">
  <button class="ui button">Overview</button>
  <button class="ui button">Specs</button>
  <button class="ui button">Support</button>
</div>
```

#### Colored Buttons
Groups can have a shared color
```html
<div class="blue ui buttons">
  <button class="ui button">One</button>
  <button class="ui button">Two</button>
  <button class="ui button">Three</button>
</div>
```

#### Basic Buttons
A button group can be less pronounced
```html
<div class="ui basic buttons">
  <div class="ui button">One</div>
  <div class="ui button">Two</div>
  <div class="ui button">Three</div>
</div>
<div class="ui vertical basic buttons">
  <button class="ui button">One</button>
  <button class="ui button">Two</button>
  <button class="ui button">Three</button>
</div>
```
```html
<div class="ui buttons">
  <button class="ui red basic button">One</button>
  <button class="ui blue basic button">Two</button>
  <button class="ui green basic button">Three</button>
</div>
```

#### Group Sizes
Groups can have a shared size
```html
<div class="large ui buttons">
  <button class="ui button">One</button>
  <button class="ui button">Two</button>
  <button class="ui button">Three</button>
</div>
```
```html
<div class="ui small basic icon buttons">
  <button class="ui button"><i class="file icon"></i></button>
  <button class="ui button"><i class="save icon"></i></button>
  <button class="ui button"><i class="upload icon"></i></button>
  <button class="ui button"><i class="download icon"></i></button>
</div>
```
```html
<div class="ui large buttons">
  <button class="ui button">One</button>
  <div class="or"></div>
  <button class="ui button">Two</button>
</div>
```


## === container.md ===

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


## === divider.md ===

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


## === flag.md ===

# Flag

A flag is used to represent a political state

## Definition

#### Flag
A flag can use the two digit country code, the full name, or a common alias
```html
<i class="ae flag"></i>
<i class="france flag"></i>
<i class="myanmar flag"></i>
```

## Types
> Many flag sets use SVG to render flags at multiple sizes. However svg flags usually appear blurry or render improperly at smaller sizes. Semantic's default theme uses an image sprite solution which provides crisper icons, but without the ability to resize
```html
<table class="ui selectable sortable compact celled striped definition table">
  <thead>
    <th class="one wide">Flag</th>
    <th>Name</th>
    <th>ISO 3166-2 Code <a href="http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2">?</a></th>
    <th>Additional Aliases</th>
  </thead>
  <tbody>
  <tr>
    <td><i class="andorra flag"></i></td>
    <td>Andorra</td>
    <td>ad</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="uae flag"></i></td>
    <td>U.A.E</td>
    <td>ae</td>
    <td>United Arab Emirates</td>
  </tr>
  <tr>
    <td><i class="afghanistan flag"></i></td>
    <td>Afghanistan</td>
    <td>af</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="antigua flag"></i></td>
    <td>Antigua</td>
    <td>ag</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="anguilla flag"></i></td>
    <td>Anguilla</td>
    <td>ai</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="albania flag"></i></td>
    <td>Albania</td>
    <td>al</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="armenia flag"></i></td>
    <td>Armenia</td>
    <td>am</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="netherlands antilles flag"></i></td>
    <td>Netherlands Antilles</td>
    <td>an</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="angola flag"></i></td>
    <td>Angola</td>
    <td>ao</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="argentina flag"></i></td>
    <td>Argentina</td>
    <td>ar</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="american samoa flag"></i></td>
    <td>American Samoa</td>
    <td>as</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="austria flag"></i></td>
    <td>Austria</td>
    <td>at</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="australia flag"></i></td>
    <td>Australia</td>
    <td>au</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="aruba flag"></i></td>
    <td>Aruba</td>
    <td>aw</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="aland islands flag"></i></td>
    <td>Aland Islands</td>
    <td>ax</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="azerbaijan flag"></i></td>
    <td>Azerbaijan</td>
    <td>az</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="bosnia flag"></i></td>
    <td>Bosnia</td>
    <td>ba</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="barbados flag"></i></td>
    <td>Barbados</td>
    <td>bb</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="bangladesh flag"></i></td>
    <td>Bangladesh</td>
    <td>bd</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="belgium flag"></i></td>
    <td>Belgium</td>
    <td>be</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="burkina faso flag"></i></td>
    <td>Burkina Faso</td>
    <td>bf</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="bulgaria flag"></i></td>
    <td>Bulgaria</td>
    <td>bg</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="bahrain flag"></i></td>
    <td>Bahrain</td>
    <td>bh</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="burundi flag"></i></td>
    <td>Burundi</td>
    <td>bi</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="benin flag"></i></td>
    <td>Benin</td>
    <td>bj</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="bermuda flag"></i></td>
    <td>Bermuda</td>
    <td>bm</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="brunei flag"></i></td>
    <td>Brunei</td>
    <td>bn</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="bolivia flag"></i></td>
    <td>Bolivia</td>
    <td>bo</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="brazil flag"></i></td>
    <td>Brazil</td>
    <td>br</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="bahamas flag"></i></td>
    <td>Bahamas</td>
    <td>bs</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="bhutan flag"></i></td>
    <td>Bhutan</td>
    <td>bt</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="bouvet island flag"></i></td>
    <td>Bouvet Island</td>
    <td>bv</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="botswana flag"></i></td>
    <td>Botswana</td>
    <td>bw</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="belarus flag"></i></td>
    <td>Belarus</td>
    <td>by</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="belize flag"></i></td>
    <td>Belize</td>
    <td>bz</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="canada flag"></i></td>
    <td>Canada</td>
    <td>ca</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="cocos islands flag"></i></td>
    <td>Cocos Islands</td>
    <td>cc</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="congo flag"></i></td>
    <td>Congo</td>
    <td>cd</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="central african republic flag"></i></td>
    <td>Central African Republic</td>
    <td>cf</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="congo brazzaville flag"></i></td>
    <td>Congo Brazzaville</td>
    <td>cg</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="switzerland flag"></i></td>
    <td>Switzerland</td>
    <td>ch</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="cote divoire flag"></i></td>
    <td>Cote Divoire</td>
    <td>ci</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="cook islands flag"></i></td>
    <td>Cook Islands</td>
    <td>ck</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="chile flag"></i></td>
    <td>Chile</td>
    <td>cl</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="cameroon flag"></i></td>
    <td>Cameroon</td>
    <td>cm</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="china flag"></i></td>
    <td>China</td>
    <td>cn</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="colombia flag"></i></td>
    <td>Colombia</td>
    <td>co</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="costa rica flag"></i></td>
    <td>Costa Rica</td>
    <td>cr</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="serbia flag"></i></td>
    <td>Serbia</td>
    <td>cs</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="cuba flag"></i></td>
    <td>Cuba</td>
    <td>cu</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="cape verde flag"></i></td>
    <td>Cape Verde</td>
    <td>cv</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="christmas island flag"></i></td>
    <td>Christmas Island</td>
    <td>cx</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="cyprus flag"></i></td>
    <td>Cyprus</td>
    <td>cy</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="czech republic flag"></i></td>
    <td>Czech Republic</td>
    <td>cz</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="germany flag"></i></td>
    <td>Germany</td>
    <td>de</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="djibouti flag"></i></td>
    <td>Djibouti</td>
    <td>dj</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="denmark flag"></i></td>
    <td>Denmark</td>
    <td>dk</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="dominica flag"></i></td>
    <td>Dominica</td>
    <td>dm</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="dominican republic flag"></i></td>
    <td>Dominican Republic</td>
    <td>do</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="algeria flag"></i></td>
    <td>Algeria</td>
    <td>dz</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="ecuador flag"></i></td>
    <td>Ecuador</td>
    <td>ec</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="estonia flag"></i></td>
    <td>Estonia</td>
    <td>ee</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="egypt flag"></i></td>
    <td>Egypt</td>
    <td>eg</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="western sahara flag"></i></td>
    <td>Western Sahara</td>
    <td>eh</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="eritrea flag"></i></td>
    <td>Eritrea</td>
    <td>er</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="spain flag"></i></td>
    <td>Spain</td>
    <td>es</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="ethiopia flag"></i></td>
    <td>Ethiopia</td>
    <td>et</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="european union flag"></i></td>
    <td>European Union</td>
    <td>eu</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="finland flag"></i></td>
    <td>Finland</td>
    <td>fi</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="fiji flag"></i></td>
    <td>Fiji</td>
    <td>fj</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="falkland islands flag"></i></td>
    <td>Falkland Islands</td>
    <td>fk</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="micronesia flag"></i></td>
    <td>Micronesia</td>
    <td>fm</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="faroe islands flag"></i></td>
    <td>Faroe Islands</td>
    <td>fo</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="france flag"></i></td>
    <td>France</td>
    <td>fr</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="gabon flag"></i></td>
    <td>Gabon</td>
    <td>ga</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="united kingdom flag"></i></td>
    <td>United Kingdom</td>
    <td>gb uk</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="england flag"></i></td>
    <td>England</td>
    <td>gb eng</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="scotland flag"></i></td>
    <td>Scotland</td>
    <td>gb sct</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="wales flag"></i></td>
    <td>Wales</td>
    <td>gb wls</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="grenada flag"></i></td>
    <td>Grenada</td>
    <td>gd</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="georgia flag"></i></td>
    <td>Georgia</td>
    <td>ge</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="french guiana flag"></i></td>
    <td>French Guiana</td>
    <td>gf</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="ghana flag"></i></td>
    <td>Ghana</td>
    <td>gh</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="gibraltar flag"></i></td>
    <td>Gibraltar</td>
    <td>gi</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="greenland flag"></i></td>
    <td>Greenland</td>
    <td>gl</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="gambia flag"></i></td>
    <td>Gambia</td>
    <td>gm</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="guinea flag"></i></td>
    <td>Guinea</td>
    <td>gn</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="guadeloupe flag"></i></td>
    <td>Guadeloupe</td>
    <td>gp</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="equatorial guinea flag"></i></td>
    <td>Equatorial Guinea</td>
    <td>gq</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="greece flag"></i></td>
    <td>Greece</td>
    <td>gr</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="sandwich islands flag"></i></td>
    <td>Sandwich Islands</td>
    <td>gs</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="guatemala flag"></i></td>
    <td>Guatemala</td>
    <td>gt</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="guam flag"></i></td>
    <td>Guam</td>
    <td>gu</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="guinea-bissau flag"></i></td>
    <td>Guinea-bissau</td>
    <td>gw</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="guyana flag"></i></td>
    <td>Guyana</td>
    <td>gy</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="hong kong flag"></i></td>
    <td>Hong Kong</td>
    <td>hk</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="heard island flag"></i></td>
    <td>Heard Island</td>
    <td>hm</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="honduras flag"></i></td>
    <td>Honduras</td>
    <td>hn</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="croatia flag"></i></td>
    <td>Croatia</td>
    <td>hr</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="haiti flag"></i></td>
    <td>Haiti</td>
    <td>ht</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="hungary flag"></i></td>
    <td>Hungary</td>
    <td>hu</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="indonesia flag"></i></td>
    <td>Indonesia</td>
    <td>id</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="ireland flag"></i></td>
    <td>Ireland</td>
    <td>ie</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="israel flag"></i></td>
    <td>Israel</td>
    <td>il</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="india flag"></i></td>
    <td>India</td>
    <td>in</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="indian ocean territory flag"></i></td>
    <td>Indian Ocean Territory</td>
    <td>io</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="iraq flag"></i></td>
    <td>Iraq</td>
    <td>iq</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="iran flag"></i></td>
    <td>Iran</td>
    <td>ir</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="iceland flag"></i></td>
    <td>Iceland</td>
    <td>is</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="italy flag"></i></td>
    <td>Italy</td>
    <td>it</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="jamaica flag"></i></td>
    <td>Jamaica</td>
    <td>jm</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="jordan flag"></i></td>
    <td>Jordan</td>
    <td>jo</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="japan flag"></i></td>
    <td>Japan</td>
    <td>jp</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="kenya flag"></i></td>
    <td>Kenya</td>
    <td>ke</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="kyrgyzstan flag"></i></td>
    <td>Kyrgyzstan</td>
    <td>kg</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="cambodia flag"></i></td>
    <td>Cambodia</td>
    <td>kh</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="kiribati flag"></i></td>
    <td>Kiribati</td>
    <td>ki</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="comoros flag"></i></td>
    <td>Comoros</td>
    <td>km</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="saint kitts and nevis flag"></i></td>
    <td>Saint Kitts And Nevis</td>
    <td>kn</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="north korea flag"></i></td>
    <td>North Korea</td>
    <td>kp</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="south korea flag"></i></td>
    <td>South Korea</td>
    <td>kr</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="kuwait flag"></i></td>
    <td>Kuwait</td>
    <td>kw</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="cayman islands flag"></i></td>
    <td>Cayman Islands</td>
    <td>ky</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="kazakhstan flag"></i></td>
    <td>Kazakhstan</td>
    <td>kz</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="laos flag"></i></td>
    <td>Laos</td>
    <td>la</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="lebanon flag"></i></td>
    <td>Lebanon</td>
    <td>lb</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="saint lucia flag"></i></td>
    <td>Saint Lucia</td>
    <td>lc</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="liechtenstein flag"></i></td>
    <td>Liechtenstein</td>
    <td>li</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="sri lanka flag"></i></td>
    <td>Sri Lanka</td>
    <td>lk</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="liberia flag"></i></td>
    <td>Liberia</td>
    <td>lr</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="lesotho flag"></i></td>
    <td>Lesotho</td>
    <td>ls</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="lithuania flag"></i></td>
    <td>Lithuania</td>
    <td>lt</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="luxembourg flag"></i></td>
    <td>Luxembourg</td>
    <td>lu</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="latvia flag"></i></td>
    <td>Latvia</td>
    <td>lv</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="libya flag"></i></td>
    <td>Libya</td>
    <td>ly</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="morocco flag"></i></td>
    <td>Morocco</td>
    <td>ma</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="monaco flag"></i></td>
    <td>Monaco</td>
    <td>mc</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="moldova flag"></i></td>
    <td>Moldova</td>
    <td>md</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="montenegro flag"></i></td>
    <td>Montenegro</td>
    <td>me</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="madagascar flag"></i></td>
    <td>Madagascar</td>
    <td>mg</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="marshall islands flag"></i></td>
    <td>Marshall Islands</td>
    <td>mh</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="macedonia flag"></i></td>
    <td>Macedonia</td>
    <td>mk</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="mali flag"></i></td>
    <td>Mali</td>
    <td>ml</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="burma flag"></i></td>
    <td>Burma</td>
    <td>mm</td>
    <td>Myanmar</td>
  </tr>
  <tr>
    <td><i class="mongolia flag"></i></td>
    <td>Mongolia</td>
    <td>mn</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="macau flag"></i></td>
    <td>Macau</td>
    <td>mo</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="northern mariana islands flag"></i></td>
    <td>Northern Mariana Islands</td>
    <td>mp</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="martinique flag"></i></td>
    <td>Martinique</td>
    <td>mq</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="mauritania flag"></i></td>
    <td>Mauritania</td>
    <td>mr</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="montserrat flag"></i></td>
    <td>Montserrat</td>
    <td>ms</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="malta flag"></i></td>
    <td>Malta</td>
    <td>mt</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="mauritius flag"></i></td>
    <td>Mauritius</td>
    <td>mu</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="maldives flag"></i></td>
    <td>Maldives</td>
    <td>mv</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="malawi flag"></i></td>
    <td>Malawi</td>
    <td>mw</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="mexico flag"></i></td>
    <td>Mexico</td>
    <td>mx</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="malaysia flag"></i></td>
    <td>Malaysia</td>
    <td>my</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="mozambique flag"></i></td>
    <td>Mozambique</td>
    <td>mz</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="namibia flag"></i></td>
    <td>Namibia</td>
    <td>na</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="new caledonia flag"></i></td>
    <td>New Caledonia</td>
    <td>nc</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="niger flag"></i></td>
    <td>Niger</td>
    <td>ne</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="norfolk island flag"></i></td>
    <td>Norfolk Island</td>
    <td>nf</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="nigeria flag"></i></td>
    <td>Nigeria</td>
    <td>ng</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="nicaragua flag"></i></td>
    <td>Nicaragua</td>
    <td>ni</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="netherlands flag"></i></td>
    <td>Netherlands</td>
    <td>nl</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="norway flag"></i></td>
    <td>Norway</td>
    <td>no</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="nepal flag"></i></td>
    <td>Nepal</td>
    <td>np</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="nauru flag"></i></td>
    <td>Nauru</td>
    <td>nr</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="niue flag"></i></td>
    <td>Niue</td>
    <td>nu</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="new zealand flag"></i></td>
    <td>New Zealand</td>
    <td>nz</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="oman flag"></i></td>
    <td>Oman</td>
    <td>om</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="panama flag"></i></td>
    <td>Panama</td>
    <td>pa</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="peru flag"></i></td>
    <td>Peru</td>
    <td>pe</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="french polynesia flag"></i></td>
    <td>French Polynesia</td>
    <td>pf</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="new guinea flag"></i></td>
    <td>New Guinea</td>
    <td>pg</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="philippines flag"></i></td>
    <td>Philippines</td>
    <td>ph</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="pakistan flag"></i></td>
    <td>Pakistan</td>
    <td>pk</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="poland flag"></i></td>
    <td>Poland</td>
    <td>pl</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="saint pierre flag"></i></td>
    <td>Saint Pierre</td>
    <td>pm</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="pitcairn islands flag"></i></td>
    <td>Pitcairn Islands</td>
    <td>pn</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="puerto rico flag"></i></td>
    <td>Puerto Rico</td>
    <td>pr</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="palestine flag"></i></td>
    <td>Palestine</td>
    <td>ps</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="portugal flag"></i></td>
    <td>Portugal</td>
    <td>pt</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="palau flag"></i></td>
    <td>Palau</td>
    <td>pw</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="paraguay flag"></i></td>
    <td>Paraguay</td>
    <td>py</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="qatar flag"></i></td>
    <td>Qatar</td>
    <td>qa</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="reunion flag"></i></td>
    <td>Reunion</td>
    <td>re</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="romania flag"></i></td>
    <td>Romania</td>
    <td>ro</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="serbia flag"></i></td>
    <td>Serbia</td>
    <td>rs</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="russia flag"></i></td>
    <td>Russia</td>
    <td>ru</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="rwanda flag"></i></td>
    <td>Rwanda</td>
    <td>rw</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="saudi arabia flag"></i></td>
    <td>Saudi Arabia</td>
    <td>sa</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="solomon islands flag"></i></td>
    <td>Solomon Islands</td>
    <td>sb</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="seychelles flag"></i></td>
    <td>Seychelles</td>
    <td>sc</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="sudan flag"></i></td>
    <td>Sudan</td>
    <td>sd</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="sweden flag"></i></td>
    <td>Sweden</td>
    <td>se</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="singapore flag"></i></td>
    <td>Singapore</td>
    <td>sg</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="saint helena flag"></i></td>
    <td>Saint Helena</td>
    <td>sh</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="slovenia flag"></i></td>
    <td>Slovenia</td>
    <td>si</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="jan mayen flag"></i></td>
    <td>Jan Mayen</td>
    <td>sj</td>
    <td>Svalbard</td>
  </tr>
  <tr>
    <td><i class="slovakia flag"></i></td>
    <td>Slovakia</td>
    <td>sk</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="sierra leone flag"></i></td>
    <td>Sierra Leone</td>
    <td>sl</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="san marino flag"></i></td>
    <td>San Marino</td>
    <td>sm</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="senegal flag"></i></td>
    <td>Senegal</td>
    <td>sn</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="somalia flag"></i></td>
    <td>Somalia</td>
    <td>so</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="suriname flag"></i></td>
    <td>Suriname</td>
    <td>sr</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="sao tome flag"></i></td>
    <td>Sao Tome</td>
    <td>st</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="el salvador flag"></i></td>
    <td>El Salvador</td>
    <td>sv</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="syria flag"></i></td>
    <td>Syria</td>
    <td>sy</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="swaziland flag"></i></td>
    <td>Swaziland</td>
    <td>sz</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="caicos islands flag"></i></td>
    <td>Caicos Islands</td>
    <td>tc</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="chad flag"></i></td>
    <td>Chad</td>
    <td>td</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="french territories flag"></i></td>
    <td>French Territories</td>
    <td>tf</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="togo flag"></i></td>
    <td>Togo</td>
    <td>tg</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="thailand flag"></i></td>
    <td>Thailand</td>
    <td>th</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="tajikistan flag"></i></td>
    <td>Tajikistan</td>
    <td>tj</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="tokelau flag"></i></td>
    <td>Tokelau</td>
    <td>tk</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="timorleste flag"></i></td>
    <td>Timorleste</td>
    <td>tl</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="turkmenistan flag"></i></td>
    <td>Turkmenistan</td>
    <td>tm</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="tunisia flag"></i></td>
    <td>Tunisia</td>
    <td>tn</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="tonga flag"></i></td>
    <td>Tonga</td>
    <td>to</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="turkey flag"></i></td>
    <td>Turkey</td>
    <td>tr</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="trinidad flag"></i></td>
    <td>Trinidad</td>
    <td>tt</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="tuvalu flag"></i></td>
    <td>Tuvalu</td>
    <td>tv</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="taiwan flag"></i></td>
    <td>Taiwan</td>
    <td>tw</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="tanzania flag"></i></td>
    <td>Tanzania</td>
    <td>tz</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="ukraine flag"></i></td>
    <td>Ukraine</td>
    <td>ua</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="uganda flag"></i></td>
    <td>Uganda</td>
    <td>ug</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="us minor islands flag"></i></td>
    <td>Us Minor Islands</td>
    <td>um</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="united states flag"></i></td>
    <td>United States</td>
    <td>us</td>
    <td>America</td>
  </tr>
  <tr>
    <td><i class="uruguay flag"></i></td>
    <td>Uruguay</td>
    <td>uy</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="uzbekistan flag"></i></td>
    <td>Uzbekistan</td>
    <td>uz</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="vatican city flag"></i></td>
    <td>Vatican City</td>
    <td>va</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="saint vincent flag"></i></td>
    <td>Saint Vincent</td>
    <td>vc</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="venezuela flag"></i></td>
    <td>Venezuela</td>
    <td>ve</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="british virgin islands flag"></i></td>
    <td>British Virgin Islands</td>
    <td>vg</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="us virgin islands flag"></i></td>
    <td>Us Virgin Islands</td>
    <td>vi</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="vietnam flag"></i></td>
    <td>Vietnam</td>
    <td>vn</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="vanuatu flag"></i></td>
    <td>Vanuatu</td>
    <td>vu</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="wallis and futuna flag"></i></td>
    <td>Wallis And Futuna</td>
    <td>wf</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="samoa flag"></i></td>
    <td>Samoa</td>
    <td>ws</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="yemen flag"></i></td>
    <td>Yemen</td>
    <td>ye</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="mayotte flag"></i></td>
    <td>Mayotte</td>
    <td>yt</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="south africa flag"></i></td>
    <td>South Africa</td>
    <td>za</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="zambia flag"></i></td>
    <td>Zambia</td>
    <td>zm</td>
    <td class="disabled"></td>
  </tr>
  <tr>
    <td><i class="zimbabwe flag"></i></td>
    <td>Zimbabwe</td>
    <td>zw</td>
    <td class="disabled"></td>
  </tr>
  </tbody>
</table>
```


## === header.md ===

# Header

A header provides a short summary of content

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

#### Content Headers
Headers may be oriented to give the importance of a section in the context of the content that surrounds it
> Content headings are sized with `em` and are based on the font-size of their container.
```html
<div class="ui ignored icon font buttons">
  <a class="increase ui button"> <i class="plus icon"></i></a>
  <a class="decrease ui button"> <i class="minus icon"></i></a>
</div>
<div class="ui sizer vertical segment">
  <div class="ui huge header">Huge Header</div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <div class="ui large header">Large Header</div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <div class="ui medium header">Medium Header</div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <div class="ui small header">Small Header</div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  <div class="ui tiny header">Tiny Header</div>
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```

#### Icon Headers
A header can be formatted to emphasize an icon
```html
<h2 class="ui icon header">
  <i class="settings icon"></i>
  <div class="content">
    Account Settings
    <div class="sub header">Manage your account settings and set e-mail preferences.</div>
  </div>
</h2>
```
```html
<h2 class="ui center aligned icon header">
  <i class="circular users icon"></i>
  Friends
</h2>
<img class="ui centered wireframe image" src="/images/wireframe/centered-paragraph.png">
```

#### Sub Headers
Headers may be formatted to label smaller or de-emphasized content.
```html
<h2 class="ui sub header">
  Price
</h2>
<span>$10.99</span>
```
```html
<div class="ui horizontal list">
  <div class="item">
    <img class="ui mini circular image" src="/images/avatar2/small/molly.png">
    <div class="content">
      <div class="ui sub header">Molly</div>
      Coordinator
    </div>
  </div>
  <div class="item">
    <img class="ui mini circular image" src="/images/avatar2/small/elyse.png">
    <div class="content">
      <div class="ui sub header">Elyse</div>
      Developer
    </div>
  </div>
  <div class="item">
    <img src="/images/avatar2/small/eve.png" class="ui mini circular image">
    <div class="content">
      <div class="ui sub header">Eve</div>
      Project Manager
    </div>
  </div>
</div>
```

## Content

#### Image
A header may contain an image
```html
<h2 class="ui header">
  <img class="ui image" src="/images/icons/school.png">
  <div class="content">
    Learn More
  </div>
</h2>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
```
```html
<h2 class="ui header">
  <img src="/images/avatar2/large/patrick.png" class="ui circular image">
  Patrick
</h2>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
```
```html
<h2 class="ui header">
  <img src="/images/icons/plugin.png">
  <div class="content">
    Plug-ins
    <div class="sub header">Check out our plug-in marketplace</div>
  </div>
</h2>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
```

#### Icon
A header may contain an icon
```html
<h2 class="ui header">
  <i class="plug icon"></i>
  <div class="content">
    Uptime Guarantee
  </div>
</h2>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
```
```html
<h2 class="ui header">
  <i class="settings icon"></i>
  <div class="content">
    Account Settings
    <div class="sub header">Manage your preferences</div>
  </div>
</h2>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
```

#### Subheader
Headers may contain subheaders
```html
<h2 class="ui header">
  Account Settings
  <div class="sub header">Manage your account settings and set e-mail preferences.</div>
</h2>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
```
```html
<h1 class="ui header">
  H1
  <div class="sub header">Sub Header</div>
</h1>
<h2 class="ui header">
  H2
  <div class="sub header">Sub Header</div>
</h2>
<h3 class="ui header">
  H3
  <div class="sub header">Sub Header</div>
</h3>
<h4 class="ui header">
  H4
  <div class="sub header">Sub Header</div>
</h4>
<h5 class="ui header">
  H5
  <div class="sub header">Sub Header</div>
</h5>
```

## States

#### Disabled
A header can show that it is inactive
```html
<div class="ui disabled header">
  Disabled Header
</div>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
```

## Variations

#### Dividing
A header can be formatted to divide itself from the content below it
```html
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
<h3 class="ui dividing header">
  Dividing Header
</h3>
<img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
```

#### Block
A header can be formatted to appear inside a content block
```html
<h3 class="ui block header">
  Block Header
</h3>
<img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
```

#### Attached
A header can be attached to other content, like a segment
```html
<h3 class="ui top attached header">
  Top Attached
</h3>
<div class="ui attached segment">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
<h3 class="ui attached header">
  Attached
</h3>
<div class="ui attached segment">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
<h3 class="ui bottom attached header">
  Bottom Attached
</h3>
```

#### Floating
A header can sit to the left or right of other content
```html
<div class="ui clearing segment">
  <h3 class="ui right floated header">
    Go Forward
  </h3>
  <h3 class="ui left floated header">
    Go Back
  </h3>
</div>
```

#### Text Alignment
A header can have its text aligned to a side
```html
<div class="ui segment">
  <h3 class="ui right aligned header">
    Right
  </h3>
  <h3 class="ui left aligned header">
    Left
  </h3>
  <h3 class="ui justified header">
    This should take up the full width even if only one line
  </h3>
  <h3 class="ui center aligned header">
    Center
  </h3>
</div>
```

#### Colored
A header can be formatted with different colors
```html
<h4 class="ui red header">Red</h4>
<h4 class="ui orange header">Orange</h4>
<h4 class="ui yellow header">Yellow</h4>
<h4 class="ui olive header">Olive</h4>
<h4 class="ui green header">Green</h4>
<h4 class="ui teal header">Teal</h4>
<h4 class="ui blue header">Blue</h4>
<h4 class="ui purple header">Purple</h4>
<h4 class="ui violet header">Violet</h4>
<h4 class="ui pink header">Pink</h4>
<h4 class="ui brown header">Brown</h4>
<h4 class="ui grey header">Grey</h4>
```

#### Inverted
A header can have its colors inverted for contrast
> Inverted headers use modified light versions of your site's color scheme that are adapted to have more contrast on dark background
```html
<div class="ui inverted segment">
  <h4 class="ui red inverted header">Red</h4>
  <h4 class="ui orange inverted header">Orange</h4>
  <h4 class="ui yellow inverted header">Yellow</h4>
  <h4 class="ui olive inverted header">Olive</h4>
  <h4 class="ui green inverted header">Green</h4>
  <h4 class="ui teal inverted header">Teal</h4>
  <h4 class="ui blue inverted header">Blue</h4>
  <h4 class="ui purple inverted header">Purple</h4>
  <h4 class="ui violet inverted header">Violet</h4>
  <h4 class="ui pink inverted header">Pink</h4>
  <h4 class="ui brown inverted header">Brown</h4>
  <h4 class="ui grey inverted header">Grey</h4>
</div>
```


## === icon.md ===

# Icon

An icon is a glyph used to represent something else

## Icon Set
An icon set contains an arbitrary number of glyphs
> Icons serve a very similar function to text in a page. In Semantic icons receive a special tag `<i>` which allow for an abbreviated markup when sitting along-side text.
> Semantic includes a complete port of [Font Awesome 5.0.8](https://fontawesome.com/) designed by the [FontAwesome](https://twitter.com/fontawesome) team for its standard icon set.

#### Accessibility
Icons can represent accessibility standards
```html
<i class="american sign language interpreting icon"></i>
<i class="assistive listening systems icon"></i>
<i class="audio description icon"></i>
<i class="blind icon"></i>
<i class="braille icon"></i>
<i class="closed captioning icon"></i>
<i class="closed captioning outline icon"></i>
<i class="deaf icon"></i>
<i class="low vision icon"></i>
<i class="phone volume icon"></i>
<i class="question circle icon"></i>
<i class="question circle outline icon"></i>
<i class="sign language icon"></i>
<i class="tty icon"></i>
<i class="universal access icon"></i>
<i class="wheelchair icon"></i>
```

#### Arrows
Icons can be used to indicate a direction
```html
<i class="angle double down icon"></i>
<i class="angle double left icon"></i>
<i class="angle double right icon"></i>
<i class="angle double up icon"></i>
<i class="angle down icon"></i>
<i class="angle left icon"></i>
<i class="angle right icon"></i>
<i class="angle up icon"></i>
<i class="arrow alternate circle down icon"></i>
<i class="arrow alternate circle down outline icon"></i>
<i class="arrow alternate circle left icon"></i>
<i class="arrow alternate circle left outline icon"></i>
<i class="arrow alternate circle right icon"></i>
<i class="arrow alternate circle right outline icon"></i>
<i class="arrow alternate circle up icon"></i>
<i class="arrow alternate circle up outline icon"></i>
<i class="arrow circle down icon"></i>
<i class="arrow circle left icon"></i>
<i class="arrow circle right icon"></i>
<i class="arrow circle up icon"></i>
<i class="arrow down icon"></i>
<i class="arrow left icon"></i>
<i class="arrow right icon"></i>
<i class="arrow up icon"></i>
<i class="arrows alternate icon"></i>
<i class="arrows alternate horizontal icon"></i>
<i class="arrows alternate vertical icon"></i>
<i class="caret down icon"></i>
<i class="caret left icon"></i>
<i class="caret right icon"></i>
<i class="caret square down icon"></i>
<i class="caret square down outline icon"></i>
<i class="caret square left icon"></i>
<i class="caret square left outline icon"></i>
<i class="caret square right icon"></i>
<i class="caret square right outline icon"></i>
<i class="caret square up icon"></i>
<i class="caret square up outline icon"></i>
<i class="caret up icon"></i>
<i class="cart arrow down icon"></i>
<i class="chart line icon"></i>
<i class="chevron circle down icon"></i>
<i class="chevron circle left icon"></i>
<i class="chevron circle right icon"></i>
<i class="chevron circle up icon"></i>
<i class="chevron down icon"></i>
<i class="chevron left icon"></i>
<i class="chevron right icon"></i>
<i class="chevron up icon"></i>
<i class="cloud download icon"></i>
<i class="cloud upload icon"></i>
<i class="download icon"></i>
<i class="exchange alternate icon"></i>
<i class="expand arrows alternate icon"></i>
<i class="external alternate icon"></i>
<i class="external square alternate icon"></i>
<i class="hand point down icon"></i>
<i class="hand point down outline icon"></i>
<i class="hand point left icon"></i>
<i class="hand point left outline icon"></i>
<i class="hand point right icon"></i>
<i class="hand point right outline icon"></i>
<i class="hand point up icon"></i>
<i class="hand point up outline icon"></i>
<i class="hand pointer icon"></i>
<i class="hand pointer outline icon"></i>
<i class="history icon"></i>
<i class="level down alternate icon"></i>
<i class="level up alternate icon"></i>
<i class="location arrow icon"></i>
<i class="long arrow alternate down icon"></i>
<i class="long arrow alternate left icon"></i>
<i class="long arrow alternate right icon"></i>
<i class="long arrow alternate up icon"></i>
<i class="mouse pointer icon"></i>
<i class="play icon"></i>
<i class="random icon"></i>
<i class="recycle icon"></i>
<i class="redo icon"></i>
<i class="redo alternate icon"></i>
<i class="reply icon"></i>
<i class="reply all icon"></i>
<i class="retweet icon"></i>
<i class="share icon"></i>
<i class="share square icon"></i>
<i class="share square outline icon"></i>
<i class="sign in alternate icon"></i>
<i class="sign out alternate icon"></i>
<i class="sort icon"></i>
<i class="sort alphabet down icon"></i>
<i class="sort alphabet up icon"></i>
<i class="sort amount down icon"></i>
<i class="sort amount up icon"></i>
<i class="sort down icon"></i>
<i class="sort numeric down icon"></i>
<i class="sort numeric up icon"></i>
<i class="sort up icon"></i>
<i class="sync icon"></i>
<i class="sync alternate icon"></i>
<i class="text height icon"></i>
<i class="text width icon"></i>
<i class="undo icon"></i>
<i class="undo alternate icon"></i>
<i class="upload icon"></i>
```

#### Audio & Video
Icons can be used to represent common ways to interact with audio and video
```html
<i class="audio description icon"></i>
<i class="backward icon"></i>
<i class="circle icon"></i>
<i class="circle outline icon"></i>
<i class="closed captioning icon"></i>
<i class="closed captioning outline icon"></i>
<i class="compress icon"></i>
<i class="eject icon"></i>
<i class="expand icon"></i>
<i class="expand arrows alternate icon"></i>
<i class="fast backward icon"></i>
<i class="fast forward icon"></i>
<i class="file audio icon"></i>
<i class="file audio outline icon"></i>
<i class="file video icon"></i>
<i class="file video outline icon"></i>
<i class="film icon"></i>
<i class="forward icon"></i>
<i class="headphones icon"></i>
<i class="microphone icon"></i>
<i class="microphone slash icon"></i>
<i class="music icon"></i>
<i class="pause icon"></i>
<i class="pause circle icon"></i>
<i class="pause circle outline icon"></i>
<i class="phone volume icon"></i>
<i class="play icon"></i>
<i class="play circle icon"></i>
<i class="play circle outline icon"></i>
<i class="podcast icon"></i>
<i class="random icon"></i>
<i class="redo icon"></i>
<i class="redo alternate icon"></i>
<i class="rss icon"></i>
<i class="rss square icon"></i>
<i class="step backward icon"></i>
<i class="step forward icon"></i>
<i class="stop icon"></i>
<i class="stop circle icon"></i>
<i class="stop circle outline icon"></i>
<i class="sync icon"></i>
<i class="sync alternate icon"></i>
<i class="undo icon"></i>
<i class="undo alternate icon"></i>
<i class="video icon"></i>
<i class="volume down icon"></i>
<i class="volume off icon"></i>
<i class="volume up icon"></i>
```

#### Business
Icons can be used to represent business and common business actions
```html
<i class="address book icon"></i>
<i class="address book outline icon"></i>
<i class="address card icon"></i>
<i class="address card outline icon"></i>
<i class="archive icon"></i>
<i class="balance scale icon"></i>
<i class="birthday cake icon"></i>
<i class="book icon"></i>
<i class="briefcase icon"></i>
<i class="building icon"></i>
<i class="building outline icon"></i>
<i class="bullhorn icon"></i>
<i class="bullseye icon"></i>
<i class="calculator icon"></i>
<i class="calendar icon"></i>
<i class="calendar outline icon"></i>
<i class="calendar alternate icon"></i>
<i class="calendar alternate outline icon"></i>
<i class="certificate icon"></i>
<i class="chart area icon"></i>
<i class="chart bar icon"></i>
<i class="chart bar outline icon"></i>
<i class="chart line icon"></i>
<i class="chart pie icon"></i>
<i class="clipboard icon"></i>
<i class="clipboard outline icon"></i>
<i class="coffee icon"></i>
<i class="columns icon"></i>
<i class="compass icon"></i>
<i class="compass outline icon"></i>
<i class="copy icon"></i>
<i class="copy outline icon"></i>
<i class="copyright icon"></i>
<i class="copyright outline icon"></i>
<i class="cut icon"></i>
<i class="edit icon"></i>
<i class="edit outline icon"></i>
<i class="envelope icon"></i>
<i class="envelope outline icon"></i>
<i class="envelope open icon"></i>
<i class="envelope open outline icon"></i>
<i class="envelope square icon"></i>
<i class="eraser icon"></i>
<i class="fax icon"></i>
<i class="file icon"></i>
<i class="file outline icon"></i>
<i class="file alternate icon"></i>
<i class="file alternate outline icon"></i>
<i class="folder icon"></i>
<i class="folder outline icon"></i>
<i class="folder open icon"></i>
<i class="folder open outline icon"></i>
<i class="globe icon"></i>
<i class="industry icon"></i>
<i class="paperclip icon"></i>
<i class="paste icon"></i>
<i class="pen square icon"></i>
<i class="pencil alternate icon"></i>
<i class="percent icon"></i>
<i class="phone icon"></i>
<i class="phone square icon"></i>
<i class="phone volume icon"></i>
<i class="registered icon"></i>
<i class="registered outline icon"></i>
<i class="save icon"></i>
<i class="save outline icon"></i>
<i class="sitemap icon"></i>
<i class="sticky note icon"></i>
<i class="sticky note outline icon"></i>
<i class="suitcase icon"></i>
<i class="table icon"></i>
<i class="tag icon"></i>
<i class="tags icon"></i>
<i class="tasks icon"></i>
<i class="thumbtack icon"></i>
<i class="trademark icon"></i>
```

#### Chess
Icons which represent the game chess
```html
<i class="chess icon"></i>
<i class="chess bishop icon"></i>
<i class="chess board icon"></i>
<i class="chess king icon"></i>
<i class="chess knight icon"></i>
<i class="chess pawn icon"></i>
<i class="chess queen icon"></i>
<i class="chess rook icon"></i>
<i class="square full icon"></i>
```

#### Code
Icons can represent programming and programming tools
```html
<i class="archive icon"></i>
<i class="barcode icon"></i>
<i class="bath icon"></i>
<i class="bug icon"></i>
<i class="code icon"></i>
<i class="code branch icon"></i>
<i class="coffee icon"></i>
<i class="file icon"></i>
<i class="file outline icon"></i>
<i class="file alternate icon"></i>
<i class="file alternate outline icon"></i>
<i class="file code icon"></i>
<i class="file code outline icon"></i>
<i class="filter icon"></i>
<i class="fire extinguisher icon"></i>
<i class="folder icon"></i>
<i class="folder outline icon"></i>
<i class="folder open icon"></i>
<i class="folder open outline icon"></i>
<i class="keyboard icon"></i>
<i class="keyboard outline icon"></i>
<i class="microchip icon"></i>
<i class="qrcode icon"></i>
<i class="shield alternate icon"></i>
<i class="sitemap icon"></i>
<i class="terminal icon"></i>
<i class="user secret icon"></i>
<i class="window close icon"></i>
<i class="window close outline icon"></i>
<i class="window maximize icon"></i>
<i class="window maximize outline icon"></i>
<i class="window minimize icon"></i>
<i class="window minimize outline icon"></i>
<i class="window restore icon"></i>
<i class="window restore outline icon"></i>
```

#### Communication
Icons which represent common ways of communication
```html
<i class="address book icon"></i>
<i class="address book outline icon"></i>
<i class="address card icon"></i>
<i class="address card outline icon"></i>
<i class="american sign language interpreting icon"></i>
<i class="assistive listening systems icon"></i>
<i class="at icon"></i>
<i class="bell icon"></i>
<i class="bell outline icon"></i>
<i class="bell slash icon"></i>
<i class="bell slash outline icon"></i>
<i class="bullhorn icon"></i>
<i class="comment icon"></i>
<i class="comment outline icon"></i>
<i class="comment alternate icon"></i>
<i class="comment alternate outline icon"></i>
<i class="comments icon"></i>
<i class="comments outline icon"></i>
<i class="envelope icon"></i>
<i class="envelope outline icon"></i>
<i class="envelope open icon"></i>
<i class="envelope open outline icon"></i>
<i class="envelope square icon"></i>
<i class="fax icon"></i>
<i class="inbox icon"></i>
<i class="language icon"></i>
<i class="microphone icon"></i>
<i class="microphone slash icon"></i>
<i class="mobile icon"></i>
<i class="mobile alternate icon"></i>
<i class="paper plane icon"></i>
<i class="paper plane outline icon"></i>
<i class="phone icon"></i>
<i class="phone square icon"></i>
<i class="phone volume icon"></i>
<i class="rss icon"></i>
<i class="rss square icon"></i>
<i class="tty icon"></i>
<i class="wifi icon"></i>
```

#### Computers
Icons can represent computing devices, or types of content found on a computer
```html
<i class="desktop icon"></i>
<i class="download icon"></i>
<i class="hdd icon"></i>
<i class="hdd outline icon"></i>
<i class="headphones icon"></i>
<i class="keyboard icon"></i>
<i class="keyboard outline icon"></i>
<i class="laptop icon"></i>
<i class="microchip icon"></i>
<i class="mobile icon"></i>
<i class="mobile alternate icon"></i>
<i class="plug icon"></i>
<i class="power off icon"></i>
<i class="print icon"></i>
<i class="save icon"></i>
<i class="save outline icon"></i>
<i class="server icon"></i>
<i class="tablet icon"></i>
<i class="tablet alternate icon"></i>
<i class="tv icon"></i>
<i class="upload icon"></i>
```

#### Currency
Icons can represent units of currency
```html
<i class="dollar sign icon"></i>
<i class="euro sign icon"></i>
<i class="lira sign icon"></i>
<i class="money bill alternate icon"></i>
<i class="money bill alternate outline icon"></i>
<i class="pound sign icon"></i>
<i class="ruble sign icon"></i>
<i class="rupee sign icon"></i>
<i class="shekel sign icon"></i>
<i class="won sign icon"></i>
<i class="yen sign icon"></i>
```

#### Date & Time
Icons that represent common ways of showing date and time
```html
<i class="bell icon"></i>
<i class="bell outline icon"></i>
<i class="bell slash icon"></i>
<i class="bell slash outline icon"></i>
<i class="calendar icon"></i>
<i class="calendar outline icon"></i>
<i class="calendar alternate icon"></i>
<i class="calendar alternate outline icon"></i>
<i class="calendar check icon"></i>
<i class="calendar check outline icon"></i>
<i class="calendar minus icon"></i>
<i class="calendar minus outline icon"></i>
<i class="calendar plus icon"></i>
<i class="calendar plus outline icon"></i>
<i class="calendar times icon"></i>
<i class="calendar times outline icon"></i>
<i class="clock icon"></i>
<i class="clock outline icon"></i>
<i class="hourglass icon"></i>
<i class="hourglass outline icon"></i>
<i class="hourglass end icon"></i>
<i class="hourglass half icon"></i>
<i class="hourglass start icon"></i>
<i class="stopwatch icon"></i>
```

#### Design
Icons can represent common design related symbols or techniques
```html
<i class="adjust icon"></i>
<i class="clone icon"></i>
<i class="clone outline icon"></i>
<i class="copy icon"></i>
<i class="copy outline icon"></i>
<i class="crop icon"></i>
<i class="crosshairs icon"></i>
<i class="cut icon"></i>
<i class="edit icon"></i>
<i class="edit outline icon"></i>
<i class="eraser icon"></i>
<i class="eye icon"></i>
<i class="eye dropper icon"></i>
<i class="eye slash icon"></i>
<i class="eye slash outline icon"></i>
<i class="object group icon"></i>
<i class="object group outline icon"></i>
<i class="object ungroup icon"></i>
<i class="object ungroup outline icon"></i>
<i class="paint brush icon"></i>
<i class="paste icon"></i>
<i class="pencil alternate icon"></i>
<i class="save icon"></i>
<i class="save outline icon"></i>
<i class="tint icon"></i>
```

#### Editors
Icons can represent text editors and common editor actions
```html
<i class="align center icon"></i>
<i class="align justify icon"></i>
<i class="align left icon"></i>
<i class="align right icon"></i>
<i class="bold icon"></i>
<i class="clipboard icon"></i>
<i class="clipboard outline icon"></i>
<i class="clone icon"></i>
<i class="clone outline icon"></i>
<i class="columns icon"></i>
<i class="copy icon"></i>
<i class="copy outline icon"></i>
<i class="cut icon"></i>
<i class="edit icon"></i>
<i class="edit outline icon"></i>
<i class="eraser icon"></i>
<i class="file icon"></i>
<i class="file outline icon"></i>
<i class="file alternate icon"></i>
<i class="file alternate outline icon"></i>
<i class="font icon"></i>
<i class="heading icon"></i>
<i class="i cursor icon"></i>
<i class="indent icon"></i>
<i class="italic icon"></i>
<i class="linkify icon"></i>
<i class="list icon"></i>
<i class="list alternate icon"></i>
<i class="list alternate outline icon"></i>
<i class="list ol icon"></i>
<i class="list ul icon"></i>
<i class="outdent icon"></i>
<i class="paper plane icon"></i>
<i class="paper plane outline icon"></i>
<i class="paperclip icon"></i>
<i class="paragraph icon"></i>
<i class="paste icon"></i>
<i class="pencil alternate icon"></i>
<i class="print icon"></i>
<i class="quote left icon"></i>
<i class="quote right icon"></i>
<i class="redo icon"></i>
<i class="redo alternate icon"></i>
<i class="reply icon"></i>
<i class="reply all icon"></i>
<i class="share icon"></i>
<i class="strikethrough icon"></i>
<i class="subscript icon"></i>
<i class="superscript icon"></i>
<i class="sync icon"></i>
<i class="sync alternate icon"></i>
<i class="table icon"></i>
<i class="tasks icon"></i>
<i class="text height icon"></i>
<i class="text width icon"></i>
<i class="th icon"></i>
<i class="th large icon"></i>
<i class="th list icon"></i>
<i class="trash icon"></i>
<i class="trash alternate icon"></i>
<i class="trash alternate outline icon"></i>
<i class="underline icon"></i>
<i class="undo icon"></i>
<i class="undo alternate icon"></i>
<i class="unlink icon"></i>
```

#### Files
Icons can represent elements of a computer and its file system
```html
<i class="archive icon"></i>
<i class="clone icon"></i>
<i class="clone outline icon"></i>
<i class="copy icon"></i>
<i class="copy outline icon"></i>
<i class="cut icon"></i>
<i class="file icon"></i>
<i class="file outline icon"></i>
<i class="file alternate icon"></i>
<i class="file alternate outline icon"></i>
<i class="file archive icon"></i>
<i class="file archive outline icon"></i>
<i class="file audio icon"></i>
<i class="file audio outline icon"></i>
<i class="file code icon"></i>
<i class="file code outline icon"></i>
<i class="file excel icon"></i>
<i class="file excel outline icon"></i>
<i class="file image icon"></i>
<i class="file image outline icon"></i>
<i class="file pdf icon"></i>
<i class="file pdf outline icon"></i>
<i class="file powerpoint icon"></i>
<i class="file powerpoint outline icon"></i>
<i class="file video icon"></i>
<i class="file video outline icon"></i>
<i class="file word icon"></i>
<i class="file word outline icon"></i>
<i class="folder icon"></i>
<i class="folder outline icon"></i>
<i class="folder open icon"></i>
<i class="folder open outline icon"></i>
<i class="paste icon"></i>
<i class="save icon"></i>
<i class="save outline icon"></i>
<i class="sticky note icon"></i>
<i class="sticky note outline icon"></i>
```

#### Genders
Icons can represent genders or types of sexuality
```html
<i class="genderless icon"></i>
<i class="mars icon"></i>
<i class="mars double icon"></i>
<i class="mars stroke icon"></i>
<i class="mars stroke horizontal icon"></i>
<i class="mars stroke vertical icon"></i>
<i class="mercury icon"></i>
<i class="neuter icon"></i>
<i class="transgender icon"></i>
<i class="transgender alternate icon"></i>
<i class="venus icon"></i>
<i class="venus double icon"></i>
<i class="venus mars icon"></i>
```

#### Hands & Gestures
Icons can represent hand signals and gestures
```html
<i class="hand lizard icon"></i>
<i class="hand lizard outline icon"></i>
<i class="hand paper icon"></i>
<i class="hand paper outline icon"></i>
<i class="hand peace icon"></i>
<i class="hand peace outline icon"></i>
<i class="hand point down icon"></i>
<i class="hand point down outline icon"></i>
<i class="hand point left icon"></i>
<i class="hand point left outline icon"></i>
<i class="hand point right icon"></i>
<i class="hand point right outline icon"></i>
<i class="hand point up icon"></i>
<i class="hand point up outline icon"></i>
<i class="hand pointer icon"></i>
<i class="hand pointer outline icon"></i>
<i class="hand rock icon"></i>
<i class="hand rock outline icon"></i>
<i class="hand scissors icon"></i>
<i class="hand scissors outline icon"></i>
<i class="hand spock icon"></i>
<i class="hand spock outline icon"></i>
<i class="handshake icon"></i>
<i class="handshake outline icon"></i>
<i class="thumbs down icon"></i>
<i class="thumbs down outline icon"></i>
<i class="thumbs up icon"></i>
<i class="thumbs up outline icon"></i>
```

#### Health
Icons which represent common health symbols
```html
<i class="ambulance icon"></i>
<i class="h square icon"></i>
<i class="heart icon"></i>
<i class="heart outline icon"></i>
<i class="heartbeat icon"></i>
<i class="hospital icon"></i>
<i class="hospital outline icon"></i>
<i class="medkit icon"></i>
<i class="plus square icon"></i>
<i class="plus square outline icon"></i>
<i class="stethoscope icon"></i>
<i class="user md icon"></i>
<i class="wheelchair icon"></i>
```

#### Images
Icons that represent common image symbols and actions
```html
<i class="adjust icon"></i>
<i class="bolt icon"></i>
<i class="camera icon"></i>
<i class="camera retro icon"></i>
<i class="clone icon"></i>
<i class="clone outline icon"></i>
<i class="compress icon"></i>
<i class="expand icon"></i>
<i class="eye icon"></i>
<i class="eye dropper icon"></i>
<i class="eye slash icon"></i>
<i class="eye slash outline icon"></i>
<i class="file image icon"></i>
<i class="file image outline icon"></i>
<i class="film icon"></i>
<i class="id badge icon"></i>
<i class="id badge outline icon"></i>
<i class="id card icon"></i>
<i class="id card outline icon"></i>
<i class="image icon"></i>
<i class="image outline icon"></i>
<i class="images icon"></i>
<i class="images outline icon"></i>
<i class="sliders horizontal icon"></i>
<i class="tint icon"></i>
```

#### Interfaces
Icons can represent common actions a user can take or use
```html
<i class="ban icon"></i>
<i class="barcode icon"></i>
<i class="bars icon"></i>
<i class="beer icon"></i>
<i class="bell icon"></i>
<i class="bell outline icon"></i>
<i class="bell slash icon"></i>
<i class="bell slash outline icon"></i>
<i class="bug icon"></i>
<i class="bullhorn icon"></i>
<i class="bullseye icon"></i>
<i class="calculator icon"></i>
<i class="calendar icon"></i>
<i class="calendar outline icon"></i>
<i class="calendar alternate icon"></i>
<i class="calendar alternate outline icon"></i>
<i class="calendar check icon"></i>
<i class="calendar check outline icon"></i>
<i class="calendar minus icon"></i>
<i class="calendar minus outline icon"></i>
<i class="calendar plus icon"></i>
<i class="calendar plus outline icon"></i>
<i class="calendar times icon"></i>
<i class="calendar times outline icon"></i>
<i class="certificate icon"></i>
<i class="check icon"></i>
<i class="check circle icon"></i>
<i class="check circle outline icon"></i>
<i class="check square icon"></i>
<i class="check square outline icon"></i>
<i class="circle icon"></i>
<i class="circle outline icon"></i>
<i class="clipboard icon"></i>
<i class="clipboard outline icon"></i>
<i class="clone icon"></i>
<i class="clone outline icon"></i>
<i class="cloud icon"></i>
<i class="cloud download icon"></i>
<i class="cloud upload icon"></i>
<i class="coffee icon"></i>
<i class="cog icon"></i>
<i class="cogs icon"></i>
<i class="copy icon"></i>
<i class="copy outline icon"></i>
<i class="cut icon"></i>
<i class="database icon"></i>
<i class="dot circle icon"></i>
<i class="dot circle outline icon"></i>
<i class="download icon"></i>
<i class="edit icon"></i>
<i class="edit outline icon"></i>
<i class="ellipsis horizontal icon"></i>
<i class="ellipsis vertical icon"></i>
<i class="envelope icon"></i>
<i class="envelope outline icon"></i>
<i class="envelope open icon"></i>
<i class="envelope open outline icon"></i>
<i class="eraser icon"></i>
<i class="exclamation icon"></i>
<i class="exclamation circle icon"></i>
<i class="exclamation triangle icon"></i>
<i class="external alternate icon"></i>
<i class="external square alternate icon"></i>
<i class="eye icon"></i>
<i class="eye slash icon"></i>
<i class="eye slash outline icon"></i>
<i class="file icon"></i>
<i class="file outline icon"></i>
<i class="file alternate icon"></i>
<i class="file alternate outline icon"></i>
<i class="filter icon"></i>
<i class="flag icon"></i>
<i class="flag outline icon"></i>
<i class="flag checkered icon"></i>
<i class="folder icon"></i>
<i class="folder outline icon"></i>
<i class="folder open icon"></i>
<i class="folder open outline icon"></i>
<i class="frown icon"></i>
<i class="frown outline icon"></i>
<i class="hashtag icon"></i>
<i class="heart icon"></i>
<i class="heart outline icon"></i>
<i class="history icon"></i>
<i class="home icon"></i>
<i class="i cursor icon"></i>
<i class="info icon"></i>
<i class="info circle icon"></i>
<i class="language icon"></i>
<i class="magic icon"></i>
<i class="meh icon"></i>
<i class="meh outline icon"></i>
<i class="microphone icon"></i>
<i class="microphone slash icon"></i>
<i class="minus icon"></i>
<i class="minus circle icon"></i>
<i class="minus square icon"></i>
<i class="minus square outline icon"></i>
<i class="paste icon"></i>
<i class="pencil alternate icon"></i>
<i class="plus icon"></i>
<i class="plus circle icon"></i>
<i class="plus square icon"></i>
<i class="plus square outline icon"></i>
<i class="qrcode icon"></i>
<i class="question icon"></i>
<i class="question circle icon"></i>
<i class="question circle outline icon"></i>
<i class="quote left icon"></i>
<i class="quote right icon"></i>
<i class="redo icon"></i>
<i class="redo alternate icon"></i>
<i class="reply icon"></i>
<i class="reply all icon"></i>
<i class="rss icon"></i>
<i class="rss square icon"></i>
<i class="save icon"></i>
<i class="save outline icon"></i>
<i class="search icon"></i>
<i class="search minus icon"></i>
<i class="search plus icon"></i>
<i class="share icon"></i>
<i class="share alternate icon"></i>
<i class="share alternate square icon"></i>
<i class="share square icon"></i>
<i class="share square outline icon"></i>
<i class="shield alternate icon"></i>
<i class="sign in alternate icon"></i>
<i class="sign out alternate icon"></i>
<i class="signal icon"></i>
<i class="sitemap icon"></i>
<i class="sliders horizontal icon"></i>
<i class="smile icon"></i>
<i class="smile outline icon"></i>
<i class="sort icon"></i>
<i class="sort alphabet down icon"></i>
<i class="sort alphabet up icon"></i>
<i class="sort amount down icon"></i>
<i class="sort amount up icon"></i>
<i class="sort down icon"></i>
<i class="sort numeric down icon"></i>
<i class="sort numeric up icon"></i>
<i class="sort up icon"></i>
<i class="star icon"></i>
<i class="star outline icon"></i>
<i class="star half icon"></i>
<i class="star half outline icon"></i>
<i class="sync icon"></i>
<i class="sync alternate icon"></i>
<i class="thumbs down icon"></i>
<i class="thumbs down outline icon"></i>
<i class="thumbs up icon"></i>
<i class="thumbs up outline icon"></i>
<i class="times icon"></i>
<i class="times circle icon"></i>
<i class="times circle outline icon"></i>
<i class="toggle off icon"></i>
<i class="toggle on icon"></i>
<i class="trash icon"></i>
<i class="trash alternate icon"></i>
<i class="trash alternate outline icon"></i>
<i class="trophy icon"></i>
<i class="undo icon"></i>
<i class="undo alternate icon"></i>
<i class="upload icon"></i>
<i class="user icon"></i>
<i class="user outline icon"></i>
<i class="user circle icon"></i>
<i class="user circle outline icon"></i>
<i class="wifi icon"></i>
```

#### Logistics
Icons can represent common logistic activity
```html
<i class="box icon"></i>
<i class="boxes icon"></i>
<i class="clipboard check icon"></i>
<i class="clipboard list icon"></i>
<i class="dolly icon"></i>
<i class="dolly flatbed icon"></i>
<i class="pallet icon"></i>
<i class="shipping fast icon"></i>
<i class="truck icon"></i>
<i class="warehouse icon"></i>
```

#### Maps
Icons can be used to represent elements on a map
```html
<i class="ambulance icon"></i>
<i class="anchor icon"></i>
<i class="balance scale icon"></i>
<i class="bath icon"></i>
<i class="bed icon"></i>
<i class="beer icon"></i>
<i class="bell icon"></i>
<i class="bell outline icon"></i>
<i class="bell slash icon"></i>
<i class="bell slash outline icon"></i>
<i class="bicycle icon"></i>
<i class="binoculars icon"></i>
<i class="birthday cake icon"></i>
<i class="blind icon"></i>
<i class="bomb icon"></i>
<i class="book icon"></i>
<i class="bookmark icon"></i>
<i class="bookmark outline icon"></i>
<i class="briefcase icon"></i>
<i class="building icon"></i>
<i class="building outline icon"></i>
<i class="car icon"></i>
<i class="coffee icon"></i>
<i class="crosshairs icon"></i>
<i class="dollar sign icon"></i>
<i class="eye icon"></i>
<i class="eye slash icon"></i>
<i class="eye slash outline icon"></i>
<i class="fighter jet icon"></i>
<i class="fire icon"></i>
<i class="fire extinguisher icon"></i>
<i class="flag icon"></i>
<i class="flag outline icon"></i>
<i class="flag checkered icon"></i>
<i class="flask icon"></i>
<i class="gamepad icon"></i>
<i class="gavel icon"></i>
<i class="gift icon"></i>
<i class="glass martini icon"></i>
<i class="globe icon"></i>
<i class="graduation cap icon"></i>
<i class="h square icon"></i>
<i class="heart icon"></i>
<i class="heart outline icon"></i>
<i class="heartbeat icon"></i>
<i class="home icon"></i>
<i class="hospital icon"></i>
<i class="hospital outline icon"></i>
<i class="image icon"></i>
<i class="image outline icon"></i>
<i class="images icon"></i>
<i class="images outline icon"></i>
<i class="industry icon"></i>
<i class="info icon"></i>
<i class="info circle icon"></i>
<i class="key icon"></i>
<i class="leaf icon"></i>
<i class="lemon icon"></i>
<i class="lemon outline icon"></i>
<i class="life ring icon"></i>
<i class="life ring outline icon"></i>
<i class="lightbulb icon"></i>
<i class="lightbulb outline icon"></i>
<i class="location arrow icon"></i>
<i class="low vision icon"></i>
<i class="magnet icon"></i>
<i class="male icon"></i>
<i class="map icon"></i>
<i class="map outline icon"></i>
<i class="map marker icon"></i>
<i class="map marker alternate icon"></i>
<i class="map pin icon"></i>
<i class="map signs icon"></i>
<i class="medkit icon"></i>
<i class="money bill alternate icon"></i>
<i class="money bill alternate outline icon"></i>
<i class="motorcycle icon"></i>
<i class="music icon"></i>
<i class="newspaper icon"></i>
<i class="newspaper outline icon"></i>
<i class="paw icon"></i>
<i class="phone icon"></i>
<i class="phone square icon"></i>
<i class="phone volume icon"></i>
<i class="plane icon"></i>
<i class="plug icon"></i>
<i class="plus icon"></i>
<i class="plus square icon"></i>
<i class="plus square outline icon"></i>
<i class="print icon"></i>
<i class="recycle icon"></i>
<i class="road icon"></i>
<i class="rocket icon"></i>
<i class="search icon"></i>
<i class="search minus icon"></i>
<i class="search plus icon"></i>
<i class="ship icon"></i>
<i class="shopping bag icon"></i>
<i class="shopping basket icon"></i>
<i class="shopping cart icon"></i>
<i class="shower icon"></i>
<i class="street view icon"></i>
<i class="subway icon"></i>
<i class="suitcase icon"></i>
<i class="tag icon"></i>
<i class="tags icon"></i>
<i class="taxi icon"></i>
<i class="thumbtack icon"></i>
<i class="ticket alternate icon"></i>
<i class="tint icon"></i>
<i class="train icon"></i>
<i class="tree icon"></i>
<i class="trophy icon"></i>
<i class="truck icon"></i>
<i class="tty icon"></i>
<i class="umbrella icon"></i>
<i class="university icon"></i>
<i class="utensil spoon icon"></i>
<i class="wheelchair icon"></i>
<i class="wifi icon"></i>
<i class="wrench icon"></i>
```


## === image.md ===

# Image

An image is a graphic representation of something

## Types

#### Image
An image
> Unless a size is specified, images will use the original dimensions of the image up to the size of its container.
> You can specify an `img` or `svg` as a `ui image` or use a child element.
```html
<img class="ui small image" src="/images/wireframe/image.png">
```
```html
<div class="ui small image">
  <img src="/images/wireframe/image.png">
</div>
```
```html
<div class="ui small image">
  <svg width="150" height="150">
    <image xlink:href="/images/wireframe/image.png" x="0" y="0" width="100%" height="100%"></image>
  </svg>
</div>
```

#### Image Link
An image can be formatted to link to other content
```html
<a href="http://google.com" class="ui medium image">
  <img src="/images/wireframe/image-text.png">
</a>
```

## States

#### Hidden
An image can be hidden
```html
<img class="hidden ui image" src="/images/wireframe/image.png">
```

#### Disabled
An image can show that it is disabled and cannot be selected
```html
<img class="disabled medium ui image" src="/images/wireframe/image.png">
```

## Variations

#### Avatar
An image may be formatted to appear inline with text as an avatar
```html
<img class="ui avatar image" src="/images/wireframe/square-image.png">
<span>Username</span>
```

#### Bordered
An image may include a border to emphasize the edges of white or transparent content
```html
<img class="ui medium bordered image" src="/images/wireframe/white-image.png">
```

#### Fluid
An image can take up the width of its container
```html
<img class="ui fluid image" src="/images/wireframe/image.png">
```

#### Rounded
An image may appear rounded
```html
<img class="ui medium rounded image" src="/images/wireframe/square-image.png">
```

#### Circular
An image may appear circular
```html
<img class="ui medium circular image" src="/images/wireframe/square-image.png">
```

#### Vertically Aligned
An image can specify its vertical alignment
```html
<img class="ui top aligned tiny image" src="/images/wireframe/square-image.png">
<span>Top Aligned</span>
<div class="ui divider"></div>
<img class="ui middle aligned tiny image" src="/images/wireframe/square-image.png">
<span>Middle Aligned</span>
<div class="ui divider"></div>
<img class="ui bottom aligned tiny image" src="/images/wireframe/square-image.png">
<span>Bottom Aligned</span>
```

#### Centered
An image can appear centered in a content block
```html
<div class="ui segment">
  <img class="ui centered medium image" src="/images/wireframe/image.png">
  <p>Te eum doming eirmod, nominati pertinacia argumentum ad his. Ex eam alia facete scriptorem, est autem aliquip detraxit at. Usu ocurreret referrentur at, cu epicurei appellantur vix. Cum ea laoreet recteque electram, eos choro alterum definiebas in. Vim dolorum definiebas an. Mei ex natum rebum iisque.</p>
  <p>Audiam quaerendum eu sea, pro omittam definiebas ex. Te est latine definitiones. Quot wisi nulla ex duo. Vis sint solet expetenda ne, his te phaedrum referrentur consectetuer. Id vix fabulas oporteat, ei quo vide phaedrum, vim vivendum maiestatis in.</p>
  <img class="ui small centered image" src="/images/wireframe/text-image.png">
  <p>Eu quo homero blandit intellegebat. Incorrupte consequuntur mei id. Mei ut facer dolores adolescens, no illum aperiri quo, usu odio brute at. Qui te porro electram, ea dico facete utroque quo. Populo quodsi te eam, wisi everti eos ex, eum elitr altera utamur at. Quodsi convenire mnesarchum eu per, quas minimum postulant per id.</p>
</div>
```

#### Spaced
An image can specify that it needs an additional spacing to separate it from nearby content

```html
<div class="ui segment">
  <p>Te eum doming eirmod, nominati pertinacia <img class="ui mini spaced image" src="/images/wireframe/image.png"> argumentum ad his. Ex eam alia facete scriptorem, est autem aliquip detraxit at. Usu ocurreret referrentur at, cu epicurei appellantur vix. Cum ea laoreet recteque electram, eos choro alterum definiebas in. Vim dolorum definiebas an. Mei ex natum rebum iisque.</p>
</div>
```
```html
<p><img class="ui mini right spaced image" src="/images/wireframe/image.png">Audiam quaerendum eu sea, pro omittam definiebas ex. Te est latine definitiones. Quot wisi nulla ex duo. Vis sint solet expetenda ne, his te phaedrum referrentur consectetuer. Id vix fabulas oporteat, ei quo vide phaedrum, vim vivendum maiestatis in.</p>

<p>Eu quo homero blandit intellegebat. Incorrupte consequuntur mei id. Mei ut facer dolores adolescens, no illum aperiri quo, usu odio brute at. Qui te porro electram, ea dico facete utroque quo. Populo quodsi te eam, wisi everti eos ex, eum elitr altera utamur at. Quodsi convenire mnesarchum eu per, quas minimum postulant per id.<img class="ui mini left spaced image" src="/images/wireframe/image.png"></p>
```

#### Floated
An image can sit to the left or right of other content
```html
<div class="ui segment">
  <img class="ui small left floated image" src="/images/wireframe/text-image.png">
  <p>Te eum doming eirmod, nominati pertinacia argumentum ad his. Ex eam alia facete scriptorem, est autem aliquip detraxit at. Usu ocurreret referrentur at, cu epicurei appellantur vix. Cum ea laoreet recteque electram, eos choro alterum definiebas in. Vim dolorum definiebas an. Mei ex natum rebum iisque.</p>
  <img class="ui small right floated image" src="/images/wireframe/text-image.png">
  <p>Audiam quaerendum eu sea, pro omittam definiebas ex. Te est latine definitiones. Quot wisi nulla ex duo. Vis sint solet expetenda ne, his te phaedrum referrentur consectetuer. Id vix fabulas oporteat, ei quo vide phaedrum, vim vivendum maiestatis in.</p>

  <p>Eu quo homero blandit intellegebat. Incorrupte consequuntur mei id. Mei ut facer dolores adolescens, no illum aperiri quo, usu odio brute at. Qui te porro electram, ea dico facete utroque quo. Populo quodsi te eam, wisi everti eos ex, eum elitr altera utamur at. Quodsi convenire mnesarchum eu per, quas minimum postulant per id.</p>
</div>
```

#### Size
An image may appear at different sizes
> Semantic uses arbitrary default values for image sizes from mini to massive. It is recommended to update these with values used in your project in `image.variables`.

| Class Name | Size |
|---|---|
| Mini | 35px |
| Tiny | 80px |
| Small | 150px |
| Medium | 300px |
| Large | 450px |
| Big | 600px |
| Huge | 800px |
| Massive | 960px |

```html
<img class="ui mini image" src="/images/wireframe/image.png">
<div class="ui hidden divider"></div>
<img class="ui tiny image" src="/images/wireframe/image.png">
<div class="ui hidden divider"></div>
<img class="ui small image" src="/images/wireframe/image.png">
<div class="ui hidden divider"></div>
<img class="ui medium image" src="/images/wireframe/image.png">
```
```html
<img class="ui mini image" src="/images/wireframe/image.png">
<img class="ui tiny image" src="/images/wireframe/image.png">
<img class="ui small image" src="/images/wireframe/image.png">
<img class="ui medium image" src="/images/wireframe/image.png">
<img class="ui large image" src="/images/wireframe/image.png">
<img class="ui big image" src="/images/wireframe/image.png">
<img class="ui huge image" src="/images/wireframe/image.png">
<img class="ui massive image" src="/images/wireframe/image.png">
```

## Groups

#### Size
A group of images can be formatted to have the same size.
```html
<div class="ui tiny images">
  <img class="ui image" src="/images/wireframe/image.png">
  <img class="ui image" src="/images/wireframe/image.png">
  <img class="ui image" src="/images/wireframe/image.png">
  <img class="ui image" src="/images/wireframe/image.png">
</div>
```
```html
<div class="ui small images">
  <img src="/images/wireframe/image.png">
  <img src="/images/wireframe/image.png">
  <img src="/images/wireframe/image.png">
  <img src="/images/wireframe/image.png">
</div>
```


## === input.md ===

# Input

An input is a field used to elicit a response from a user

## Types

#### Input
A standard input
```html
<div class="ui input">
  <input type="text" placeholder="Search...">
</div>
```

## States

#### Focus
An input field can show a user is currently interacting with it
```html
<div class="ui input focus">
  <input type="text" placeholder="Search...">
</div>
```

#### Loading
An icon input field can show that it is currently loading data
> Loading inputs automatically modify the input's icon on loading state to show loading indication
```html
<div class="ui left icon input loading">
  <input type="text" placeholder="Search...">
  <i class="search icon"></i>
</div>
```
```html
<div class="ui icon input loading">
  <input type="text" placeholder="Search...">
  <i class="search icon"></i>
</div>
```

#### Disabled
An input field can show that it is disabled
```html
<div class="ui disabled input">
  <input type="text" placeholder="Search...">
</div>
```
```html
<div class="ui disabled icon input">
  <i class="search icon"></i>
  <input type="text" placeholder="Search...">
</div>
```
```html
<div class="ui input">
  <input type="text" placeholder="Search..." disabled>
</div>
```

#### Error
An input field can show the data contains errors
```html
<div class="ui input error">
  <input type="text" placeholder="Search...">
</div>
```

## Variations

#### Icon
An input can be formatted with an icon
> Input icons do not receive `pointer-events` unless a `link icon` is used.
```html
<div class="ui icon input">
  <input type="text" placeholder="Search...">
  <i class="search icon"></i>
</div>
```
```html
<div class="ui left icon input">
  <input type="text" placeholder="Search users...">
  <i class="users icon"></i>
</div>
```
```html
<div class="ui icon input">
  <input type="text" placeholder="Search...">
  <i class="circular search link icon"></i>
</div>
```
```html
<div class="ui icon input">
  <input type="text" placeholder="Search...">
  <i class="inverted circular search link icon"></i>
</div>
```

#### Labeled
An input can be formatted with a label
```html
<div class="ui labeled input">
  <div class="ui label">
    http://
  </div>
  <input type="text" placeholder="mysite.com">
</div>
```
```html
<div class="ui right labeled input">
  <input type="text" placeholder="Find domain">
  <div class="ui dropdown label">
    <div class="text">.com</div>
    <i class="dropdown icon"></i>
    <div class="menu">
      <div class="item">.com</div>
      <div class="item">.net</div>
      <div class="item">.org</div>
    </div>
  </div>
</div>
```
```html
<div class="ui right labeled input">
  <input type="text" placeholder="Enter weight..">
  <div class="ui basic label">
    kg
  </div>
</div>
```
```html
<div class="ui right labeled input">
  <label for="amount" class="ui label">$</label>
  <input type="text" placeholder="Amount" id="amount">
  <div class="ui basic label">.00</div>
</div>
```
```html
<div class="ui right labeled left icon input">
  <i class="tags icon"></i>
  <input type="text" placeholder="Enter tags">
  <a class="ui tag label">
    Add Tag
  </a>
</div>
```
```html
<div class="ui left corner labeled input">
  <input type="text" placeholder="Search...">
  <div class="ui left corner label">
    <i class="asterisk icon"></i>
  </div>
</div>
```
```html
<div class="ui corner labeled input">
  <input type="text" placeholder="Search...">
  <div class="ui corner label">
    <i class="asterisk icon"></i>
  </div>
</div>
```

#### Action
An input can be formatted to alert the user to an action they may perform
```html
<div class="ui action input">
  <input type="text" placeholder="Search...">
  <button class="ui button">Search</button>
</div>
```
```html
<div class="ui left action input">
  <button class="ui teal labeled icon button">
    <i class="cart icon"></i>
    Checkout
  </button>
  <input type="text" value="$52.03">
</div>
```
```html
<div class="ui right action left icon input">
  <i class="search icon"></i>
  <input type="text" placeholder="Search">
  <div class="ui basic floating dropdown button">
    <div class="text">This Page</div>
    <i class="dropdown icon"></i>
    <div class="menu">
      <div class="item">This Organization</div>
      <div class="item">Entire Site</div>
    </div>
  </div>
</div>
```
```html
<div class="ui action input">
  <input type="text" placeholder="Search...">
  <select class="ui compact selection dropdown">
    <option value="all">All</option>
    <option selected value="articles">Articles</option>
    <option value="products">Products</option>
  </select>
  <div class="ui button">Search</div>
</div>
```
```html
<div class="ui action input">
  <input type="text" value="http://ww.short.url/c0opq">
  <button class="ui teal right labeled icon button">
    <i class="copy icon"></i>
    Copy
  </button>
</div>
```
```html
<div class="ui action input">
  <input type="text" placeholder="Search...">
  <button class="ui icon button">
    <i class="search icon"></i>
  </button>
</div>
```

#### Transparent
A transparent input has no background
```html
<div class="ui transparent input">
  <input type="text" placeholder="Search...">
</div>
```
```html
<div class="ui transparent icon input">
  <input type="text" placeholder="Search...">
  <i class="search icon"></i>
</div>
```
```html
<div class="ui transparent left icon input">
  <input type="text" placeholder="Search...">
  <i class="search icon"></i>
</div>
```

#### Inverted
An input can be formatted to appear on dark backgrounds
```html
<div class="ui inverted segment">
  <div class="ui inverted input">
    <input type="text" placeholder="Search...">
  </div>
  <div class="ui inverted divider"></div>
  <div class="ui inverted left icon input">
    <input type="text" placeholder="Search...">
    <i class="search icon"></i>
  </div>
  <div class="ui inverted divider"></div>
  <div class="ui inverted transparent icon input">
    <input type="text" placeholder="Search...">
    <i class="search icon"></i>
  </div>
</div>
```

#### Fluid
An input can take the size of its container
```html
<div class="ui fluid icon input">
  <input type="text" placeholder="Search a very wide input...">
  <i class="search icon"></i>
</div>
<div class="ui ignored divider"></div>
<div class="ui fluid action input">
  <input type="text" placeholder="Search...">
  <div class="ui button">Search</div>
</div>
```

#### Size
An input can vary in size
> Inputs will automatically size themselves unless you manually declare a width
```html
<div class="ui mini icon input">
  <input type="text" placeholder="Search mini...">
  <i class="search icon"></i>
</div>
```
```html
<div class="ui small icon input">
  <input type="text" placeholder="Search small...">
  <i class="search icon"></i>
</div>
```
```html
<div class="ui large icon input">
  <input type="text" placeholder="Search large...">
  <i class="search icon"></i>
</div>
```
```html
<div class="ui big icon input">
  <input type="text" placeholder="Search big...">
  <i class="search icon"></i>
</div>
```
```html
<div class="ui huge icon input">
  <input type="text" placeholder="Search huge...">
  <i class="search icon"></i>
</div>
```
```html
<div class="ui massive icon input">
  <input type="text" placeholder="Search massive...">
  <i class="search icon"></i>
</div>
```


## === label.md ===

# Label

A label displays content classification

## Types

#### Label
A label
```html
<div class="ui label">
  <i class="mail icon"></i> 23
</div>
```

#### Image
A label can be formatted to emphasize an image
```html
<a class="ui image label">
  <img src="/images/avatar/small/joe.jpg">
  Joe
</a>
<a class="ui image label">
  <img src="/images/avatar/small/elliot.jpg">
  Elliot
</a>
<a class="ui image label">
  <img src="/images/avatar/small/stevie.jpg">
  Stevie
</a>
```
```html
<a class="ui blue image label">
  <img src="/images/avatar/small/veronika.jpg">
  Veronika
  <div class="detail">Friend</div>
</a>
<a class="ui teal image label">
  <img src="/images/avatar/small/jenny.jpg">
  Veronika
  <div class="detail">Student</div>
</a>
<a class="ui yellow image label">
  <img src="/images/avatar/small/christian.jpg">
  Helen
  <div class="detail">Co-worker</div>
</a>
```
```html
<div class="ui image label">
  <img src="/images/avatar/small/ade.jpg">
  Adrienne
  <i class="delete icon"></i>
</div>
<div class="ui image label">
  <img src="/images/avatar/small/zoe.jpg">
  Zoe
  <i class="delete icon"></i>
</div>
<div class="ui image label">
  <img src="/images/avatar/small/nan.jpg">
  Nan
  <i class="delete icon"></i>
</div>
```

#### Pointing
A label can point to content next to it
```html
<form class="ui fluid form">
  <div class="field">
    <input type="text" placeholder="First name">
    <div class="ui pointing label">
      Please enter a value
    </div>
  </div>
  <div class="ui divider"></div>
  <div class="field" placeholder="Last Name">
    <div class="ui pointing below label">
      Please enter a value
    </div>
    <input type="text">
  </div>
  <div class="ui divider"></div>
  <div class="inline field">
    <input type="text" placeholder="Username">
    <div class="ui left pointing label">
      That name is taken!
    </div>
  </div>
  <div class="ui divider"></div>
  <div class="inline field">
    <div class="ui right pointing label">
      Your password must be 6 characters or more
    </div>
    <input type="password">
  </div>
</form>
```
```html
<form class="ui fluid form">
  <div class="field">
    <input type="text" placeholder="First name">
    <div class="ui pointing red basic label">
      Please enter a value
    </div>
  </div>
  <div class="ui divider"></div>
  <div class="field" placeholder="Last Name">
    <div class="ui pointing below red basic label">
      Please enter a value
    </div>
    <input type="text">
  </div>
  <div class="ui divider"></div>
  <div class="inline field">
    <input type="text" placeholder="Username">
    <div class="ui left pointing red basic label">
      That name is taken!
    </div>
  </div>
  <div class="ui divider"></div>
  <div class="inline field">
    <div class="ui right pointing red basic label">
      Your password must be 6 characters or more
    </div>
    <input type="password">
  </div>
</form>
```

#### Corner
A label can position itself in the corner of an element
> A corner label must be positioned inside a container with **position: relative** to display properly. If a container is rounded you will need to add `overflow:hidden` to the container to produce a rounded label.
```html
<div class="ui two column grid">
  <div class="column">
    <div class="ui fluid image">
      <a class="ui left corner label">
        <i class="heart icon"></i>
      </a>
      <img src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="column">
    <div class="ui fluid image">
      <a class="ui red right corner label">
        <i class="save icon"></i>
      </a>
      <img src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

#### Tag
A label can appear as a tag
```html
<a class="ui tag label">New</a>
<a class="ui red tag label">Upcoming</a>
<a class="ui teal tag label">Featured</a>
```

#### Ribbon
A label can appear as a ribbon attaching itself to an element.
```html
<div class="ui two column grid">
  <div class="column">
    <div class="ui raised segment">
      <a class="ui red ribbon label">Overview</a>
      <span>Account Details</span>
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      <a class="ui blue ribbon label">Community</a> User Reviews
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
  <div class="column">
    <div class="ui segment">
      <a class="ui orange right ribbon label">Specs</a>
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      <a class="ui teal right ribbon label">Reviews</a>
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
</div>
```
```html
<div class="ui two column grid">
  <div class="column">
    <div class="ui fluid image">
      <div class="ui black ribbon label">
        <i class="hotel icon"></i> Hotel
      </div>
      <img src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="column">
    <div class="ui fluid image">
      <div class="ui blue ribbon label">
        <i class="spoon icon"></i> Food
      </div>
      <img src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

#### Attached
A label can attach to a content segment
> Attached labels attempt to intelligently pad other content to account for their position, but may not in all cases apply this padding correctly.
> If this happens you may need to manually correct the padding of the other elements inside the container.
```html
<div class="ui three column grid">
  <div class="row">
    <div class="column">
      <div class="ui segment">
        <div class="ui top attached label">HTML</div>
        <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        <div class="ui bottom attached label">CSS</div>
        <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        <div class="ui top right attached label">Code</div>
        <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      </div>
    </div>
  </div>
  <div class="row">
    <div class="column">
      <div class="ui segment">
        <div class="ui top left attached label">View</div>
        <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        <div class="ui bottom left attached label">User View</div>
        <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        <div class="ui bottom right attached label">Admin View</div>
        <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      </div>
    </div>
  </div>
</div>
```
```html
<div class="ui top attached label">HTML</div>
<div class="ui bottom attached label">CSS</div>
<div class="ui top right attached label">Code</div>
<div class="ui top left attached label">View</div>
<div class="ui bottom left attached label">User View</div>
<div class="ui bottom right attached label">Admin View</div>
```

#### Horizontal
A horizontal label is formatted to label content along-side it horizontally
```html
<div class="ui divided selection list">
  <a class="item">
    <div class="ui red horizontal label">Fruit</div>
    Kumquats
  </a>
  <a class="item">
    <div class="ui purple horizontal label">Candy</div>
    Ice Cream
  </a>
  <a class="item">
    <div class="ui red horizontal label">Fruit</div>
    Orange
  </a>
  <a class="item">
    <div class="ui horizontal label">Dog</div>
    Poodle
  </a>
</div>
```

#### Floating
A label can float above another element.
> A floating label must be positioned inside a container with **position: relative** to display properly.
```html
<div class="ui compact menu">
  <a class="item">
    <i class="icon mail"></i> Messages
    <div class="floating ui red label">22</div>
  </a>
  <a class="item">
    <i class="icon users"></i> Friends
    <div class="floating ui teal label">22</div>
  </a>
</div>
```

## Content

#### Detail
A label can contain a detail
```html
<div class="ui label">
  Dogs
  <div class="detail">214</div>
</div>
```

#### Icon
A label can include an icon
```html
<a class="ui label">
  <i class="mail icon"></i>
  Mail
</a>
<a class="ui label">
  Tag
  <i class="delete icon"></i>
</a>
```

#### Image
A label can include an image
```html
<a class="ui label">
  <img class="ui right spaced avatar image" src="/images/avatar/small/elliot.jpg">
  Elliot
</a>
<a class="ui label">
  <img src="/images/avatar/small/stevie.jpg">
  Stevie
</a>
```

#### Link
A label can be a link or contain an item that links
```html
<a class="ui label">
  <i class="mail icon"></i> 23
</a>
```
```html
<div class="ui label">
  <i class="mail icon"></i>
  23
  <a class="detail">View Mail</a>
</div>
```

## Variations

#### Circular
A label can be circular
```html
<a class="ui red circular label">2</a>
<a class="ui orange circular label">2</a>
<a class="ui yellow circular label">2</a>
<a class="ui olive circular label">2</a>
<a class="ui green circular label">2</a>
<a class="ui teal circular label">2</a>
<a class="ui blue circular label">2</a>
<a class="ui violet circular label">2</a>
<a class="ui purple circular label">2</a>
<a class="ui pink circular label">2</a>
<a class="ui brown circular label">2</a>
<a class="ui grey circular label">2</a>
<a class="ui black circular label">2</a>
```
```html
<a class="ui red empty circular label"></a>
<a class="ui orange empty circular label"></a>
<a class="ui yellow empty circular label"></a>
<a class="ui olive empty circular label"></a>
<a class="ui green empty circular label"></a>
<a class="ui teal empty circular label"></a>
<a class="ui blue empty circular label"></a>
<a class="ui violet empty circular label"></a>
<a class="ui purple empty circular label"></a>
<a class="ui pink empty circular label"></a>
<a class="ui brown empty circular label"></a>
<a class="ui grey empty circular label"></a>
<a class="ui black empty circular label"></a>
```

#### Basic
A label can reduce its complexity
```html
<a class="ui basic label">Basic</a>
<a class="ui pointing basic label">Pointing</a>
<a class="ui basic image label">
  <img src="/images/avatar/small/elliot.jpg">
  Elliot
<a class="ui pointing red basic label">Red Pointing</a>
<a class="ui blue basic label">Blue</a>
</a>
```

#### Colored
A label can have different colors
```html
<a class="ui red label">Red</a>
<a class="ui orange label">Orange</a>
<a class="ui yellow label">Yellow</a>
<a class="ui olive label">Olive</a>
<a class="ui green label">Green</a>
<a class="ui teal label">Teal</a>
<a class="ui blue label">Blue</a>
<a class="ui violet label">Violet</a>
<a class="ui purple label">Purple</a>
<a class="ui pink label">Pink</a>
<a class="ui brown label">Brown</a>
<a class="ui grey label">Grey</a>
<a class="ui black label">Black</a>
```

#### Size
A label can be small or large
```html
<div class="ui mini label">
  Mini
</div>
<div class="ui tiny label">
  Tiny
</div>
<div class="ui small label">
  Small
</div>
<div class="ui label">
  Medium
</div>
<div class="ui large label">
  Large
</div>
<div class="ui big label">
  Big
</div>
<div class="ui huge label">
  Huge
</div>
<div class="ui massive label">
  Massive
</div>
```

## Groups

#### Group Size
Labels can share sizes together
```html
<div class="ui huge labels">
  <div class="ui label">
    Fun
  </div>
  <div class="ui label">
    Happy
  </div>
  <div class="ui label">
    Smart
  </div>
  <div class="ui label">
    Witty
  </div>
</div>
```

#### Colored Group
Labels can share colors together
```html
<div class="ui blue labels">
  <a class="ui label">
    Fun <i class="icon close"></i>
  </a>
  <a class="ui label">
    Happy
    <div class="detail">22</div>
  </a>
  <a class="ui label">
    Smart
  </a>
  <a class="ui label">
    Insane
  </a>
  <a class="ui label">
    Exciting
  </a>
</div>
```

#### Tag Group
Labels can share tag formatting
```html
<div class="ui tag labels">
  <a class="ui label">
    $10.00
  </a>
  <a class="ui label">
    $19.99
  </a>
  <a class="ui label">
    $24.99
  </a>
  <a class="ui label">
    $30.99
  </a>
  <a class="ui label">
    $10.25
  </a>
</div>
```

#### Circular Group
Labels can share shapes
```html
<div class="ui circular labels">
  <a class="ui label">
    11
  </a>
  <a class="ui label">
    22
  </a>
  <a class="ui label">
    33
  </a>
  <a class="ui label">
    44
  </a>
  <a class="ui label">
    141
  </a>
</div>
```


## === list.md ===

# List

A list is used to group related content

## Types

#### List
A list groups related content
```html
<div class="ui list">
  <div class="item">Apples</div>
  <div class="item">Pears</div>
  <div class="item">Oranges</div>
</div>
```
```html
<div class="ui list">
  <div class="item">
    <i class="users icon"></i>
    <div class="content">
      Semantic UI
    </div>
  </div>
  <div class="item">
    <i class="marker icon"></i>
    <div class="content">
      New York, NY
    </div>
  </div>
  <div class="item">
    <i class="mail icon"></i>
    <div class="content">
      <a href="mailto:jack@semantic-ui.com">jack@semantic-ui.com</a>
    </div>
  </div>
  <div class="item">
    <i class="linkify icon"></i>
    <div class="content">
      <a href="http://www.semantic-ui.com">semantic-ui.com</a>
    </div>
  </div>
</div>
```
```html
<div class="ui relaxed divided list">
  <div class="item">
    <i class="large github middle aligned icon"></i>
    <div class="content">
      <a class="header">Semantic-Org/Semantic-UI</a>
      <div class="description">Updated 10 mins ago</div>
    </div>
  </div>
  <div class="item">
    <i class="large github middle aligned icon"></i>
    <div class="content">
      <a class="header">Semantic-Org/Semantic-UI-Docs</a>
      <div class="description">Updated 22 mins ago</div>
    </div>
  </div>
  <div class="item">
    <i class="large github middle aligned icon"></i>
    <div class="content">
      <a class="header">Semantic-Org/Semantic-UI-Meteor</a>
      <div class="description">Updated 34 mins ago</div>
    </div>
  </div>
</div>
```
```html
<div class="ui list">
  <div class="item">
    <i class="folder icon"></i>
    <div class="content">
      <div class="header">src</div>
      <div class="description">Source files for project</div>
      <div class="list">
        <div class="item">
          <i class="folder icon"></i>
          <div class="content">
            <div class="header">site</div>
            <div class="description">Your site's theme</div>
          </div>
        </div>
        <div class="item">
          <i class="folder icon"></i>
          <div class="content">
            <div class="header">themes</div>
            <div class="description">Packaged theme files</div>
            <div class="list">
              <div class="item">
                <i class="folder icon"></i>
                <div class="content">
                  <div class="header">default</div>
                  <div class="description">Default packaged theme</div>
                </div>
              </div>
              <div class="item">
                <i class="folder icon"></i>
                <div class="content">
                  <div class="header">my_theme</div>
                  <div class="description">Packaged themes are also available in this folder</div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="item">
          <i class="file icon"></i>
          <div class="content">
            <div class="header">theme.config</div>
            <div class="description">Config file for setting packaged themes</div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="item">
    <i class="folder icon"></i>
    <div class="content">
      <div class="header">dist</div>
      <div class="description">Compiled CSS and JS files</div>
      <div class="list">
        <div class="item">
          <i class="folder icon"></i>
          <div class="content">
            <div class="header">components</div>
            <div class="description">Individual component CSS and JS</div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="item">
    <i class="file icon"></i>
    <div class="content">
      <div class="header">semantic.json</div>
      <div class="description">Contains build settings for gulp</div>
    </div>
  </div>
</div>
```

#### Bulleted
A list can mark items with a bullet
```html
<div class="ui bulleted list">
  <div class="item">Gaining Access</div>
  <div class="item">Inviting Friends</div>
  <div class="item">
    <div>Benefits</div>
    <div class="list">
      <a class="item" href="#">Link to somewhere</a>
      <div class="item">Rebates</div>
      <div class="item">Discounts</div>
    </div>
  </div>
  <div class="item">Warranty</div>
</div>
```
> For convenience, a simple bulleted list can also use `ul` tag.
```html
<ul class="ui list">
  <li>Gaining Access</li>
  <li>Inviting Friends</li>
  <li>Benefits
    <ul>
      <li>Use Anywhere</li>
      <li>Rebates</li>
      <li>Discounts</li>
    </ul>
  </li>
  <li>Warranty</li>
</ul>
```
```html
<div class="ui horizontal bulleted list">
  <a class="item">
    About Us
  </a>
  <a class="item">
    Sitemap
  </a>
  <a class="item">
    Contact
  </a>
</div>
```

#### Ordered
A list can be ordered numerically
```html
<div class="ui ordered list">
  <a class="item">Getting Started</a>
  <a class="item">Introduction</a>
  <div class="item">
    <a>Languages</a>
    <div class="list">
      <a class="item">HTML</a>
      <a class="item">Javascript</a>
      <a class="item">CSS</a>
    </div>
  </div>
  <a class="item">Review</a>
</div>
```
> An ordered list can also use the `ol` tag
```html
<ol class="ui list">
  <li>Signing Up</li>
  <li>User Benefits</li>
  <li>User Types
    <ol>
      <li>Admin</li>
      <li>Power User</li>
      <li>Regular User</li>
    </ol>
  </li>
  <li>Deleting Your Account</li>
</ol>
```
> You can also manually specify a value for an ordered list using `data-value` on a `div`, or `value` on an `li`
```html
<ol class="ui list">
  <li value="*">Signing Up</li>
  <li value="*">User Benefits</li>
  <li value="*">User Types
    <ol>
      <li value="-">Admin</li>
      <li value="-">Power User</li>
      <li value="-">Regular User</li>
    </ol>
  </li>
  <li value="*">Deleting Your Account</li>
</ol>
```

#### Link
A list can be specially formatted for navigation links
```html
<div class="ui link list">
  <div class="active item">Home</div>
  <a class="item">About</a>
  <a class="item">Jobs</a>
  <a class="item">Team</a>
</div>
```

## Content

#### Item
A list item can contain a set of items
```html
<div class="ui list">
  <div class="item">
    1
  </div>
  <div class="item">
    2
  </div>
  <div class="item">
    3
  </div>
</div>
```

#### Icon
A list item can contain an icon
```html
<div class="ui list">
  <a class="item">
    <i class="help icon"></i>
    <div class="content">
      <div class="header">Floated Icon</div>
      <div class="description">This text will always have a left margin to make sure it sits alongside your icon</div>
    </div>
  </a>
  <a class="item">
    <i class="right triangle icon"></i>
    <div class="content">
      <div class="header">Icon Alignment</div>
      <div class="description">Floated icons are by default top aligned. To have an icon top aligned try this example.</div>
    </div>
  </a>
  <div class="item">
    <i class="help icon"></i>
    Inline Text
  </div>
</div>
```

#### Image
A list item can contain an image
```html
<div class="ui list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar2/small/rachel.png">
    <div class="content">
      <a class="header">Rachel</a>
      <div class="description">Last seen watching <a><b>Arrested Development</b></a> just now.</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar2/small/lindsay.png">
    <div class="content">
      <a class="header">Lindsay</a>
      <div class="description">Last seen watching <a><b>Bob's Burgers</b></a> 10 hours ago.</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar2/small/matthew.png">
    <div class="content">
      <a class="header">Matthew</a>
      <div class="description">Last seen watching <a><b>The Godfather Part 2</b></a> yesterday.</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/jenny.jpg">
    <div class="content">
      <a class="header">Jenny Hess</a>
      <div class="description">Last seen watching <a><b>Twin Peaks</b></a> 3 days ago.</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/veronika.jpg">
    <div class="content">
      <a class="header">Veronika Ossi</a>
      <div class="description">Has not watched anything recently</div>
    </div>
  </div>
</div>
```

#### Link
A list can contain links
```html
<div class="ui list">
  <a class="item">What is a FAQ?</a>
  <a class="item">Who is our user?</a>
  <a class="item">Where is our office located?</a>
</div>
```
```html
<div class="ui list">
  <div class="item">
    <a class="header">Header</a>
    <div class="description">
      Click a link in our <a>description</a>.
    </div>
  </div>
  <div class="item">
    <a class="header">Learn More</a>
    <div class="description">
      Learn more about this site on <a>our FAQ page</a>.
    </div>
  </div>
</div>
```

#### Header
A list item can contain a header
```html
<div class="ui list">
  <div class="item">
    <div class="header">New York City</div>
    A lovely city
  </div>
  <div class="item">
    <div class="header">Chicago</div>
    Also quite a lovely city
  </div>
  <div class="item">
    <div class="header">Los Angeles</div>
    Sometimes can be a lovely city
  </div>
  <div class="item">
    <div class="header">San Francisco</div>
    What a lovely city
  </div>
</div>
```

#### Description
A list item can contain a description
```html
<div class="ui list">
  <div class="item">
    <i class="map marker icon"></i>
    <div class="content">
      <a class="header">Krolewskie Jadlo</a>
      <div class="description">An excellent polish restaurant, quick delivery and hearty, filling meals.</div>
    </div>
  </div>
  <div class="item">
    <i class="map marker icon"></i>
    <div class="content">
      <a class="header">Xian Famous Foods</a>
      <div class="description">A taste of Shaanxi's delicious culinary traditions, with delights like spicy cold noodles and lamb burgers.</div>
    </div>
  </div>
  <div class="item">
    <i class="map marker icon"></i>
    <div class="content">
      <a class="header">Sapporo Haru</a>
      <div class="description">Greenpoint's best choice for quick and delicious sushi.</div>
    </div>
  </div>
  <div class="item">
    <i class="map marker icon"></i>
    <div class="content">
      <a class="header">Enid's</a>
      <div class="description">At night a bar, during the day a delicious brunch spot.</div>
    </div>
  </div>
</div>
```

## Variations

#### Horizontal
A list can be formatted to have items appear horizontally
```html
<div class="ui horizontal list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/tom.jpg">
    <div class="content">
      <div class="header">Tom</div>
      Top Contributor
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/christian.jpg">
    <div class="content">
      <div class="header">Christian Rocha</div>
      Admin
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/matt.jpg">
    <div class="content">
      <div class="header">Matt</div>
      Top Rated User
    </div>
  </div>
</div>
```
```html
<div class="ui ordered horizontal list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/tom.jpg">
    <div class="content">
      <div class="header">Steve Jobes</div>
      50 Points
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/stevie.jpg">
    <div class="content">
      <div class="header">Stevie Feliciano</div>
      44 Points
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/jenny.jpg">
    <div class="content">
      <div class="header">Jenny Hess</div>
      11 Points
    </div>
  </div>
</div>
```
```html
<div class="ui horizontal bulleted link list">
  <a class="item">
    Terms and Conditions
  </a>
  <a class="item">
    Privacy Policy
  </a>
  <a class="item">
    Contact Us
  </a>
</div>
```

#### Inverted
A list can be inverted to appear on a dark background
```html
<div class="ui inverted segment">
  <div class="ui inverted relaxed divided list">
    <div class="item">
      <div class="content">
        <div class="header">Snickerdoodle</div>
        An excellent companion
      </div>
    </div>
    <div class="item">
      <div class="content">
        <div class="header">Poodle</div>
        A poodle, its pretty basic
      </div>
    </div>
    <div class="item">
      <div class="content">
        <div class="header">Paulo</div>
        He's also a dog
      </div>
    </div>
  </div>
</div>
```

#### Selection
A selection list formats list items as possible choices
```html
<div class="ui middle aligned selection list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/helen.jpg">
    <div class="content">
      <div class="header">Helen</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/christian.jpg">
    <div class="content">
      <div class="header">Christian</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/daniel.jpg">
    <div class="content">
      <div class="header">Daniel</div>
    </div>
  </div>
</div>
```

#### Animated
A list can animate to set the current item apart from the list
> Be sure content can fit on one line when using the animated variation, otherwise text content will reflow when hovered.
```html
<div class="ui middle aligned animated list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/helen.jpg">
    <div class="content">
      <div class="header">Helen</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/christian.jpg">
    <div class="content">
      <div class="header">Christian</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/daniel.jpg">
    <div class="content">
      <div class="header">Daniel</div>
    </div>
  </div>
</div>
```

#### Relaxed
A list can relax its padding to provide more negative space
```html
<div class="ui relaxed list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/daniel.jpg">
    <div class="content">
      <a class="header">Daniel Louise</a>
      <div class="description">Last seen watching <a><b>Arrested Development</b></a> just now.</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/stevie.jpg">
    <div class="content">
      <a class="header">Stevie Feliciano</a>
      <div class="description">Last seen watching <a><b>Bob's Burgers</b></a> 10 hours ago.</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/elliot.jpg">
    <div class="content">
      <a class="header">Elliot Fu</a>
      <div class="description">Last seen watching <a><b>The Godfather Part 2</b></a> yesterday.</div>
    </div>
  </div>
</div>
```
```html
<div class="ui relaxed horizontal list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/daniel.jpg">
    <div class="content">
      <a class="header">Daniel Louise</a>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/stevie.jpg">
    <div class="content">
      <a class="header">Stevie Feliciano</a>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/elliot.jpg">
    <div class="content">
      <a class="header">Elliot Fu</a>
    </div>
  </div>
</div>
```
```html
<div class="ui very relaxed list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/daniel.jpg">
    <div class="content">
      <a class="header">Daniel Louise</a>
      <div class="description">Last seen watching <a><b>Arrested Development</b></a> just now.</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/stevie.jpg">
    <div class="content">
      <a class="header">Stevie Feliciano</a>
      <div class="description">Last seen watching <a><b>Bob's Burgers</b></a> 10 hours ago.</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/elliot.jpg">
    <div class="content">
      <a class="header">Elliot Fu</a>
      <div class="description">Last seen watching <a><b>The Godfather Part 2</b></a> yesterday.</div>
    </div>
  </div>
</div>
```
```html
<div class="ui very relaxed horizontal list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/daniel.jpg">
    <div class="content">
      <a class="header">Daniel Louise</a>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/stevie.jpg">
    <div class="content">
      <a class="header">Stevie Feliciano</a>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/elliot.jpg">
    <div class="content">
      <a class="header">Elliot Fu</a>
    </div>
  </div>
</div>
```

#### Divided
A list can show divisions between content
```html
<div class="ui middle aligned divided list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/daniel.jpg">
    <div class="content">
      <a class="header">Daniel Louise</a>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/stevie.jpg">
    <div class="content">
      <a class="header">Stevie Feliciano</a>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/elliot.jpg">
    <div class="content">
      <a class="header">Elliot Fu</a>
    </div>
  </div>
</div>
```

#### Celled
A list can divide its items into cells
```html
<div class="ui celled list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/helen.jpg">
    <div class="content">
      <div class="header">Snickerdoodle</div>
      An excellent companion
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/daniel.jpg">
    <div class="content">
      <div class="header">Poodle</div>
      A poodle, its pretty basic
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/daniel.jpg">
    <div class="content">
      <div class="header">Paulo</div>
      He's also a dog
    </div>
  </div>
</div>
```
```html
<div class="ui celled ordered list">
  <div class="item">Cats</div>
  <div class="item">Horses</div>
  <div class="item">Dogs
    <div class="list">
      <div class="item">Labradoodles</div>
      <div class="item">Shiba Inu</div>
      <div class="item">Mastiff</div>
    </div>
  </div>
</div>
```
```html
<div class="ui celled horizontal list">
  <div class="item">About Us</div>
  <div class="item">Contact</div>
  <div class="item">Support</div>
</div>
```

#### Size
A list can vary in size
```html
<div class="ui mini horizontal divided list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/helen.jpg">
    <div class="content">
      <div class="header">Helen</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/christian.jpg">
    <div class="content">
      <div class="header">Christian</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/daniel.jpg">
    <div class="content">
      <div class="header">Daniel</div>
    </div>
  </div>
</div>
```
```html
<div class="ui tiny horizontal list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/helen.jpg">
    <div class="content">
      <div class="header">Helen</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/christian.jpg">
    <div class="content">
      <div class="header">Christian</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/daniel.jpg">
    <div class="content">
      <div class="header">Daniel</div>
    </div>
  </div>
</div>
```
```html
<div class="ui small horizontal list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/helen.jpg">
    <div class="content">
      <div class="header">Helen</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/christian.jpg">
    <div class="content">
      <div class="header">Christian</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/daniel.jpg">
    <div class="content">
      <div class="header">Daniel</div>
    </div>
  </div>
</div>
```
```html
<div class="ui large horizontal divided list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/helen.jpg">
    <div class="content">
      <div class="header">Helen</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/christian.jpg">
    <div class="content">
      <div class="header">Christian</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/daniel.jpg">
    <div class="content">
      <div class="header">Daniel</div>
    </div>
  </div>
</div>
```
```html
<div class="ui big horizontal divided list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/helen.jpg">
    <div class="content">
      <div class="header">Helen</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/christian.jpg">
    <div class="content">
      <div class="header">Christian</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/daniel.jpg">
    <div class="content">
      <div class="header">Daniel</div>
    </div>
  </div>
</div>
```
```html
<div class="ui huge horizontal divided list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/helen.jpg">
    <div class="content">
      <div class="header">Helen</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/christian.jpg">
    <div class="content">
      <div class="header">Christian</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/daniel.jpg">
    <div class="content">
      <div class="header">Daniel</div>
    </div>
  </div>
</div>
```
```html
<div class="ui massive horizontal divided list">
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/helen.jpg">
    <div class="content">
      <div class="header">Helen</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/christian.jpg">
    <div class="content">
      <div class="header">Christian</div>
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/avatar/small/daniel.jpg">
    <div class="content">
      <div class="header">Daniel</div>
    </div>
  </div>
</div>
```

## Content Variations

#### Vertically Aligned
An element inside a list can be vertically aligned
```html
<div class="ui horizontal list">
  <div class="item">
    <img class="ui avatar image" src="/images/wireframe/square-image.png">
    <div class="top aligned content">
      Top Aligned
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/wireframe/square-image.png">
    <div class="middle aligned content">
      Middle
    </div>
  </div>
  <div class="item">
    <img class="ui avatar image" src="/images/wireframe/square-image.png">
    <div class="bottom aligned content">
      Bottom
    </div>
  </div>
</div>
```

#### Floated
An list, or an element inside a list can be floated left or right
```html
<div class="ui middle aligned divided list">
  <div class="item">
    <div class="right floated content">
      <div class="ui button">Add</div>
    </div>
    <img class="ui avatar image" src="/images/avatar2/small/lena.png">
    <div class="content">
      Lena
    </div>
  </div>
  <div class="item">
    <div class="right floated content">
      <div class="ui button">Add</div>
    </div>
    <img class="ui avatar image" src="/images/avatar2/small/lindsay.png">
    <div class="content">
      Lindsay
    </div>
  </div>
  <div class="item">
    <div class="right floated content">
      <div class="ui button">Add</div>
    </div>
    <img class="ui avatar image" src="/images/avatar2/small/mark.png">
    <div class="content">
      Mark
    </div>
  </div>
  <div class="item">
    <div class="right floated content">
      <div class="ui button">Add</div>
    </div>
    <img class="ui avatar image" src="/images/avatar2/small/molly.png">
    <div class="content">
      Molly
    </div>
  </div>
</div>
```
```html
<div class="ui right floated horizontal list">
  <div class="disabled item" href="#">&copy; GitHub, Inc.</div>
  <a class="item" href="#">Terms</a>
  <a class="item" href="#">Privacy</a>
  <a class="item" href="#">Contact</a>
</div>
<div class="ui horizontal list">
  <a class="item" href="#">About Us</a>
  <a class="item" href="#">Jobs</a>
</div>
```


## === loader.md ===

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


## === placeholder.md ===

# Placeholder

A placeholder is used to reserve splace for content that soon will appear in a layout

## Types

#### Placeholder
A placeholder is used to reserve space for content that soon will appear in a layout.
> Placeholders can include `paragraph`, `header`, `image header` and `image` to let you format the loaders to emulate the content being loaded.
```html
<div class="ui placeholder">
  <div class="image header">
    <div class="line"></div>
    <div class="line"></div>
  </div>
  <div class="paragraph">
    <div class="line"></div>
    <div class="line"></div>
    <div class="line"></div>
    <div class="line"></div>
    <div class="line"></div>
  </div>
</div>
```
```html
<div class="ui three column stackable grid">
  <div class="column">
    <div class="ui raised segment">
      <div class="ui placeholder">
        <div class="image header">
          <div class="line"></div>
          <div class="line"></div>
        </div>
        <div class="paragraph">
          <div class="medium line"></div>
          <div class="short line"></div>
        </div>
      </div>
    </div>
  </div>
  <div class="column">
    <div class="ui raised segment">
      <div class="ui placeholder">
        <div class="image header">
          <div class="line"></div>
          <div class="line"></div>
        </div>
        <div class="paragraph">
          <div class="medium line"></div>
          <div class="short line"></div>
        </div>
      </div>
    </div>
  </div>
  <div class="column">
    <div class="ui raised segment">
      <div class="ui placeholder">
        <div class="image header">
          <div class="line"></div>
          <div class="line"></div>
        </div>
        <div class="paragraph">
          <div class="medium line"></div>
          <div class="short line"></div>
        </div>
      </div>
    </div>
  </div>
</div>
```
```html
<%- @partial('examples/content-loader') %>
```

## Content

#### Lines
A placeholder can contain lines of text
> By default, repeated lines will appear varied in width. However, it may be useful to specify an exact length to make it match up with content more effectively
```html
<div class="ui placeholder">
  <div class="line"></div>
  <div class="line"></div>
  <div class="line"></div>
  <div class="line"></div>
  <div class="line"></div>
</div>
```

#### Headers
A placeholder can contain a header
> Header content will have a slightly larger block size from paragraph
```html
<div class="ui placeholder">
  <div class="image header">
    <div class="line"></div>
    <div class="line"></div>
  </div>
</div>
```
```html
<div class="ui placeholder">
  <div class="header">
    <div class="line"></div>
    <div class="line"></div>
  </div>
</div>
```

#### Paragraph
A placeholder can contain a paragraph
> Paragraphs are used to group lines together.
```html
<div class="ui placeholder">
  <div class="paragraph">
    <div class="line"></div>
    <div class="line"></div>
    <div class="line"></div>
    <div class="line"></div>
    <div class="line"></div>
  </div>
  <div class="paragraph">
    <div class="line"></div>
    <div class="line"></div>
    <div class="line"></div>
  </div>
</div>
```

#### Image
A placeholder can contain an image
```html
<div class="ui placeholder" style="width:150px;height:150px;">
  <div class="image"></div>
</div>
```
> Using `square` (1:1) or `rectangular` (4:3) will embed an aspect ratio into the image loader so that they modify size correctly with responsive styles.
```html
<div class="ui three cards">
  <div class="ui card">
    <div class="content">
      <div class="ui placeholder">
        <div class="square image"></div>
      </div>
    </div>
  </div>
  <div class="ui card">
    <div class="content">
      <div class="ui placeholder">
        <div class="square image"></div>
      </div>
    </div>
  </div>
  <div class="ui card">
    <div class="content">
      <div class="ui placeholder">
        <div class="square image"></div>
      </div>
    </div>
  </div>
</div>
```
```html
<div class="ui three cards">
  <div class="ui card">
    <div class="content">
      <div class="ui placeholder">
        <div class="rectangular image"></div>
      </div>
    </div>
  </div>
  <div class="ui card">
    <div class="content">
      <div class="ui placeholder">
        <div class="rectangular image"></div>
      </div>
    </div>
  </div>
  <div class="ui card">
    <div class="content">
      <div class="ui placeholder">
        <div class="rectangular image"></div>
      </div>
    </div>
  </div>
</div>
```

## Variations

#### Line Length
A line can specify how long its contents should appear
```html
<div class="ui placeholder">
  <div class="full line"></div>
  <div class="very long line"></div>
  <div class="long line"></div>
  <div class="medium line"></div>
  <div class="short line"></div>
  <div class="very short line"></div>
</div>
```
```html
<div class="ui placeholder">
  <div class="image header">
    <div class="medium line"></div>
    <div class="full line"></div>
  </div>
  <div class="paragraph">
    <div class="full line"></div>
    <div class="medium line"></div>
  </div>
</div>
```

#### Fluid
A fluid placeholder takes up the width of its container
```html
<div class="ui fluid placeholder">
  <div class="image header">
    <div class="line"></div>
    <div class="line"></div>
  </div>
  <div class="paragraph">
    <div class="line"></div>
    <div class="line"></div>
    <div class="line"></div>
  </div>
</div>
```

#### Inverted
A placeholder can have their colors inverted.
```html
<div class="ui inverted segment">
  <div class="ui active inverted placeholder">
    <div class="image header">
      <div class="line"></div>
      <div class="line"></div>
    </div>
    <div class="paragraph">
      <div class="line"></div>
      <div class="line"></div>
      <div class="line"></div>
    </div>
  </div>
</div>
```


## === rail.md ===

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


## === reveal.md ===

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


## === segment.md ===

# Segment

A segment is used to create a grouping of related content

## Types

#### Segment
A segment of content
```html
<div class="ui segment">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```

#### Placeholder Segment
A segment can be used to reserve space for conditionally displayed content.
```html
<div class="ui placeholder segment">
  <div class="ui icon header">
    <i class="pdf file outline icon"></i>
    No documents are listed for this customer.
  </div>
  <div class="ui primary button">Add Document</div>
</div>
```
> To use inline-block content inside a placeholder, wrap the content in `inline`.
```html
<div class="ui placeholder segment">
  <div class="ui icon header">
    <i class="search icon"></i>
    We don't have any documents matching your query
  </div>
  <div class="inline">
    <div class="ui primary button">Clear Query</div>
    <div class="ui button">Add Document</div>
  </div>
</div>
```
```html
<div class="ui placeholder segment">
  <div class="ui two column stackable center aligned grid">
    <div class="ui vertical divider">Or</div>
    <div class="middle aligned row">
      <div class="column">
        <div class="ui icon header">
          <i class="search icon"></i>
          Find Country
        </div>
        <div class="field">
          <div class="ui search">
            <div class="ui icon input">
              <input class="prompt" type="text" placeholder="Search countries...">
              <i class="search icon"></i>
            </div>
            <div class="results"></div>
          </div>
        </div>
      </div>
      <div class="column">
        <div class="ui icon header">
          <i class="world icon"></i>
          Add New Country
        </div>
        <div class="ui primary button">
          Create
        </div>
      </div>
    </div>
  </div>
</div>
```

#### Raised
A segment may be formatted to raise above the page.
```html
<div class="ui raised segment">
  <p>Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.</p>
</div>
```

#### Stacked
A segment can be formatted to show it contains multiple pages
```html
<div class="ui stacked segment">
  <p>Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.</p>
</div>
```
```html
<div class="ui tall stacked segment">
  <p>Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.</p>
</div>
```

#### Piled
A segment can be formatted to look like a pile of pages
> Piled segments use <b>negative z-index</b> to format the additional pages below the segment. In order for them to appear correctly, your segment's offset container must have a z-index declared.
```html
<div class="ui piled segment">
  <h4 class="ui header">A header</h4>
  <p>Te eum doming eirmod, nominati pertinacia argumentum ad his. Ex eam alia facete scriptorem, est autem aliquip detraxit at. Usu ocurreret referrentur at, cu epicurei appellantur vix. Cum ea laoreet recteque electram, eos choro alterum definiebas in. Vim dolorum definiebas an. Mei ex natum rebum iisque.</p>

  <p>Audiam quaerendum eu sea, pro omittam definiebas ex. Te est latine definitiones. Quot wisi nulla ex duo. Vis sint solet expetenda ne, his te phaedrum referrentur consectetuer. Id vix fabulas oporteat, ei quo vide phaedrum, vim vivendum maiestatis in.</p>

  <p>Eu quo homero blandit intellegebat. Incorrupte consequuntur mei id. Mei ut facer dolores adolescens, no illum aperiri quo, usu odio brute at. Qui te porro electram, ea dico facete utroque quo. Populo quodsi te eam, wisi everti eos ex, eum elitr altera utamur at. Quodsi convenire mnesarchum eu per, quas minimum postulant per id.</p>
</div>
```

#### Vertical Segment
A vertical segment formats content to be aligned as part of a vertical group
```html
<div class="ui vertical segment">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
<div class="ui vertical segment">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
<div class="ui vertical segment">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```

## Groups

#### Segments
A group of segments can be formatted to appear together
```html
<div class="ui segments">
  <div class="ui segment">
    <p>Top</p>
  </div>
  <div class="ui segment">
    <p>Middle</p>
  </div>
  <div class="ui segment">
    <p>Middle</p>
  </div>
  <div class="ui segment">
    <p>Middle</p>
  </div>
  <div class="ui segment">
    <p>Bottom</p>
  </div>
</div>
```
```html
<div class="ui segments">
  <div class="ui segment">
    <p>Top</p>
  </div>
  <div class="ui red segment">
    <p>Middle</p>
  </div>
  <div class="ui blue segment">
    <p>Middle</p>
  </div>
  <div class="ui green segment">
    <p>Middle</p>
  </div>
  <div class="ui yellow segment">
    <p>Bottom</p>
  </div>
</div>
```
```html
<div class="ui segments">
  <div class="ui segment">
    <p>Top</p>
  </div>
  <div class="ui secondary segment">
    <p>Secondary Content</p>
  </div>
</div>
```

#### Nested Segments
A group of segments can be nested in another group of segments
```html
<div class="ui segments">
  <div class="ui segment">
    <p>Top</p>
  </div>
  <div class="ui segments">
    <div class="ui segment">
      <p>Nested Top</p>
    </div>
    <div class="ui segment">
      <p>Nested Middle</p>
    </div>
    <div class="ui segment">
      <p>Nested Bottom</p>
    </div>
  </div>
  <div class="ui segment">
    <p>Middle</p>
  </div>
  <div class="ui horizontal segments">
    <div class="ui segment">
      <p>Top</p>
    </div>
    <div class="ui segment">
      <p>Middle</p>
    </div>
    <div class="ui segment">
      <p>Bottom</p>
    </div>
  </div>
  <div class="ui segment">
    <p>Bottom</p>
  </div>
</div>
```

#### Horizontal Segments
A segment group can appear horizontally
```html
<div class="ui horizontal segments">
  <div class="ui segment">
    <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  </div>
  <div class="ui segment">
    <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  </div>
  <div class="ui segment">
    <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
  </div>
</div>
```

#### Raised Segments
A group of segments can be raised
```html
<div class="ui raised segments">
  <div class="ui segment">
    <p>Top</p>
  </div>
  <div class="ui segment">
    <p>Middle</p>
  </div>
  <div class="ui segment">
    <p>Bottom</p>
  </div>
</div>
```

#### Stacked Segments
A group of segments can be stacked
```html
<div class="ui stacked segments">
  <div class="ui segment">
    <p>Top</p>
  </div>
  <div class="ui segment">
    <p>Middle</p>
  </div>
  <div class="ui segment">
    <p>Bottom</p>
  </div>
</div>
```

#### Piled Segments
A group of segments can be piled
```html
<div class="ui piled segments">
  <div class="ui segment">
    <p>Top</p>
  </div>
  <div class="ui segment">
    <p>Middle</p>
  </div>
  <div class="ui segment">
    <p>Bottom</p>
  </div>
</div>
```

## States

#### Disabled
A segment may show its content is disabled
```html
<div class="ui disabled segment">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```

#### Loading
A segment may show its content is being loaded
```html
<div class="ui loading segment">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
```

## Variations

#### Inverted
A segment can have its colors inverted for contrast
```html
<div class="ui inverted segment">
  <p>I'm here to tell you something, and you will probably read me first.</p>
</div>
```

#### Attached
A segment can be attached to other content on a page
> Attached segments are designed to be used with other `attached` variations like attached header or attached messages.
```html
<div class="ui top attached segment">
  <p>This segment is on top</p>
</div>
<div class="ui attached segment">
  <p>This segment is attached on both sides</p>
</div>
<div class="ui bottom attached segment">
  <p>This segment is on bottom</p>
</div>
```
```html
<h5 class="ui top attached header">
  Dogs
</h5>
<div class="ui attached segment">
  <p>Dogs are one type of animal</p>
</div>
<h5 class="ui attached header">
  Cats
</h5>
<div class="ui attached segment">
  <p>Cats are thought of as being related to dogs, but only humans think this.</p>
</div>
<h5 class="ui attached header">
  Lions
</h5>
<div class="ui attached segment">
  <p>Humans don't think of lions as being like cats, but they are.</p>
</div>
<div class="ui bottom attached warning message">
  <i class="warning icon"></i>
  You've reached the end of this content segment!
</div>
```

#### Padded
A segment can increase its padding
```html
<div class="ui padded segment">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```
```html
<div class="ui very padded segment">
  <img class="ui wireframe image" src="/images/wireframe/short-paragraph.png">
</div>
```

#### Compact
A segment may take up only as much space as is necessary
```html
<div class="ui compact segment">
  <p>Pellentesque habitant morbi</p>
</div>
```
```html
<div class="ui compact segments">
  <div class="ui segment">
    <p>Pellentesque habitant morbi</p>
  </div>
  <div class="ui segment">
    <p>Pellentesque habitant morbi</p>
  </div>
</div>
```

#### Colored
A segment can be colored
```html
<div class="ui red segment">Red</div>
<div class="ui orange segment">Orange</div>
<div class="ui yellow segment">Yellow</div>
<div class="ui olive segment">Olive</div>
<div class="ui green segment">Green</div>
<div class="ui teal segment">Teal</div>
<div class="ui blue segment">Blue</div>
<div class="ui violet segment">Violet</div>
<div class="ui purple segment">Purple</div>
<div class="ui pink segment">Pink</div>
<div class="ui brown segment">Brown</div>
<div class="ui grey segment">Grey</div>
<div class="ui black segment">Black</div>
```

<p>These colors can be inverted</p>
```html
<div class="ui red inverted segment">Red</div>
<div class="ui orange inverted segment">Orange</div>
<div class="ui yellow inverted segment">Yellow</div>
<div class="ui olive inverted segment">Olive</div>
<div class="ui green inverted segment">Green</div>
<div class="ui teal inverted segment">Teal</div>
<div class="ui blue inverted segment">Blue</div>
<div class="ui violet inverted segment">Violet</div>
<div class="ui purple inverted segment">Purple</div>
<div class="ui pink inverted segment">Pink</div>
<div class="ui brown inverted segment">Brown</div>
<div class="ui grey inverted segment">Grey</div>
<div class="ui black inverted segment">Black</div>
```

#### Emphasis
A segment can be formatted to appear more or less noticeable
```html
<div class="ui segment">
  <p>I'm here to tell you something, and you will probably read me first.</p>
</div>
<div class="ui secondary segment">
  <p>I am pretty noticeable but you might check out other content before you look at me.</p>
</div>
<div class="ui tertiary segment">
  <p>If you notice me you must be looking very hard.</p>
</div>
```

<p>Inverted colors may also be more or less noticeable</p>
```html
<div class="ui inverted segment">
  <p>I'm here to tell you something, and you will probably read me first.</p>
</div>
<div class="ui secondary inverted segment">
  <p>I am pretty noticeable but you might check out other content before you look at me.</p>
</div>
<div class="ui tertiary inverted segment">
  <p>If you notice me you must be looking very hard.</p>
</div>
```
```html
<div class="ui inverted red segment">
  <p>I'm here to tell you something, and you will probably read me first.</p>
</div>
<div class="ui secondary inverted red segment">
  <p>I am pretty noticeable but you might check out other content before you look at me.</p>
</div>
<div class="ui tertiary inverted red segment">
  <p>If you notice me you must be looking very hard.</p>
</div>
```

#### Circular
A segment can be circular
> A circular segment will most likely have to have its content manually sized to be equal width and height, otherwise it will flow to the size of your content
```html
<div class="ui circular segment">
  <h2 class="ui header">
    Buy Now
    <div class="sub header">$10.99</div>
  </h2>
</div>
<div class="ui inverted circular segment">
  <h2 class="ui inverted header">
    Buy Now
    <div class="sub header">$10.99</div>
  </h2>
</div>
```

#### Clearing
A segment can clear floated content
```html
<div class="ui clearing segment">
  <div class="ui right floated button">Floated</div>
</div>
```

#### Floated
A segment can appear to the left or right of other content
```html
<div class="ui right floated segment">
  <p>This segment will appear to the right
</div>
<div class="ui left floated segment">
  This segment will appear to the left
</div>
```

#### Text Alignment
A segment can have its text aligned to a side
```html
<div class="ui right aligned segment">
  Right
</div>
<div class="ui left aligned segment">
  Left
</div>
<div class="ui center aligned segment">
  Center
</div>
```

#### Basic
A basic segment has no special formatting
```html
<div class="ui basic segment">
  <p>Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.</p>
</div>
```


## === step.md ===

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
