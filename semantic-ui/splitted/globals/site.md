# Site

A site is a set of global constraints that define the basic parameters of all UI elements

## Introduction

Site is a special global definition which includes baseline parameters which all other elements inherit. In addition to providing global variables defaults, site also provides page styling for content that exists outside of interface elements.

### Theming

Customizing site variables is an important part of using Semantic UI, to learn more about global site variables visit our [theming guide](/usage/theming.html).

## Content

#### Headers
A site can define styles for headers

```html
<h1>First Header</h1>
<h2>Second Header</h2>
<h3>Third Header</h3>
<h4>Fourth Header</h4>
<h5>Fifth Header</h5>
```

#### Page Font
A site can specify styles for page content.

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam vel tincidunt eros, nec venenatis ipsum. Nulla hendrerit urna ex, id sagittis mi scelerisque vitae. Vestibulum posuere rutrum interdum. Sed ut ullamcorper odio, non pharetra eros. Aenean sed lacus sed enim ornare vestibulum quis a felis. Sed cursus nunc sit amet mauris sodales tempus. Nullam mattis, dolor non posuere commodo, sapien ligula hendrerit orci, non placerat erat felis vel dui. Cras vulputate ligula ut ex tincidunt tincidunt. Maecenas eget gravida lorem. Nunc nec facilisis risus. Mauris congue elit sit amet elit varius mattis. Praesent convallis placerat magna, a bibendum nibh lacinia non.

Fusce mollis sagittis elit ut maximus. Nullam blandit lacus sit amet luctus euismod. Duis luctus leo vel consectetur consequat. Phasellus ex ligula, pellentesque et neque vitae, elementum placerat eros. Proin eleifend odio nec velit lacinia suscipit. Morbi mollis ante nec dapibus gravida. In tincidunt augue eu elit porta, vel condimentum purus posuere. Maecenas tincidunt, erat sed elementum sagittis, tortor erat faucibus tellus, nec molestie mi purus sit amet tellus. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Mauris a tincidunt metus. Fusce congue metus aliquam ex auctor eleifend.
Ut imperdiet dignissim feugiat. Phasellus tristique odio eu justo dapibus, nec rutrum ipsum luctus. Ut posuere nec tortor eu ullamcorper. Etiam pellentesque tincidunt tortor, non sagittis nibh pretium sit amet. Sed neque dolor, blandit eu ornare vel, lacinia porttitor nisi. Vestibulum sit amet diam rhoncus, consectetur enim sit amet, interdum mauris. Praesent feugiat finibus quam, porttitor varius est egestas id.

#### Text Selection
A site can specify text selection styles.
> Highlight the text below with your cursor to see a demonstration

Fusce mollis sagittis elit ut maximus. Nullam blandit lacus sit amet luctus euismod. Duis luctus leo vel consectetur consequat. Phasellus ex ligula, pellentesque et neque vitae, elementum placerat eros. Proin eleifend odio nec velit lacinia suscipit. Morbi mollis ante nec dapibus gravida. In tincidunt augue eu elit porta, vel condimentum purus posuere. Maecenas tincidunt, erat sed elementum sagittis, tortor erat faucibus tellus, nec molestie mi purus sit amet tellus. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Mauris a tincidunt metus. Fusce congue metus aliquam ex auctor eleifend.

#### Spacing
A site can define default spacing for headers and paragraphs

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam vel tincidunt eros, nec venenatis ipsum. Nulla hendrerit urna ex, id sagittis mi scelerisque vitae. Vestibulum posuere rutrum interdum. Sed ut ullamcorper odio, non pharetra eros. Aenean sed lacus sed enim ornare vestibulum quis a felis. Sed cursus nunc sit amet mauris sodales tempus. Nullam mattis, dolor non posuere commodo, sapien ligula hendrerit orci, non placerat erat felis vel dui. Cras vulputate ligula ut ex tincidunt tincidunt. Maecenas eget gravida lorem. Nunc nec facilisis risus. Mauris congue elit sit amet elit varius mattis. Praesent convallis placerat magna, a bibendum nibh lacinia non.

Fusce mollis sagittis elit ut maximus. Nullam blandit lacus sit amet luctus euismod. Duis luctus leo vel consectetur consequat. Phasellus ex ligula, pellentesque et neque vitae, elementum placerat eros. Proin eleifend odio nec velit lacinia suscipit. Morbi mollis ante nec dapibus gravida. In tincidunt augue eu elit porta, vel condimentum purus posuere. Maecenas tincidunt, erat sed elementum sagittis, tortor erat faucibus tellus, nec molestie mi purus sit amet tellus. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Mauris a tincidunt metus. Fusce congue metus aliquam ex auctor eleifend.

