# Menu

A menu displays grouped navigation actions

## Types

#### Menu
A menu
> Starting in `2.0` menus now use flexbox. This allows each menu item to automatically stretch to the size of the largest item.
```html
<div class="ui three item menu">
  <a class="active item">Editorials</a>
  <a class="item">Reviews</a>
  <a class="item">Upcoming Events</a>
</div>
```
> Many of the following examples use a coupling with dropdowns to display dropdown menus inside of `ui menu`. Please consult the dropdown documentation for the correct javascript initialization for this component.
```html
<div class="ui text menu">
  <div class="item">
    <img src="/images/new-school.jpg">
  </div>
  <a class="browse item">
    Browse Courses
    <i class="dropdown icon"></i>
  </a>
  <div class="ui right dropdown item">
    More
    <i class="dropdown icon"></i>
    <div class="menu">
      <div class="item">Applications</div>
      <div class="item">International Students</div>
      <div class="item">Scholarships</div>
    </div>
  </div>
</div>
```
```html
<div class="ui top attached menu">
  <div class="ui dropdown icon item">
    <i class="wrench icon"></i>
    <div class="menu">
      <div class="item">
        <i class="dropdown icon"></i>
        <span class="text">New</span>
        <div class="menu">
          <div class="item">Document</div>
          <div class="item">Image</div>
        </div>
      </div>
      <div class="item">
        Open...
      </div>
      <div class="item">
        Save...
      </div>
      <div class="item">Edit Permissions</div>
      <div class="divider"></div>
      <div class="header">
        Export
      </div>
      <div class="item">
        Share...
      </div>
    </div>
  </div>
  <div class="right menu">
    <div class="ui right aligned category search item">
      <div class="ui transparent icon input">
        <input class="prompt" type="text" placeholder="Search animals...">
        <i class="search link icon"></i>
      </div>
      <div class="results"></div>
    </div>
  </div>
</div>
<div class="ui bottom attached segment">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
```

#### Secondary Menu
A menu can adjust its appearance to de-emphasize its contents
```html
<div class="ui secondary  menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
  <div class="right menu">
    <div class="item">
      <div class="ui icon input">
        <input type="text" placeholder="Search...">
        <i class="search link icon"></i>
      </div>
    </div>
    <a class="ui item">
      Logout
    </a>
  </div>
</div>
```

#### Pointing
A menu can point to show its relationship to nearby content
```html
<div class="ui pointing menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
  <div class="right menu">
    <div class="item">
      <div class="ui transparent icon input">
        <input type="text" placeholder="Search...">
        <i class="search link icon"></i>
      </div>
    </div>
  </div>
</div>
<div class="ui segment">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
```
```html
<div class="ui secondary pointing menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
  <div class="right menu">
    <a class="ui item">
      Logout
    </a>
  </div>
</div>
<div class="ui segment">
  <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
</div>
```

#### Tabular
A menu can be formatted to show tabs of information
> Be sure to visit the tab documentation for information on how to set up dynamic tabs
```html
<div class="ui tabular menu">
  <a class="active item">
    Bio
  </a>
  <a class="item">
    Photos
  </a>
</div>
```
```html
<div class="ui top attached tabular menu">
  <a class="active item">
    Bio
  </a>
  <a class="item">
    Photos
  </a>
  <div class="right menu">
    <div class="item">
      <div class="ui transparent icon input">
        <input type="text" placeholder="Search users...">
        <i class="search link icon"></i>
      </div>
    </div>
  </div>
</div>
<div class="ui bottom attached segment">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
```
```html
<div class="ui top attached segment">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
<div class="ui bottom attached tabular menu">
  <a class="active item">
    Active Project
  </a>
  <a class="item">
    Project #2
  </a>
  <a class="item">
    Project #3
  </a>
  <div class="right menu">
    <a class="item">
      <i class="add icon"></i> New Tab
    </a>
  </div>
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

#### Text
A menu can be formatted for text content
```html
<div class="ui text menu">
  <div class="header item">Sort By</div>
  <a class="active item">
    Closest
  </a>
  <a class="item">
    Most Comments
  </a>
  <a class="item">
    Most Popular
  </a>
