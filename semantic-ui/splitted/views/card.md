# Card

A card displays site content in a manner similar to a playing card

## Types

#### Card
A single card.
> To ensure cards are equal height use the plural, `cards`. Card groups automatically uses [flex](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Flexible_boxes) styles to match height between cards in the same row.
```html
<div class="ui card">
  <div class="image">
    <img src="/images/avatar2/large/kristy.png">
  </div>
  <div class="content">
    <a class="header">Kristy</a>
    <div class="meta">
      <span class="date">Joined in 2013</span>
    </div>
    <div class="description">
      Kristy is an art director living in New York.
    </div>
  </div>
  <div class="extra content">
    <a>
      <i class="user icon"></i>
      22 Friends
    </a>
  </div>
</div>
```
```html
<div class="ui card">
  <div class="content">
    <div class="right floated meta">14h</div>
    <img class="ui avatar image" src="/images/avatar/large/elliot.jpg"> Elliot
  </div>
  <div class="image">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
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
```

#### Cards
A group of cards.
> Cards are designed to be flexible to your content. `content` blocks can include any custom elements related to your content.
```html
<div class="ui cards">
  <div class="card">
    <div class="content">
      <img class="right floated mini ui image" src="/images/avatar/large/elliot.jpg">
      <div class="header">
        Elliot Fu
      </div>
      <div class="meta">
        Friends of Veronika
      </div>
      <div class="description">
        Elliot requested permission to view your contact details
      </div>
    </div>
    <div class="extra content">
      <div class="ui two buttons">
        <div class="ui basic green button">Approve</div>
        <div class="ui basic red button">Decline</div>
      </div>
    </div>
  </div>
  <div class="card">
    <div class="content">
      <img class="right floated mini ui image" src="/images/avatar/large/jenny.jpg">
      <div class="header">
        Jenny Hess
      </div>
      <div class="meta">
        New Member
      </div>
      <div class="description">
        Jenny wants to add you to the group **best friends**
      </div>
    </div>
    <div class="extra content">
      <div class="ui two buttons">
        <div class="ui basic green button">Approve</div>
        <div class="ui basic red button">Decline</div>
      </div>
    </div>
  </div>
</div>
```
```html
<div class="ui link cards">
  <div class="card">
    <div class="image">
      <img src="/images/avatar2/large/matthew.png">
    </div>
    <div class="content">
      <div class="header">Matt Giampietro</div>
      <div class="meta">
        <a>Friends</a>
      </div>
      <div class="description">
        Matthew is an interior designer living in New York.
      </div>
    </div>
    <div class="extra content">
      <span class="right floated">
        Joined in 2013
      </span>
      <span>
        <i class="user icon"></i>
        75 Friends
      </span>
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img src="/images/avatar2/large/molly.png">
    </div>
    <div class="content">
      <div class="header">Molly</div>
      <div class="meta">
        <span class="date">Coworker</span>
      </div>
      <div class="description">
        Molly is a personal assistant living in Paris.
      </div>
    </div>
    <div class="extra content">
      <span class="right floated">
        Joined in 2011
      </span>
      <span>
        <i class="user icon"></i>
        35 Friends
      </span>
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img src="/images/avatar2/large/elyse.png">
    </div>
    <div class="content">
      <div class="header">Elyse</div>
      <div class="meta">
        <a>Coworker</a>
      </div>
      <div class="description">
        Elyse is a copywriter working in New York.
      </div>
    </div>
    <div class="extra content">
      <span class="right floated">
        Joined in 2014
      </span>
      <span>
        <i class="user icon"></i>
        151 Friends
      </span>
    </div>
  </div>
</div>
```

## Content

#### Content Block
A card can contain blocks of content
```html
<div class="ui card">
  <div class="content">
    <div class="header">Project Timeline</div>
  </div>
  <div class="content">
    <h4 class="ui sub header">Activity</h4>
    <div class="ui small feed">
      <div class="event">
        <div class="content">
          <div class="summary">
             <a>Elliot Fu</a> added <a>Jenny Hess</a> to the project
          </div>
        </div>
      </div>
      <div class="event">
        <div class="content">
          <div class="summary">
             <a>Stevie Feliciano</a> was added as an <a>Administrator</a>
          </div>
        </div>
      </div>
      <div class="event">
        <div class="content">
          <div class="summary">
             <a>Helen Troy</a> added two pictures
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="extra content">
    <button class="ui button">Join Project</button>
  </div>
</div>
```