Ut imperdiet dignissim feugiat. Phasellus tristique odio eu justo dapibus, nec rutrum ipsum luctus. Ut posuere nec tortor eu ullamcorper. Etiam pellentesque tincidunt tortor, non sagittis nibh pretium sit amet. Sed neque dolor, blandit eu ornare vel, lacinia porttitor nisi. Vestibulum sit amet diam rhoncus, consectetur enim sit amet, interdum mauris. Praesent feugiat finibus quam, porttitor varius est egestas id.

#### Links
A site can define link font formatting.
Ut imperdiet dignissim feugiat. Phasellus tristique odio eu justo dapibus, nec rutrum ipsum luctus. Ut posuere nec tortor eu ullamcorper. [Etiam pellentesque](#link) tincidunt tortor, non sagittis nibh pretium sit amet.

*   [List Link](#link)
*   [List Link](#link)
*   [List Link](#link)

```html
<div class="ui card">
  <a class="image" href="#link">
    <img src="/images/avatar/large/steve.jpg">
  </a>
  <div class="content">
    <a class="header" href="#link">Steve Jobes</a>
    <div class="meta">
      <a class="time">Last Seen 2 days ago</a>
    </div>
  </div>
</div>
```
```html
<div class="ui very relaxed items">
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="content">
      <a class="ui header" href="#link">Link Header</a>
      <div class="description">
        <p>Ut imperdiet dignissim feugiat. Phasellus tristique odio eu justo dapibus, nec rutrum ipsum luctus. Ut posuere nec tortor eu ullamcorper. <a href="#link">Etiam pellentesque</a> tincidunt tortor, non sagittis nibh pretium sit amet. Sed neque dolor, blandit eu ornare vel, lacinia porttitor nisi. Vestibulum sit amet diam rhoncus, consectetur enim sit amet, interdum mauris. Praesent feugiat finibus quam, porttitor varius est egestas id.</p>
      </div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="content">
      <a class="ui header" href="#link">Link Header</a>
      <div class="description">
        <p>Ut imperdiet dignissim feugiat. Phasellus tristique odio eu justo dapibus, nec rutrum ipsum luctus. Ut posuere nec tortor eu ullamcorper. <a href="#link">Etiam pellentesque</a> tincidunt tortor, non sagittis nibh pretium sit amet. Sed neque dolor, blandit eu ornare vel, lacinia porttitor nisi. Vestibulum sit amet diam rhoncus, consectetur enim sit amet, interdum mauris. Praesent feugiat finibus quam, porttitor varius est egestas id.</p>
      </div>
    </div>
  </div>
</div>
```

## Variables

#### Brand Colors
A site can specify a primary and secondary brand color.
```html
<a class="ui primary button">Primary Brand Color</a>
<a class="ui secondary button">Secondary Brand Color</a>
```

#### Colors
A site can define a set of hex values for common named colors
```html
<div class="ui five column stackable padded grid">
  <div class="red column">Red</div>
  <div class="orange column">Orange</div>
  <div class="yellow column">Yellow</div>
  <div class="olive column">Olive</div>
  <div class="green column">Green</div>
  <div class="teal column">Teal</div>
  <div class="blue column">Blue</div>
  <div class="violet column">Violet</div>
  <div class="purple column">Purple</div>
  <div class="pink column">Pink</div>
  <div class="brown column">Brown</div>
  <div class="grey column">Grey</div>
  <div class="black column">Black</div>
</div>
```

#### Border Styles
A site can specify default border styles and radius.

### Examples of UI that inherit border styles
```html
<div class="ui segment">Segment</div>
<div class="ui button">Button</div>
<div class="ui menu">
  <div class="item">One</div>
  <div class="item">Two</div>
</div>
<table class="ui definition table">
  <thead>
    <th></th>
    <th>Header 1</th>
    <th>Header 2</th>
  </thead>
  <tbody>
    <tr>
      <td>Definition</td>
      <td>1A</td>
      <td>1B</td>
    </tr>
    <tr>
      <td>Definition</td>
      <td>2A</td>
      <td>2B</td>
    </tr>
  </tbody>
</table>
```

#### Size
A site can define a root em size, used for providing relative sizes for the rest of a site's content
> `em` and `rem` are special units used to provide relative measurements for elements. `1em` defines what baseline size, `medium`, is for UI elements. Most elements are sized in `rem` which are affected by this value, however some UI can also be defined using `em` which will be based on the surrounding font size of the parent element.

### Examples of Absolutely Sized UI
```html
<div class="ui button">
  Button
</div>
<div class="ui input">
  <input type="text" placeholder="Input">
</div>
```

### Examples of Relative Sized UI
```html
<div style="font-size: 18px;">
  <p>Larger content container</p>
  <div class="ui bulleted link list">
    <a class="item">List Item</a>
    <a class="item">List Item</a>
    <a class="item">List Item</a>
    <a class="item">List Item</a>
    <a class="item">List Item</a>
  </div>
  <div class="ui message">
    <p>Message</p>
  </div>
</div>
```
