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
