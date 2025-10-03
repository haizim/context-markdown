## === advertisement.md ===

# Advertisement

An ad displays third-party promotional content

## Types

#### Ad
A standard ad
> The following example uses a basic [AdSense implementation](https://support.google.com/adsense/answer/181947?ctx=as2&rd=2&ref_topic=29033). Your code will vary depending on your ad network.
```html
<div class="ui medium rectangle ad">
  <script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
  <ins class="adsbygoogle"
       style="display:inline-block;width:300px;height:250px"
       data-ad-client="ca-pub-4591861188995436"
       data-ad-slot="4640466102"></ins>
  <script>
  (adsbygoogle = window.adsbygoogle || []).push({});
  </script>
</div>
<div class="ui leaderboard ad">
  <script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
  <!-- Leaderboard -->
  <ins class="adsbygoogle"
       style="display:inline-block;width:728px;height:90px"
       data-ad-client="ca-pub-4591861188995436"
       data-ad-slot="6710577704"></ins>
  <script>
  (adsbygoogle = window.adsbygoogle || []).push({});
  </script>
</div>
<div class="ui banner ad">
  <script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
  <!-- Banner -->
  <ins class="adsbygoogle"
       style="display:inline-block;width:468px;height:60px"
       data-ad-client="ca-pub-4591861188995436"
       data-ad-slot="9803644904"></ins>
  <script>
  (adsbygoogle = window.adsbygoogle || []).push({});
  </script>
</div>
```
```html
<div class="ui medium rectangle ad">
  <!-- Ad Code Goes Here
  <ins class="adsbygoogle"
       style="display:inline-block;width:300px;height:250px"
       data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
       data-ad-slot="XXXXXXXXXX"></ins>
  <script>
  (adsbygoogle = window.adsbygoogle || []).push({});
  </script>
  !-->
</div>
<div class="ui leaderboard ad">
<!-- Leaderboard
<ins class="adsbygoogle"
     style="display:inline-block;width:728px;height:90px"
     data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
     data-ad-slot="XXXXXXXXXXXXXXXX"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>
!-->
</div>
<div class="ui banner ad">
<!-- Banner
<ins class="adsbygoogle"
     style="display:inline-block;width:468px;height:60px"
     data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
     data-ad-slot="XXXXXXXXXXXXXXXX"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>
!-->
</div>
```

#### Common Units
An advertisement can appear in common ad unit sizes
> These additional examples use the `test` variation to appear on the page. `ui ad` is best used as a wrapper for third party ad network content like [AdSense](http://www.google.com/adsense/start/) or [DoubleClick](http://www.google.com/doubleclick/publishers/welcome/).
```html
<div class="ui medium rectangle test ad" data-text="Medium Rectangle"></div>
<div class="ui banner test ad" data-text="Banner"></div>
<div class="ui leaderboard test ad" data-text="Leaderboard"></div>
<div class="ui large rectangle test ad" data-text="Large Rectangle"></div>
<div class="ui half page test ad" data-text="Half Page"></div>
```

#### Mobile
An ad can use common mobile ad sizes
> Mobile ads will automatically only appear on mobile browser viewports
```html
<div class="ui mobile leaderboard test ad" data-text="Mobile Leaderboard"></div>
<div class="ui mobile banner test ad" data-text="Mobile Banner"></div>
```

#### Rectangle
An ad can use a common rectangle ad unit size
```html
<div class="ui vertical rectangle test ad" data-text="Vertical Rectangle"></div>
<div class="ui small rectangle test ad" data-text="Small Rectangle"></div>
```

#### Button
An ad can use button ad unit size
```html
<div class="ui button test ad" data-text="Button"></div>
<div class="ui square button test ad" data-text="Square Button"></div>
<div class="ui small button test ad" data-text="Small Button"></div>
```

#### Skyscraper
An ad can use skyscraper ad unit size
```html
<div class="ui skyscraper test ad" data-text="Skyscraper"></div>
<div class="ui wide skyscraper test ad" data-text="Wide Skyscraper"></div>
```

#### Banner
An ad can use banner ad unit size
```html
<div class="ui banner test ad" data-text="Banner"></div>
<div class="ui vertical banner test ad" data-text="Vertical Banner"></div>
<div class="ui top banner test ad" data-text="Top Banner"></div>
<div class="ui half banner test ad" data-text="Half Banner"></div>
```

#### Leaderboards
An ad can use leaderboard ad unit size
```html
<div class="ui leaderboard test ad" data-text="Leaderboard"></div>
<div class="ui large leaderboard test ad" data-text="Large Leaderboard"></div>
<div class="ui billboard test ad" data-text="Billboard"></div>
```

#### Panorama
An ad can use panorama ad unit size
```html
<div class="ui panorama test ad" data-text="Panorama"></div>
```

#### Netboard
An ad can use netboard ad unit size
```html
<div class="ui netboard test ad" data-text="Netboard"></div>
```

## Variations

#### Centered
An advertisement can appear centered
```html
<div class="ui centered banner test ad"></div>
```

#### Test
A advertisement can be formatted to help verify placement
> You can adjust the text displayed for your test ad placement by changing the value of `data-text`
```html
<div class="ui medium rectangle test ad" data-text="Ad Unit 1"></div>
<div class="ui medium rectangle test ad" data-text="Ad Unit 2"></div>
```


## === card.md ===

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


## === comment.md ===

# Comment

A comment displays user feedback to site content

## Types

#### Comments
A basic list of comments
> These examples uses `ui segment` to create content segments. This is not required.
> **UI Views** provide structured layouts, but do not hook up site specific code. You will need to add your own Javascript behaviors to hide and show the appropriate forms. For example, having a reply button open a reply form
```html
<div class="ui comments">
  <h3 class="ui dividing header">Comments</h3>
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/matt.jpg">
    </a>
    <div class="content">
      <a class="author">Matt</a>
      <div class="metadata">
        <span class="date">Today at 5:42PM</span>
      </div>
      <div class="text">
        How artistic!
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
  </div>
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/elliot.jpg">
    </a>
    <div class="content">
      <a class="author">Elliot Fu</a>
      <div class="metadata">
        <span class="date">Yesterday at 12:30AM</span>
      </div>
      <div class="text">
        <p>This has been very useful for my research. Thanks as well!</p>
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
    <div class="comments">
      <div class="comment">
        <a class="avatar">
          <img src="/images/avatar/small/jenny.jpg">
        </a>
        <div class="content">
          <a class="author">Jenny Hess</a>
          <div class="metadata">
            <span class="date">Just now</span>
          </div>
          <div class="text">
            Elliot you are always so right :)
          </div>
          <div class="actions">
            <a class="reply">Reply</a>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/joe.jpg">
    </a>
    <div class="content">
      <a class="author">Joe Henderson</a>
      <div class="metadata">
        <span class="date">5 days ago</span>
      </div>
      <div class="text">
        Dude, this is awesome. Thanks so much
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
  </div>
  <form class="ui reply form">
    <div class="field">
      <textarea></textarea>
    </div>
    <div class="ui blue labeled submit icon button">
      <i class="icon edit"></i> Add Reply
    </div>
  </form>
</div>
```

## Content

### Comment

#### Avatar
A comment can contain an image or avatar
```html
<div class="ui comments">
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/elliot.jpg">
    </a>
    <div class="content">
      <a class="author">Elliot Fu</a>
    </div>
  </div>
</div>
```

#### Metadata
A comment can contain metadata about the comment, an arbitrary amount of metadata may be defined.
```html
<div class="ui comments">
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/stevie.jpg">
    </a>
    <div class="content">
      <a class="author">Stevie Feliciano</a>
      <div class="metadata">
        <div class="date">2 days ago</div>
        <div class="rating">
          <i class="star icon"></i>
          5 Faves
        </div>
      </div>
      <div class="text">
        Hey guys, I hope this example comment is helping you read this documentation.
      </div>
    </div>
  </div>
</div>
```

#### Actions
A comment can contain an list of actions a user may perform related to this comment.
```html
<div class="ui comments">
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/joe.jpg">
    </a>
    <div class="content">
      <a class="author">Tom Lukic</a>
      <div class="text">
        This will be great for business reports. I will definitely download this.
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
        <a class="save">Save</a>
        <a class="hide">Hide</a>
        <a>
          <i class="expand icon"></i>
          Full-screen
        </a>
      </div>
    </div>
  </div>
</div>
```

#### Reply Form
A comment can contain a form to reply to a comment. This may have arbitrary content.
> If a comment form is located inside a `ui comment` it will be formatted as an nested reply form. If the comment form is included after all comments, it will be formatted as a normal reply form.
```html
<div class="ui comments">
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/steve.jpg">
    </a>
    <div class="content">
      <a class="author">Steve Jobes</a>
      <div class="metadata">
        <div class="date">2 days ago</div>
      </div>
      <div class="text">
        Revolutionary!
      </div>
      <div class="actions">
        <a class="reply active">Reply</a>
      </div>
      <form class="ui reply form">
        <div class="field">
          <textarea></textarea>
        </div>
        <div class="ui primary submit labeled icon button">
          <i class="icon edit"></i> Add Reply
        </div>
      </form>
    </div>
  </div>
</div>
```
```html
<div class="ui comments">
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/joe.jpg">
    </a>
    <div class="content">
      <a class="author">Joe Henderson</a>
      <div class="metadata">
        <div class="date">1 day ago</div>
      </div>
      <div class="text">
        <p>The hours, minutes and seconds stand as visible reminders that your effort put them all there. </p>
        <p>Preserve until your next run, when the watch lets you see how Impermanent your efforts are.</p>
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
  </div>
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/christian.jpg">
    </a>
    <div class="content">
      <a class="author">Christian Rocha</a>
      <div class="metadata">
        <div class="date">2 days ago</div>
      </div>
      <div class="text">
        I re-tweeted this.
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
  </div>
  <form class="ui reply form">
    <div class="field">
      <textarea></textarea>
    </div>
    <div class="ui primary submit labeled icon button">
      <i class="icon edit"></i> Add Comment
    </div>
  </form>
</div>
```

## States

#### Collapsed
Comments can be collapsed, or hidden from view
```html
<div class="ui comments">
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/christian.jpg">
    </a>
    <div class="content">
      <a class="author">Christian Rocha</a>
      <div class="metadata">
        <span class="date">2 days ago</span>
      </div>
      <div class="text">
        I'm very interested in this motherboard. Do you know if it'd work in a Intel LGA775 CPU socket?
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
    <div class="collapsed comments">
      <div class="comment">
        <a class="avatar">
          <img src="/images/avatar/small/elliot.jpg">
        </a>
        <div class="content">
          <a class="author">Elliot Fu</a>
          <div class="metadata">
            <span class="date">1 day ago</span>
          </div>
          <div class="text">
            No, it wont
          </div>
          <div class="actions">
            <a class="reply">Reply</a>
          </div>
        </div>
        <div class="comments">
          <div class="comment">
            <a class="avatar">
              <img src="/images/avatar/small/jenny.jpg">
            </a>
            <div class="content">
              <a class="author">Jenny Hess</a>
              <div class="metadata">
                <span class="date">20 minutes ago</span>
              </div>
              <div class="text">
                Maybe it would.
              </div>
              <div class="actions">
                <a class="reply">Reply</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
```

## Variations

#### Threaded
A comment list can be threaded to showing the relationship between conversations
```html
<div class="ui threaded comments">
  <h3 class="ui dividing header">Comments</h3>
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/matt.jpg">
    </a>
    <div class="content">
      <a class="author">Matt</a>
      <div class="metadata">
        <span class="date">Today at 5:42PM</span>
      </div>
      <div class="text">
        How artistic!
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
  </div>
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/elliot.jpg">
    </a>
    <div class="content">
      <a class="author">Elliot Fu</a>
      <div class="metadata">
        <span class="date">Yesterday at 12:30AM</span>
      </div>
      <div class="text">
        <p>This has been very useful for my research. Thanks as well!</p>
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
    <div class="comments">
      <div class="comment">
        <a class="avatar">
          <img src="/images/avatar/small/jenny.jpg">
        </a>
        <div class="content">
          <a class="author">Jenny Hess</a>
          <div class="metadata">
            <span class="date">Just now</span>
          </div>
          <div class="text">
            Elliot you are always so right :)
          </div>
          <div class="actions">
            <a class="reply">Reply</a>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/joe.jpg">
    </a>
    <div class="content">
      <a class="author">Joe Henderson</a>
      <div class="metadata">
        <span class="date">5 days ago</span>
      </div>
      <div class="text">
        Dude, this is awesome. Thanks so much
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
  </div>
  <form class="ui reply form">
    <div class="field">
      <textarea></textarea>
    </div>
    <div class="ui blue labeled submit icon button">
      <i class="icon edit"></i> Add Reply
    </div>
  </form>
</div>
```

#### Minimal
Comments can hide extra information unless a user shows intent to interact with a comment.
```html
<div class="ui minimal comments">
  <h3 class="ui dividing header">Comments</h3>
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/matt.jpg">
    </a>
    <div class="content">
      <a class="author">Matt</a>
      <div class="metadata">
        <span class="date">Today at 5:42PM</span>
      </div>
      <div class="text">
        How artistic!
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
  </div>
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/elliot.jpg">
    </a>
    <div class="content">
      <a class="author">Elliot Fu</a>
      <div class="metadata">
        <span class="date">Yesterday at 12:30AM</span>
      </div>
      <div class="text">
        <p>This has been very useful for my research. Thanks as well!</p>
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
    <div class="comments">
      <div class="comment">
        <a class="avatar">
          <img src="/images/avatar/small/jenny.jpg">
        </a>
        <div class="content">
          <a class="author">Jenny Hess</a>
          <div class="metadata">
            <span class="date">Just now</span>
          </div>
          <div class="text">
            Elliot you are always so right :)
          </div>
          <div class="actions">
            <a class="reply">Reply</a>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/joe.jpg">
    </a>
    <div class="content">
      <a class="author">Joe Henderson</a>
      <div class="metadata">
        <span class="date">5 days ago</span>
      </div>
      <div class="text">
        Dude, this is awesome. Thanks so much
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
  </div>
  <form class="ui reply form">
    <div class="field">
      <textarea></textarea>
    </div>
    <div class="ui blue labeled submit icon button">
      <i class="icon edit"></i> Add Reply
    </div>
  </form>
</div>
```

#### Size
Comments can have different sizes
```html
<div class="ui small comments">
  <h3 class="ui dividing header">Comments</h3>
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/matt.jpg">
    </a>
    <div class="content">
      <a class="author">Matt</a>
      <div class="metadata">
        <span class="date">Today at 5:42PM</span>
      </div>
      <div class="text">
        How artistic!
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
  </div>
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/elliot.jpg">
    </a>
    <div class="content">
      <a class="author">Elliot Fu</a>
      <div class="metadata">
        <span class="date">Yesterday at 12:30AM</span>
      </div>
      <div class="text">
        <p>This has been very useful for my research. Thanks as well!</p>
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
    <div class="comments">
      <div class="comment">
        <a class="avatar">
          <img src="/images/avatar/small/jenny.jpg">
        </a>
        <div class="content">
          <a class="author">Jenny Hess</a>
          <div class="metadata">
            <span class="date">Just now</span>
          </div>
          <div class="text">
            Elliot you are always so right :)
          </div>
          <div class="actions">
            <a class="reply">Reply</a>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/joe.jpg">
    </a>
    <div class="content">
      <a class="author">Joe Henderson</a>
      <div class="metadata">
        <span class="date">5 days ago</span>
      </div>
      <div class="text">
        Dude, this is awesome. Thanks so much
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
  </div>
  <form class="ui reply form">
    <div class="field">
      <textarea></textarea>
    </div>
    <div class="ui blue labeled submit icon button">
      <i class="icon edit"></i> Add Reply
    </div>
  </form>
</div>
```
```html
<div class="ui small comments">
  <h3 class="ui dividing header">Comments</h3>
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/matt.jpg">
    </a>
    <div class="content">
      <a class="author">Matt</a>
      <div class="metadata">
        <span class="date">Today at 5:42PM</span>
      </div>
      <div class="text">
        How artistic!
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
  </div>
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/elliot.jpg">
    </a>
    <div class="content">
      <a class="author">Elliot Fu</a>
      <div class="metadata">
        <span class="date">Yesterday at 12:30AM</span>
      </div>
      <div class="text">
        <p>This has been very useful for my research. Thanks as well!</p>
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
    <div class="comments">
      <div class="comment">
        <a class="avatar">
          <img src="/images/avatar/small/jenny.jpg">
        </a>
        <div class="content">
          <a class="author">Jenny Hess</a>
          <div class="metadata">
            <span class="date">Just now</span>
          </div>
          <div class="text">
            Elliot you are always so right :)
          </div>
          <div class="actions">
            <a class="reply">Reply</a>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="comment">
    <a class="avatar">
      <img src="/images/avatar/small/joe.jpg">
    </a>
    <div class="content">
      <a class="author">Joe Henderson</a>
      <div class="metadata">
        <span class="date">5 days ago</span>
      </div>
      <div class="text">
        Dude, this is awesome. Thanks so much
      </div>
      <div class="actions">
        <a class="reply">Reply</a>
      </div>
    </div>
  </div>
  <form class="ui reply form">
    <div class="field">
      <textarea></textarea>
    </div>
    <div class="ui blue labeled submit icon button">
      <i class="icon edit"></i> Add Reply
    </div>
  </form>
</div>
```


## === feed.md ===

# Feed

A feed presents user activity chronologically

## Types

#### Feed
A feed
```html
<div class="ui feed">
  <div class="event">
    <div class="label">
      <img src="/images/avatar/small/elliot.jpg">
    </div>
    <div class="content">
      <div class="summary">
        <a class="user">
          Elliot Fu
        </a> added you as a friend
        <div class="date">
          1 Hour Ago
        </div>
      </div>
      <div class="meta">
        <a class="like">
          <i class="like icon"></i> 4 Likes
        </a>
      </div>
    </div>
  </div>
  <div class="event">
    <div class="label">
      <img src="/images/avatar/small/helen.jpg">
    </div>
    <div class="content">
      <div class="summary">
        <a>Helen Troy</a> added <a>2 new illustrations</a>
        <div class="date">
          4 days ago
        </div>
      </div>
      <div class="extra images">
        <a><img src="/images/wireframe/image.png"></a>
        <a><img src="/images/wireframe/image.png"></a>
      </div>
      <div class="meta">
        <a class="like">
          <i class="like icon"></i> 1 Like
        </a>
      </div>
    </div>
  </div>
  <div class="event">
    <div class="label">
      <img src="/images/avatar/small/jenny.jpg">
    </div>
    <div class="content">
      <div class="summary">
        <a class="user">
          Jenny Hess
        </a> added you as a friend
        <div class="date">
          2 Days Ago
        </div>
      </div>
      <div class="meta">
        <a class="like">
          <i class="like icon"></i> 8 Likes
        </a>
      </div>
    </div>
  </div>
  <div class="event">
    <div class="label">
      <img src="/images/avatar/small/joe.jpg">
    </div>
    <div class="content">
      <div class="summary">
        <a>Joe Henderson</a> posted on his page
        <div class="date">
          3 days ago
        </div>
      </div>
      <div class="extra text">
        Ours is a life of constant reruns. We're always circling back to where we'd we started, then starting all over again. Even if we don't run extra laps that day, we surely will come back for more of the same another day soon.
      </div>
      <div class="meta">
        <a class="like">
          <i class="like icon"></i> 5 Likes
        </a>
      </div>
    </div>
  </div>
  <div class="event">
    <div class="label">
      <img src="/images/avatar/small/justen.jpg">
    </div>
    <div class="content">
      <div class="summary">
        <a>Justen Kitsune</a> added <a>2 new photos</a> of you
        <div class="date">
          4 days ago
        </div>
      </div>
      <div class="extra images">
        <a><img src="/images/wireframe/image.png"></a>
        <a><img src="/images/wireframe/image.png"></a>
      </div>
      <div class="meta">
        <a class="like">
          <i class="like icon"></i> 41 Likes
        </a>
      </div>
    </div>
  </div>
</div>
```

## Content

#### Label
An event can contain an image or icon label
```html
<div class="ui feed">
  <div class="event">
    <div class="label">
      <img src="/images/avatar/small/elliot.jpg">
    </div>
    <div class="content">
      You added Elliot Fu to the group <a>Coworkers</a>
    </div>
  </div>
</div>
```
```html
<div class="ui feed">
  <div class="event">
    <div class="label">
      <i class="pencil icon"></i>
    </div>
    <div class="content">
      <div class="summary">
        You posted on your friend <a>Stevie Feliciano's</a> wall.
        <div class="date">Today</div>
      </div>
    </div>
  </div>
</div>
```

#### Date
An event or an event summary can contain a date
```html
<div class="ui feed">
  <div class="event">
    <div class="label">
      <img src="/images/avatar/small/jenny.jpg">
    </div>
    <div class="content">
      <div class="date">
        3 days ago
      </div>
      <div class="summary">
         You added <a>Jenny Hess</a> to your <a>coworker</a> group.
      </div>
    </div>
  </div>
</div>
```
```html
<div class="ui feed">
  <div class="event">
    <div class="label">
      <img src="/images/avatar/small/jenny.jpg">
    </div>
    <div class="content">
      <div class="summary">
        You added <a>Jenny Hess</a> to your <a>coworker</a> group.
        <div class="date">
          3 days ago
        </div>
      </div>
    </div>
  </div>
</div>
```

#### Additional information
An event can contain additional information like a set of images or text
```html
<div class="ui feed">
  <div class="event">
    <div class="label">
      <img src="/images/avatar/small/helen.jpg">
    </div>
    <div class="content">
      <div class="date">
        3 days ago
      </div>
      <div class="summary">
         <a>Helen Troy</a> added 2 photos
      </div>
      <div class="extra images">
        <a><img src="/images/wireframe/image.png"></a>
        <a><img src="/images/wireframe/image.png"></a>
      </div>
    </div>
  </div>
  <div class="event">
    <div class="label">
      <img src="/images/avatar/small/laura.jpg">
    </div>
    <div class="content">
      <div class="date">
        3 days ago
      </div>
      <div class="summary">
         <a>Laura Faucet</a> created a post
      </div>
      <div class="extra text">
        Have you seen what's going on in Israel? Can you believe it.
      </div>
    </div>
  </div>
</div>
```

## Variations

#### Size
A feed can have different sizes
```html
<div class="ui small feed">
  <h4 class="ui header">Followers Activity</h4>
  <div class="event">
    <div class="content">
      <div class="summary">
         <a>Elliot Fu</a> added <a>Jenny Hess</a> as a friend
      </div>
    </div>
  </div>
  <div class="event">
    <div class="content">
      <div class="summary">
         <a>Stevie Feliciano</a> added <a>Elliot Fu</a> as a friend
      </div>
    </div>
  </div>
  <div class="event">
    <div class="content">
      <div class="summary">
         <a>Helen Troy</a> added <a>Christian Rocha</a> as a friend
      </div>
    </div>
  </div>
  <div class="event">
    <div class="content">
      <div class="summary">
         <a>Christian Rocha</a> signed up for the  site.
      </div>
    </div>
  </div>
</div>
```
```html
<div class="ui large feed">
  <div class="event">
    <div class="label">
      <img src="/images/avatar/small/elliot.jpg">
    </div>
    <div class="content">
      <div class="summary">
        <a class="user">
          Elliot Fu
        </a> added you as a friend
        <div class="date">
          1 Hour Ago
        </div>
      </div>
      <div class="meta">
        <a class="like">
          <i class="like icon"></i> 4 Likes
        </a>
      </div>
    </div>
  </div>
  <div class="event">
    <div class="label">
      <i class="pencil icon"></i>
    </div>
    <div class="content">
      <div class="summary">
        You submitted a new post to the page
        <div class="date">
          3 days ago
        </div>
      </div>
      <div class="extra text">
        I'm having a BBQ this weekend. Come by around 4pm if you can.
      </div>
      <div class="meta">
        <a class="like">
          <i class="like icon"></i> 11 Likes
        </a>
      </div>
    </div>
  </div>
  <div class="event">
    <div class="label">
      <img src="/images/avatar/small/helen.jpg">
    </div>
    <div class="content">
      <div class="date">
        4 days ago
      </div>
      <div class="summary">
        <a>Helen Troy</a> added <a>2 new illustrations</a>
      </div>
      <div class="extra images">
        <a><img src="/images/wireframe/image.png"></a>
        <a><img src="/images/wireframe/image.png"></a>
      </div>
      <div class="meta">
        <a class="like">
          <i class="like icon"></i> 1 Like
        </a>
      </div>
    </div>
  </div>
</div>
```


## === item.md ===

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


## === statistic.md ===

# Statistic

A statistic emphasizes the current value of an attribute

## Types

#### Statistic
A statistic can display a value with a label above or below it.
```html
<div class="ui statistic">
  <div class="value">
    5,550
  </div>
  <div class="label">
    Downloads
  </div>
</div>
```
```html
<div class="ui statistic">
  <div class="label">
    Views
  </div>
  <div class="value">
    40,509
  </div>
</div>
```

#### Statistic Group
A group of statistics
```html
<div class="ui statistics">
  <div class="statistic">
    <div class="value">
      22
    </div>
    <div class="label">
      Faves
    </div>
  </div>
  <div class="statistic">
    <div class="value">
      31,200
    </div>
    <div class="label">
      Views
    </div>
  </div>
  <div class="statistic">
    <div class="value">
      22
    </div>
    <div class="label">
      Members
    </div>
  </div>
</div>
```

## Content

#### Value
A statistic can contain a numeric, icon, image, or text value
```html
<div class="ui statistics">
  <div class="statistic">
    <div class="value">
      22
    </div>
    <div class="label">
      Saves
    </div>
  </div>
  <div class="statistic">
    <div class="text value">
      Three<br>
      Thousand
    </div>
    <div class="label">
      Signups
    </div>
  </div>
  <div class="statistic">
    <div class="value">
      <i class="plane icon"></i> 5
    </div>
    <div class="label">
      Flights
    </div>
  </div>
  <div class="statistic">
    <div class="value">
      <img src="/images/avatar/small/joe.jpg" class="ui circular inline image">
      42
    </div>
    <div class="label">
      Team Members
    </div>
  </div>
</div>
```

#### Label
A statistic can contain a label to help provide context for the presented value
```html
<div class="ui statistic">
  <div class="value">
    2,204
  </div>
  <div class="label">
    Views
  </div>
</div>
```

## Variations

#### Horizontal Statistic
A statistic can present its measurement horizontally
```html
<div class="ui horizontal statistic">
  <div class="value">
    2,204
  </div>
  <div class="label">
    Views
  </div>
</div>
```
```html
<div class="ui horizontal statistics">
  <div class="statistic">
    <div class="value">
      2,204
    </div>
    <div class="label">
      Views
    </div>
  </div>
  <div class="statistic">
    <div class="value">
      3,322
    </div>
    <div class="label">
      Downloads
    </div>
  </div>
  <div class="statistic">
    <div class="value">
      22
    </div>
    <div class="label">
      Tasks
    </div>
  </div>
</div>
```

#### Colored
A statistic can be formatted to be different colors
```html
<div class="ui statistics">
  <div class="red statistic">
    <div class="value">
      27
    </div>
    <div class="label">
      Red
    </div>
  </div>
  <div class="orange statistic">
    <div class="value">
      8
    </div>
    <div class="label">
      Orange
    </div>
  </div>
  <div class="yellow statistic">
    <div class="value">
      28
    </div>
    <div class="label">
      Yellow
    </div>
  </div>
  <div class="olive statistic">
    <div class="value">
      7
    </div>
    <div class="label">
      Olive
    </div>
  </div>
  <div class="green statistic">
    <div class="value">
      14
    </div>
    <div class="label">
      Green
    </div>
  </div>
  <div class="teal statistic">
    <div class="value">
      82
    </div>
    <div class="label">
      Teal
    </div>
  </div>
  <div class="blue statistic">
    <div class="value">
      1
    </div>
    <div class="label">
      Blue
    </div>
  </div>
  <div class="violet statistic">
    <div class="value">
      22
    </div>
    <div class="label">
      Violet
    </div>
  </div>
  <div class="purple statistic">
    <div class="value">
      23
    </div>
    <div class="label">
      Purple
    </div>
  </div>
  <div class="pink statistic">
    <div class="value">
      15
    </div>
    <div class="label">
      Pink
    </div>
  </div>
  <div class="brown statistic">
    <div class="value">
      36
    </div>
    <div class="label">
      Brown
    </div>
  </div>
  <div class="grey statistic">
    <div class="value">
      49
    </div>
    <div class="label">
      Grey
    </div>
  </div>
</div>
```

#### Inverted
A statistic can be formatted to fit on a dark background
```html
<div class="ui inverted segment">
  <div class="ui inverted statistic">
    <div class="value">
      54
    </div>
    <div class="label">
      Inverted
    </div>
  </div>
  <div class="ui red inverted statistic">
    <div class="value">
      27
    </div>
    <div class="label">
      Red
    </div>
  </div>
  <div class="ui orange inverted statistic">
    <div class="value">
      8
    </div>
    <div class="label">
      Orange
    </div>
  </div>
  <div class="ui yellow inverted statistic">
    <div class="value">
      28
    </div>
    <div class="label">
      Yellow
    </div>
  </div>
  <div class="ui olive inverted statistic">
    <div class="value">
      7
    </div>
    <div class="label">
      Olive
    </div>
  </div>
    <div class="ui green inverted statistic">
    <div class="value">
      14
    </div>
    <div class="label">
      Green
    </div>
  </div>
  <div class="ui teal inverted statistic">
    <div class="value">
      82
    </div>
    <div class="label">
      Teal
    </div>
  </div>
  <div class="ui blue inverted statistic">
    <div class="value">
      1
    </div>
    <div class="label">
      Blue
    </div>
  </div>
  <div class="ui violet inverted statistic">
    <div class="value">
      22
    </div>
    <div class="label">
      Violet
    </div>
  </div>
  <div class="ui purple inverted statistic">
    <div class="value">
      23
    </div>
    <div class="label">
      Purple
    </div>
  </div>
  <div class="ui pink inverted statistic">
    <div class="value">
      15
    </div>
    <div class="label">
      Pink
    </div>
  </div>
  <div class="ui brown inverted statistic">
    <div class="value">
      36
    </div>
    <div class="label">
      Brown
    </div>
  </div>
  <div class="ui grey inverted statistic">
    <div class="value">
      49
    </div>
    <div class="label">
      Grey
    </div>
  </div>
</div>
```

#### Evenly Divided
A statistic group can have its items divided evenly
```html
<div class="ui four statistics">
  <div class="statistic">
    <div class="value">
      22
    </div>
    <div class="label">
      Saves
    </div>
  </div>
  <div class="statistic">
    <div class="text value">
      Three<br>
      Thousand
    </div>
    <div class="label">
      Signups
    </div>
  </div>
  <div class="statistic">
    <div class="value">
      <i class="plane icon"></i> 5
    </div>
    <div class="label">
      Flights
    </div>
  </div>
  <div class="statistic">
    <div class="value">
      <img src="/images/avatar/small/joe.jpg" class="ui circular inline image">
      42
    </div>
    <div class="label">
      Team Members
    </div>
  </div>
</div>
```

#### Floated
An statistic can sit to the left or right of other content
```html
<div class="ui segment">
  <div class="ui right floated statistic">
    <div class="value">
      2,204
    </div>
    <div class="label">
      Views
    </div>
  </div>
  <p>Te eum doming eirmod, nominati pertinacia argumentum ad his. Ex eam alia facete scriptorem, est autem aliquip detraxit at. Usu ocurreret referrentur at, cu epicurei appellantur vix. Cum ea laoreet recteque electram, eos choro alterum definiebas in. Vim dolorum definiebas an. Mei ex natum rebum iisque.</p>

  <p>Audiam quaerendum eu sea, pro omittam definiebas ex. Te est latine definitiones. Quot wisi nulla ex duo. Vis sint solet expetenda ne, his te phaedrum referrentur consectetuer. Id vix fabulas oporteat, ei quo vide phaedrum, vim vivendum maiestatis in.</p>

  <div class="ui left floated statistic">
    <div class="value">
      2,204
    </div>
    <div class="label">
      Views
    </div>
  </div>
  <p>Eu quo homero blandit intellegebat. Incorrupte consequuntur mei id. Mei ut facer dolores adolescens, no illum aperiri quo, usu odio brute at. Qui te porro electram, ea dico facete utroque quo. Populo quodsi te eam, wisi everti eos ex, eum elitr altera utamur at. Quodsi convenire mnesarchum eu per, quas minimum postulant per id.</p>

  <p>Audiam quaerendum eu sea, pro omittam definiebas ex. Te est latine definitiones. Quot wisi nulla ex duo. Vis sint solet expetenda ne, his te phaedrum referrentur consectetuer. Id vix fabulas oporteat, ei quo vide phaedrum, vim vivendum maiestatis in.</p>

</div>
```

#### Size
A statistic can vary in size
```html
<div class="ui mini statistic">
  <div class="value">
    2,204
  </div>
  <div class="label">
    Views
  </div>
</div>
<div class="ui tiny statistic">
  <div class="value">
    2,204
  </div>
  <div class="label">
    Views
  </div>
</div>
<div class="ui small statistic">
  <div class="value">
    2,204
  </div>
  <div class="label">
    Views
  </div>
</div>
<div class="ui statistic">
  <div class="value">
    2,204
  </div>
  <div class="label">
    Views
  </div>
</div>
<div class="ui large statistic">
  <div class="value">
    2,204
  </div>
  <div class="label">
    Views
  </div>
</div>
<div class="ui huge statistic">
  <div class="value">
    2,204
  </div>
  <div class="label">
    Views
  </div>
</div>
```
```html
<div class="ui ignored divider"></div>
<div class="ui mini horizontal statistic">
  <div class="value">
    2,204
  </div>
  <div class="label">
    Views
  </div>
</div>
<div class="ui ignored divider"></div>
<div class="ui tiny horizontal statistic">
  <div class="value">
    2,204
  </div>
  <div class="label">
    Views
  </div>
</div>
<div class="ui ignored divider"></div>
<div class="ui small horizontal statistic">
  <div class="value">
    2,204
  </div>
  <div class="label">
    Views
  </div>
</div>
<div class="ui ignored divider"></div>
<div class="ui horizontal statistic">
  <div class="value">
    2,204
  </div>
  <div class="label">
    Views
  </div>
</div>
<div class="ui ignored divider"></div>
<div class="ui large horizontal statistic">
  <div class="value">
    2,204
  </div>
  <div class="label">
    Views
  </div>
</div>
<div class="ui ignored divider"></div>
<div class="ui huge horizontal statistic">
  <div class="value">
    2,204
  </div>
  <div class="label">
    Views
  </div>
</div>
```
