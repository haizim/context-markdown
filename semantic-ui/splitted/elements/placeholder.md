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
