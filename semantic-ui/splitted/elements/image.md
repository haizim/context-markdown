# Image

An image is a graphic representation of something

## Types

#### Image
An image
> Unless a size is specified, images will use the original dimensions of the image up to the size of its container.
> You can specify an `img` or `svg` as a `ui image` or use a child element.
```html
<img class="ui small image" src="/images/wireframe/image.png">
```
```html
<div class="ui small image">
  <img src="/images/wireframe/image.png">
</div>
```
```html
<div class="ui small image">
  <svg width="150" height="150">
    <image xlink:href="/images/wireframe/image.png" x="0" y="0" width="100%" height="100%"></image>
  </svg>
</div>
```

#### Image Link
An image can be formatted to link to other content
```html
<a href="http://google.com" class="ui medium image">
  <img src="/images/wireframe/image-text.png">
</a>
```

## States

#### Hidden
An image can be hidden
```html
<img class="hidden ui image" src="/images/wireframe/image.png">
```

#### Disabled
An image can show that it is disabled and cannot be selected
```html
<img class="disabled medium ui image" src="/images/wireframe/image.png">
```

## Variations

#### Avatar
An image may be formatted to appear inline with text as an avatar
```html
<img class="ui avatar image" src="/images/wireframe/square-image.png">
<span>Username</span>
```

#### Bordered
An image may include a border to emphasize the edges of white or transparent content
```html
<img class="ui medium bordered image" src="/images/wireframe/white-image.png">
```

#### Fluid
An image can take up the width of its container
```html
<img class="ui fluid image" src="/images/wireframe/image.png">
```

#### Rounded
An image may appear rounded
```html
<img class="ui medium rounded image" src="/images/wireframe/square-image.png">
```

#### Circular
An image may appear circular
```html
<img class="ui medium circular image" src="/images/wireframe/square-image.png">
```

#### Vertically Aligned
An image can specify its vertical alignment
```html
<img class="ui top aligned tiny image" src="/images/wireframe/square-image.png">
<span>Top Aligned</span>
<div class="ui divider"></div>
<img class="ui middle aligned tiny image" src="/images/wireframe/square-image.png">
<span>Middle Aligned</span>
<div class="ui divider"></div>
<img class="ui bottom aligned tiny image" src="/images/wireframe/square-image.png">
<span>Bottom Aligned</span>
```

#### Centered
An image can appear centered in a content block
```html
<div class="ui segment">
  <img class="ui centered medium image" src="/images/wireframe/image.png">
  <p>Te eum doming eirmod, nominati pertinacia argumentum ad his. Ex eam alia facete scriptorem, est autem aliquip detraxit at. Usu ocurreret referrentur at, cu epicurei appellantur vix. Cum ea laoreet recteque electram, eos choro alterum definiebas in. Vim dolorum definiebas an. Mei ex natum rebum iisque.</p>
  <p>Audiam quaerendum eu sea, pro omittam definiebas ex. Te est latine definitiones. Quot wisi nulla ex duo. Vis sint solet expetenda ne, his te phaedrum referrentur consectetuer. Id vix fabulas oporteat, ei quo vide phaedrum, vim vivendum maiestatis in.</p>
  <img class="ui small centered image" src="/images/wireframe/text-image.png">
  <p>Eu quo homero blandit intellegebat. Incorrupte consequuntur mei id. Mei ut facer dolores adolescens, no illum aperiri quo, usu odio brute at. Qui te porro electram, ea dico facete utroque quo. Populo quodsi te eam, wisi everti eos ex, eum elitr altera utamur at. Quodsi convenire mnesarchum eu per, quas minimum postulant per id.</p>
</div>
```

#### Spaced
An image can specify that it needs an additional spacing to separate it from nearby content

