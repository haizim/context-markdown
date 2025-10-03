# Label

A label displays content classification

## Types

#### Label
A label
```html
<div class="ui label">
  <i class="mail icon"></i> 23
</div>
```

#### Image
A label can be formatted to emphasize an image
```html
<a class="ui image label">
  <img src="/images/avatar/small/joe.jpg">
  Joe
</a>
<a class="ui image label">
  <img src="/images/avatar/small/elliot.jpg">
  Elliot
</a>
<a class="ui image label">
  <img src="/images/avatar/small/stevie.jpg">
  Stevie
</a>
```
```html
<a class="ui blue image label">
  <img src="/images/avatar/small/veronika.jpg">
  Veronika
  <div class="detail">Friend</div>
</a>
<a class="ui teal image label">
  <img src="/images/avatar/small/jenny.jpg">
  Veronika
  <div class="detail">Student</div>
</a>
<a class="ui yellow image label">
  <img src="/images/avatar/small/christian.jpg">
  Helen
  <div class="detail">Co-worker</div>
</a>
```
```html
<div class="ui image label">
  <img src="/images/avatar/small/ade.jpg">
  Adrienne
  <i class="delete icon"></i>
</div>
<div class="ui image label">
  <img src="/images/avatar/small/zoe.jpg">
  Zoe
  <i class="delete icon"></i>
</div>
<div class="ui image label">
  <img src="/images/avatar/small/nan.jpg">
  Nan
  <i class="delete icon"></i>
</div>
```

#### Pointing
A label can point to content next to it
```html
<form class="ui fluid form">
  <div class="field">
    <input type="text" placeholder="First name">
    <div class="ui pointing label">
      Please enter a value
    </div>
  </div>
  <div class="ui divider"></div>
  <div class="field" placeholder="Last Name">
    <div class="ui pointing below label">
      Please enter a value
    </div>
    <input type="text">
  </div>
  <div class="ui divider"></div>
  <div class="inline field">
    <input type="text" placeholder="Username">
    <div class="ui left pointing label">
      That name is taken!
    </div>
  </div>
  <div class="ui divider"></div>
  <div class="inline field">
    <div class="ui right pointing label">
      Your password must be 6 characters or more
    </div>
    <input type="password">
  </div>
</form>
```
```html
<form class="ui fluid form">
  <div class="field">
    <input type="text" placeholder="First name">
    <div class="ui pointing red basic label">
      Please enter a value
    </div>
  </div>
  <div class="ui divider"></div>
  <div class="field" placeholder="Last Name">
    <div class="ui pointing below red basic label">
      Please enter a value
    </div>
    <input type="text">
  </div>
  <div class="ui divider"></div>
  <div class="inline field">
    <input type="text" placeholder="Username">
    <div class="ui left pointing red basic label">
      That name is taken!
    </div>
  </div>
  <div class="ui divider"></div>
  <div class="inline field">
    <div class="ui right pointing red basic label">
      Your password must be 6 characters or more
    </div>
    <input type="password">
  </div>
</form>
```

#### Corner
A label can position itself in the corner of an element
> A corner label must be positioned inside a container with **position: relative** to display properly. If a container is rounded you will need to add `overflow:hidden` to the container to produce a rounded label.
```html
<div class="ui two column grid">
  <div class="column">
    <div class="ui fluid image">
      <a class="ui left corner label">
        <i class="heart icon"></i>
      </a>
      <img src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="column">
    <div class="ui fluid image">
      <a class="ui red right corner label">
        <i class="save icon"></i>
      </a>
      <img src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

#### Tag
A label can appear as a tag
```html
<a class="ui tag label">New</a>
<a class="ui red tag label">Upcoming</a>
<a class="ui teal tag label">Featured</a>
```

#### Ribbon
A label can appear as a ribbon attaching itself to an element.
```html
<div class="ui two column grid">
  <div class="column">
    <div class="ui raised segment">
      <a class="ui red ribbon label">Overview</a>
      <span>Account Details</span>
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      <a class="ui blue ribbon label">Community</a> User Reviews
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
  <div class="column">
    <div class="ui segment">
      <a class="ui orange right ribbon label">Specs</a>
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      <a class="ui teal right ribbon label">Reviews</a>
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
</div>
```
```html
<div class="ui two column grid">
  <div class="column">
    <div class="ui fluid image">
      <div class="ui black ribbon label">
        <i class="hotel icon"></i> Hotel
      </div>
      <img src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="column">
    <div class="ui fluid image">
      <div class="ui blue ribbon label">
        <i class="spoon icon"></i> Food
      </div>
      <img src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

#### Attached
A label can attach to a content segment
> Attached labels attempt to intelligently pad other content to account for their position, but may not in all cases apply this padding correctly.
> If this happens you may need to manually correct the padding of the other elements inside the container.
```html
<div class="ui three column grid">
  <div class="row">
    <div class="column">
      <div class="ui segment">
        <div class="ui top attached label">HTML</div>
        <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        <div class="ui bottom attached label">CSS</div>
        <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        <div class="ui top right attached label">Code</div>
        <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      </div>
    </div>
  </div>
  <div class="row">
    <div class="column">
      <div class="ui segment">
        <div class="ui top left attached label">View</div>
        <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        <div class="ui bottom left attached label">User View</div>
        <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        <div class="ui bottom right attached label">Admin View</div>
        <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      </div>
    </div>
  </div>
</div>
```
```html
<div class="ui top attached label">HTML</div>
<div class="ui bottom attached label">CSS</div>
<div class="ui top right attached label">Code</div>
<div class="ui top left attached label">View</div>
<div class="ui bottom left attached label">User View</div>
<div class="ui bottom right attached label">Admin View</div>
```