</div>
```

#### Vertical Menu
A vertical menu displays elements vertically..
> A vertical menu's width defaults to an arbitrary size. To have it fit your content more precisely use the fluid variation in conjunction with ui grid.
```html
<div class="ui vertical menu">
  <a class="active teal item">
    Inbox
    <div class="ui teal left pointing label">1</div>
  </a>
  <a class="item">
    Spam
    <div class="ui label">51</div>
  </a>
  <a class="item">
    Updates
    <div class="ui label">1</div>
  </a>
  <div class="item">
    <div class="ui transparent icon input">
      <input type="text" placeholder="Search mail...">
      <i class="search icon"></i>
    </div>
  </div>
</div>
```
```html
<div class="ui secondary vertical menu">
  <a class="active item">
    Account
  </a>
  <a class="item">
    Settings
  </a>
  <div class="ui dropdown item">
    <i class="dropdown icon"></i>
    Display Options
    <div class="menu">
      <div class="header">Text Size</div>
      <a class="item">Small</a>
      <a class="item">Medium</a>
      <a class="item">Large</a>
    </div>
  </div>
</div>
```
```html
<div class="ui vertical text menu">
  <div class="header item">Sort By</div>
  <a class="active item">
    Closest
  </a>
  <a class="item">
    Most Comments
  </a>
  <a class="item">
    Most Popular
  </a>
</div>
```
```html
<div class="ui vertical pointing menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
```
```html
<div class="ui secondary vertical pointing menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
```

#### Pagination
A pagination menu is specially formatted to present links to pages of content
```html
<div class="ui pagination menu">
  <a class="active item">
    1
  </a>
  <div class="disabled item">
    ...
  </div>
  <a class="item">
    10
  </a>
  <a class="item">
    11
  </a>
  <a class="item">
    12
  </a>
</div>
```

## Content

#### Header
A menu item may include a header or may itself be a header
```html
<div class="ui menu">
  <div class="header item">
    Our Company
  </div>
  <a class="item">
    About Us
  </a>
  <a class="item">
    Jobs
  </a>
  <a class="item">
    Locations
  </a>
</div>
```
```html
<div class="ui vertical menu">
  <div class="item">
    <div class="header">Products</div>
    <div class="menu">
      <a class="item">Enterprise</a>
      <a class="item">Consumer</a>
    </div>
  </div>
  <div class="item">
    <div class="header">CMS Solutions</div>
    <div class="menu">
      <a class="item">Rails</a>
      <a class="item">Python</a>
      <a class="item">PHP</a>
    </div>
  </div>
  <div class="item">
    <div class="header">Hosting</div>
    <div class="menu">
      <a class="item">Shared</a>
      <a class="item">Dedicated</a>
    </div>
  </div>
  <div class="item">
    <div class="header">Support</div>
    <div class="menu">
      <a class="item">E-mail Support</a>
      <a class="item">FAQs</a>
    </div>
  </div>
</div>
```

#### Text
A vertical menu item can include any type of text content.
```html
<div class="ui vertical menu">
  <a class="item">
    <h4 class="ui header">Promotions</h4>
    <p>Check out our new promotions</p>
  </a>
  <a class="item">
    <h4 class="ui header">Coupons</h4>
    <p>Check out our collection of coupons</p>
  </a>
  <a class="item">
    <h4 class="ui header">Rebates</h4>
    <p>Visit our rebate forum for information on claiming rebates</p>
  </a>
</div>
```

#### Input
A menu item can contain an input inside of it
```html
<div class="ui menu">
  <div class="item">
    <div class="ui icon input">
      <input type="text" placeholder="Search...">
      <i class="search icon"></i>
    </div>
  </div>
  <div class="right item">
    <div class="ui action input">
      <input type="text" placeholder="Navigate to...">
      <div class="ui button">Go</div>
    </div>
  </div>
</div>
```

#### Button
A menu item can contain a button inside of it
```html
<div class="ui menu">
  <div class="item">
    <div class="ui primary button">Sign up</div>
  </div>
  <div class="item">
    <div class="ui button">Log-in</div>
  </div>