```html
<div class="ui segment">
  <p>Te eum doming eirmod, nominati pertinacia <img class="ui mini spaced image" src="/images/wireframe/image.png"> argumentum ad his. Ex eam alia facete scriptorem, est autem aliquip detraxit at. Usu ocurreret referrentur at, cu epicurei appellantur vix. Cum ea laoreet recteque electram, eos choro alterum definiebas in. Vim dolorum definiebas an. Mei ex natum rebum iisque.</p>
</div>
```
```html
<p><img class="ui mini right spaced image" src="/images/wireframe/image.png">Audiam quaerendum eu sea, pro omittam definiebas ex. Te est latine definitiones. Quot wisi nulla ex duo. Vis sint solet expetenda ne, his te phaedrum referrentur consectetuer. Id vix fabulas oporteat, ei quo vide phaedrum, vim vivendum maiestatis in.</p>

<p>Eu quo homero blandit intellegebat. Incorrupte consequuntur mei id. Mei ut facer dolores adolescens, no illum aperiri quo, usu odio brute at. Qui te porro electram, ea dico facete utroque quo. Populo quodsi te eam, wisi everti eos ex, eum elitr altera utamur at. Quodsi convenire mnesarchum eu per, quas minimum postulant per id.<img class="ui mini left spaced image" src="/images/wireframe/image.png"></p>
```

#### Floated
An image can sit to the left or right of other content
```html
<div class="ui segment">
  <img class="ui small left floated image" src="/images/wireframe/text-image.png">
  <p>Te eum doming eirmod, nominati pertinacia argumentum ad his. Ex eam alia facete scriptorem, est autem aliquip detraxit at. Usu ocurreret referrentur at, cu epicurei appellantur vix. Cum ea laoreet recteque electram, eos choro alterum definiebas in. Vim dolorum definiebas an. Mei ex natum rebum iisque.</p>
  <img class="ui small right floated image" src="/images/wireframe/text-image.png">
  <p>Audiam quaerendum eu sea, pro omittam definiebas ex. Te est latine definitiones. Quot wisi nulla ex duo. Vis sint solet expetenda ne, his te phaedrum referrentur consectetuer. Id vix fabulas oporteat, ei quo vide phaedrum, vim vivendum maiestatis in.</p>

  <p>Eu quo homero blandit intellegebat. Incorrupte consequuntur mei id. Mei ut facer dolores adolescens, no illum aperiri quo, usu odio brute at. Qui te porro electram, ea dico facete utroque quo. Populo quodsi te eam, wisi everti eos ex, eum elitr altera utamur at. Quodsi convenire mnesarchum eu per, quas minimum postulant per id.</p>
</div>
```

#### Size
An image may appear at different sizes
> Semantic uses arbitrary default values for image sizes from mini to massive. It is recommended to update these with values used in your project in `image.variables`.

| Class Name | Size |
|---|---|
| Mini | 35px |
| Tiny | 80px |
| Small | 150px |
| Medium | 300px |
| Large | 450px |
| Big | 600px |
| Huge | 800px |
| Massive | 960px |

```html
<img class="ui mini image" src="/images/wireframe/image.png">
<div class="ui hidden divider"></div>
<img class="ui tiny image" src="/images/wireframe/image.png">
<div class="ui hidden divider"></div>
<img class="ui small image" src="/images/wireframe/image.png">
<div class="ui hidden divider"></div>
<img class="ui medium image" src="/images/wireframe/image.png">
```
```html
<img class="ui mini image" src="/images/wireframe/image.png">
<img class="ui tiny image" src="/images/wireframe/image.png">
<img class="ui small image" src="/images/wireframe/image.png">
<img class="ui medium image" src="/images/wireframe/image.png">
<img class="ui large image" src="/images/wireframe/image.png">
<img class="ui big image" src="/images/wireframe/image.png">
<img class="ui huge image" src="/images/wireframe/image.png">
<img class="ui massive image" src="/images/wireframe/image.png">
```

## Groups

#### Size
A group of images can be formatted to have the same size.
```html
<div class="ui tiny images">
  <img class="ui image" src="/images/wireframe/image.png">
  <img class="ui image" src="/images/wireframe/image.png">
  <img class="ui image" src="/images/wireframe/image.png">
  <img class="ui image" src="/images/wireframe/image.png">
</div>
```
```html
<div class="ui small images">
  <img src="/images/wireframe/image.png">
  <img src="/images/wireframe/image.png">
  <img src="/images/wireframe/image.png">
  <img src="/images/wireframe/image.png">
</div>
```