#### Horizontal
A horizontal label is formatted to label content along-side it horizontally
```html
<div class="ui divided selection list">
  <a class="item">
    <div class="ui red horizontal label">Fruit</div>
    Kumquats
  </a>
  <a class="item">
    <div class="ui purple horizontal label">Candy</div>
    Ice Cream
  </a>
  <a class="item">
    <div class="ui red horizontal label">Fruit</div>
    Orange
  </a>
  <a class="item">
    <div class="ui horizontal label">Dog</div>
    Poodle
  </a>
</div>
```

#### Floating
A label can float above another element.
> A floating label must be positioned inside a container with **position: relative** to display properly.
```html
<div class="ui compact menu">
  <a class="item">
    <i class="icon mail"></i> Messages
    <div class="floating ui red label">22</div>
  </a>
  <a class="item">
    <i class="icon users"></i> Friends
    <div class="floating ui teal label">22</div>
  </a>
</div>
```

## Content

#### Detail
A label can contain a detail
```html
<div class="ui label">
  Dogs
  <div class="detail">214</div>
</div>
```

#### Icon
A label can include an icon
```html
<a class="ui label">
  <i class="mail icon"></i>
  Mail
</a>
<a class="ui label">
  Tag
  <i class="delete icon"></i>
</a>
```

#### Image
A label can include an image
```html
<a class="ui label">
  <img class="ui right spaced avatar image" src="/images/avatar/small/elliot.jpg">
  Elliot
</a>
<a class="ui label">
  <img src="/images/avatar/small/stevie.jpg">
  Stevie
</a>
```

#### Link
A label can be a link or contain an item that links
```html
<a class="ui label">
  <i class="mail icon"></i> 23
</a>
```
```html
<div class="ui label">
  <i class="mail icon"></i>
  23
  <a class="detail">View Mail</a>
</div>
```

## Variations

#### Circular
A label can be circular
```html
<a class="ui red circular label">2</a>
<a class="ui orange circular label">2</a>
<a class="ui yellow circular label">2</a>
<a class="ui olive circular label">2</a>
<a class="ui green circular label">2</a>
<a class="ui teal circular label">2</a>
<a class="ui blue circular label">2</a>
<a class="ui violet circular label">2</a>
<a class="ui purple circular label">2</a>
<a class="ui pink circular label">2</a>
<a class="ui brown circular label">2</a>
<a class="ui grey circular label">2</a>
<a class="ui black circular label">2</a>
```
```html
<a class="ui red empty circular label"></a>
<a class="ui orange empty circular label"></a>
<a class="ui yellow empty circular label"></a>
<a class="ui olive empty circular label"></a>
<a class="ui green empty circular label"></a>
<a class="ui teal empty circular label"></a>
<a class="ui blue empty circular label"></a>
<a class="ui violet empty circular label"></a>
<a class="ui purple empty circular label"></a>
<a class="ui pink empty circular label"></a>
<a class="ui brown empty circular label"></a>
<a class="ui grey empty circular label"></a>
<a class="ui black empty circular label"></a>
```

#### Basic
A label can reduce its complexity
```html
<a class="ui basic label">Basic</a>
<a class="ui pointing basic label">Pointing</a>
<a class="ui basic image label">
  <img src="/images/avatar/small/elliot.jpg">
  Elliot
<a class="ui pointing red basic label">Red Pointing</a>
<a class="ui blue basic label">Blue</a>
</a>
```

#### Colored
A label can have different colors
```html
<a class="ui red label">Red</a>
<a class="ui orange label">Orange</a>
<a class="ui yellow label">Yellow</a>
<a class="ui olive label">Olive</a>
<a class="ui green label">Green</a>
<a class="ui teal label">Teal</a>
<a class="ui blue label">Blue</a>
<a class="ui violet label">Violet</a>
<a class="ui purple label">Purple</a>
<a class="ui pink label">Pink</a>
<a class="ui brown label">Brown</a>
<a class="ui grey label">Grey</a>
<a class="ui black label">Black</a>
```

#### Size
A label can be small or large
```html
<div class="ui mini label">
  Mini
</div>
<div class="ui tiny label">
  Tiny
</div>
<div class="ui small label">
  Small
</div>
<div class="ui label">
  Medium
</div>
<div class="ui large label">
  Large
</div>
<div class="ui big label">
  Big
</div>
<div class="ui huge label">
  Huge
</div>
<div class="ui massive label">
  Massive
</div>
```

## Groups

#### Group Size
Labels can share sizes together
```html
<div class="ui huge labels">
  <div class="ui label">
    Fun
  </div>
  <div class="ui label">
    Happy
  </div>
  <div class="ui label">
    Smart
  </div>
  <div class="ui label">
    Witty
  </div>
</div>
```

#### Colored Group
Labels can share colors together
```html
<div class="ui blue labels">
  <a class="ui label">
    Fun <i class="icon close"></i>
  </a>
  <a class="ui label">
    Happy
    <div class="detail">22</div>
  </a>
  <a class="ui label">
    Smart
  </a>
  <a class="ui label">
    Insane
  </a>
  <a class="ui label">
    Exciting
  </a>
</div>
```

#### Tag Group
Labels can share tag formatting
```html
<div class="ui tag labels">
  <a class="ui label">
    $10.00
  </a>
  <a class="ui label">
    $19.99
  </a>
  <a class="ui label">
    $24.99
  </a>
  <a class="ui label">
    $30.99
  </a>
  <a class="ui label">
    $10.25
  </a>
</div>
```

#### Circular Group
Labels can share shapes
```html
<div class="ui circular labels">
  <a class="ui label">
    11
  </a>
  <a class="ui label">
    22
  </a>
  <a class="ui label">
    33
  </a>
  <a class="ui label">
    44
  </a>
  <a class="ui label">
    141
  </a>
</div>
```