</div>
```

#### Link Item
A menu may contain a link item, or an item formatted as if it is a link.
```html
<div class="ui vertical menu">
  <a href="http://www.google.com" class="item">
    Visit Google
  </a>
  <div class="link item">
    Javascript Link
  </div>
</div>
```

#### Dropdown Item
An item may contain a nested menu in a dropdown.
> To have a dropdown open without Javascript, use the simple variation
```html
<div class="ui vertical menu">
  <div class="ui dropdown item">
    Categories
    <i class="dropdown icon"></i>
    <div class="menu">
      <a class="item">Electronics</a>
      <a class="item">Automotive</a>
      <a class="item">Home</a>
    </div>
  </div>
</div>
```

#### Popup Menu
A menu item may show a large menu, or additional content using a popup
```html
<div class="ui menu">
  <a class="browse item">
    Browse
    <i class="dropdown icon"></i>
  </a>
</div>
```

#### Search
A menu can contain a search input
```html
<div class="ui menu">
  <div class="ui category search item">
    <div class="ui transparent icon input">
      <input class="prompt" type="text" placeholder="Search animals...">
      <i class="search link icon"></i>
    </div>
    <div class="results"></div>
  </div>
</div>
<div class="ui segment">
  <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
</div>
```

#### Menu
A menu may contain another menu group in the same level as menu items.
```html
<div class="ui menu">
  <a class="item">Browse</a>
  <a class="item">Submit</a>
  <div class="right menu">
    <a class="item">Sign Up</a>
    <a class="item">Help</a>
  </div>
</div>
```

#### Sub Menu
A menu item may contain another menu nested inside that acts as a grouped sub-menu.
```html
<div class="ui vertical menu">
  <div class="item">
    <div class="ui input"><input type="text" placeholder="Search..."></div>
  </div>
  <div class="item">
    Home
    <div class="menu">
      <a class="active item">Search</a>
      <a class="item">Add</a>
      <a class="item">Remove</a>
    </div>
  </div>
  <a class="item">
    <i class="grid layout icon"></i> Browse
  </a>
  <a class="item">
    Messages
  </a>
  <div class="ui dropdown item">
    More
    <i class="dropdown icon"></i>
    <div class="menu">
      <a class="item"><i class="edit icon"></i> Edit Profile</a>
      <a class="item"><i class="globe icon"></i> Choose Language</a>
      <a class="item"><i class="settings icon"></i> Account Settings</a>
    </div>
  </div>
</div>
```

## States

#### Hover
A menu item can be hovered
> Menu items are only hoverable if they are `a` links, or given the class name `link`
```html
<div class="ui compact menu">
  <a class="item">
    A link
  </a>
  <div class="link item">
    div Link
  </div>
</div>
```

#### Active
A menu item can be active
```html
<div class="ui compact menu">
  <div class="active item">
    Link
  </div>
</div>
```

## Variations

#### Fixed
A menu can be fixed to a side of its context
> These examples use a an `iframe`, to prevent content from sticking to the browser viewport.
> For more advanced behaviors consider using a sticky menu or visibility APIs.
```html
<div class="ui top fixed menu">
  <div class="item">
    <img src="/images/logo.png">
  </div>
  <a class="item">Features</a>
  <a class="item">Testimonials</a>
  <a class="item">Sign-in</a>
</div>
<div class="ui bottom fixed menu">
  <div class="item">
    <img src="/images/logo.png">
  </div>
  <a class="item">Features</a>
  <a class="item">Testimonials</a>
  <a class="item">Sign-in</a>
</div>
<p></p>
<p></p>
```
```html
<div class="ui left fixed vertical menu">
  <div class="item">
    <img class="ui mini image" src="/images/logo.png">
  </div>
  <a class="item">Features</a>
  <a class="item">Testimonials</a>
  <a class="item">Sign-in</a>
</div>
<div class="ui right fixed vertical menu">
  <div class="item">
    <img class="ui mini image" src="/images/logo.png">
  </div>
  <a class="item">Features</a>
  <a class="item">Testimonials</a>
  <a class="item">Sign-in</a>
