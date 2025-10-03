# Input

An input is a field used to elicit a response from a user

## Types

#### Input
A standard input
```html
<div class="ui input">
  <input type="text" placeholder="Search...">
</div>
```

## States

#### Focus
An input field can show a user is currently interacting with it
```html
<div class="ui input focus">
  <input type="text" placeholder="Search...">
</div>
```

#### Loading
An icon input field can show that it is currently loading data
> Loading inputs automatically modify the input's icon on loading state to show loading indication
```html
<div class="ui left icon input loading">
  <input type="text" placeholder="Search...">
  <i class="search icon"></i>
</div>
```
```html
<div class="ui icon input loading">
  <input type="text" placeholder="Search...">
  <i class="search icon"></i>
</div>
```

#### Disabled
An input field can show that it is disabled
```html
<div class="ui disabled input">
  <input type="text" placeholder="Search...">
</div>
```
```html
<div class="ui disabled icon input">
  <i class="search icon"></i>
  <input type="text" placeholder="Search...">
</div>
```
```html
<div class="ui input">
  <input type="text" placeholder="Search..." disabled>
</div>
```

#### Error
An input field can show the data contains errors
```html
<div class="ui input error">
  <input type="text" placeholder="Search...">
</div>
```

## Variations

#### Icon
An input can be formatted with an icon
> Input icons do not receive `pointer-events` unless a `link icon` is used.
```html
<div class="ui icon input">
  <input type="text" placeholder="Search...">
  <i class="search icon"></i>
</div>
```
```html
<div class="ui left icon input">
  <input type="text" placeholder="Search users...">
  <i class="users icon"></i>
</div>
```
```html
<div class="ui icon input">
  <input type="text" placeholder="Search...">
  <i class="circular search link icon"></i>
</div>
```
```html
<div class="ui icon input">
  <input type="text" placeholder="Search...">
  <i class="inverted circular search link icon"></i>
</div>
```

#### Labeled
An input can be formatted with a label
```html
<div class="ui labeled input">
  <div class="ui label">
    http://
  </div>
  <input type="text" placeholder="mysite.com">
</div>
```
```html
<div class="ui right labeled input">
  <input type="text" placeholder="Find domain">
  <div class="ui dropdown label">
    <div class="text">.com</div>
    <i class="dropdown icon"></i>
    <div class="menu">
      <div class="item">.com</div>
      <div class="item">.net</div>
      <div class="item">.org</div>
    </div>
  </div>
</div>
```
```html
<div class="ui right labeled input">
  <input type="text" placeholder="Enter weight..">
  <div class="ui basic label">
    kg
  </div>
</div>
```
```html
<div class="ui right labeled input">
  <label for="amount" class="ui label">$</label>
  <input type="text" placeholder="Amount" id="amount">
  <div class="ui basic label">.00</div>
</div>
```
```html
<div class="ui right labeled left icon input">
  <i class="tags icon"></i>
  <input type="text" placeholder="Enter tags">
  <a class="ui tag label">
    Add Tag
  </a>
</div>
```
```html
<div class="ui left corner labeled input">
  <input type="text" placeholder="Search...">
  <div class="ui left corner label">
    <i class="asterisk icon"></i>
  </div>
</div>
```
```html
<div class="ui corner labeled input">
  <input type="text" placeholder="Search...">
  <div class="ui corner label">
    <i class="asterisk icon"></i>
  </div>
</div>
```

#### Action
An input can be formatted to alert the user to an action they may perform
```html
<div class="ui action input">
  <input type="text" placeholder="Search...">
  <button class="ui button">Search</button>
</div>
```
```html
<div class="ui left action input">
  <button class="ui teal labeled icon button">
    <i class="cart icon"></i>
    Checkout
  </button>
  <input type="text" value="$52.03">
</div>
```
```html
<div class="ui right action left icon input">
  <i class="search icon"></i>
  <input type="text" placeholder="Search">
  <div class="ui basic floating dropdown button">
    <div class="text">This Page</div>
    <i class="dropdown icon"></i>
    <div class="menu">
      <div class="item">This Organization</div>
      <div class="item">Entire Site</div>
    </div>
  </div>
</div>
```
```html
<div class="ui action input">
  <input type="text" placeholder="Search...">
  <select class="ui compact selection dropdown">
    <option value="all">All</option>
    <option selected value="articles">Articles</option>
    <option value="products">Products</option>
  </select>
  <div class="ui button">Search</div>
</div>
```
```html
<div class="ui action input">
  <input type="text" value="http://ww.short.url/c0opq">
  <button class="ui teal right labeled icon button">
    <i class="copy icon"></i>
    Copy
  </button>
</div>
```
```html
<div class="ui action input">
  <input type="text" placeholder="Search...">
  <button class="ui icon button">
    <i class="search icon"></i>
  </button>
</div>
```

#### Transparent
A transparent input has no background
```html
<div class="ui transparent input">
  <input type="text" placeholder="Search...">
</div>
```
```html
<div class="ui transparent icon input">
  <input type="text" placeholder="Search...">
  <i class="search icon"></i>
</div>
```
```html
<div class="ui transparent left icon input">
  <input type="text" placeholder="Search...">
  <i class="search icon"></i>
</div>
```

#### Inverted
An input can be formatted to appear on dark backgrounds
```html
<div class="ui inverted segment">
  <div class="ui inverted input">
    <input type="text" placeholder="Search...">
  </div>
  <div class="ui inverted divider"></div>
  <div class="ui inverted left icon input">
    <input type="text" placeholder="Search...">
    <i class="search icon"></i>
  </div>
  <div class="ui inverted divider"></div>
  <div class="ui inverted transparent icon input">
    <input type="text" placeholder="Search...">
    <i class="search icon"></i>
  </div>
</div>
```

#### Fluid
An input can take the size of its container
```html
<div class="ui fluid icon input">
  <input type="text" placeholder="Search a very wide input...">
  <i class="search icon"></i>
</div>
<div class="ui ignored divider"></div>
<div class="ui fluid action input">
  <input type="text" placeholder="Search...">
  <div class="ui button">Search</div>
</div>
```

#### Size
An input can vary in size
> Inputs will automatically size themselves unless you manually declare a width
```html
<div class="ui mini icon input">
  <input type="text" placeholder="Search mini...">
  <i class="search icon"></i>
</div>
```
```html
<div class="ui small icon input">
  <input type="text" placeholder="Search small...">
  <i class="search icon"></i>
</div>
```
```html
<div class="ui large icon input">
  <input type="text" placeholder="Search large...">
  <i class="search icon"></i>
</div>
```
```html
<div class="ui big icon input">
  <input type="text" placeholder="Search big...">
  <i class="search icon"></i>
</div>
```
```html
<div class="ui huge icon input">
  <input type="text" placeholder="Search huge...">
  <i class="search icon"></i>
</div>
```
```html
<div class="ui massive icon input">
  <input type="text" placeholder="Search massive...">
  <i class="search icon"></i>
</div>
```
