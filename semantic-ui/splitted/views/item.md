# Item

An item view presents large collections of site content for display

## Types

#### Items
A group of items.
> Item views are designed to be responsive with images stacking at mobile resolutions.
```html
<div class="ui items">
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="content">
      <a class="header">Header</a>
      <div class="meta">
        <span>Description</span>
      </div>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
      <div class="extra">
        Additional Details
      </div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="content">
      <a class="header">Header</a>
      <div class="meta">
        <span>Description</span>
      </div>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
      <div class="extra">
        Additional Details
      </div>
    </div>
  </div>
</div>
```

## Content

#### Image
An item can contain an image
```html
<div class="ui divided items">
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

#### Content
An item can contain content
```html
<div class="ui divided items">
  <div class="item">
    <div class="ui tiny image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="middle aligned content">
      Content A
    </div>
  </div>
  <div class="item">
    <div class="ui tiny image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="middle aligned content">
      Content B
    </div>
  </div>
  <div class="item">
    <div class="ui tiny image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="middle aligned content">
      Content C
    </div>
  </div>
</div>
```

#### Header
An item can contain a header
```html
<div class="ui items">
  <div class="item">
    <div class="ui tiny image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="middle aligned content">
      <a class="header">12 Years a Slave</a>
    </div>
  </div>
  <div class="item">
    <div class="ui tiny image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="middle aligned content">
      <a class="header">My Neighbor Totoro</a>
    </div>
  </div>
  <div class="item">
    <div class="ui tiny image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="middle aligned content">
      <a class="header">Watchmen</a>
    </div>
  </div>
</div>
```

#### Metadata
An item can contain content metadata
> You can include an arbitrary amount of metadata using your own class conventions, all child elements will automatically be spaced
```html
<div class="ui items">
  <div class="item">
    <div class="ui small image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="content">
      <div class="header">Arrowhead Valley Camp</div>
      <div class="meta">
        <span class="price">$1200</span>
        <span class="stay">1 Month</span>
      </div>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
    </div>
  </div>
  <div class="item">
    <div class="ui small image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="content">
      <div class="header">Buck's Homebrew Stayaway</div>
      <div class="meta">
        <span class="price">$1000</span>
        <span class="stay">2 Weeks</span>
      </div>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
    </div>
  </div>
  <div class="item">
    <div class="ui small image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="content">
      <div class="header">Astrology Camp</div>
      <div class="meta">
        <span class="price">$1600</span>
        <span class="stay">6 Weeks</span>
      </div>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
    </div>
  </div>
</div>
```

#### Link
An item can contain links as images, headers, or inside content
> To make the entire content of an item link, check out the link variation below
```html
<div class="ui items">
  <div class="item">
    <a class="ui tiny image">
      <img src="/images/avatar/large/stevie.jpg">
    </a>
    <div class="content">
      <a class="header">Stevie Feliciano</a>
      <div class="description">
        <p>Stevie Feliciano is a <a>library scientist</a> living in New York City. She likes to spend her time reading, running, and writing.</p>
      </div>
    </div>
  </div>
  <div class="item">
    <a class="ui tiny image">
      <img src="/images/avatar/large/veronika.jpg">
    </a>
    <div class="content">
      <a class="header">Veronika Ossi</a>
      <div class="description">
        <p>Veronika Ossi is a set designer living in New York who <a>enjoys</a> kittens, music, and partying.</p>
      </div>
    </div>
  </div>
  <div class="item">
    <a class="ui tiny image">
      <img src="/images/avatar/large/jenny.jpg">
    </a>
    <div class="content">
      <a class="header">Jenny Hess</a>
      <div class="description">
        <p>Jenny is a student studying Media Management at <a>the New School</a>.</p>
      </div>
    </div>
  </div>
</div>
```

#### Description
An item can contain a description with a single or multiple paragraphs
```html
<div class="ui items">
  <div class="item">
    <a class="ui small image">
      <img src="/images/wireframe/image.png" class="ui wireframe image">
    </a>
    <div class="content">
      <a class="header">Cute Dog</a>
      <div class="description">
        <p>Cute dogs come in a variety of shapes and sizes. Some cute dogs are cute for their adorable faces, others for their tiny stature, and even others for their massive size.</p>
        <p>Many people also have their own barometers for what makes a cute dog.</p>
      </div>
    </div>
  </div>
</div>
```

#### Extra Content
An item can contain extra content meant to be formatted separately from the main content
```html
<div class="ui items">
  <div class="item">
    <div class="content">
      <a class="header">Cute Dog</a>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
      <div class="extra">
        <i class="green check icon"></i>
        121 Votes
      </div>
    </div>
  </div>
</div>
```

#### Rating
An item can contain icons signifying a 'like' or 'favorite' action
> You can use the rating component to attach events to like and favorite icons
```html
<div class="ui items">
  <div class="item">
    <a class="ui tiny image">
      <img src="/images/avatar/large/jenny.jpg">
    </a>
    <div class="middle aligned content">
      <div class="header">
        <i class="like icon"></i>
        Veronika Ossi
      </div>
    </div>
  </div>
  <div class="item">
    <a class="ui tiny image">
      <img src="/images/avatar/large/justen.jpg">
    </a>
    <div class="middle aligned content">
      <div class="header">
        <i class="favorite icon"></i>
        Justen Kitsune
      </div>
    </div>
  </div>