</div>
<p></p>
<p></p>
```

#### Stackable
A menu can stack at mobile resolutions
> Stackable menus are intended to be used with only simple menu content. Stacked menus will not replicate all additional stylings for vertical menus like adjusting dropdown position.
```html
<div class="ui stackable menu">
  <div class="item">
    <img src="/images/logo.png">
  </div>
  <a class="item">Features</a>
  <a class="item">Testimonials</a>
  <a class="item">Sign-in</a>
</div>
```

#### Inverted
A menu may have its colors inverted to show greater contrast
```html
<div class="ui inverted menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
```
```html
<div class="ui inverted vertical menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
```
```html
<div class="ui inverted vertical pointing menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
```
```html
<div class="ui inverted segment">
  <div class="ui inverted secondary menu">
    <a class="active item">
      Home
    </a>
    <a class="item">
      Messages
    </a>
    <a class="item">
      Friends
    </a>
  </div>
</div>
```
```html
<div class="ui inverted segment">
  <div class="ui inverted secondary pointing menu">
    <a class="active item">
      Home
    </a>
    <a class="item">
      Messages
    </a>
    <a class="item">
      Friends
    </a>
  </div>
</div>
```

#### Colored
Additional colors can be specified.
```html
<div class="ui menu">
  <a class="active red item">Red</a>
  <a class="orange item">Orange</a>
  <a class="yellow item">Yellow</a>
  <a class="olive item">Olive</a>
  <a class="green item">Green</a>
  <a class="teal item">Teal</a>
</div>
<div class="ui menu">
  <a class="blue item">Blue</a>
  <a class="violet item">Violet</a>
  <a class="purple item">Purple</a>
  <a class="pink item">Pink</a>
  <a class="brown item">Brown</a>
  <a class="grey item">Grey</a>
</div>
```
```html
<div class="ui red three item menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui orange three item menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui yellow three item menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui olive three item menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui green three item menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui teal three item menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui blue three item menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui violet three item menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui purple three item menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui pink three item menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui brown three item menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui grey three item menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
```
```html
<p>These colors can also be inverted</p>
<div class="ui inverted menu">
  <a class="active red item">Red</a>
  <a class="orange item">Orange</a>
  <a class="yellow item">Yellow</a>
  <a class="olive item">Olive</a>
  <a class="green item">Green</a>
  <a class="teal item">Teal</a>
</div>
<div class="ui inverted menu">
  <a class="blue item">Blue</a>
  <a class="violet item">Violet</a>
  <a class="purple item">Purple</a>
  <a class="pink item">Pink</a>
  <a class="brown item">Brown</a>
  <a class="grey item">Grey</a>
</div>
```
```html
<div class="ui red three item inverted menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui orange three item inverted menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui yellow three item inverted menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui olive three item inverted menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui green three item inverted menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui teal three item inverted menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui blue three item inverted menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui violet three item inverted menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui purple three item inverted menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui pink three item inverted menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui brown three item inverted menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
<div class="ui grey three item inverted menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <a class="item">
    Friends
  </a>
</div>
```

#### Icons
A menu may have just icons
```html
<div class="ui icon menu">
  <a class="item">
    <i class="gamepad icon"></i>
  </a>
  <a class="item">
    <i class="video camera icon"></i>
  </a>
  <a class="item">
    <i class="video play icon"></i>
  </a>
</div>
<br><br>
<div class="ui vertical icon menu">
  <a class="item">
    <i class="gamepad icon"></i>
  </a>
  <a class="item">
    <i class="video camera icon"></i>
  </a>
  <a class="item">
    <i class="video play icon"></i>
  </a>
</div>
```

#### Labeled Icon
A menu may have labeled icons
```html
<div class="ui labeled icon menu">
  <a class="item">
    <i class="gamepad icon"></i>
    Games
  </a>
  <a class="item">
    <i class="video camera icon"></i>
    Channels
  </a>
  <a class="item">
    <i class="video play icon"></i>
    Videos
  </a>
</div>
<br><br>
<div class="ui vertical labeled icon menu">
  <a class="item">
    <i class="gamepad icon"></i>
    Games
  </a>
  <a class="item">
    <i class="video camera icon"></i>
    Channels
  </a>
  <a class="item">
    <i class="video play icon"></i>
    Videos
  </a>
