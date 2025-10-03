# Sticky

Sticky content fixes itself to the browser viewport as content is scrolled

## Examples

### Introduction

Sticky content stays fixed to the browser viewport while another column of content is visible on the page.

Although sticky content can be used inside any container, sticky pairs well with [ui rail](/elements/rail.html) because often "stuck" content is used to occupy additional canvas space outside of the main content of a website, making sure follow up links, ads, and other ancillary content remains on screen while engaging the sites main content.

> The following examples may be hidden on small screen sizes. For the best experience, view these examples on a large resolution display.

## Examples

#### Sticking to Adjacent Context
Sticky content attaches itself to the viewport when it is passed, and remains fixed to the viewport until this fixed content collides with the bottom edge of the passed `context`. Additional static content can exist above `sticky` content without affecting its position.

```javascript
$('.ui.sticky')
  .sticky({
    context: '#example1'
  })
;
```
```html
<div class="ui segment" id="example1">
  <div class="left ui rail">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <div class="ui sticky">
      <h3 class="ui header">Stuck Content</h3>
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="right ui rail">
    <div class="ui sticky">
      <h3 class="ui header">Stuck Content</h3>
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
</div>
```

#### Pushing
Specifying `pushing: true` will have the viewport "push" the sticky content depending on the scroll direction. When scrolling down content will be stuck to the top of the viewport, but in the opposite direction content is stuck to the bottom of the viewport.
```javascript
$('.ui.sticky')
  .sticky({
    context: '#example2',
    pushing: true
  })
;
```
```html
<div class="ui segment" id="example2">
  <div class="left ui rail">
    <div class="ui sticky">
      <h3 class="ui header">Stuck Content</h3>
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="right ui rail">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <div class="ui sticky">
      <h3 class="ui header">Stuck Content</h3>
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
</div>
```

#### Oversized Content

Sticky content that is larger than the viewport will automatically scroll independently from the context, shifting scroll direction at any time will also immediately adjust the scroll position of the fixed content.

This behavior makes sure users aren't required to navigate all the way to the top of the context element to see content that can't fit on-screen inside the sticky element.

```javascript
$('.ui.sticky')
  .sticky({
    context: '#example3'
  })
;
```
```html
<div class="ui segment" id="example3">
  <div class="left ui rail">
    <div class="ui sticky">
      <h3 class="ui header">Long Stuck Content</h3>
      <div class="ui divided items">
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="ui tiny image">
            <img src="/images/wireframe/image.png">
          </div>
          <div class="middle aligned content">
            <a class="header">Followup Article</a>
            <div class="meta">
              <span class="author">By <a>Author</a></span>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="right ui rail">
      <div class="ui sticky">
        <h3 class="ui header">Short Stuck Content</h3>
        <img class="ui wireframe image" src="/images/wireframe/image.png">
      </div>
    </div>
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
</div>
```

#### Sticking to Own Context

Sticky content without a specified context can also stick itself to its current context, although this may cause overlap issues with content.

Content that sticks to its own context will adjust its own layout when being "stuck". You can fix layout issues caused by this reflow by adding styles to the next element after a `ui fixed sticky`

```css
.ui.fixed.sticky + p {
  margin-top: 39px;
}
```

```javascript
$('.ui.sticky')
  .sticky()
;
```
```html
<div class="ui segment">
  <div class="ui sticky">
    <div class="ui fluid three item tabular menu">
      <a class="active item">Tab 1</a>
      <a class="item">Tab 2</a>
      <a class="item">Tab 3</a>
    </div>
  </div>
  <div class="ui active tab">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
    <img class="ui wireframe paragraph image" src="/images/wireframe/paragraph.png">
  </div>
</div>
```

## Usage

### Initializing

Sticky is initialized on content that should be stuck to viewport. Most instances require specifying a secondary `context` which will define the top and bottom bounds of the sticky element. Sticky content must be included inside a containing element. This container can be a [ui rail](/elements/rail.html) or your own arbitrary container, but should exist parallel to your context.

> Sticky does not work in tables without using `table-layout: fixed` to prevent automatic resizing with content
```html
<div class="ui rail">
  <div class="ui sticky">
    <!-- Any arbitrary content !-->
  </div>
</div>
<div id="context">
  <!-- Long flowing text content !-->
</div>
```
```javascript
$('.ui.sticky')
  .sticky({
    context: '#context'
  })
;
```

#### Refreshing Cached Values
Sticky content caches its current offset on the page and other crucial values on initialization. This prevents it from having to query the DOM on each browser scroll which would drastically reduce performance.

Sticky uses [mutation observers](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver) to adjust its position when content is added to the context, and also will automatically recalculate on browser `resize`, but any other changes to your page that adjust the elements context require you to refresh the sticky's position

Examples of changes that might affect sticky elements are:

*   Loading images without specified size
*   Setting CSS which adjusts the layout of the page
*   Hiding elements using Javascript

Refreshing cached values just requires calling the `refresh` behavior.
```javascript
// recalculates offsets
$('.ui.sticky')
  .sticky('refresh')
;
```

#### Sticky Conditions
Sticky content is required to be inside its own `position: relative` container that is either the sticky context, or **shares vertical positioning with the context element**.

You can use `ui rail` or `ui grid` column that are in the same row to provide this set-up, or your own custom CSS

