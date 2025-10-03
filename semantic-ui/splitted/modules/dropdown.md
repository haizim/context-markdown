# Semantic UI

User Interface is the language of the web

## Design Beautiful Websites Quickly

Semantic is a development framework that helps create beautiful, responsive layouts using human-friendly HTML.

## Concise HTML
Semantic UI treats words and classes as exchangeable concepts.

Classes use syntax from natural languages like noun/modifier relationships, word order, and plurality to link concepts intuitively.

Get the same benefits as [BEM](https://en.bem.info) or [SMACSS](https://smacss.com), but without the tedium.

```html
<div class="ui three buttons">
  <button class="ui active button">One</button>
  <button class="ui button">Two</button>
  <button class="ui button">Three</button>
</div>
```

## Intuitive Javascript
Semantic uses simple phrases called behaviors that trigger functionality.

Any arbitrary decision in a component is included as a setting that developers can modify.

```javascript
$('select.dropdown')
  .dropdown('set selected', ['meteor', 'ember'])
;
```
```html
<select name="skills" multiple class="ui fluid dropdown">
  <option value="">Skills</option>
  <option value="angular">Angular</option>
  <option value="css">CSS</option>
  <option value="ember">Ember</option>
  <option value="html">HTML</option>
  <option value="javascript">Javascript</option>
  <option value="meteor">Meteor</option>
  <option value="node">NodeJS</option>
</select>
```

## Simplified Debugging
Performance logging lets you track down bottlenecks without digging through stack traces.

> Don't have access to development tools right now? Check out [this short clip](http://t.co/GOUQx8iCyG).

```javascript
$('.sequenced.images .image')
  .transition({
    debug     : true,
    animation : 'jiggle',
    duration  : 500,
    interval  : 200
  })
;
```
```html
<div class="ui small sequenced images">
  <img src="/images/avatar2/large/elyse.png" class="ui circular image">
  <img src="/images/avatar2/large/matthew.png" class="ui circular image">
  <img src="/images/avatar2/large/kristy.png" class="ui circular image">
</div>
```

## Semantic is growing fast. Want to see just how much? Sign up and we'll let you know

```html
<form class="ui form" method="post" action="https://semantic-ui.clients.ubivox.com/handlers/post/">
  <input type="hidden" name="action" value="subscribe" />
  <input type="hidden" name="lists" value="29450" />
  <div class="field">
    <div class="ui huge input">
      <input type="text" name="email_address" data-validate="email" placeholder="E-mail">
    </div>
    <button type="submit" value="Subscribe" class="ui huge secondary submit button">
      Sign-up
    </button>
  </div>
</form>
```

## Unbelievable Theming

Semantic comes equipped with an intuitive inheritance system and high level theming variables that let you have complete design freedom.

Develop your UI once, then deploy with the same code everywhere.

```html
<div data-type="element" data-element="button" class="ui large floating dropdown theme button">
  <span class="text">Select Theme</span>
  <i class="dropdown icon"></i>
  <div class="menu ui transition hidden" tabindex="-1">
    <div data-value="Default" class="item">Semantic UI</div>
    <div data-value="Amazon" class="item">Amazon</div>
    <div data-value="Material" class="item">Google Material</div>
    <div data-value="GitHub" class="item">GitHub</div>
    <div data-value="Bootstrap3" class="item">Bootstrap</div>
    <div data-value="Twitter" class="item">Twitter</div>
    <div class="divider"></div>
    <div data-value="Raised" class="item">Raised</div>
    <div data-value="Chubby" class="item">Chubby</div>
    <div data-value="Classic" class="item">Classic</div>
  </div>
</div>
<div class="ui divider"></div>
<div class="ui button">
  View
</div>
<div class="ui primary button">
  <i class="shop icon"></i> Add to Cart
</div>
<div class="ui secondary button">
  <i class="save icon"></i> Save for Later
</div>
<div class="ui labeled icon button">
  <i class="star icon"></i>
  Rate
</div>
<div class="ui demo buttons">
  <div class="ui active button">1</div>
  <div class="ui button">2</div>
  <div class="ui button">3</div>
</div>
```

### Variable File
```html
<div class="variable code" data-type="less" data-preserve="true">
</div>
```

### Override File
```html
<div class="override code" data-type="less" data-preserve="true">
</div>
```

## Unbelievable Breadth

Definitions aren't limited to just buttons on a page. Semantic's components allow several distinct types of definitions: elements, collections, views, modules and behaviors which cover the gamut of interface design.

[See Layout Examples](/usage/layout.html)

### Menu
```html
<div class="ui vertical demo menu">
  <a class="active teal item">
    Inbox
    <div class="ui teal label">1</div>
  </a>
  <a class="item">
    Trash
    <div class="ui label">1</div>
  </a>
  <div class="item">
    <div class="ui transparent icon input">
      <input type="text" placeholder="Search mail...">
      <i class="search icon"></i>
    </div>
  </div>
</div>
<div class="ui fluid demo tabular menu">
  <a class="active item">
    Tab
  </a>
  <a class="item">
    Tab
  </a>
</div>
<div class="ui secondary vertical demo menu">
  <a class="active item">
    Inbox
  </a>
  <a class="item">
    Starred
  </a>
  <a class="item">
    Trash
  </a>
</div>
<div class="ui secondary pointing vertical demo menu">
  <a class="active item">
    Inbox
  </a>
  <a class="item">
    Starred
  </a>
  <a class="item">
    Trash
  </a>
</div>
```

### Divider
```html
<div class="ui two column stackable center aligned grid segment">
  <div class="column">
    <div class="ui button">A</div>
  </div>
  <div class="ui vertical divider">or</div>
  <div class="column">
    <div class="teal ui button">B</div>
  </div>
</div>
```

### Accordion
```html
<div class="ui vertical fluid accordion menu">
  <div class="item">
    <a class="active title">
      <i class="dropdown icon"></i>
      Size
    </a>
    <div class="active content">
      <div class="ui form">
        <div class="grouped fields">
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="size" value="small">
              <label>Small</label>
            </div>
          </div>
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="size" value="medium">
              <label>Medium</label>
            </div>
            </div>
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="size" value="large">
              <label>Large</label>
            </div>
          </div>
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="size" value="x-large">
              <label>X-Large</label>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="item">
    <a class="title">
      <i class="dropdown icon"></i>
      Colors
    </a>
    <div class="content">
      <div class="ui form">
        <div class="grouped fields">
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="color">
              <label>Red</label>
            </div>
          </div>
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="color">
              <label>Orange</label>
            </div>
          </div>
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="color">
              <label>Green</label>
            </div>
          </div>
          <div class="field">
            <div class="ui radio checkbox">
              <input type="radio" name="color">
              <label>Blue</label>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
```

### Message
```html
<div class="ui message">
  <i class="close icon"></i>
  This site uses cookies
</div>
<div class="ui warning icon message">
  <div class="content">
    <div class="header">Looking for help? </div>
    <ul class="list">
      <li>Use our <a href="#">help center</a></li>
      <li>Check our <a href"#"="">FAQ</a></li>
    </ul>
  </div>
</div>
<div class="ui info message">
  <div class="header">We're creating your profile page</div>
  <p>It will be ready in just a second.</p>
</div>
```

### Card
```html
<div class="ui card">
  <div class="blurring dimmable image">
    <div class="ui dimmer">
      <div class="content">
        <div class="center">
          <div class="ui inverted button">Add Friend</div>
        </div>
      </div>
    </div>
    <img src="/images/avatar2/large/rachel.png">
  </div>
  <div class="content">
    <div class="header">Rachel Maddaw</div>
    <div class="meta">
      <a class="group">Pundit</a>
    </div>
  </div>
  <div class="extra content">
    <a class="right floated created">
      Joined in 1998
    </a>
    <a class="friends">
      <i class="user icon"></i>
      22 Friends
    </a>
  </div>
</div>
```

### Feed
```html
<div class="ui feed">
  <div class="event">
    <div class="label">
      <img src="/images/avatar2/small/mark.png">
    </div>
    <div class="content">
      <div class="summary">
        <a class="user">
          Mark
        </a> added you as a friend
      </div>
    </div>
  </div>
  <div class="event">
    <div class="label">
      <img src="/images/avatar2/small/lena.png">
    </div>
    <div class="content">
      You added Lena to the group <a>Close Friends</a>
    </div>
  </div>
  <div class="event">
    <div class="label">
      <img src="/images/avatar2/small/eve.png">
    </div>
    <div class="content">
      Eve just <a>posted on your page</a>
    </div>
  </div>
</div>
```

### Label
```html
<div class="ui image label">
  <img src="/images/avatar2/small/molly.png">
  molly@thebears.com
  <i class="delete icon"></i>
</div>
<a class="ui teal label">
  <i class="mail icon"></i> 23 New
</a>
<a class="ui tag label">Dresses</a>
```

### Step
```html
<div class="ui fluid vertical steps">
  <a class="step">
    <i class="truck icon"></i>
    <div class="content">
      <div class="title">Shipping</div>
      <div class="description">Choose your shipping options</div>
    </div>
  </a>
  <a class="active step">
    <i class="payment icon"></i>
    <div class="content">
      <div class="title">Billing</div>
      <div class="description">Enter billing information</div>
    </div>
  </a>
  <a class="disabled step">
    <i class="info icon"></i>
    <div class="content">
      <div class="title">Confirm Order</div>
      <div class="description">Verify order details</div>
    </div>
  </a>
</div>
```

### Dropdown
```html
<div class="ui fluid search selection dropdown">
  <input type="hidden" name="country">
  <i class="dropdown icon"></i>
  <input class="search" tabindex="0"><div class="default text">Select Country</div>
  <div class="menu" tabindex="-1">
    <div class="item" data-value="ad"><i class="ad flag"></i>Andorra</div>
    <div class="item" data-value="ae"><i class="ae flag"></i>United Arab Emirates</div>
    <div class="item" data-value="af"><i class="af flag"></i>Afghanistan</div>
    <div class="item" data-value="ag"><i class="ag flag"></i>Antigua</div>
    <div class="item" data-value="ai"><i class="ai flag"></i>Anguilla</div>
    <div class="item" data-value="al"><i class="al flag"></i>Albania</div>
    <div class="item" data-value="am"><i class="am flag"></i>Armenia</div>
    <div class="item" data-value="an"><i class="an flag"></i>Netherlands Antilles</div>
    <div class="item" data-value="ao"><i class="ao flag"></i>Angola</div>
    <div class="item" data-value="ar"><i class="ar flag"></i>Argentina</div>
    <div class="item" data-value="as"><i class="as flag"></i>American Samoa</div>
    <div class="item" data-value="at"><i class="at flag"></i>Austria</div>
    <div class="item" data-value="au"><i class="au flag"></i>Australia</div>
    <div class="item" data-value="aw"><i class="aw flag"></i>Aruba</div>
    <div class="item" data-value="ax"><i class="ax flag"></i>Aland Islands</div>
    <div class="item" data-value="az"><i class="az flag"></i>Azerbaijan</div>
    <div class="item" data-value="ba"><i class="ba flag"></i>Bosnia</div>
    <div class="item" data-value="bb"><i class="bb flag"></i>Barbados</div>
    <div class="item" data-value="bd"><i class="bd flag"></i>Bangladesh</div>
    <div class="item" data-value="be"><i class="be flag"></i>Belgium</div>
    <div class="item" data-value="bf"><i class="bf flag"></i>Burkina Faso</div>
    <div class="item" data-value="bg"><i class="bg flag"></i>Bulgaria</div>
    <div class="item" data-value="bh"><i class="bh flag"></i>Bahrain</div>
    <div class="item" data-value="bi"><i class="bi flag"></i>Burundi</div>
    <div class="item" data-value="bj"><i class="bj flag"></i>Benin</div>
    <div class="item" data-value="bm"><i class="bm flag"></i>Bermuda</div>
    <div class="item" data-value="bn"><i class="bn flag"></i>Brunei</div>
    <div class="item" data-value="bo"><i class="bo flag"></i>Bolivia</div>
    <div class="item" data-value="br"><i class="br flag"></i>Brazil</div>
    <div class="item" data-value="bs"><i class="bs flag"></i>Bahamas</div>
    <div class="item" data-value="bt"><i class="bt flag"></i>Bhutan</div>
    <div class="item" data-value="bv"><i class="bv flag"></i>Bouvet Island</div>
    <div class="item" data-value="bw"><i class="bw flag"></i>Botswana</div>
    <div class="item" data-value="by"><i class="by flag"></i>Belarus</div>
    <div class="item" data-value="bz"><i class="bz flag"></i>Belize</div>
    <div class="item" data-value="ca"><i class="ca flag"></i>Canada</div>
    <div class="item" data-value="cc"><i class="cc flag"></i>Cocos Islands</div>
    <div class="item" data-value="cd"><i class="cd flag"></i>Congo</div>
    <div class="item" data-value="cf"><i class="cf flag"></i>Central African Republic</div>
    <div class="item" data-value="cg"><i class="cg flag"></i>Congo Brazzaville</div>
    <div class="item" data-value="ch"><i class="ch flag"></i>Switzerland</div>
    <div class="item" data-value="ci"><i class="ci flag"></i>Cote Divoire</div>
    <div class="item" data-value="ck"><i class="ck flag"></i>Cook Islands</div>
    <div class="item" data-value="cl"><i class="cl flag"></i>Chile</div>
    <div class="item" data-value="cm"><i class="cm flag"></i>Cameroon</div>
    <div class="item" data-value="cn"><i class="cn flag"></i>China</div>
    <div class="item" data-value="co"><i class="co flag"></i>Colombia</div>
    <div class="item" data-value="cr"><i class="cr flag"></i>Costa Rica</div>
    <div class="item" data-value="cs"><i class="cs flag"></i>Serbia</div>
    <div class="item" data-value="cu"><i class="cu flag"></i>Cuba</div>
    <div class="item" data-value="cv"><i class="cv flag"></i>Cape Verde</div>
    <div class="item" data-value="cx"><i class="cx flag"></i>Christmas Island</div>
    <div class="item" data-value="cy"><i class="cy flag"></i>Cyprus</div>
    <div class="item" data-value="cz"><i class="cz flag"></i>Czech Republic</div>
    <div class="item" data-value="de"><i class="de flag"></i>Germany</div>
    <div class="item" data-value="dj"><i class="dj flag"></i>Djibouti</div>
    <div class="item" data-value="dk"><i class="dk flag"></i>Denmark</div>
    <div class="item" data-value="dm"><i class="dm flag"></i>Dominica</div>
    <div class="item" data-value="do"><i class="do flag"></i>Dominican Republic</div>
    <div class="item" data-value="dz"><i class="dz flag"></i>Algeria</div>
    <div class="item" data-value="ec"><i class="ec flag"></i>Ecuador</div>
    <div class="item" data-value="ee"><i class="ee flag"></i>Estonia</div>
    <div class="item" data-value="eg"><i class="eg flag"></i>Egypt</div>
    <div class="item" data-value="eh"><i class="eh flag"></i>Western Sahara</div>
    <div class="item" data-value="er"><i class="er flag"></i>Eritrea</div>
    <div class="item" data-value="es"><i class="es flag"></i>Spain</div>
    <div class="item" data-value="et"><i class="et flag"></i>Ethiopia</div>
    <div class="item" data-value="eu"><i class="eu flag"></i>European Union</div>
    <div class="item" data-value="fi"><i class="fi flag"></i>Finland</div>
    <div class="item" data-value="fj"><i class="fj flag"></i>Fiji</div>
    <div class="item" data-value="fk"><i class="fk flag"></i>Falkland Islands</div>
    <div class="item" data-value="fm"><i class="fm flag"></i>Micronesia</div>
    <div class="item" data-value="fo"><i class="fo flag"></i>Faroe Islands</div>
    <div class="item" data-value="fr"><i class="fr flag"></i>France</div>
    <div class="item" data-value="ga"><i class="ga flag"></i>Gabon</div>
    <div class="item" data-value="gb"><i class="gb flag"></i>England</div>
    <div class="item" data-value="gd"><i class="gd flag"></i>Grenada</div>
    <div class="item" data-value="ge"><i class="ge flag"></i>Georgia</div>
    <div class="item" data-value="gf"><i class="gf flag"></i>French Guiana</div>
    <div class="item" data-value="gh"><i class="gh flag"></i>Ghana</div>
    <div class="item" data-value="gi"><i class="gi flag"></i>Gibraltar</div>
    <div class="item" data-value="gl"><i class="gl flag"></i>Greenland</div>
    <div class="item" data-value="gm"><i class="gm flag"></i>Gambia</div>
    <div class="item" data-value="gn"><i class="gn flag"></i>Guinea</div>
    <div class="item" data-value="gp"><i class="gp flag"></i>Guadeloupe</div>
    <div class="item" data-value="gq"><i class="gq flag"></i>Equatorial Guinea</div>
    <div class="item" data-value="gr"><i class="gr flag"></i>Greece</div>
    <div class="item" data-value="gs"><i class="gs flag"></i>Sandwich Islands</div>
    <div class="item" data-value="gt"><i class="gt flag"></i>Guatemala</div>
    <div class="item" data-value="gu"><i class="gu flag"></i>Guam</div>
    <div class="item" data-value="gw"><i class="gw flag"></i>Guinea-Bissau</div>
    <div class="item" data-value="gy"><i class="gy flag"></i>Guyana</div>
    <div class="item" data-value="hk"><i class="hk flag"></i>Hong Kong</div>
    <div class="item" data-value="hm"><i class="hm flag"></i>Heard Island</div>
    <div class="item" data-value="hn"><i class="hn flag"></i>Honduras</div>
    <div class="item" data-value="hr"><i class="hr flag"></i>Croatia</div>
    <div class="item" data-value="ht"><i class="ht flag"></i>Haiti</div>
    <div class="item" data-value="hu"><i class="hu flag"></i>Hungary</div>
    <div class="item" data-value="id"><i class="id flag"></i>Indonesia</div>
    <div class="item" data-value="ie"><i class="ie flag"></i>Ireland</div>
    <div class="item" data-value="il"><i class="il flag"></i>Israel</div>
    <div class="item" data-value="in"><i class="in flag"></i>India</div>
    <div class="item" data-value="io"><i class="io flag"></i>Indian Ocean Territory</div>
    <div class="item" data-value="iq"><i class="iq flag"></i>Iraq</div>
    <div class="item" data-value="ir"><i class="ir flag"></i>Iran</div>
    <div class="item" data-value="is"><i class="is flag"></i>Iceland</div>
    <div class="item" data-value="it"><i class="it flag"></i>Italy</div>
    <div class="item" data-value="jm"><i class="jm flag"></i>Jamaica</div>
    <div class="item" data-value="jo"><i class="jo flag"></i>Jordan</div>
    <div class="item" data-value="jp"><i class="jp flag"></i>Japan</div>
    <div class="item" data-value="ke"><i class="ke flag"></i>Kenya</div>
    <div class="item" data-value="kg"><i class="kg flag"></i>Kyrgyzstan</div>
    <div class="item" data-value="kh"><i class="kh flag"></i>Cambodia</div>
    <div class="item" data-value="ki"><i class="ki flag"></i>Kiribati</div>
    <div class="item" data-value="km"><i class="km flag"></i>Comoros</div>
    <div class="item" data-value="kn"><i class="kn flag"></i>Saint Kitts and Nevis</div>
    <div class="item" data-value="kp"><i class="kp flag"></i>North Korea</div>
    <div class="item" data-value="kr"><i class="kr flag"></i>South Korea</div>
    <div class="item" data-value="kw"><i class="kw flag"></i>Kuwait</div>
    <div class="item" data-value="ky"><i class="ky flag"></i>Cayman Islands</div>
    <div class="item" data-value="kz"><i class="kz flag"></i>Kazakhstan</div>
    <div class="item" data-value="la"><i class="la flag"></i>Laos</div>
    <div class="item" data-value="lb"><i class="lb flag"></i>Lebanon</div>
    <div class="item" data-value="lc"><i class="lc flag"></i>Saint Lucia</div>
    <div class="item" data-value="li"><i class="li flag"></i>Liechtenstein</div>
    <div class="item" data-value="lk"><i class="lk flag"></i>Sri Lanka</div>
    <div class="item" data-value="lr"><i class="lr flag"></i>Liberia</div>
    <div class="item" data-value="ls"><i class="ls flag"></i>Lesotho</div>
    <div class="item" data-value="lt"><i class="lt flag"></i>Lithuania</div>
    <div class="item" data-value="lu"><i class="lu flag"></i>Luxembourg</div>
    <div class="item" data-value="lv"><i class="lv flag"></i>Latvia</div>
    <div class="item" data-value="ly"><i class="ly flag"></i>Libya</div>
    <div class="item" data-value="ma"><i class="ma flag"></i>Morocco</div>
    <div class="item" data-value="mc"><i class="mc flag"></i>Monaco</div>
    <div class="item" data-value="md"><i class="md flag"></i>Moldova</div>
    <div class="item" data-value="me"><i class="me flag"></i>Montenegro</div>
    <div class="item" data-value="mg"><i class="mg flag"></i>Madagascar</div>
    <div class="item" data-value="mh"><i class="mh flag"></i>Marshall Islands</div>
    <div class="item" data-value="mk"><i class="mk flag"></i>MacEdonia</div>
    <div class="item" data-value="ml"><i class="ml flag"></i>Mali</div>
    <div class="item" data-value="ar"><i class="ar flag"></i>Burma</div>
    <div class="item" data-value="mn"><i class="mn flag"></i>Mongolia</div>
    <div class="item" data-value="mo"><i class="mo flag"></i>MacAu</div>
    <div class="item" data-value="mp"><i class="mp flag"></i>Northern Mariana Islands</div>
    <div class="item" data-value="mq"><i class="mq flag"></i>Martinique</div>
    <div class="item" data-value="mr"><i class="mr flag"></i>Mauritania</div>
    <div class="item" data-value="ms"><i class="ms flag"></i>Montserrat</div>
    <div class="item" data-value="mt"><i class="mt flag"></i>Malta</div>
    <div class="item" data-value="mu"><i class="mu flag"></i>Mauritius</div>
    <div class="item" data-value="mv"><i class="mv flag"></i>Maldives</div>
    <div class="item" data-value="mw"><i class="mw flag"></i>Malawi</div>
    <div class="item" data-value="mx"><i class="mx flag"></i>Mexico</div>
    <div class="item" data-value="my"><i class="my flag"></i>Malaysia</div>
    <div class="item" data-value="mz"><i class="mz flag"></i>Mozambique</div>
    <div class="item" data-value="na"><i class="na flag"></i>Namibia</div>
    <div class="item" data-value="nc"><i class="nc flag"></i>New Caledonia</div>
    <div class="item" data-value="ne"><i class="ne flag"></i>Niger</div>
    <div class="item" data-value="nf"><i class="nf flag"></i>Norfolk Island</div>
    <div class="item" data-value="ng"><i class="ng flag"></i>Nigeria</div>
    <div class="item" data-value="ni"><i class="ni flag"></i>Nicaragua</div>
    <div class="item" data-value="nl"><i class="nl flag"></i>Netherlands</div>
    <div class="item" data-value="no"><i class="no flag"></i>Norway</div>
    <div class="item" data-value="np"><i class="np flag"></i>Nepal</div>
    <div class="item" data-value="nr"><i class="nr flag"></i>Nauru</div>
    <div class="item" data-value="nu"><i class="nu flag"></i>Niue</div>
    <div class="item" data-value="nz"><i class="nz flag"></i>New Zealand</div>
    <div class="item" data-value="om"><i class="om flag"></i>Oman</div>
    <div class="item" data-value="pa"><i class="pa flag"></i>Panama</div>
    <div class="item" data-value="pe"><i class="pe flag"></i>Peru</div>
    <div class="item" data-value="pf"><i class="pf flag"></i>French Polynesia</div>
    <div class="item" data-value="pg"><i class="pg flag"></i>New Guinea</div>
    <div class="item" data-value="ph"><i class="ph flag"></i>Philippines</div>
    <div class="item" data-value="pk"><i class="pk flag"></i>Pakistan</div>
    <div class="item" data-value="pl"><i class="pl flag"></i>Poland</div>
    <div class="item" data-value="pm"><i class="pm flag"></i>Saint Pierre</div>
    <div class="item" data-value="pn"><i class="pn flag"></i>Pitcairn Islands</div>
    <div class="item" data-value="pr"><i class="pr flag"></i>Puerto Rico</div>
    <div class="item" data-value="ps"><i class="ps flag"></i>Palestine</div>
    <div class="item" data-value="pt"><i class="pt flag"></i>Portugal</div>
    <div class="item" data-value="pw"><i class="pw flag"></i>Palau</div>
    <div class="item" data-value="py"><i class="py flag"></i>Paraguay</div>
    <div class="item" data-value="qa"><i class="qa flag"></i>Qatar</div>
    <div class="item" data-value="re"><i class="re flag"></i>Reunion</div>
    <div class="item" data-value="ro"><i class="ro flag"></i>Romania</div>
    <div class="item" data-value="rs"><i class="rs flag"></i>Serbia</div>
    <div class="item" data-value="ru"><i class="ru flag"></i>Russia</div>
    <div class="item" data-value="rw"><i class="rw flag"></i>Rwanda</div>
    <div class="item" data-value="sa"><i class="sa flag"></i>Saudi Arabia</div>
    <div class="item" data-value="sb"><i class="sb flag"></i>Solomon Islands</div>
    <div class="item" data-value="sc"><i class="sc flag"></i>Seychelles</div>
    <div class="item" data-value="sd"><i class="sd flag"></i>Sudan</div>
    <div class="item" data-value="se"><i class="se flag"></i>Sweden</div>
    <div class="item" data-value="sg"><i class="sg flag"></i>Singapore</div>
    <div class="item" data-value="sh"><i class="sh flag"></i>Saint Helena</div>
    <div class="item" data-value="si"><i class="si flag"></i>Slovenia</div>
    <div class="item" data-value="sj"><i class="sj flag"></i>Svalbard, I Flag Jan Mayen</div>
    <div class="item" data-value="sk"><i class="sk flag"></i>Slovakia</div>
    <div class="item" data-value="sl"><i class="sl flag"></i>Sierra Leone</div>
    <div class="item" data-value="sm"><i class="sm flag"></i>San Marino</div>
    <div class="item" data-value="sn"><i class="sn flag"></i>Senegal</div>
    <div class="item" data-value="so"><i class="so flag"></i>Somalia</div>
    <div class="item" data-value="sr"><i class="sr flag"></i>Suriname</div>
    <div class="item" data-value="st"><i class="st flag"></i>Sao Tome</div>
    <div class="item" data-value="sv"><i class="sv flag"></i>El Salvador</div>
    <div class="item" data-value="sy"><i class="sy flag"></i>Syria</div>
    <div class="item" data-value="sz"><i class="sz flag"></i>Swaziland</div>
    <div class="item" data-value="tc"><i class="tc flag"></i>Caicos Islands</div>
    <div class="item" data-value="td"><i class="td flag"></i>Chad</div>
    <div class="item" data-value="tf"><i class="tf flag"></i>French Territories</div>
    <div class="item" data-value="tg"><i class="tg flag"></i>Togo</div>
    <div class="item" data-value="th"><i class="th flag"></i>Thailand</div>
    <div class="item" data-value="tj"><i class="tj flag"></i>Tajikistan</div>
    <div class="item" data-value="tk"><i class="tk flag"></i>Tokelau</div>
    <div class="item" data-value="tl"><i class="tl flag"></i>Timorleste</div>
    <div class="item" data-value="tm"><i class="tm flag"></i>Turkmenistan</div>
    <div class="item" data-value="tn"><i class="tn flag"></i>Tunisia</div>
    <div class="item" data-value="to"><i class="to flag"></i>Tonga</div>
    <div class="item" data-value="tr"><i class="tr flag"></i>Turkey</div>
    <div class="item" data-value="tt"><i class="tt flag"></i>Trinidad</div>
    <div class="item" data-value="tv"><i class="tv flag"></i>Tuvalu</div>
    <div class="item" data-value="tw"><i class="tw flag"></i>Taiwan</div>
    <div class="item" data-value="tz"><i class="tz flag"></i>Tanzania</div>
    <div class="item" data-value="ua"><i class="ua flag"></i>Ukraine</div>
    <div class="item" data-value="ug"><i class="ug flag"></i>Uganda</div>
    <div class="item" data-value="um"><i class="um flag"></i>Us Minor Islands</div>
    <div class="item" data-value="us"><i class="us flag"></i>United States</div>
    <div class="item" data-value="uy"><i class="uy flag"></i>Uruguay</div>
    <div class="item" data-value="uz"><i class="uz flag"></i>Uzbekistan</div>
    <div class="item" data-value="va"><i class="va flag"></i>Vatican City</div>
    <div class="item" data-value="vc"><i class="vc flag"></i>Saint Vincent</div>
    <div class="item" data-value="ve"><i class="ve flag"></i>Venezuela</div>
    <div class="item" data-value="vg"><i class="vg flag"></i>British Virgin Islands</div>
    <div class="item" data-value="vi"><i class="vi flag"></i>Us Virgin Islands</div>
    <div class="item" data-value="vn"><i class="vn flag"></i>Vietnam</div>
    <div class="item" data-value="vu"><i class="vu flag"></i>Vanuatu</div>
    <div class="item" data-value="wf"><i class="wf flag"></i>Wallis and Futuna</div>
    <div class="item" data-value="ws"><i class="ws flag"></i>Samoa</div>
    <div class="item" data-value="ye"><i class="ye flag"></i>Yemen</div>
    <div class="item" data-value="yt"><i class="yt flag"></i>Mayotte</div>
    <div class="item" data-value="za"><i class="za flag"></i>South Africa</div>
    <div class="item" data-value="zm"><i class="zm flag"></i>Zambia</div>
    <div class="item" data-value="zw"><i class="zw flag"></i>Zimbabwe</div>
  </div>
</div>
```

## Settings

### Dropdown Settings
Settings to configure dropdown behavior
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th>Setting</th>
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>action</td>
      <td>activate</td>
      <td>When an item is selected, the default action to take. Can be set to `activate`, `select`, `hide`, `auto`, `combo`, `nothing`.</td>
    </tr>
    <tr>
      <td>minCharacters</td>
      <td>1</td>
      <td>Minimum characters to query for results when creating a searchable dropdown</td>
    </tr>
    <tr>
      <td>apiSettings</td>
      <td>false</td>
      <td>Settings object for [$.api](/behaviors/api.html) call</td>
    </tr>
    <tr>
      <td>fields</td>
      <td>
        <div class="code">
fields: {
  remoteValues : 'results',
  values       : 'values',
  name         : 'name',
  value        : 'value',
  text         : 'text'
}
        </div>
      </td>
      <td>Mapping of standard properties to element attributes.</td>
    </tr>
    <tr>
      <td>saveRemoteData</td>
      <td>true</td>
      <td>When using a remote query, whether to automatically store remote results in a dropdown's cache after the initial search.</td>
    </tr>
    <tr>
      <td>filterRemoteData</td>
      <td>false</td>
      <td>When using a remote query, whether to filter results with current query after the initial search.</td>
    </tr>
    <tr>
      <td>hideOnScroll</td>
      <td>auto</td>
      <td>Whether dropdown should hide on scroll or touchmove, `auto` only hides for dropdowns without `on: 'click'`.<br>
      Set this to `false` to prevent mobile browsers from closing dropdowns when you tap inside input fields.</td>
    </tr>
    <tr>
      <td>forceSelection</td>
      <td>true</td>
      <td>When using search selection, whether the selected result must match a value from the existing menu.</td>
    </tr>
    <tr>
      <td>allowAdditions</td>
      <td>false</td>
      <td>When using a search dropdown, whether a user can add a new item to a previous selection.</td>
    </tr>
    <tr>
      <td>allowCategorySelection</td>
      <td>false</td>
      <td>When using a multi-level menu, whether a user can select a category that has sub-menus.</td>
    </tr>
    <tr>
      <td>maxSelections</td>
      <td>false</td>
      <td>When using a multiple select, the maximum number of selections a user may make.</td>
    </tr>
    <tr>
      <td>useLabels</td>
      <td>true</td>
      <td>When using a multiple select, whether to show currently selected options as labels.</td>
    </tr>
    <tr>
      <td>delimiter</td>
      <td>,</td>
      <td>When using a multiple select, the character to use to delimit values in the hidden input.</td>
    </tr>
    <tr>
      <td>showOnFocus</td>
      <td>true</td>
      <td>Whether dropdown should show menu on focus</td>
    </tr>
    <tr>
      <td>allowReselection</td>
      <td>false</td>
      <td>When set to `true` a user can reselect the currently selected menu item to close a dropdown.</td>
    </tr>
    <tr>
      <td>match</td>
      <td>both</td>
      <td>When using a search dropdown, specifies how search queries should match against menu values. Can be set to `both`, `value`, or `text`.</td>
    </tr>
    <tr>
      <td>placeholder</td>
      <td>auto</td>
      <td>When set to `auto` will use the text content of the first `option` element in a `select` as a placeholder. Can also be set to a string or `false`.</td>
    </tr>
    <tr>
      <td>direction</td>
      <td>auto</td>
      <td>Direction of dropdown. Can be set to `auto`, `upward`, `downward`.</td>
    </tr>
    <tr>
      <td>transition</td>
      <td>
        slide down
      </td>
      <td>Named transition to use when animating menu in and out. Fade and slide down are available without including <a href="/modules/transition.html">ui transitions</a></td>
    </tr>
    <tr>
      <td>duration</td>
      <td>
        200
      </td>
      <td>Duration of animation events</td>
    </tr>
    <tr>
      <td>fullTextSearch</td>
      <td>false</td>
      <td>Whether search should include all content when searching, not just values.</td>
    </tr>
    <tr>
      <td>sortSelect</td>
      <td>false</td>
      <td>Whether to sort values when creating a dropdown from a select element.</td>
    </tr>
    <tr>
      <td>values</td>
      <td>false</td>
      <td>An array of objects that will be used to create a dropdown menu.</td>
    </tr>
  </tbody>
</table>
```

### Callbacks
Callbacks specify a function to occur after a specific behavior.

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <tr>
      <th class="four wide"></th>
      <th class="four wide">Parameters</th>
      <th>Context</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>onChange(value, text, $choice)</td>
      <td>module</td>
      <td>Is called after a value is selected and menu is closed. Receives the name and value of selection.</td>
    </tr>
    <tr>
      <td>onAdd(value, text, $choice)</td>
      <td>module</td>
      <td>Is called after a value is added to a multiple select dropdown. Receives the name and value of selection.</td>
    </tr>
    <tr>
      <td>onRemove(value, text, $choice)</td>
      <td>module</td>
      <td>Is called after a value is removed from a multiple select dropdown. Receives the name and value of selection.</td>
    </tr>
    <tr>
      <td>onLabelCreate(value, text, $label)</td>
      <td>module</td>
      <td>Is called after a label is created in a multiple select dropdown. Receives the value and text and the created label element. Should return a W3C compliant element.</td>
    </tr>
    <tr>
      <td>onLabelRemove(value, text, $label)</td>
      <td>module</td>
      <td>Is called after a label is removed in a multiple select dropdown. Receives the value and text and the removed label element. Should return `false` to prevent default label removal.</td>
    </tr>
    <tr>
      <td>onLabelSelect($labels)</td>
      <td>module</td>
      <td>Is called after a label is selected. Receives the selected labels.</td>
    </tr>
    <tr>
      <td>onNoResults(searchTerm)</td>
      <td>module</td>
      <td>Is called after a search or filter returns no results. Receives the search term that was entered.</td>
    </tr>
    <tr>
      <td>onShow</td>
      <td>module</td>
      <td>Is called before a dropdown is shown. Returning `false` from this callback will cancel the show action.</td>
    </tr>
    <tr>
      <td>onVisible</td>
      <td>module</td>
      <td>Is called after a dropdown is shown.</td>
    </tr>
    <tr>
      <td>onHide</td>
      <td>module</td>
      <td>Is called before a dropdown is hidden. Returning `false` from this callback will cancel the hide action.</td>
    </tr>
    <tr>
      <td>onHidden</td>
      <td>module</td>
      <td>Is called after a dropdown is hidden.</td>
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
      <td>dropdown</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>selector</td>
      <td>
        <div class="code">
selector    : {
  menu        : '.menu',
  item        : '.menu > .item',
  uiSelect    : 'select.ui.dropdown',
  dropdown    : '.ui.dropdown',
  text        : '.text:not(.icon)',
  input       : 'input[type="hidden"]',
  icon        : '.dropdown.icon',
  clear       : '.clear.icon',
  search      : 'input.search',
  sizer       : '.sizer',
  label       : '.ui.label',
  active      : '.active',
  message     : '.message'
}
        </div>
      </td>
      <td>Selectors used to find parts of a module</td>
    </tr>
    <tr>
      <td>metadata</td>
      <td>
        <div class="code">
metadata    : {
  defaultText : 'defaultText',
  defaultValue: 'defaultValue',
  placeholder : 'placeholder',
  text        : 'text',
  value       : 'value'
}
        </div>
      </td>
      <td>HTML5 metadata attributes used internally</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
className   : {
  active      : 'active',
  addition    : 'addition',
  animating   : 'animating',
  disabled    : 'disabled',
  hidden      : 'hidden',
  item        : 'item',
  label       : 'ui label',
  loading     : 'loading',
  menu        : 'menu',
  message     : 'message',
  multiple    : 'multiple',
  placeholder : 'placeholder',
  search      : 'search',
  selected    : 'selected',
  selection   : 'selection',
  upward      : 'upward',
  visible     : 'visible'
}
        </div>
      </td>
      <td>Class names used to determine element state</td>
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
      <td>Dropdown</td>
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
errors: {
  action     : 'You called a dropdown action that was not defined',
  combo      : 'Combo menu items must have both a text and value property to set',
  invalidType: 'Dropdown input type is not supported.',
  noAPICall  : 'The API module is not enabled for this dropdown',
  noResults  : 'There were no results that matched your query',
  noSearch   : 'The search process was unable to calculate and update values correctly.',
  server     : 'There was an error contacting the server',
  show       : 'Errors already visible, cannot show new errors',
  text       : 'The text you specified is not an allowed value',
  values     : 'Values must be contained in a stringified JS array for this type of dropdown',
  method     : 'The method you called is not defined.'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```