</div>
```

## Variations

#### Stacking
A table can specify how it stacks items responsively
```html
<div class="ui unstackable items">
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="content">
      <a class="header">Header</a>
      <div class="meta">
        <span>Description</span>
      </div>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
      <div class="extra">
        Additional Details
      </div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="content">
      <a class="header">Header</a>
      <div class="meta">
        <span>Description</span>
      </div>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
      <div class="extra">
        Additional Details
      </div>
    </div>
  </div>
</div>
```

#### Divided
Items can be divided to better distinguish between grouped content
> The following example uses `ui` for legibility only. This is not necessary for using `ui items`
```html
<div class="ui divided items">
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="content">
      <a class="header">12 Years a Slave</a>
      <div class="meta">
        <span class="cinema">Union Square 14</span>
      </div>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
      <div class="extra">
        <div class="ui label">IMAX</div>
        <div class="ui label"><i class="globe icon"></i> Additional Languages</div>
      </div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="content">
      <a class="header">My Neighbor Totoro</a>
      <div class="meta">
        <span class="cinema">IFC Cinema</span>
      </div>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
      <div class="extra">
        <div class="ui right floated primary button">
          Buy tickets
          <i class="right chevron icon"></i>
        </div>
        <div class="ui label">Limited</div>
      </div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="content">
      <a class="header">Watchmen</a>
      <div class="meta">
        <span class="cinema">IFC</span>
      </div>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
      <div class="extra">
        <div class="ui right floated primary button">
          Buy tickets
          <i class="right chevron icon"></i>
        </div>
      </div>
    </div>
  </div>
</div>
```

#### Relaxed
A group of items can relax its padding to provide more negative space
```html
<div class="ui relaxed items">
  <div class="item">
    <div class="ui tiny image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="middle aligned content">
      <a class="header">12 Years a Slave</a>
    </div>
  </div>
  <div class="item">
    <div class="ui tiny image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="middle aligned content">
      <a class="header">My Neighbor Totoro</a>
    </div>
  </div>
  <div class="item">
    <div class="ui tiny image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="middle aligned content">
      <a class="header">Watchmen</a>
    </div>
  </div>
</div>
```
```html
<div class="ui very relaxed items">
  <div class="item">
    <div class="ui tiny image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="middle aligned content">
      <a class="header">12 Years a Slave</a>
    </div>
  </div>
  <div class="item">
    <div class="ui tiny image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="middle aligned content">
      <a class="header">My Neighbor Totoro</a>
    </div>
  </div>
  <div class="item">
    <div class="ui tiny image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="middle aligned content">
      <a class="header">Watchmen</a>
    </div>
  </div>
</div>
```

#### Link Item
An item can be formatted so that the entire contents link to another page
```html
<div class="ui link items">
  <div class="item">
    <div class="ui tiny image">
      <img src="/images/avatar/large/stevie.jpg">
    </div>
    <div class="content">
      <div class="header">Stevie Feliciano</div>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
    </div>
  </div>
  <div class="item">
    <div class="ui tiny image">
      <img src="/images/avatar/large/veronika.jpg">
    </div>
    <div class="content">
      <div class="header">Veronika Ossi</div>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
    </div>
  </div>
  <div class="item">
    <div class="ui tiny image">
      <img src="/images/avatar/large/jenny.jpg">
    </div>
    <div class="content">
      <div class="header">Jenny Hess</div>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
    </div>
  </div>
</div>
```

#### Vertical Alignment
Content can specify its vertical alignment
> You can include an arbitrary amount of metadata using your own class conventions, all child elements will automatically be spaced
```html
<div class="ui items">
  <div class="item">
    <div class="ui small image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="content">
      <div class="header">
        Top Aligned
      </div>
    </div>
  </div>
  <div class="item">
    <div class="ui small image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="middle aligned content">
      <div class="header">
        Middle Aligned
      </div>
    </div>
  </div>
  <div class="item">
    <div class="ui small image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="bottom aligned content">
      <div class="header">
        Bottom Aligned
      </div>
    </div>
  </div>
</div>
```

#### Floated Content
Any content element can be floated left or right
> You can include an arbitrary amount of metadata using your own class conventions, all child elements will automatically be spaced
```html
<div class="ui items">
  <div class="item">
    <div class="ui small image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="middle aligned content">
      <div class="header">
        Content A
      </div>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
      <div class="extra">
        <div class="ui right floated button">
          Action
        </div>
      </div>
    </div>
  </div>
  <div class="item">
    <div class="ui small image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="middle aligned content">
      <div class="header">
        Content B
      </div>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
      <div class="extra">
        <div class="ui right floated button">
          Action
        </div>
      </div>
    </div>
  </div>
  <div class="item">
    <div class="ui small image">
      <img src="/images/wireframe/image.png">
    </div>
    <div class="middle aligned content">
      <div class="header">
        Content C
      </div>
      <div class="description">
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
      <div class="extra">
        <div class="ui right floated button">
          Action
        </div>
      </div>
    </div>
  </div>
</div>
```