Sticky elements swap between being bound to the edges of their container, or fixed to the edges of the browser viewport
```html
<table class="ui ignored celled definition table">
  <thead>
    <tr>
      <th></th>
      <th>Class</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Fixed Top</td>
      <td>ui fixed top sticky</td>
      <td>Element is fixed to top of viewport</td>
    </tr>
    <tr>
      <td>Fixed Bottom</td>
      <td>ui fixed bottom sticky</td>
      <td>Element is fixed to bottom of viewport</td>
    </tr>
    <tr>
      <td>Bound Top</td>
      <td>ui bound top sticky</td>
      <td>Element is bound to the top of its containing element (usually rail or column)</td>
    </tr>
    <tr>
      <td>Bound Bottom</td>
      <td>ui bound bottom sticky</td>
      <td>Element is bound to the bottom of its containing element (usually rail or column)</td>
    </tr>
  </tbody>
</table>
```

#### Adjusting Offset and Padding
If you have content fixed to the viewport it might make sense to include a top or bottom offset. An `offset` will adjust all values so that content does not overlap any content between the top of the browser and the specified value. A `bottomOffset` will do the same thing for content fixed to the bottom of the viewport.
```javascript
$('.ui.sticky')
  .sticky({
    offset       : 50,
    bottomOffset : 50,
    context      : '#element-to-follow'
  })
;
```

## Settings

### Sticky Settings
Settings to configure sticky behavior
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th>Setting</th>
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>pushing</td>
      <td>false</td>
      <td>Whether element should be "pushed" by the viewport, attaching to the bottom of the screen when scrolling up</td>
    </tr>
    <tr>
      <td>setSize</td>
      <td>true <div class="ui label">New in 2.2.11</div></td>
      <td>Sets size of `fixed` content to match its width before fixing to screen dynamically. This is used because fixed may display block or 100% width content differently than it appears before sticking.</td>
    </tr>
    <tr>
      <td>jitter</td>
      <td>5</td>
      <td>Sticky container height will only be set if the difference between heights of container and context is larger than this jitter value.</td>
    </tr>
    <tr>
      <td>observeChanges</td>
      <td>false</td>
      <td>Whether any change in `context` DOM should automatically refresh cached sticky positions</td>
    </tr>
    <tr>
      <td>context</td>
      <td>false</td>
      <td>Context which sticky element should stick to</td>
    </tr>
    <tr>
      <td>scrollContext</td>
      <td>window</td>
      <td>Context which sticky should attach `onscroll` events.</td>
    </tr>
    <tr>
      <td>offset</td>
      <td>0</td>
      <td>Offset in pixels from the top of the screen when fixing element to viewport</td>
    </tr>
    <tr>
      <td>bottomOffset</td>
      <td>0</td>
      <td>Offset in pixels from the bottom of the screen when fixing element to viewport</td>
    </tr>
  </tbody>
</table>
```

#### Callbacks
Callbacks specify a function to occur after a specific behavior.

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <tr>
      <th class="four wide"></th>
      <th>Context</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>onReposition</td>
      <td>$module</td>
      <td>Callback when element is repositioned from layout change</td>
    </tr>
    <tr>
      <td>onScroll</td>
      <td>$module</td>
      <td>Callback when `requestAnimationFrame` fires from scroll handler.</td>
    </tr>
    <tr>
      <td>onStick</td>
      <td>$module</td>
      <td>Callback when element is fixed to page</td>
    </tr>
    <tr>
      <td>onUnstick</td>
      <td>$module</td>
      <td>Callback when element is unfixed from page</td>
    </tr>
    <tr>
      <td>onTop</td>
      <td>$module</td>
      <td>Callback when element is bound to top of parent container</td>
    </tr>
    <tr>
      <td>onBottom</td>
      <td>$module</td>
      <td>Callback when element is bound to bottom of parent container</td>
    </tr>
  </tbody>
</table>
```

### DOM Settings
DOM settings specify how this module should interface with the DOM
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th>Setting</th>
    <th class="six wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>namespace</td>
      <td>sticky</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
className : {
  bound     : 'bound',
  fixed     : 'fixed',
  supported : 'native',
  top       : 'top',
  bottom    : 'bottom'
}
        </div>
      </td>
      <td>Class names used to attach style to state</td>
    </tr>
  </tbody>
</table>
```

### Debug Settings
Debug settings controls debug output to the console

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th>Setting</th>
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>Sticky</td>
      <td>Name used in debug logs</td>
    </tr>
    <tr>
      <td>silent</td>
      <td>False</td>
      <td>Silences all console output including error messages, regardless of other debug settings.</td>
    </tr>
    <tr>
      <td>debug</td>
      <td>False</td>
      <td>Provides standard debug output to console</td>
    </tr>
    <tr>
      <td>performance</td>
      <td>True</td>
      <td>Provides standard debug output to console</td>
    </tr>
    <tr>
      <td>verbose</td>
      <td>True</td>
      <td>Provides ancillary debug output to console</td>
    </tr>
    <tr>
      <td>errors</td>
      <td colspan="2">
        <div class="code">
error         : {
  container      : 'Sticky element must be inside a relative container',
  visible        : 'Element is hidden, you must call refresh after element becomes visible',
  method         : 'The method you called is not defined.',
  invalidContext : 'Context specified does not exist',
  elementSize    : 'Sticky element is larger than its container, cannot create sticky.'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```