</div>
```

#### Fluid
A vertical menu may take the size of its container. (A horizontal menu does this by default)
```html
<div class="ui fluid vertical menu">
  <a class="item">Run</a>
  <a class="item">Walk</a>
  <a class="item">Bike</a>
</div>
```

#### Compact
A menu can take up only the space necessary to fit its content
```html
<div class="ui compact menu">
  <a class="item">
    <i class="gamepad icon"></i>
    Games
  </a>
  <a class="item">
    <i class="video camera icon"></i>
    Channels
  </a>
  <a class="item">
    <i class="video play icon"></i>
    Videos
  </a>
</div>
```
```html
<div class="ui compact vertical labeled icon menu">
  <a class="item">
    <i class="gamepad icon"></i>
    Games
  </a>
  <a class="item">
    <i class="video camera icon"></i>
    Channels
  </a>
  <a class="item">
    <i class="video play icon"></i>
    Videos
  </a>
</div>
```

#### Evenly Divided
A menu may divide its items evenly
```html
<div class="ui fluid three item menu">
  <a class="item">Buy</a>
  <a class="item">Sell</a>
  <a class="item">Rent</a>
</div>
```

```html
<div class="ui pointing vertical menu">
  <a class="item">
    Site Title
  </a>
  <div class="item">
    <b>Grouped Section</b>
    <div class="menu">
      <a class="active item">Subsection 1</a>
      <a class="item">Subsection 1</a>
      <a class="item">Subsection 1</a>
    </div>
  </div>
  <div class="ui dropdown item">
    Dropdown <i class="dropdown icon"></i>
    <div class="menu">
      <div class="item">Choice 1</div>
      <div class="item">Choice 2</div>
      <div class="item">Choice 3</div>
    </div>
  </div>
</div>
```

#### Attached
A menu may be attached to other content segments
```html
<div class="ui top attached tabular menu">
  <a class="active item">
    Tab 1
  </a>
  <a class="item">
    Tab 2
  </a>
</div>
<div class="ui bottom attached segment">
  There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don't look even slightly believable. If you are going to use a passage of Lorem Ipsum, you need to be sure there isn't anything embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary, making this the first true generator on the Internet. It uses a dictionary of over 200 Latin words, combined with a handful of model sentence structures, to generate Lorem Ipsum which looks reasonable. The generated Lorem Ipsum is therefore always free from repetition, injected humour, or non-characteristic words etc.
</div>
```
```html
<div class="ui top attached menu">
  <a class="active item">
    Section 1
  </a>
  <a class="item">
    Section 2
  </a>
</div>
<div class="ui attached segment">
  There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don't look even slightly believable. If you are going to use a passage of Lorem Ipsum, you need to be sure there isn't anything embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary, making this the first true generator on the Internet. It uses a dictionary of over 200 Latin words, combined with a handful of model sentence structures, to generate Lorem Ipsum which looks reasonable. The generated Lorem Ipsum is therefore always free from repetition, injected humour, or non-characteristic words etc.
</div>
<div class="ui bottom attached menu">
  <a class="active item">
    Section 1
  </a>
  <a class="item">
    Section 2
  </a>
</div>
```

#### Size
A menu can vary in size
```html
<div class="ui mini menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <div class="right menu">
    <div class="ui dropdown item">
      Language <i class="dropdown icon"></i>
      <div class="menu">
        <a class="item">English</a>
        <a class="item">Russian</a>
        <a class="item">Spanish</a>
      </div>
    </div>
    <div class="item">
        <div class="ui primary button">Sign Up</div>
    </div>
  </div>
</div>
```
```html
<div class="ui tiny menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <div class="right menu">
    <div class="ui dropdown item">
      Language <i class="dropdown icon"></i>
      <div class="menu">
        <a class="item">English</a>
        <a class="item">Russian</a>
        <a class="item">Spanish</a>
      </div>
    </div>
    <div class="item">
        <div class="ui primary button">Sign Up</div>
    </div>
  </div>