#### Image
A card can contain an image
> Cards can use [reveal](/elements/reveal.html) or [dimmers](/modules/dimmer.html) to easily show additional content, or options on hover
```html
<div class="ui card">
  <div class="ui slide masked reveal image">
    <img src="/images/avatar/large/jenny.jpg" class="visible content">
    <img src="/images/avatar/large/elliot.jpg" class="hidden content">
  </div>
  <div class="content">
    <a class="header">Team Fu & Hess</a>
    <div class="meta">
      <span class="date">Created in Sep 2014</span>
    </div>
  </div>
  <div class="extra content">
    <a>
      <i class="users icon"></i>
      2 Members
    </a>
  </div>
</div>
```
```javascript
$('.special.cards .image').dimmer({
  on: 'hover'
});
```
```html
<div class="ui special cards">
  <div class="card">
    <div class="blurring dimmable image">
      <div class="ui dimmer">
        <div class="content">
          <div class="center">
            <div class="ui inverted button">Add Friend</div>
          </div>
        </div>
      </div>
      <img src="/images/avatar/large/elliot.jpg">
    </div>
    <div class="content">
      <a class="header">Team Fu</a>
      <div class="meta">
        <span class="date">Created in Sep 2014</span>
      </div>
    </div>
    <div class="extra content">
      <a>
        <i class="users icon"></i>
        2 Members
      </a>
    </div>
  </div>
  <div class="card">
    <div class="blurring dimmable image">
      <div class="ui inverted dimmer">
        <div class="content">
          <div class="center">
            <div class="ui primary button">Add Friend</div>
          </div>
        </div>
      </div>
      <img src="/images/avatar/large/jenny.jpg">
    </div>
    <div class="content">
      <a class="header">Team Hess</a>
      <div class="meta">
        <span class="date">Created in Aug 2014</span>
      </div>
    </div>
    <div class="extra content">
      <a>
        <i class="users icon"></i>
        2 Members
      </a>
    </div>
  </div>
</div>
```

#### Header
A card can contain a header
```html
<div class="ui cards">
  <div class="card">
    <div class="content">
      <div class="header">Elliot Fu</div>
      <div class="meta">Friend</div>
      <div class="description">
        Elliot Fu is a film-maker from New York.
      </div>
    </div>
  </div>
  <div class="card">
    <div class="content">
      <div class="header">Veronika Ossi</div>
      <div class="meta">Friend</div>
      <div class="description">
        Veronika Ossi is a set designer living in New York who enjoys kittens, music, and partying.
      </div>
    </div>
  </div>
  <div class="card">
    <div class="content">
      <div class="header">Jenny Hess</div>
      <div class="meta">Friend</div>
      <div class="description">
        Jenny is a student studying Media Management at the New School
      </div>
    </div>
  </div>
</div>
```

#### Metadata
A card can contain content metadata
> You can include an arbitrary amount of metadata using your own class conventions, all child elements will automatically be spaced
```html
<div class="ui card">
  <div class="content">
    <div class="header">Cute Dog</div>
    <div class="meta">
      <span>2 days ago</span>
      <a>Animals</a>
    </div>
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
</div>
```

#### Link
A card can contain contain links as images, headers, or inside content
> To make the entire content of a card link, check out the link variation below
```html
<div class="ui card">
  <a class="image" href="#">
    <img src="/images/avatar/large/steve.jpg">
  </a>
  <div class="content">
    <a class="header" href="#">Steve Jobes</a>
    <div class="meta">
      <a>Last Seen 2 days ago</a>
    </div>
  </div>
</div>
```

#### Buttons
A card can contain buttons
```html
<div class="ui cards">
  <div class="card">
    <div class="content">
      <div class="header">Elliot Fu</div>
      <div class="description">
        Elliot Fu is a film-maker from New York.
      </div>
    </div>
    <div class="ui bottom attached button">
      <i class="add icon"></i>
      Add Friend
    </div>
  </div>
  <div class="card">
    <div class="content">
      <div class="header">Veronika Ossi</div>
      <div class="description">
        Veronika Ossi is a set designer living in New York who enjoys kittens, music, and partying.
      </div>
    </div>
    <div class="ui bottom attached button">
      <i class="add icon"></i>
      Add Friend
    </div>
  </div>
  <div class="card">
    <div class="content">
      <div class="header">Jenny Hess</div>
      <div class="description">
        Jenny is a student studying Media Management at the New School
      </div>
    </div>
    <div class="ui bottom attached button">
      <i class="add icon"></i>
      Add Friend
    </div>
  </div>
</div>
```

