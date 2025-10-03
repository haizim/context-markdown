# New in 2.4

An introduction to new features found in the latest release

## New in 2.4

### Solving Empty State
Semantic `2.4` brings a new components for handling content loading [ui placeholder](/elements/placeholder.html), as well as a new type of `segment` used to reserve space for content: [ui placeholder segment](/elements/segment.html#empty).

Additionally several important component updates are included in this release.

*   Modals have been re-architected to use hybrid flex support, falling back to JS positioning for more complex use-cases (or older browsers).
*   Dropdowns now include a `clearable` setting for letting users reset dropdowns to its empty state.

> If you are upgrading from a previous SUI version, be sure to add `@placeholder` to your [theme.config](/introduction/build-tools.html) to include the placeholder component in your code.

## New UI Component

#### Placeholders
[Placeholders](/elements/placeholder.html) can be used to reduce the jarringness, and perceived load time when loading new content
```html
<%- @partial('examples/content-loader') %>
```
```html
<div class="ui relaxed divided list">
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
      <div class="ui placeholder">
        <div class="paragraph">
          <div class="medium line"></div>
          <div class="short line"></div>
        </div>
      </div>
    </div>
  </div>
  <div class="item">
    <i class="large github middle aligned icon"></i>
    <div class="content">
      <div class="ui placeholder">
        <div class="paragraph">
          <div class="medium line"></div>
          <div class="short line"></div>
        </div>
      </div>
    </div>
  </div>
  <div class="item">
    <i class="large github middle aligned icon"></i>
    <div class="content">
      <div class="ui placeholder">
        <div class="paragraph">
          <div class="medium line"></div>
          <div class="short line"></div>
        </div>
      </div>
    </div>
  </div>
  <div class="item">
    <i class="large github middle aligned icon"></i>
    <div class="content">
      <div class="ui placeholder">
        <div class="paragraph">
          <div class="medium line"></div>
          <div class="short line"></div>
        </div>
      </div>
    </div>
  </div>
</div>
```

#### Placeholder Segment
[Placeholder segments](/elements/segment.html#placeholder) allow you to reserve space in your design for where content is intended to appear. This is useful when a page should prompt a user about its intended functionality, even when no content is present.
```html
<div class="ui placeholder segment">
  <div class="ui icon header">
    <i class="dont icon"></i>
    No users have been added yet
  </div>
  <div class="ui primary button">Add User</div>
</div>
```
```html
<div class="ui placeholder segment">
  <div class="ui stackable two column center aligned grid">
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

## New Features

#### Clearable Dropdowns
Now dropdowns can specify that their content can be cleared with `clearable: true`.

```html
<div class="ui search selection dropdown">
  <input type="hidden" name="country" value="kr">
  <div class="text">
    <i class="kr flag"></i>South Korea
  </div>
  <i class="dropdown icon"></i>
  <%- @partial('examples/single/flag-menu') %>
</div>
<div class="ui divider"></div>
<div class="ui secondary segment">
  Show me
  <div class="ui inline scrolling dropdown">
    <input type="hidden" name="skill" value="css">
    <div class="text">css</div>
    <i class="dropdown icon"></i>
    <div class="menu">
      <%- @partial('examples/single/preset-menu') %>
    </div>
  </div>
  classes currently available.
</div>
```

#### Improved Flexbox Modals
Although flex-box were introduced in `2.3.0` there were limitations which may have prevented some advanced use-cases. For example, flexbox modals did not support modals that used `detachable: false` and werent directly inside dimmer flex containers. Also some flex browsers (IE11) do not support absolutely positioned elements inside flex containers, so multiple overlapping modals could not be used in those cases.

`2.4.0` solves this by introducing a hybrid flex system, that will fall back to javascript positioning for browsers or layouts that aren't compatible with flex.

## 2.3

### A New Approach
After an extended period of patches, Semantic UI `2.3` marks the return to significant feature changes for the project.

In upcoming Semantic releases we will be releasing more frequently, but with smaller changesets, to make it easier for users to upgrade and adjust to global changes.

## New Features

#### Font Awesome 5.0 & Better Icon Searching
In `2.3` [icons](/elements/icon.html) now include a full port of [Font Awesome](https://fontawesome.com/) `5.0.6`, including 929 icons.

Icon categories now match icon categories in Font Awesome's documentation, making it easier to find icons between docs.
```html
<div class="ui doubling five column vertically padded grid">
  <div class="column"><i class="smile icon"></i>Smile</div>
  <div class="column"><i class="smile outline icon"></i>Smile Outline</div>
  <div class="column"><i class="hand rock icon"></i>Hand Rock </div>
  <div class="column"><i class="hand paper icon"></i>Hand Paper </div>
  <div class="column"><i class="hand scissors icon"></i>Hand Scissors</div>
</div>
```
Semantic UI [icon docs](/elements/icon.html) now includes a global icon search with easy copy and paste access to html

#### Flexbox Modals and Dimmers

Semantic UI `2.3` includes a rewrite of modal to include non-js flexbox positioning for vertical centering. No longer will you have to call `$('.ui.modal').modal('refresh')` if content height changes to recenter.

In addition there's a new setting `centered: false` which makes it easier to do top aligned modals when the internal may be dynamic and you dont want content to shift vertically.

```html
<div class="ui special modal">
  <div class="header">
    Top Aligned Modal
  </div>
  <div class="content">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    <div class="ui hidden divider"></div>
  </div>
  <div class="actions">
    <div class="ui button">
      Cancel
    </div>
    <div class="ui primary right labeled icon button">
      Submit
      <i class="checkmark icon"></i>
    </div>
  </div>
</div>
<a class="ui button" data-url="/images/large-pdf.pdf">
  Open Top Aligned Modal
</a>
```
```javascript
$('.ui.special.modal')
  .modal({
    centered: false
  })
  .modal('attach events', '.modal.example .button')
;
```

#### New Transitions
[Transition](/modules/transition.html) now includes `zoom` and `glow`. Glow is useful for highlighting elements on page,

```javascript
$('.autumn.leaf')
  .transition('zoom')
;
```
```javascript
$('.autumn.leaf')
  .transition('glow')
;
```
```html
<img src="/images/leaves/7.png" class="ui autumn leaf medium image">
```

#### Global Font Weight Variables
Theming now uses two no global variables `@bold` and `@normal` making it easier to modify font weights in a more complex font stack
```less
/* Use some custom font weights */
@bold: 600;
@normal: 400;
```

#### Local Category Search
You can now use category search with the `source` option without having to add API callbacks
```html
<div class="ui search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search countries...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```
```javascript
var categoryContent = [
  { category: 'South America', title: 'Brazil' },
  { category: 'South America', title: 'Peru' },
  { category: 'North America', title: 'Canada' },
  { category: 'Asia', title: 'South Korea' },
  { category: 'Asia', title: 'Japan' },
  { category: 'Asia', title: 'China' },
  { category: 'Europe', title: 'Denmark' },
  { category: 'Europe', title: 'England' },
  { category: 'Europe', title: 'France' },
  { category: 'Europe', title: 'Germany' },
  { category: 'Africa', title: 'Ethiopia' },
  { category: 'Africa', title: 'Nigeria' },
  { category: 'Africa', title: 'Zimbabwe' },
];
$('.local-category.example .ui.search')
  .search({
    type: 'category',
    source: categoryContent,
    searchFields: [
      'title',
      'category'
    ]
  })
;
```

#### Arrow Aligment on Small Popups
Semantic [popups](/modules/popup.html) now detects when horizontally aligning the popup on it's arrow is more reasonable than matching edges with a popup.
> To use this feature be sure to specify `movePopup: false` in your settings
```html
<img src="http://oi66.tinypic.com/2zr2ckk.jpg" class="ui image">

<div class="ui divider"></div>
<img src="/images/avatar/small/elliot.jpg" data-title="Elliot Fu" data-content="Elliot has been a member since July 2012" class="ui avatar image">
```
```javascript
$('.centering.example .avatar.image').popup();
```

#### Popups Support Multiple Coordinate Systems
Popups now can correctly place elements with two different coordinate systems. These are typically caused by having a parent element with css properties `transform` or `position`.
```html
<div id="one">
  <p>Button is in here</p>
  <div class="ui button">Button</div>
</div>
<div id="two">
  <p>Popup is in here</p>
  <div class="ui popup">
    <h4 class="ui header">
      Test
    </h4>
    <p>This popup now appears correct without having to move the popup to the same coordinate system by moving the DOM element.</p>
  </div>
</div>
```
```html
<div id="one">
  <p>Button is in here</p>
  <div class="ui button">Button</div>
</div>
<div id="two">
  <p>Popup is in here</p>
  <div class="ui popup">
    <h4 class="ui header">
      Test
    </h4>
    <p>This popup now appears correct without having to move the popup to the same coordinate system by moving the DOM element.</p>
  </div>
</div>
```
```css
/* Activating element is inside #one with different positioning context */
#one {
  display: block;
  position: relative;
  padding: 50px 100px;
  background-color: #F0F0F0;
}
/* Popup is inside two with position relative (creating another positioning context) */
#two {
  display: block;
  background-color: #E2EAE4;
  position: relative;
  top: 10px;
  padding: 50px 8px;
}
```
```javascript
$('.complex-popup.example .ui.button')
  .popup({
    movePopup: false,
    popup: $('.complex-popup.example .popup')
  })
;
```

#### New Matching Options
In addition, search now includes three tiers of matched results, similar to the options available in dropdown. Fuzzy results now are turned off by the new default `fullTextSearch: 'exact'`

*   Query matches the start of field exactly
*   Query matches any part of field
*   Query "fuzzy" matches field

```javascript
$('.ui.search')
  .search({
    fullTextSearch: 'exact' // only matches exact matches (no fuzzy matching)
  })
;
```

## 2.2

### By The Numbers
`2.2` represents nearly a half year of updates, many new features, and bug patches.

*   **124** [closed issues](https://github.com/Semantic-Org/Semantic-UI/issues?q=is%3Aissue+milestone%3A2.1+is%3Aclosed)
*   **40** new features
*   **70** bug fixes

For the complete list of bugs, their accompanying issue threads and the fixes please consult the release notes

[Release Notes](https://github.com/Semantic-Org/Semantic-UI/blob/master/RELEASE-NOTES.md#version-220---june-26-2016)

## Project Changes

#### Critical Bug Fixes

`2.2` brings many new bug fixes. For a complete list please check out our release notes. Here is a highlight of some critical bugs

```html
<div class="ui styled bug accordion">
  <div class="title">
    <i class="dropdown icon"></i>
    View Critical Bug List
  </div>
  <div class="content">
    <div class="ui large relaxed bulleted list">
      <div class="item">
        <b>All UI</b> - Using `component('setting, {})` to add multiple settings as an object literal, for example `error: {}`, will now deep extend the existing object instead of replacing it.
      </div>
      <div class="item">
        <b>API</b> - `beforeSend` would not correctly cancel request when `return false;` is used in callback.
      </div>
      <div class="item">
        <b>API</b> - `cache: 'local'` would not return the localstorage cached results in some cases
      </div>
      <div class="item">
        <b>Divider</b> - Descenders like "g" are cut off in `horizontal divider`
      </div>
      <div class="item">
        <b>Dropdown</b> - `forceSelection` will now automatically select values with multi dropdowns. When using `userAdditions` setting it will now automatically tokenize the current entered value
      </div>
      <div class="item">
        <b>Dropdown</b> - Fixed issue where value set using javascript DOM metadata would be cleared when a message or user addition triggered `refresh`
      </div>
      <div class="item">
        <b>Form Validation / Dropdown</b> - Using "enter" key in a `search dropdown` could cause a form to be submitted
      </div>
      <div class="item">
        <b>Form Validation</b> - Fix issue with some foreign email addresses with extended charsets causing email validation to fail
      </div>
      <div class="item">
        <b>Form Validation</b> - Revalidating a field `on: blur` could cause fields not yet interacted with to be validated
      </div>
      <div class="item">
        <b>Form</b> - Fixed issue with `(x) fields` and `equal width` fields where middle rows would be slightly smaller because they include both left and right padding in % width. (Edges only have one side padding). Field groups now use negative margins instead.
      </div>
      <div class="item">
        <b>Popup</b> - Fixed issue where clicking element inside popup removed from DOM (like clicking a multi select label) would cause popup to close
      </div>
      <div class="item">
        <b>Rail</b> - Fixed incorrect width for `close rail` and `very close rail` caused by variable addition with mixed units `px` + `em`
      </div>
      <div class="item">
        <b>Search</b> - Fixed bug where a previously XHR query could cause the next one to fail depending on the latency of the request.
      </div>
      <div class="item">
        <b>Search</b> - Fixed an issue where `onResult` returning `false` would not prevent the search menu from hiding. Clicking on an empty results message will also no longer close the search results.
      </div>
      <div class="item">
        <b>Sticky/Visibility</b> -  Added mutation observer to teardown element with `destroy` if removed from DOM context, fixing a possible memory leak
      </div>
      <div class="item">
        <b>Video</b> - Fixed issue with `.video('change')` behavior not properly changing video.
      </div>
    </div>
  </div>
</div>
```

## New Features

#### CSS-Only Tooltips
2.2 includes CSS only popups that work without JS initialization using the `data-tooltip` property on any element. CSS tooltips even support inversion and specified positioning.
```html
<div class="ui icon button" data-tooltip="Add users to your feed" data-delay="500">
  <i class="add icon"></i>
</div>
<div class="ui icon button" data-tooltip="Add users to your feed" data-inverted>
  <i class="add icon"></i>
</div>
<div class="ui button" data-tooltip="Add users to your feed" data-position="top left">
  Top Left
</div>
<div class="ui button" data-tooltip="Add users to your feed" data-position="top center">
  Top Center
</div>
<div class="ui button" data-tooltip="Add users to your feed" data-position="top right">
  Top Right
</div>
<div class="ui divider"></div>
<div class="ui button" data-tooltip="Add users to your feed" data-position="bottom left">
  Bottom Left
</div>
<div class="ui button" data-tooltip="Add users to your feed" data-position="bottom center">
  Bottom Center
</div>
<div class="ui button" data-tooltip="Add users to your feed" data-position="bottom right">
  Bottom Right
</div>
<div class="ui divider"></div>
<div class="ui button" data-tooltip="Add users to your feed" data-position="right center">
  Right Center
</div>
<div class="ui button" data-tooltip="Add users to your feed" data-position="left center">
  Left Center
</div>
```
```html
<div class="ui button" data-inverted data-tooltip="Add users to your feed" data-position="top left">
  Top Left
</div>
<div class="ui button" data-inverted data-tooltip="Add users to your feed" data-position="top center">
  Top Center
</div>
<div class="ui button" data-inverted data-tooltip="Add users to your feed" data-position="top right">
  Top Right
</div>
<div class="ui divider"></div>
<div class="ui button" data-inverted data-tooltip="Add users to your feed" data-position="bottom left">
  Bottom Left
</div>
<div class="ui button" data-inverted data-tooltip="Add users to your feed" data-position="bottom center">
  Bottom Center
</div>
<div class="ui button" data-inverted data-tooltip="Add users to your feed" data-position="bottom right">
  Bottom Right
</div>
<div class="ui divider"></div>
<div class="ui button" data-inverted data-tooltip="Add users to your feed" data-position="right center">
  Right Center
</div>
<div class="ui button" data-inverted data-tooltip="Add users to your feed" data-position="left center">
  Left Center
</div>
```

#### New Icons
2.2 of Semantic UI includes the latest version of [Font Awesome](http://fontawesome.io/) with 50+ new icons. For a complete breakdown of new icons please check [Font Awesome's list](http://fontawesome.io/whats-new/).
```html
<div class="ui doubling five column grid">
  <div class="column"><i class="wheelchair icon"></i>Wheelchair</div>
  <div class="column"><i class="asl interpreting icon"></i>American Sign Language (ASL) Interpreting</div>
  <div class="column"><i class="assistive listening systems icon"></i>Assistive Listening Systems</div>
  <div class="column"><i class="audio description icon"></i>Audio Description</div>
  <div class="column"><i class="blind icon"></i>Blind</div>
  <div class="column"><i class="braille icon"></i>Braille</div>
  <div class="column"><i class="deafness icon"></i>Deafness</div>
  <div class="column"><i class="low vision icon"></i>Low Vision</div>
  <div class="column"><i class="sign language icon"></i>Sign Language</div>
  <div class="column"><i class="universal access icon"></i>Universal Access</div>
  <div class="column"><i class="volume control phone icon"></i>Volume Control Phone</div>
</div>
<div class="ui divider"></div>
<a href="/elements/icon.html" class="ui primary button">View All Icons <i class="right chevron icon"></i></a>
```

#### Rapid-Ready Progress
Progress bars in 2.2 have been recoded to handle rapid update events.

Now developers can trigger updates at fast intervals without causing animations to stutter, or easing tweens to occur unnaturally.
```html
<div class="ui indicating progress" data-value="1" data-total="200" id="example5">
  <div class="bar">
    <div class="progress"></div>
  </div>
  <div class="label">Waiting for you to press button</div>
</div>
<a class="ui button" data-url="/images/large-pdf.pdf">
  Rapidly Update
</a>
```
```javascript
$('.rapid.example .ui.button')
  .on('click', function() {
    var
      $progress       = $('.rapid.example .ui.progress'),
      $button         = $(this),
      updateEvent
    ;
    clearInterval(window.fakeProgress)
    $progress.progress('reset');

    // updates every 10ms until complete
    window.fakeProgress = setInterval(function() {
      $progress.progress('increment');
      $button.text( $progress.progress('get value') );
      // stop incrementing when complete
      if($progress.progress('is complete')) {
        clearInterval(window.fakeProgress)
      }
    }, 10);
  })
;
$('.rapid.example .ui.progress')
  .progress({
    duration : 200,
    total    : 200,
    text     : {
      active: '{value} of {total} done'
    }
  })
;
```

#### Reduced Memory Leaks
[Sticky](/modules/sticky.html), [visibility](/behaviors/visibility.html), [popup](/modules/popup.html), and [dropdown](/modules/dropdown.html), modules that can attach events on initialization to `window` and `body`, for example to detect changes in window scroll, will now use [additional mutation observers](https://github.com/Semantic-Org/Semantic-UI/blob/master/dist/components/visibility.js#L143) to determine if they are removed from the DOM and automatically fire their `destroy` behaviors.

This can prevent memory leaks when the parent element of a component is removed without the element is propertly teared down by calling its `destroy` behavior.
```html
<div class="ui primary button">Simulate Memory Leak</div>
<div class="ui display segment">
  Not Active
</div>
<div class="wrapper">
  <div class="ui demo segment">
    This segment has visibility events attached to modify the button above to say "active" when it is on screen
  </div>
</div>
```
```javascript
$('.memory.example .demo.segment')
  .visibility({
    onOnScreen: function() {
      // this will no longer fire even though element was removed indirectly
      $('.memory.example .display.segment').html('This is active');
    }
  })
;
// button will remove parent of visibility element and callback will stop firing automatically
$('.memory.example .ui.button')
  .on('click', function() {
    $('.memory.example .display.segment').html('De-activated');
    $('.memory.example .wrapper')
      .remove()
    ;
  })
;
```

#### Dependent Form Validation
Form field validation can now specify a [depends property](/behaviors/form.html#dependent-fields) which will only cause validation to occur only when another field, like a checkbox or input, is selected.
```html
<form class="ui form segment">
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" name="isDoctor" />
      <label>Are you a doctor?</label>
    </div>
  </div>
  <div class="field">
    <label>How long have you been a medical professional</label>
    <input type="text" name="yearsPracticed">
  </div>
  <div class="ui divider"></div>
  <div class="ui blue submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```
```javascript
$('.depends.example .ui.form')
  .form({
    onSuccess: function() {
      alert('No form problems');
      return false;
    },
    fields: {
      yearsPracticed: {
        identifier : 'yearsPracticed',
        depends    : 'isDoctor',
        rules      : [
          {
            type   : 'empty',
            prompt : 'Please enter the number of years you have been a doctor'
          }
        ]
      }
    }
  })
;
```

#### Faster Dropdown Selection
We've updated dropdowns to make it simpler to breeze through forms with dropdowns, and provide more intuitive selection controls

*   Multiple select dropdowns use a new algorithm for line breaks based on actual rendered pixels and not estimated length based on glyph width calculations, meaning more choices can squeeze on a line than before.
*   Dropdowns now change selections on keyboards without hitting "enter", this lets users quickly navigate between dropdown elements in a form without having to hit "enter" before "tab" after each field entry, saving an additional keystroke.
*   All dropdown menus now support letter keyboard shortcuts. Hitting "C" for instance will let you jump to "California" in a dropdown list, then hitting it again "Colorado", even without using a search selection dropdown.

```html
<div class="ui two column very relaxed divided grid">
  <div class="column">
    <select class="ui fluid dropdown">
      <%- @partial('examples/single/state-options') %>
    </select>
  </div>
  <div class="column">
    <select class="ui multiple search fluid dropdown" multiple>
      <%- @partial('examples/single/state-options') %>
    </select>
  </div>
</div>
```

#### More Basic Buttons
We've added `primary`, `secondary`, `positive` and `negative` [basic buttons](/elements/button.html#basic)
```html
<button class="ui primary basic button">Primary</button>
<button class="ui secondary basic button">Secondary</button>
<button class="ui positive basic button">Positive</button>
<button class="ui negative basic button">Negative</button>
```

#### Popup Boundaries and Scroll Context
Popups now include a new setting `boundary` that let you specify that a popup should not escape the boundary of another section. This can be useful in complex paned layouts

Additionally popups can now specify a scroll context, to allow for scroll containers other than window to cause a clicked popup to hide on scroll.
```javascript
$('.boundary.example .button')
  .popup({
    boundary: '.boundary.example .segment'
  })
;
```
```html
<div class="ui segment">
  <div class="ui button" data-content="This popup is very long but wont escape the segment it is placed in">Hover Me</div>
  <p>Normally this popup would open in the default position `top center` but because this would escape the boundaries of the segment it will search other available positions until it can find one to place the popup while staying inside the segment</p>
</div>
```

## New Settings

We've added many new settings to components to help provide more granular control for some use-cases.

#### Dropdowns
```html
<table class="ui definition table">
  <tbody>
    <tr>
      <td>selectOnKeydown</td>
      <td>Whether dropdown should change active selection on keyboard shortcuts, preventing the requirement of hitting `enter` to confirm selection before the user tabs out of the field. (This will save one extra keystroke)
      </td>
    </tr>
    <tr>
      <td>allowReselection</td>
      <td>Setting to `true` will allow `onChange` to be triggered even when reselecting the same option</td>
    </tr>
    <tr>
      <td>fullTextSearch</td>
      <td>Setting to true will allow search across any part of string, setting to `exact` will disable fuzzy matching for dropdowns.</td>
    </tr>
    <tr>
      <td>hideAdditions</td>
      <td>Setting to true will allow custom user additions without triggering a special dropdown message for "Add custom choice". This is now enabled by default</td>
    </tr>
    <tr>
      <td>minCharacters</td>
      <td>Minimum characters required to begin showing filtered results</td>
    </tr>
  </tbody>
</table>
```
[Dropdown settings](/modules/dropdown.html#settings)

#### Popup
```html
<table class="ui definition table">
  <tbody>
    <tr>
      <td>boundary</td>
      <td>A selector, or DOM element that the popup should never escape when positioning itself
      </td>
    </tr>
    <tr>
      <td>scrollContext</td>
      <td>A selector or DOM element which should be used for determining if user has scrolled.</td>
    </tr>
    <tr>
      <td>observeChanges</td>
      <td>Whether popup should automatically watch for its own removal from page to avoid memory leaks.</td>
    </tr>
  </tbody>
</table>
```
[Popup settings](/modules/popup.html#settings)

#### Search
```html
<table class="ui definition table">
  <tbody>
    <tr>
      <td>selectFirstResult</td>
      <td>Whether the first search result element should be selected after results appear.
      </td>
    </tr>
    <tr>
      <td>showNoResults</td>
      <td>Whether a message should appear when no search results are returned
      </td>
    </tr>
  </tbody>
</table>
```
[Search settings](/modules/search.html#settings)

#### Rating
```html
<table class="ui definition table">
  <tbody>
    <tr>
      <td>fireOnInit</td>
      <td>Whether the rating component should fire callbacks on initialization.
      </td>
    </tr>
  </tbody>
</table>
```
[Rating settings](/modules/rating.html#settings)

#### Visibility
```html
<table class="ui definition table">
  <tbody>
    <tr>
      <td>zIndex</td>
      <td>Allows you to specify the `z-index` used with `type: 'fixed'`
      </td>
    </tr>
    <tr>
      <td>onFixed</td>
      <td>A callback used with `type: 'fixed'` to occur when content is fixed to the page.
      </td>
    </tr>
    <tr>
      <td>onUnfixed</td>
      <td>A callback used with `type: 'fixed'` to occur when content is fixed to the page.
      </td>
    </tr>
    <tr>
      <td>onLoaded</td>
      <td>A callback used with `type: 'image'` to occur when content is loaded.
      </td>
    </tr>
    <tr>
      <td>onAllLoaded</td>
      <td>A callback used with `type: 'image'` to occur when all images initialized together are loaded.
      </td>
    </tr>
  </tbody>
</table>
```
[Visibility settings](/behaviors/visibility.html#settings)

#### Tab
```html
<table class="ui definition table">
  <tbody>
    <tr>
      <td>cacheType</td>
      <td>When set to `html` will cache the tabs html after load, reloading with the exact same html. Setting to `response` will cache the serve response, allowing for load events to fire with same contents.
      </td>
    </tr>
    <tr>
      <td>deactivate</td>
      <td>When set to `siblings` deactivates only DOM elements that are siblings of the selected tab activator. `all` will deactivate all other elements initialized at the same time.
      </td>
    </tr>
  </tbody>
</table>
```
[Tab settings](/modules/tab.html#settings)

#### Shape
```html
<table class="ui definition table">
  <tbody>
    <tr>
      <td>width</td>
      <td>When set to `next` will use the size of the next `side` during the shape's animation. When set to `initial` it will use the size of the shape at initialization. When set to a specifix pixel width, will force the size to that width.
      </td>
    </tr>
    <tr>
      <td>height</td>
      <td>When set to `next` will use the size of the next `side` during the shape's animation. When set to `initial` it will use the size of the shape at initialization. When set to a specifix pixel height, will force the size to that height.
      </td>
    </tr>
  </tbody>
</table>
```
[Shape settings](/modules/shape.html#settings)

## 2.1

### The Tally
`2.1` sums up around two months of work, including many new features, and updates to help bulletproof existing UI.

*   **72** [closed issues](https://github.com/Semantic-Org/Semantic-UI/issues?q=is%3Aissue+milestone%3A2.1+is%3Aclosed)
*   **70** bug fixes
*   **23** new UI updates
*   **14** feature enhancements

To see the complete list of updates [review our release notes](https://github.com/Semantic-Org/Semantic-UI/blob/<%= @getBranch() %>/RELEASE-NOTES.md#version-210---sep-01-2015)

#### Labeled Buttons
[Labeled buttons](/elements/button.html#labeled) are a useful design pattern for displaying a tally alongside a button.

Labeled buttons are compatible with any label type, but looks great alongside a `basic label`.
```html
<div class="ui labeled button" tabindex="0">
  <div class="ui red button">
    <i class="heart icon"></i> Like
  </div>
  <a class="ui basic red label">
    2,048
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
<div class="ui labeled button" tabindex="0">
  <div class="ui basic violet button">
    <i class="hospital icon"></i> Hospitals
  </div>
  <a class="ui violet tag label">
    2,048
  </a>
</div>
<div class="ui divider"></div>
<div class="ui labeled button" tabindex="0">
  <div class="ui yellow button">
    <i class="star icon"></i> Star
  </div>
  <a class="ui basic yellow left pointing label">
    1,048
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

#### Basic Labels
We've added a new style [basic label](/elements/label.html#basic) that is less intrusive, and compatible with all other label variations, reducing their complexity.
```html
<a class="ui basic label">Basic</a>
<a class="ui pointing basic label">Pointing</a>
<a class="ui basic image label">
  <img src="/images/avatar/small/elliot.jpg">
  Elliot
<a class="ui pointing red basic label">Red Pointing</a>
<a class="ui blue basic label">Blue</a>
</a>
<div class="ui divider"></div>
<div class="ui equal width stretched grid">
  <div class="column">
    <div class="ui segment">
      <a class="ui right pointing basic teal ribbon label">Pointing</a> Look over here
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
  <div class="column">
    <div class="ui segment">
      <a class="ui teal top right attached basic label">So Complex</a>
      <a class="ui orange top left attached basic label">So Simple</a>
      <a class="ui violet bottom attached top pointing basic label">Much adjectives</a>
    </div>
  </div>
</div>
```

#### Multiple Input Labels
[Labeled input](/elements/input.html#labeled) now supports labels on both sides of content at the same time.
```html
<div class="ui right labeled input">
  <div class="ui basic label">$</div>
  <input type="text" placeholder="Amount">
  <div class="ui basic label">.00</div>
</div>
```

#### More Tabular Directions
[Tabular menus](/collections/menu.html#tabular) now support `right` and `bottom` positioning.
```html
<div class="ui grid">
  <div class="twelve wide stretched column">
    <div class="ui segment">
      This is an stretched grid column. This segment will always match the tab height
    </div>
  </div>
  <div class="four wide column">
    <div class="ui vertical fluid right tabular menu">
      <a class="active item">
        Bio
      </a>
      <a class="item">
        Pics
      </a>
      <a class="item">
        Companies
      </a>
      <a class="item">
        Links
      </a>
    </div>
  </div>
</div>
```
```html
<div class="ui top attached segment">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
<div class="ui three item bottom attached tabular menu">
  <a class="active item">
    Active Project
  </a>
  <a class="item">
    Project #2
  </a>
  <a class="item">
    Project #3
  </a>
</div>
```
```html
<div class="ui grid">
  <div class="four wide column">
    <div class="ui vertical fluid tabular menu">
      <a class="active item">
        Bio
      </a>
      <a class="item">
        Pics
      </a>
      <a class="item">
        Companies
      </a>
      <a class="item">
        Links
      </a>
    </div>
  </div>
  <div class="twelve wide stretched column">
    <div class="ui segment">
      This is an stretched grid column. This segment will always match the tab height
    </div>
  </div>
</div>
```

#### Enhanced Vertical Dividers
Grids now support using multiple [vertical dividers](/elements/divider.html#vertical-divider) per column, in any specified arrangement.
```html
<div class="ui very relaxed vertically divided grid">
  <div class="row" style="position:relative;">
    <div class="six wide column">
      <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
    </div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ui vertical divider">and</div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ui vertical divider">and</div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="row" style="position:relative;">
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ui vertical divider">not</div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ui vertical divider">nor</div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="six wide column">
      <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
    </div>
  </div>
</div>
```

#### Inverted Colored Menu
[Inverted menus](/collections/menu.html#inverted) now support individual `item` colors

```html
<div class="ui three item labeled icon inverted menu">
  <a class="active red item">
    <i class="gamepad icon"></i>
    Games
  </a>
  <a class="pink item">
    <i class="video camera icon"></i>
    Channels
  </a>
  <a class="blue item">
    <i class="video play icon"></i>
    Videos
  </a>
</div>
```
```html
<div class="ui vertical inverted menu">
  <a class="active teal item">
    Inbox
  </a>
  <a class="orange item">
    Spam
  </a>
  <a class="violet item">
    Updates
  </a>
  <div class="item">
    <div class="ui transparent inverted icon input">
      <input type="text" placeholder="Search mail...">
      <i class="search icon"></i>
    </div>
  </div>
</div>
```

#### Reversable Grid Columns
Grids now support [reversing their column flow](/collections/grid.html#reversed) per-device. This can be useful when a column should appear on the opposite side of the screen on smaller screens.

Reversing grids are also designed to be compatible with column-order specific variations like divided or celled
```html
<div class="ui tablet reversed divided equal width grid">
  <div class="column">
    Computer First <br>
    Tablet Fourth
  </div>
  <div class="column">
    Computer Second <br>
    Tablet Third
  </div>
  <div class="column">
    Computer Third <br>
    Tablet Second
  </div>
  <div class="column">
    Computer Fourth <br>
    Tablet First
  </div>
</div>
```

#### Stackable Cards
Cards have a [stackable](/views/card.html#stackable) variation so that they appear full width on mobile.
```html
<div class="ui two stackable cards">
  <div class="ui card">
    <div class="content">
      <div class="right floated meta">14h</div>
      <img class="ui avatar image" src="/images/avatar/large/elliot.jpg"> Elliot
    </div>
    <div class="content">
      <span class="right floated">
        <i class="heart outline like icon"></i>
        17 likes
      </span>
      <i class="comment icon"></i>
      3 comments
    </div>
    <div class="extra content">
      <div class="ui large transparent left icon input">
        <i class="heart outline icon"></i>
        <input type="text" placeholder="Add Comment...">
      </div>
    </div>
  </div>
  <div class="ui card">
    <div class="content">
      <div class="right floated meta">14h</div>
      <img class="ui avatar image" src="/images/avatar/large/elliot.jpg"> Elliot
    </div>
    <div class="content">
      <span class="right floated">
        <i class="heart outline like icon"></i>
        17 likes
      </span>
      <i class="comment icon"></i>
      3 comments
    </div>
    <div class="extra content">
      <div class="ui large transparent left icon input">
        <i class="heart outline icon"></i>
        <input type="text" placeholder="Add Comment...">
      </div>
    </div>
  </div>
  <div class="ui card">
    <div class="content">
      <div class="right floated meta">14h</div>
      <img class="ui avatar image" src="/images/avatar/large/elliot.jpg"> Elliot
    </div>
    <div class="content">
      <span class="right floated">
        <i class="heart outline like icon"></i>
        17 likes
      </span>
      <i class="comment icon"></i>
      3 comments
    </div>
    <div class="extra content">
      <div class="ui large transparent left icon input">
        <i class="heart outline icon"></i>
        <input type="text" placeholder="Add Comment...">
      </div>
    </div>
  </div>
  <div class="ui card">
    <div class="content">
      <div class="right floated meta">14h</div>
      <img class="ui avatar image" src="/images/avatar/large/elliot.jpg"> Elliot
    </div>
    <div class="content">
      <span class="right floated">
        <i class="heart outline like icon"></i>
        17 likes
      </span>
      <i class="comment icon"></i>
      3 comments
    </div>
    <div class="extra content">
      <div class="ui large transparent left icon input">
        <i class="heart outline icon"></i>
        <input type="text" placeholder="Add Comment...">
      </div>
    </div>
  </div>
</div>
```

#### Fixed Tables
[Tables](/collections/table.html#fixed) now include a variation for using `table-layout: fixed`, which does not adjust column widths based on size.

This can help present data more cleanly with content that is uniformly formatted.

Fixed tables also support content collapsing using `text-overflow: ellipsis` when used with `single line`.
```html
<table class="ui fixed center aligned celled table">
  <thead>
    <th>Name</th>
    <th>Status</th>
    <th>Gender</th>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>Male</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Male</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>Female</td>
    </tr>
  </tbody>
</table>
```
```html
<h4 class="ui header">
  Fixed Tables
</h4>
<table class="ui fixed single line celled table">
  <thead>
    <th>Name</th>
    <th>Status</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td title="This is much too long to fit I'm sorry about that">This is much too long to fit I'm sorry about that</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Shorter description</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>Shorter description</td>
    </tr>
  </tbody>
</table>
```

## New Behaviors

#### Fully Customizable JSON
In `2.1` all component that uses remote data will let you specify a `fields` array to modify expected JSON property names, saving you the trouble of specifying an [onResponse](/behaviors/api.html#response-callbacks) callback to modify the data structure.
```html
<div class="ui search">
  <div class="ui left icon input">
    <input class="prompt" type="text" placeholder="Search GitHub">
    <i class="github icon"></i>
  </div>
</div>
```
```javascript
$('.ui.search')
  .search({
    apiSettings: {
      url: '//api.github.com/search/repositories?q={query}'
    },
    fields: {
      results : 'items',
      title   : 'name',
      url     : 'html_url'
    }
  })
;
```

#### Fields can also be used with local search to simplify working with unusual search sources.
```javascript
$('.ui.search')
  .search({
    searchFields: ['pickle'],
    fields: {
      title   : 'mustard'
    },
    source: [
      {
        mustard: 'Title #1',
        pickle: 'thing'
      },
      {
        mustard: 'Title #2',
        pickle: 'another thing'
      },
      {
        mustard: 'Title #3',
        pickle: 'thing 100'
      }
    ]
  })
;
```
```html
<div class="ui search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search...">
    <i class="search icon"></i>
  </div>
</div>
```

#### Credit Card Validation
We've added new validation rules for payment. These work with luhn and [non-luhn card numbers](http://stackoverflow.com/questions/7863058/does-the-luhn-algorithm-work-for-all-mainstream-credit-cards-discover-visa-m?answertab=votes#tab-top). If you only accept a certain set of credit cards you can specify that too.
> Try `4565340519181845` a test visa card number
```html
<form class="ui form segment">
  <div class="field">
    <label>Credit Card</label>
    <input name="card" type="text" value="4444444444444444">
  </div>
  <div class="field">
    <label>Visa / Amex</label>
    <input name="exact-card" type="text" value="4444444444444444">
  </div>
  <div class="ui submit button">Submit</div>
</form>
```
```javascript
$('.payment.example form')
  .form({
    on: 'blur',
    inline: true,
    fields: {
      card: {
        identifier  : 'card',
        rules: [
          {
            type   : 'creditCard',
            prompt : 'Please enter a valid credit card'
          }
        ]
      },
      exactCard: {
        identifier  : 'exact-card',
        rules: [
          {
            type   : 'creditCard[visa,amex]',
            prompt : 'Please enter a visa or amex card'
          }
        ]
      }
    }
  })
;
```

#### Cancellable Checkboxes
[Checkboxes](/modules/checkbox.html) now include four new callbacks `beforeChecked`, `beforeUnchecked`, `beforeDeterminate`, and `beforeIndeterminate`, returning `false` from these callbacks will cancel the action from occuring.
```html
<div class="ui checkbox">
  <input type="checkbox" name="example" />
  <label>Maybe this will work</label>
</div>
```
```javascript
$('.cancel.example .ui.checkbox')
  .checkbox({
    beforeChecked: function() {
      var
        luckyPerson = (Math.random() < 0.5)
      ;
      return luckyPerson;
    }
  })
;
```

## Theme Updates

#### Global Form Focus
Global variables have been added to modify form focus color across all components. The default theme now uses a light blue to signal selection.
```html
<form class="ui form">
  <div class="two fields">
    <div class="field">
      <label>First Name</label>
      <input type="text" name="first-name" placeholder="First Name">
    </div>
    <div class="field">
      <label>Last Name</label>
      <input type="text" name="last-name" placeholder="Last Name">
    </div>
  </div>
  <div class="field">
    <label>Gender</label>
    <select class="ui dropdown">
      <option value="">Gender</option>
      <option value="1">Male</option>
      <option value="0">Female</option>
    </select>
  </div>
  <div class="field">
    <div class="ui checkbox">
      <input type="checkbox" />
      <label>I agree to the Terms and Conditions</label>
    </div>
  </div>
  <button class="ui button" type="submit">Submit</button>
</form>
```

#### Updated Form Validation
[Form validation](/behaviors/form.html) now uses `basic label` for validation prompts.
```html
<form class="ui form">
  <div class="field">
    <label>First Name</label>
    <input type="text" name="first-name" placeholder="First Name">
  </div>
  <div class="field">
    <label>Last Name</label>
    <input type="text" name="last-name" placeholder="Last Name">
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" name="terms" />
      <label>I agree to the Terms and Conditions</label>
    </div>
  </div>
  <button class="ui button" type="submit">Submit</button>
</form>
```

#### Colored Basic Buttons
[Basic colored buttons](/elements/button.html#basic) now are colored without `hover`, making the style more similar to common usage on most sites.
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

#### Labeled Icon Menu
Horizontal `labeled icon menu` now use stacked icons to appear more in-tune with common icon menu usage.
```html
<div class="ui three item labeled icon inverted menu">
  <a class="active red item">
    <i class="gamepad icon"></i>
    Games
  </a>
  <a class="pink item">
    <i class="video camera icon"></i>
    Channels
  </a>
  <a class="blue item">
    <i class="video play icon"></i>
    Videos
  </a>
</div>
```

## 2.0

### Introduction

#### The Devil is in the Details
2.0 brings a whopping set of changes to the project:

*   **129** enhancements
*   **118** bug fixes
*   **3** new components
*   Rewrites of many components including [menu](/collections/menu.html), and [input](/elements/input.html)

There's just too much to cover in one page, but we've tried our best to give you examples of some of the new features available in 2.0

To see the full list of what's changed check out the project's release notes.

[View Release Notes](https://github.com/Semantic-Org/Semantic-UI/blob/<%= @getBranch() %>/RELEASE-NOTES.md#version-200---june-30-2015)

## Global Changes

#### Flexbox All The Things
[Flexbox](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Flexible_boxes) allows for elements to intuitively resize to fill available space, making many complex layouts much simpler.

13 components: [Form](/collections/form.html), [Grid](/collections/grid.html), [Menu](/collections/menu.html), [Message](/elements/message.html), [Button](/elements/button.html), [Segment](/elements/segment.html), [Step](/elements/step.html), [Dropdown](/modules/dropdown.html), [Modal](/modules/modal.html), [Feed](/views/feed.html), [Statistic](/views/statistics.html), [Card](/views/card.html), [Item](/views/item.html) now use [flex](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Flexible_boxes) for positioning.

#### Complete Spectrum
Semantic now includes twelve named colors, enough for most languages to [distinguish between colors](https://en.wikipedia.org/wiki/Linguistic_relativity_and_the_color_naming_debate#Berlin_and_Kay). New in 2.0 are: olive, violet, brown and grey.
```html
<a class="ui grey label">Grey</a>
<a class="ui red pointing label">Red</a>
<a class="ui orange tag label">Orange</a>
<a class="ui yellow bottom pointing label">Yellow</a>
<a class="ui olive label">
  <i class="mail icon"></i>
  Olive
</a>
<a class="ui green right pointing label">Green</a>
<a class="ui teal label">
  Teal
  <div class="detail">Detail</div>
</a>
<a class="ui blue image label">
  <img src="/images/avatar2/small/elyse.png">
  Blue
</a>
<a class="ui violet label">
  Violet
</a>
<a class="ui purple label">
  Purple
  <i class="delete icon"></i>
</a>
<div class="ui horizontal segments">
  <div class="ui segment">
    <div class="ui pink top left ribbon label">Pink</div>
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
  <div class="ui segment">
    <div class="ui brown right ribbon label">Brown</div>
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
</div>
```

#### New Default Theme
All components have received a face-lift for 2.0. Styles give slightly more negative space and a few idiosyncratic design touches have been removed.

#### More Precise EM Values
EM sizing has been improved in 2.0, with all values rounding to exact pixel values. This helps common relative sizing pitfalls like rounding errors in vertical alignment.

Em variables now use new globally calculated em ratios, like `@relative4px`, to express pixel values in terms of root em size. This makes sure components don't include confusing decimal or fractional values when dealing with sizing.

## Grids

#### Flexbox Grid
Grids in 2.0 now use [flexbox](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Flexible_boxes) so columns are always equal height across rows.
```html
<div class="ui three column divided grid">
  <div class="row">
    <div class="column">
      <div class="ui segment">
        1
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        1
      </div>
      <div class="ui segment">
        2
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        1
      </div>
      <div class="ui segment">
        2
      </div>
      <div class="ui segment">
        3
      </div>
    </div>
  </div>
</div>
```

#### Grids Create Themselves
The new [equal width](/collections/grid.html#equal-width) variation adjusts column widths automatically splitting available width between columns.
```html
<div class="ui equal width grid">
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
</div>
```
> If a column has a specified width, other columns will adapt to take available space around it.
```html
<div class="ui equal width grid">
  <div class="column"></div>
  <div class="eight wide column"></div>
  <div class="column"></div>
</div>
```

#### Containers
[Containers](/elements/container.html) have been added as a simple way to limit content width.
```html
<div class="ui container">
  <div class="ui three column grid">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
</div>
```

#### Stretched rows
The new [stretched](/collections/grid.html#stretched) variation makes vertically aligning layouts much simpler. Columns will not only match heights, but stretch their contents to match heights.
```html
<div class="ui three column stretched grid">
  <div class="column">
    <div class="ui segment">
      1
    </div>
    <div class="ui segment">
      2
    </div>
  </div>
  <div class="column">
    <div class="ui segment">
      <img class="ui image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="column">
    <div class="ui segment">
      1
    </div>
    <div class="ui segment">
      2
    </div>
  </div>
</div>
```

## Dropdowns

#### Multiple Selection
Multiple select dropdowns are now available, and can generate automatically from standard HTML selects.

Dropdowns now all support advanced keyboard shortcuts like `pagedown`, `delete`, `shift+left` `ctrl+click`, and selection using first letter of item.

Additionally dropdowns will now automatically open `upward` if there is not enough space available in the viewport below a dropdown.
```html
<select class="ui fluid dropdown" multiple>
  <%- @partial('examples/single/state-options') %>
</select>
```

#### User Tagging
All dropdowns, single and multiple now support user tagging. Values can be automatically separated by a delimiter and placed in a hidden input, or extend an existing select element.
```javascript
$('.ui.dropdown')
  .dropdown({
    allowAdditions: true
  })
;
```
```html
<div class="ui form">
  <div class="two fields">
    <div class="field">
      <label>Primary Skill</label>
      <div class="ui search selection dropdown">
        <input name="primary-skill" type="hidden" />
        <i class="dropdown icon"></i>
        <div class="default text">Skills</div>
        <div class="menu">
          <%- @partial('examples/single/preset-menu') %>
        </div>
      </div>
    </div>
    <div class="field">
      <label>Skills</label>
      <div class="ui multiple search selection dropdown">
        <input name="all-skills" type="hidden" />
        <i class="dropdown icon"></i>
        <div class="default text">Skills</div>
        <div class="menu">
          <%- @partial('examples/single/preset-menu') %>
        </div>
      </div>
    </div>
  </div>
</div>
```

#### Remote Data
All dropdowns now support loading remote data. Selected name value pairs retrieved remotely are stored in [sessionStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage) so that selected values are repopulated correctly even after a page refresh.

Try refreshing the page and searching the same letter, results will appear instantly without a server roundtrip.
```javascript
// somewhere in app
$.api.settings.api = {
  queryTags: '//api.semantic-ui.com/tags/{query}'
};
$('.ui.dropdown')
  .dropdown({
    apiSettings: {
      action: 'queryTags'
    }
  })
;
```
```html
<div class="ui form">
  <div class="two fields">
    <div class="field">
      <label>Favorite Animal</label>
      <div class="ui search selection dropdown">
        <input type="hidden">
        <i class="dropdown icon"></i>
        <input type="text" class="search">
        <div class="default text">Select one...</div>
      </div>
    </div>
    <div class="field">
      <label>Favorite Animals</label>
      <div class="ui multiple search selection dropdown">
        <input type="hidden">
        <i class="dropdown icon"></i>
        <input type="text" class="search">
        <div class="default text">Select...</div>
      </div>
    </div>
  </div>
</div>
```

#### Scrolling Menus
[Scrolling menu](/modules/dropdown.html#scrolling) and nested menus are now supported.

Listing choices in a nested menu will still give all the same keyboard shortcuts and filtering as regular menus.
```html
<div class="ui floating dropdown labeled icon button">
  <i class="filter icon"></i>
  <span class="text">Filter Posts</span>
  <div class="menu">
    <div class="ui icon search input">
      <i class="search icon"></i>
      <input type="text" placeholder="Search tags...">
    </div>
    <div class="divider"></div>
    <div class="header">
      <i class="tags icon"></i>
      Tag Label
    </div>
    <div class="scrolling menu">
      <div class="item">
        <div class="ui violet empty circular label"></div>
        Already Fixed
      </div>
      <div class="item">
        <div class="ui blue empty circular label"></div>
        Announcement
      </div>
      <div class="item">
        <div class="ui black empty circular label"></div>
        Cannot Fix
      </div>
      <div class="item">
        <div class="ui green empty circular label"></div>
        Discussion
      </div>
      <div class="item">
        <div class="ui orange empty circular label"></div>
        Enhancement
      </div>
      <div class="item">
        <div class="ui red empty circular label"></div>
        Important
      </div>
      <div class="item">
        <div class="ui pink empty circular label"></div>
        Interesting
      </div>
      <div class="item">
        <div class="ui purple empty circular label"></div>
        News
      </div>
      <div class="item">
        <div class="ui yellow empty circular label"></div>
        Off Topic
      </div>
      <div class="item">
        <div class="ui brown empty circular label"></div>
        Up Next
      </div>
    </div>
  </div>
</div>
```

#### Advanced Shortcuts
Dropdowns now support advanced shortcuts like `page down` and `page up`, scrolling to selection on first letter press, i.e. "N" for New York, `shift+left/right` for group selection, and `ctrl+click` for modifying groups.
```html
<img class="ui image" src="/images/gif/multi-shortcuts.gif">
```

#### Much More
Dropdowns support many, many new features, including:

*   Maximum selection count is supported for multiple selects
*   Mutation observers will now watch for changes in menus or the elements they are generated from and will update choices automatically
*   Custom templated error messages are now supported with dropdowns

## API

#### Local Caching
API now supports [sessionStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage) caching. This setting makes repeated requests to a URL return results instantly across a user's session, drastically improving performance for components like [search](/modules/search.html).

Try refreshing the page and searching the same letter, results will appear instantly without a server roundtrip.
```javascript
$('.ui.dropdown')
  .dropdown({
    apiSettings: {
      cache : 'local',
      url: '//api.semantic-ui.com/tags/{query}'
    }
  })
;
```
```html
<div class="ui form">
  <div class="field">
    <label>Favorite Animal</label>
    <div class="ui search selection dropdown">
      <input type="hidden">
      <i class="dropdown icon"></i>
      <input type="text" class="search">
      <div class="default text">Select one...</div>
    </div>
  </div>
</div>
```

#### Translates Any API
[API](/behaviors/api.html) now lets you adjust a server's JSON response using a new callback, [onResponse](/behaviors/api.html#response-callbacks). This can let you restructure third party APIs to match your local data requirements.
```html
<div class="ui search">
  <div class="ui left icon input">
    <input class="prompt" type="text" placeholder="Search GitHub">
    <i class="github icon"></i>
  </div>
</div>
```
```javascript
$('.ui.search')
  .search({
    type          : 'category',
    minCharacters : 3,
    apiSettings   : {
      onResponse: function(githubResponse) {
        var
          response = {
            results : {}
          }
        ;
        // translate GitHub API response to work with search
        $.each(githubResponse.items, function(index, item) {
          var
            language   = item.language || 'Unknown',
            maxResults = 8
          ;
          if(index >= maxResults) {
            return false;
          }
          // create new language category
          if(response.results[language] === undefined) {
            response.results[language] = {
              name    : language,
              results : []
            };
          }
          // add result to category
          response.results[language].results.push({
            title       : item.name,
            description : item.description,
            url         : item.html_url
          });
        });
        return response;
      },
      url: '//api.github.com/search/repositories?q={query}'
    }
  })
;
```

#### Mocked Responses
[API](/behaviors/api.html) now supports mocked responses, letting you specify how responses are returned in advance.
