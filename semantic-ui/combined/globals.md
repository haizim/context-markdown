## === reset.md ===

# Reset

A reset is a set of normalized values for CSS properties that correct for abberations in browser defaults

## Overview

### What's In Our Reset
Semantic's default theme includes the latest [Normalize CSS](http://necolas.github.io/normalize.css/) to provide a base line HTML reset. In addition, Semantic UI requires a **Box-sizing** reset, to make sure that elements handle width definitions in the same way.
> The reset is required for Semantic UI components to function properly, and should also be included when using individual components.

## Reset Options

The **basic** themes **only** includes the required `box-sizing` reset and nothing else. The **resetcss** theme provides a version of [Reset CSS](http://meyerweb.com/eric/tools/css/reset/), a less opinionated CSS reset.

## Test

### Reset Test

### `html`

#### should have sans-serif font family (opinionated)
```html
abcdefghijklmnopqrstuvwxyz
```

### `body`

#### should have no margin (opinionated)
```html
(there should be no red background visible on this page)
```

### `article`, `aside`, `details`, `figure`, `figcaption`, `footer`, `header`, `hgroup`, `main`, `nav`, `section`, `summary`

#### should render as block
```html
<article>article</article>
<aside>aside</aside>
<details>
  <summary>summary</summary>
  details
</details>
<figure>
  figure
  <figcaption>figcaption</figcaption>
</figure>
<footer>footer</footer>
<header>header</header>
<hgroup>hgroup</hgroup>
<main>main</main>
<nav>nav</nav>
<section>section</section>
```

### `audio`, `canvas`, `progress`, `video`

#### should render as inline-block and baseline-aligned
```html
<audio controls>audio</audio>
<canvas>canvas</canvas>
<progress>progress</progress>
<video controls>video</video>
```

### `audio:not([controls])`, `template`, `[hidden]`

#### should not display
```html
<audio>audio</audio>
<template>
  <h1>{{title}}</h1>
  <content></content>
</template>
<p hidden>This should be hidden</p>
```

### `a`

#### should have a transparent background when active
```html
<a href="#non">dummy anchor</a>
```

#### should not have a focus outline when both focused and hovered (opinionated)
```html
<a href="#non">dummy anchor</a>
```

### `abbr[title]`

#### should have a dotted bottom border
```html
<abbr title="abbreviation">abbr</abbr>
```

### `b`, `strong`

#### should have bold font-weight
```html
<b>b</b>
<strong>strong</strong>
```

### `dfn`

#### should have italic font-style
```html
<dfn>dfn</dfn>
```

### `h1`

#### should not change size within an `article`
```html
<h1>Heading (control)</h1>
<article>
  <h1>Heading (in article)</h1>
</article>
```

#### should not change size within a `section`
```html
<h1>Heading (control)</h1>
<section>
  <h1>Heading (in section)</h1>
</section>
```

### `mark`

#### should have a yellow background
```html
<mark>mark</mark>
```

### `small`

#### should render equally small in all browsers
```html
control. <small>small.</small>
```

### `sub` and `sup`

#### should not affect a line's visual line-height
```html
<p>control.</p>
<p>control. <sub>sub.</sub></p>
<p>control. <sup>sup.</sup></p>
```

### `img`

#### should not have a border when wrapped in an anchor
```html
<a href="#non">
  <!-- scaled-up 1px image -->
  <img style="background-color:#ADD8E6" src="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7" width="100" height="100">
</a>
```

### `svg`

#### should not overflow
```html
<svg width="100px" height="100px">
  <circle cx="100" cy="100" r="100" fill="#ADD8E6" />
</svg>
```

### `figure`

#### should have margins
```html
<figure>
  <img style="background-color:#ADD8E6" src="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7" width="400" height="200">
</figure>
```

### `hr`

#### should have a `content-box` box model
```html
<hr style="height:2px; border:solid #ADD8E6; border-width:2px 0;">
```

### `pre`

#### should trigger a scrollbar when too wide for its container
```html
<pre>Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et me.</pre>
```

### `code`, `kbd`, `pre`, `samp`

#### should render `em`-unit preformatted text at the same absolute size as normal text
```html
<span>span: abcdefghijklmnopqrstuvwxyz.</span><br>
<code>code: abcdefghijklmnopqrstuvwxyz.</code><br>
<kbd>kbd: abcdefghijklmnopqrstuvwxyz.</kbd><br>
<samp>samp: abcdefghijklmnopqrstuvwxyz.</samp>
<pre>pre: abcdefghijklmnopqrstuvwxyz.</pre>
```

### `button`, `input`, `optgroup`, `select`, `textarea`

#### should inherit `color` from ancestor
```html
<button>button</button><br>
<input value="input"><br>
<select style="border:1px solid #999;">
  <optgroup label="optgroup">
    <option>option</option>
  </optgroup>
  <option>option</option>
</select><br>
<textarea>textarea</textarea>
```

#### should inherit `font` from ancestor
```html
<button>button</button><br>
<input value="input"><br>
<select style="border:1px solid #999;">
  <optgroup label="optgroup">
    <option>option</option>
  </optgroup>
  <option>option</option>
</select><br>
<textarea>textarea</textarea>
```

#### should not have margins
```css
#form-collection-margins {
  outline: 1px solid #ADD8E6;
  overflow: hidden;
}

#form-collection-margins button,
#form-collection-margins input,
#form-collection-margins select,
#form-collection-margins textarea {
  display: block;
}
```
```html
<button>button</button>
<input value="input">
<select style="border:1px solid #999;">
  <optgroup label="optgroup">
    <option>option</option>
  </optgroup>
  <option>option</option>
</select>
<textarea>textarea</textarea>
```

### `button`

#### should have visible overflow
```css
#button-overflow button:after {
  content: "";
  background: #ADD8E6;
  display: inline-block;
  height: 10px;
  position:relative;
  right: -20px;
  width: 10px;
}
```
```html
<button>abcdefghijklmnopqrstuvwxyz</button>
```

### `button`, `select`

#### should not inherit `text-transform`
```html
<button>button</button>
<select><option>option</option></select>
```

### `button` and button-style `input`

#### should have `pointer` cursor style
```html
<p><button>button</button></p>
<p><input type="image" src="http://lorempixel.com/90/24" alt="input (image)"></p>
<p><input type="button" value="input (button)"></p>
<p><input type="reset" value="input (reset)"></p>
<p><input type="submit" value="input (submit)"></p>
```

#### should be styleable
```css
#button-like-style button,
#button-like-style input {
  background: #ADD8E6;
  border: 2px solid black;
  border-radius: 2px;
  padding: 5px;
}
```
```html
<p><button>button</button></p>
<p><input type="image" src="http://lorempixel.com/90/24" alt="input (image)"></p>
<p><input type="button" value="input (button)"></p>
<p><input type="reset" value="input (reset)"></p>
<p><input type="submit" value="input (submit)"></p>
```

### disabled `button` and `input`

#### should have `default` cursor style
```html
<p><button disabled>button</button></p>
<p><input disabled type="image" src="http://lorempixel.com/90/24" alt="input (image)"></p>
<p><input disabled type="button" value="input (button)"></p>
<p><input disabled type="reset" value="input (reset)"></p>
<p><input disabled type="submit" value="input (submit)"></p>
```

### `button`, `input`

#### should not have extra inner padding in Firefox
```css
#button-input-padding button,
#button-input-padding input {
  border: 0;
  padding: 0;
  outline: 1px solid #ADD8E6;
}
```
```html
<p><button>button</button></p>
<p><input value="input (text)"></p>
<p><input type="button" value="input (button)"></p>
<p><input type="reset" value="input (reset)"></p>
<p><input type="submit" value="input (submit)"></p>
```

### `input`

#### should not inherit `line-height`
```html
<input value="input (text)">
```

### `input[type="checkbox"]`, `input[type="radio"]`

#### should have a `border-box` box model
```css
#radio-box-model {
  width: 200px;
  border: 1px solid red;
}

#radio-box-model input {
  width: 100%;
  border: 5px solid #ADD8E6;
  display: block;
  position: relative;
}
```
```html
<input type="checkbox">
<input type="radio" name="rad">
```

#### should not have padding
```html
<input type="checkbox">
<input type="radio" name="rad">
```

### `input[type="number"]`

#### should display a default cursor for the decrement button's click target in Chrome
```html
<input style="height:50px; font-size:15px;" type="number" id="in" min="0" max="10" value="5">
```

### `input[type="search"]`

#### should be styleable
```html
<input type="search" style="border:1px solid #ADD8E6; padding:10px; width:200px;">
```

#### should have a `content-box` box model
```html
<div style="background:red; display:inline-block; height:62px; width:242px;">
  <input type="search" style="border:1px solid #ADD8E6; height:20px; padding:20px; width:200px;">
</div>
```

#### should not have a cancel button in Safari or Chrome
```html
<input type="search" value="search">
```

### `fieldset`

#### should have consistent border, padding, and margin
```html
<fieldset>
  <div style="width:100%; height:100px; background:#ADD8E6;"></div>
</fieldset>
```

### `legend`

#### should inherit color
```html
<fieldset>
  <legend>legend</legend>
</fieldset>
```

#### should not have padding
```html
<fieldset>
  <legend>legend</legend>
</fieldset>
```

### `textarea`

#### should not have a scrollbar unless overflowing
```html
<textarea>textarea</textarea>
```

### `table`

#### should not have spaces between cells
```html
<table>
  <caption>Jimi Hendrix - albums</caption>
  <thead>
    <tr>
      <th>Album</th>
      <th>Year</th>
      <th>Price</th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <th>Album</th>
      <th>Year</th>
      <th>Price</th>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <td>Are You Experienced</td>
      <td>1967</td>
      <td>$10.00</td>
    </tr>
    <tr>
      <td>Axis: Bold as Love</td>
      <td>1967</td>
      <td>$12.00</td>
    </tr>
    <tr>
      <td>Electric Ladyland</td>
      <td>1968</td>
      <td>$10.00</td>
    </tr>
    <tr>
      <td>Band of Gypsies</td>
      <td>1970</td>
      <td>$12.00</td>
    </tr>
  </tbody>
</table>
```


## === site.md ===

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