#### Approval
A card can contain a like or star action.
```html
<div class="ui card">
  <div class="content">
    <i class="right floated like icon"></i>
    <i class="right floated star icon"></i>
    <div class="header">Cute Dog</div>
    <div class="description">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
  <div class="extra content">
    <span class="left floated like">
      <i class="like icon"></i>
      Like
    </span>
    <span class="right floated star">
      <i class="star icon"></i>
      Favorite
    </span>
  </div>
</div>
```

#### Description
A card can contain a description with one or more paragraphs
```html
<div class="ui card">
  <div class="content">
    <div class="header">Cute Dog</div>
    <div class="meta">2 days ago</div>
    <div class="description">
      <p>Cute dogs come in a variety of shapes and sizes. Some cute dogs are cute for their adorable faces, others for their tiny stature, and even others for their massive size.</p>
      <p>Many people also have their own barometers for what makes a cute dog.</p>
    </div>
  </div>
</div>
```

#### Extra Content
A card can contain extra content meant to be formatted separately from the main content
```html
<div class="ui card">
  <div class="content">
    <div class="header">Cute Dog</div>
    <div class="meta">2 days ago</div>
    <div class="description">
      <p>Cute dogs come in a variety of shapes and sizes. Some cute dogs are cute for their adorable faces, others for their tiny stature, and even others for their massive size.</p>
      <p>Many people also have their own barometers for what makes a cute dog.</p>
    </div>
  </div>
  <div class="extra content">
    <i class="check icon"></i>
    121 Votes
  </div>
</div>
```

## Variations

#### Fluid Card
A fluid card takes up the width of its container
```html
<div class="ui three column grid">
  <div class="column">
    <div class="ui fluid card">
      <div class="image">
        <img src="/images/avatar/large/daniel.jpg">
      </div>
      <div class="content">
        <a class="header">Daniel Louise</a>
      </div>
    </div>
  </div>
  <div class="column">
    <div class="ui fluid card">
      <div class="image">
        <img src="/images/avatar/large/helen.jpg">
      </div>
      <div class="content">
        <a class="header">Helen Troy</a>
      </div>
    </div>
  </div>
  <div class="column">
    <div class="ui fluid card">
      <div class="image">
        <img src="/images/avatar/large/elliot.jpg">
      </div>
      <div class="content">
        <a class="header">Elliot Fu</a>
      </div>
    </div>
  </div>
</div>
```

#### Centered Card
A card can center itself inside its container
```html
<div class="ui centered card">
  <div class="image">
    <img src="/images/avatar2/large/elyse.png">
  </div>
  <div class="content">
    <a class="header">Elyse</a>
  </div>
</div>
```

#### Raised Card
A card may be formatted to raise above the page.
```html
<div class="ui raised card">
  <div class="content">
    <div class="header">Cute Dog</div>
    <div class="meta">
      <span class="category">Animals</span>
    </div>
    <div class="description">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
  <div class="extra content">
    <div class="right floated author">
      <img class="ui avatar image" src="/images/avatar/small/matt.jpg"> Matt
    </div>
  </div>
</div>
```
```html
<div class="ui raised link card">
  <div class="content">
    <div class="header">Cute Dog</div>
    <div class="meta">
      <span class="category">Animals</span>
    </div>
    <div class="description">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
  <div class="extra content">
    <div class="right floated author">
      <img class="ui avatar image" src="/images/avatar/small/matt.jpg"> Matt
    </div>
  </div>
</div>
```

#### Link Card
A card can be formatted so that the entire contents link to another page
```html
<a class="ui card" href="http://www.dog.com">
  <div class="content">
    <div class="header">Cute Dog</div>
    <div class="meta">
      <span class="category">Animals</span>
    </div>
    <div class="description">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
  <div class="extra content">
    <div class="right floated author">
      <img class="ui avatar image" src="/images/avatar/small/matt.jpg"> Matt
    </div>
  </div>
</a>
```
```html
<div class="ui link card">
  <div class="content">
    <div class="header">Cute Dog</div>
    <div class="meta">
      <span class="category">Animals</span>
    </div>
    <div class="description">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
  <div class="extra content">
    <div class="right floated author">
      <img class="ui avatar image" src="/images/avatar/small/matt.jpg"> Matt
    </div>
  </div>
</div>
```

