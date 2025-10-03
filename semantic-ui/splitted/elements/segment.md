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