</div>
```
```html
<div class="ui small menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <div class="right menu">
    <div class="ui dropdown item">
      Language <i class="dropdown icon"></i>
      <div class="menu">
        <a class="item">English</a>
        <a class="item">Russian</a>
        <a class="item">Spanish</a>
      </div>
    </div>
    <div class="item">
        <div class="ui primary button">Sign Up</div>
    </div>
  </div>
</div>
```
```html
<div class="ui large menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <div class="right menu">
    <div class="ui dropdown item">
      Language <i class="dropdown icon"></i>
      <div class="menu">
        <a class="item">English</a>
        <a class="item">Russian</a>
        <a class="item">Spanish</a>
      </div>
    </div>
    <div class="item">
        <div class="ui primary button">Sign Up</div>
    </div>
  </div>
</div>
```
```html
<div class="ui huge menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <div class="right menu">
    <div class="ui dropdown item">
      Language <i class="dropdown icon"></i>
      <div class="menu">
        <a class="item">English</a>
        <a class="item">Russian</a>
        <a class="item">Spanish</a>
      </div>
    </div>
    <div class="item">
        <div class="ui primary button">Sign Up</div>
    </div>
  </div>
</div>
```
```html
<div class="ui massive menu">
  <a class="active item">
    Home
  </a>
  <a class="item">
    Messages
  </a>
  <div class="right menu">
    <div class="ui dropdown item">
      Language <i class="dropdown icon"></i>
      <div class="menu">
        <a class="item">English</a>
        <a class="item">Russian</a>
        <a class="item">Spanish</a>
      </div>
    </div>
    <div class="item">
        <div class="ui primary button">Sign Up</div>
    </div>
  </div>
</div>
```

<p>A vertical menu can also vary in size</p>
```html
<div class="ui mini vertical menu">
  <a class="active item">
    <div class="ui teal label">1</div>
    Inbox
  </a>
  <a class="item">
    <div class="ui label">51</div>
    Spam
  </a>
  <a class="item">
    <div class="ui label">1</div>
    Updates
  </a>
  <div class="item">
    <div class="ui icon input">
      <input type="text" placeholder="Search mail...">
      <i class="search icon"></i>
    </div>
  </div>
</div>
```
```html
<div class="ui small vertical menu">
  <a class="active item">
    <div class="ui small teal label">1</div>
    Inbox
  </a>
  <a class="item">
    <div class="ui small label">51</div>
    Spam
  </a>
  <a class="item">
    <div class="ui small label">1</div>
    Updates
  </a>
  <div class="item">
    <div class="ui icon input">
      <input type="text" placeholder="Search mail...">
      <i class="search icon"></i>
    </div>
  </div>
</div>
```
```html
<div class="ui large vertical menu">
  <a class="active item">
    <div class="ui small teal label">1</div>
    Inbox
  </a>
  <a class="item">
    <div class="ui small label">51</div>
    Spam
  </a>
  <a class="item">
    <div class="ui small label">1</div>
    Updates
  </a>
  <div class="item">
    <div class="ui icon input">
      <input type="text" placeholder="Search mail...">
      <i class="search icon"></i>
    </div>
  </div>
</div>
```
```html
<div class="ui massive vertical menu">
  <a class="active item">
    <div class="ui small teal label">1</div>
    Inbox
  </a>
  <a class="item">
    <div class="ui small label">51</div>
    Spam
  </a>
  <a class="item">
    <div class="ui small label">1</div>
    Updates
  </a>
  <div class="item">
    <div class="ui icon input">
      <input type="text" placeholder="Search mail...">
      <i class="search icon"></i>
    </div>
  </div>
</div>
```

### Items

#### Fitted
A menu item or menu can remove element padding, vertically or horizontally
```html
<div class="ui menu">
  <div class="fitted item">
    No padding whatsoever
  </div>
  <div class="horizontally fitted item">
    No horizontal padding
  </div>
  <div class="vertically fitted item">
    No vertical padding
  </div>
</div>
```

#### Borderless
A menu item or menu can have no borders
```html
<div class="ui borderless menu">
  <a class="item">1</a>
  <a class="item">2</a>
  <a class="item">3</a>
  <a class="item">4</a>
  <a class="item">5</a>
  <a class="item">6</a>
</div>
```