#### Floated Content
Any content element can be floated left or right
> You can include an arbitrary amount of metadata using your own class conventions, all child elements will automatically be spaced
```html
<div class="ui card">
  <div class="content">
    <div class="header">Cute Dog</div>
    <div class="meta">
      <span class="right floated time">2 days ago</span>
      <span class="category">Animals</span>
    </div>
    <div class="description">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
  <div class="extra content">
    <div class="right floated author">
      <img class="ui avatar image" src="/images/avatar/small/matt.jpg"> Matt
    </div>
  </div>
</div>
```

#### Text Alignment
Any element inside a card can have its text alignment specified
> You can include an arbitrary amount of metadata using your own class conventions, all child elements will automatically be spaced
```html
<div class="ui card">
  <div class="content">
    <div class="center aligned header">Jenny Hess</div>
    <div class="center aligned description">
      <p>Jenny is a student studying Media Management at the New School</p>
    </div>
  </div>
  <div class="extra content">
    <div class="center aligned author">
      <img class="ui avatar image" src="http://semantic-ui.com/images/avatar/small/jenny.jpg"> Jenny
    </div>
  </div>
</div>
```

#### Colored
A card can specify a color
```html
<div class="ui four cards">
  <a class="red card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/white-image.png">
    </div>
  </a>
  <a class="orange card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/white-image.png">
    </div>
  </a>
  <a class="yellow card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/white-image.png">
    </div>
  </a>
  <a class="olive card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/white-image.png">
    </div>
  </a>
  <a class="green card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/white-image.png">
    </div>
  </a>
  <a class="teal card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/white-image.png">
    </div>
  </a>
  <a class="blue card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/white-image.png">
    </div>
  </a>
  <a class="violet card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/white-image.png">
    </div>
  </a>
  <a class="purple card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/white-image.png">
    </div>
  </a>
  <a class="pink card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/white-image.png">
    </div>
  </a>
  <a class="brown card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/white-image.png">
    </div>
  </a>
  <a class="grey card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/white-image.png">
    </div>
  </a>
  <a class="black card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/white-image.png">
    </div>
  </a>
</div>
```

#### Column Count
A group of cards can set how many cards should exist in a row
```html
<div class="ui four cards">
  <div class="card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="extra">
      Rating:
      <div class="ui star rating" data-rating="4"></div>
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="extra">
      Rating:
      <div class="ui star rating" data-rating="2"></div>
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="extra">
      Rating:
      <div class="ui star rating" data-rating="3"></div>
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="extra">
      Rating:
      <div class="ui star rating" data-rating="4"></div>
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="extra">
      Rating:
      <div class="ui star rating" data-rating="3"></div>
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="extra">
      Rating:
      <div class="ui star rating" data-rating="3"></div>
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="extra">
      Rating:
      <div class="ui star rating" data-rating="4"></div>
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="extra">
      Rating:
      <div class="ui star rating" data-rating="4"></div>
    </div>
  </div>
</div>
```

#### Stackable
A group of cards can automatically stack rows to a single columns on mobile devices
> Resize your browser to a smaller size to see the cards stack after reaching mobile breakpoints
```html
<div class="ui three stackable cards">
  <div class="card">
    <div class="image">
      <img src="/images/avatar/large/elliot.jpg">
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img src="/images/avatar/large/helen.jpg">
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img src="/images/avatar/large/jenny.jpg">
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img src="/images/avatar/large/veronika.jpg">
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img src="/images/avatar/large/stevie.jpg">
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img src="/images/avatar/large/steve.jpg">
    </div>
  </div>
</div>
```

#### Doubling
A group of cards can double its column width for mobile
> Resize your browser to a smaller size to see the cards stack after reaching mobile breakpoints
```html
<div class="ui six doubling cards">
  <div class="card">
    <div class="image">
      <img src="/images/avatar/large/elliot.jpg">
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img src="/images/avatar/large/helen.jpg">
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img src="/images/avatar/large/jenny.jpg">
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img src="/images/avatar/large/veronika.jpg">
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img src="/images/avatar/large/stevie.jpg">
    </div>
  </div>
  <div class="card">
    <div class="image">
      <img src="/images/avatar/large/steve.jpg">
    </div>
  </div>
</div>
```
