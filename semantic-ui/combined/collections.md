## === breadcrumb.md ===

# Breadcrumb

A breadcrumb is used to show hierarchy between content

## Types

#### Breadcrumb
A standard breadcrumb
```html
<div class="ui breadcrumb">
  <a class="section">Home</a>
  <div class="divider"> / </div>
  <a class="section">Store</a>
  <div class="divider"> / </div>
  <div class="active section">T-Shirt</div>
</div>
```
```html
<div class="ui breadcrumb">
  <a class="section">Home</a>
  <i class="right angle icon divider"></i>
  <a class="section">Store</a>
  <i class="right angle icon divider"></i>
  <div class="active section">T-Shirt</div>
</div>
```

## Content

#### Divider
A breadcrumb can contain a divider to show the relationship between sections, this can be formatted as an icon or text.
```html
<div class="ui breadcrumb">
  <a class="section">Home</a>
  <span class="divider">/</span>
  <a class="section">Registration</a>
  <span class="divider">/</span>
  <div class="active section">Personal Information</div>
</div>
```
```html
<div class="ui breadcrumb">
  <a class="section">Home</a>
  <i class="right chevron icon divider"></i>
  <a class="section">Registration</a>
  <i class="right arrow icon divider"></i>
  <div class="active section">Personal Information</div>
</div>
```

#### Section
A breadcrumb can contain sections that can either be formatted as a link or text
```html
<div class="ui breadcrumb">
  <div class="section">Home</div>
  <div class="divider"> / </div>
  <div class="active section">Search</div>
</div>
```

#### Link
A section may be linkable or contain a link
```html
<div class="ui breadcrumb">
  <a class="section">Home</a>
  <div class="divider"> / </div>
  <div class="active section">Search for: <a href="#">paper towels</a></div>
</div>
```

## States

#### Active
A section can be active
```html
<div class="ui breadcrumb">
  <a class="section">Products</a>
  <div class="divider"> / </div>
  <div class="active section">Paper Towels</div>
</div>
```

## Variations

#### Size
A breadcrumb can vary in size
```html
<div class="ui mini breadcrumb">
  <a class="section">Home</a>
  <i class="right chevron icon divider"></i>
  <a class="section">Registration</a>
  <i class="right chevron icon divider"></i>
  <div class="active section">Personal Information</div>
</div>
```
```html
<div class="ui tiny breadcrumb">
  <a class="section">Home</a>
  <i class="right chevron icon divider"></i>
  <a class="section">Registration</a>
  <i class="right chevron icon divider"></i>
  <div class="active section">Personal Information</div>
</div>
```
```html
<div class="ui small breadcrumb">
  <a class="section">Home</a>
  <i class="right chevron icon divider"></i>
  <a class="section">Registration</a>
  <i class="right chevron icon divider"></i>
  <div class="active section">Personal Information</div>
</div>
```
```html
<div class="ui large breadcrumb">
  <a class="section">Home</a>
  <i class="right chevron icon divider"></i>
  <a class="section">Registration</a>
  <i class="right chevron icon divider"></i>
  <div class="active section">Personal Information</div>
</div>
```
```html
<div class="ui big breadcrumb">
  <a class="section">Home</a>
  <i class="right chevron icon divider"></i>
  <a class="section">Registration</a>
  <i class="right chevron icon divider"></i>
  <div class="active section">Personal Information</div>
</div>
```
```html
<div class="ui huge breadcrumb">
  <a class="section">Home</a>
  <i class="right chevron icon divider"></i>
  <a class="section">Registration</a>
  <i class="right chevron icon divider"></i>
  <div class="active section">Personal Information</div>
</div>
```
```html
<div class="ui massive breadcrumb">
  <a class="section">Home</a>
  <i class="right chevron icon divider"></i>
  <a class="section">Registration</a>
  <i class="right chevron icon divider"></i>
  <div class="active section">Personal Information</div>
</div>
```


## === form.md ===

# Form

A form displays a set of related user input fields in a structured way

## Types

#### Form
A form
> If you are looking for validation you should check out form behaviors.
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
  <div class="field">
    <div class="ui checkbox">
      <input type="checkbox" />
      <label>I agree to the Terms and Conditions</label>
    </div>
  </div>
  <button class="ui button" type="submit">Submit</button>
</form>
```
```html
<form class="ui form">
  <h4 class="ui dividing header">Shipping Information</h4>
  <div class="field">
    <label>Name</label>
    <div class="two fields">
      <div class="field">
        <input type="text" name="shipping[first-name]" placeholder="First Name">
      </div>
      <div class="field">
        <input type="text" name="shipping[last-name]" placeholder="Last Name">
      </div>
    </div>
  </div>
  <div class="field">
    <label>Billing Address</label>
    <div class="fields">
      <div class="twelve wide field">
        <input type="text" name="shipping[address]" placeholder="Street Address">
      </div>
      <div class="four wide field">
        <input type="text" name="shipping[address-2]" placeholder="Apt #">
      </div>
    </div>
  </div>
  <div class="two fields">
    <div class="field">
      <label>State</label>
      <select class="ui fluid dropdown">
        <%- @partial('examples/single/state-options') %>
      </select>
    </div>
    <div class="field">
      <label>Country</label>
      <div class="ui fluid search selection dropdown">
        <input type="hidden" name="country">
        <i class="dropdown icon"></i>
        <div class="default text">Select Country</div>
        <%- @partial('examples/single/flag-menu') %>
      </div>
    </div>
  </div>
  <h4 class="ui dividing header">Billing Information</h4>
  <div class="field">
    <label>Card Type</label>
    <div class="ui selection dropdown">
      <input type="hidden" name="card[type]">
      <div class="default text">Type</div>
      <i class="dropdown icon"></i>
      <div class="menu">
        <div class="item" data-value="visa">
          <i class="visa icon"></i>
          Visa
        </div>
        <div class="item" data-value="amex">
          <i class="amex icon"></i>
          American Express
        </div>
        <div class="item" data-value="discover">
          <i class="discover icon"></i>
          Discover
        </div>
      </div>
    </div>
  </div>
  <div class="fields">
    <div class="seven wide field">
      <label>Card Number</label>
      <input type="text" name="card[number]" maxlength="16" placeholder="Card #">
    </div>
    <div class="three wide field">
      <label>CVC</label>
      <input type="text" name="card[cvc]" maxlength="3" placeholder="CVC">
    </div>
    <div class="six wide field">
      <label>Expiration</label>
      <div class="two fields">
        <div class="field">
          <select class="ui fluid search dropdown" name="card[expire-month]">
            <option value="">Month</option>
            <option value="1">January</option>
            <option value="2">February</option>
            <option value="3">March</option>
            <option value="4">April</option>
            <option value="5">May</option>
            <option value="6">June</option>
            <option value="7">July</option>
            <option value="8">August</option>
            <option value="9">September</option>
            <option value="10">October</option>
            <option value="11">November</option>
            <option value="12">December</option>
          </select>
        </div>
        <div class="field">
          <input type="text" name="card[expire-year]" maxlength="4" placeholder="Year">
        </div>
      </div>
    </div>
  </div>

  <h4 class="ui dividing header">Receipt</h4>

  <div class="field">
    <label>Send Receipt To:</label>
    <div class="ui fluid multiple search selection dropdown">
      <input type="hidden" name="receipt">
      <i class="dropdown icon"></i>
      <div class="default text">Saved Contacts</div>
      <div class="menu">
        <div class="item" data-value="jenny" data-text="Jenny">
          <img class="ui mini avatar image" src="/images/avatar/small/jenny.jpg">
          Jenny Hess
        </div>
        <div class="item" data-value="elliot" data-text="Elliot">
          <img class="ui mini avatar image" src="/images/avatar/small/elliot.jpg">
          Elliot Fu
        </div>
        <div class="item" data-value="stevie" data-text="Stevie">
          <img class="ui mini avatar image" src="/images/avatar/small/stevie.jpg">
          Stevie Feliciano
        </div>
        <div class="item" data-value="christian" data-text="Christian">
          <img class="ui mini avatar image" src="/images/avatar/small/christian.jpg">
          Christian
        </div>
        <div class="item" data-value="matt" data-text="Matt">
          <img class="ui mini avatar image" src="/images/avatar/small/matt.jpg">
          Matt
        </div>
        <div class="item" data-value="justen" data-text="Justen">
          <img class="ui mini avatar image" src="/images/avatar/small/justen.jpg">
          Justen Kitsune
        </div>
      </div>
    </div>
  </div>

  <div class="ui segment">
    <div class="field">
      <div class="ui toggle checkbox">
        <input type="checkbox" name="gift">
        <label>Do not include a receipt in the package</label>
      </div>
    </div>
  </div>
  <div class="ui button" tabindex="0">Submit Order</div>
</form>
```

## Content

#### Field
A field is a form element containing a label and an input
```html
<div class="ui form">
  <div class="field">
    <label>User Input</label>
    <input type="text">
  </div>
</div>
```

#### Fields
A set of fields can appear grouped together
> Field groups automatically receive responsive styling, swapping to one field per row on mobile devices.
```html
<div class="ui form">
  <div class="fields">
    <div class="field">
      <label>First name</label>
      <input type="text" placeholder="First Name">
    </div>
    <div class="field">
      <label>Middle name</label>
      <input type="text" placeholder="Middle Name">
    </div>
    <div class="field">
      <label>Last name</label>
      <input type="text" placeholder="Last Name">
    </div>
  </div>
</div>
```
```html
<div class="ui form">
  <div class="three fields">
    <div class="field">
      <label>First name</label>
      <input type="text" placeholder="First Name">
    </div>
    <div class="field">
      <label>Middle name</label>
      <input type="text" placeholder="Middle Name">
    </div>
    <div class="field">
      <label>Last name</label>
      <input type="text" placeholder="Last Name">
    </div>
  </div>
</div>
```
```html
<div class="ui form">
  <div class="inline fields">
    <div class="eight wide field">
      <label>Name</label>
      <input type="text" placeholder="First Name">
    </div>
    <div class="three wide field">
      <input type="text" placeholder="Middle Name">
    </div>
    <div class="five wide field">
      <input type="text" placeholder="Last Name">
    </div>
  </div>
</div>
```

#### Text Area
A textarea can be used to allow for extended user input.
> To specify an approximate text area size use the `rows` attribute.
```html
<div class="ui form">
  <div class="field">
    <label>Text</label>
    <textarea></textarea>
  </div>
  <div class="field">
    <label>Short Text</label>
    <textarea rows="2"></textarea>
  </div>
</div>
```

#### Checkbox
A form can contain a checkbox
> UI checkbox are special, styled versions of standard HTML checkboxes.
```javascript
$('.ui.checkbox')
  .checkbox()
;
```
```html
<div class="ui form">
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" />
      <label>Checkbox</label>
    </div>
  </div>
  <div class="inline field">
    <div class="ui slider checkbox">
      <input type="checkbox" />
      <label>Slider</label>
    </div>
    <label></label>
  </div>
  <div class="inline field">
    <div class="ui toggle checkbox">
      <input type="checkbox" />
      <label>Toggle</label>
    </div>
  </div>
</div>
```

#### Radio Checkbox
A form can include a radio checkbox
```javascript
$('.ui.radio.checkbox')
  .checkbox()
;
```
```html
<div class="ui form">
  <div class="inline fields">
    <label for="fruit">Select your favorite fruit:</label>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="fruit" checked />
        <label>Apples</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="fruit" />
        <label>Oranges</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="fruit" />
        <label>Pears</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="fruit" />
        <label>Grapefruit</label>
      </div>
    </div>
  </div>
  <div class="grouped fields">
    <label for="fruit">Select your second favorite fruit:</label>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="fruit" checked />
        <label>Apples</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="fruit" />
        <label>Oranges</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="fruit" />
        <label>Pears</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="fruit" />
        <label>Grapefruit</label>
      </div>
    </div>
  </div>
</div>
```

#### Dropdown
A form can contain a dropdown
> Dropdown will automatically convert `select` elements initialized as dropdowns. For more details check out the dropdown docs
```javascript
$('select.dropdown')
  .dropdown()
;
```
```html
<div class="ui form">
  <div class="field">
      <label>Gender</label>
      <div class="ui selection dropdown">
          <input type="hidden" name="gender">
          <i class="dropdown icon"></i>
          <div class="default text">Gender</div>
          <div class="menu">
              <div class="item" data-value="1">Male</div>
              <div class="item" data-value="0">Female</div>
          </div>
      </div>
  </div>
</div>
```
```html
<div class="ui form">
  <div class="field">
    <label>Country</label>
    <select class="ui search dropdown">
      <option value="">Select Country</option>
      <option value="AF">Afghanistan</option>
      <option value="AX">Åland Islands</option>
      <option value="AL">Albania</option>
      <option value="DZ">Algeria</option>
      <option value="AS">American Samoa</option>
      <option value="AD">Andorra</option>
      <option value="AO">Angola</option>
      <option value="AI">Anguilla</option>
      <option value="AQ">Antarctica</option>
      <option value="AG">Antigua and Barbuda</option>
      <option value="AR">Argentina</option>
      <option value="AM">Armenia</option>
      <option value="AW">Aruba</option>
      <option value="AU">Australia</option>
      <option value="AT">Austria</option>
      <option value="AZ">Azerbaijan</option>
      <option value="BS">Bahamas</option>
      <option value="BH">Bahrain</option>
      <option value="BD">Bangladesh</option>
      <option value="BB">Barbados</option>
      <option value="BY">Belarus</option>
      <option value="BE">Belgium</option>
      <option value="BZ">Belize</option>
      <option value="BJ">Benin</option>
      <option value="BM">Bermuda</option>
      <option value="BT">Bhutan</option>
      <option value="BO">Bolivia, Plurinational State of</option>
      <option value="BQ">Bonaire, Sint Eustatius and Saba</option>
      <option value="BA">Bosnia and Herzegovina</option>
      <option value="BW">Botswana</option>
      <option value="BV">Bouvet Island</option>
      <option value="BR">Brazil</option>
      <option value="IO">British Indian Ocean Territory</option>
      <option value="BN">Brunei Darussalam</option>
      <option value="BG">Bulgaria</option>
      <option value="BF">Burkina Faso</option>
      <option value="BI">Burundi</option>
      <option value="KH">Cambodia</option>
      <option value="CM">Cameroon</option>
      <option value="CA">Canada</option>
      <option value="CV">Cape Verde</option>
      <option value="KY">Cayman Islands</option>
      <option value="CF">Central African Republic</option>
      <option value="TD">Chad</option>
      <option value="CL">Chile</option>
      <option value="CN">China</option>
      <option value="CX">Christmas Island</option>
      <option value="CC">Cocos (Keeling) Islands</option>
      <option value="CO">Colombia</option>
      <option value="KM">Comoros</option>
      <option value="CG">Congo</option>
      <option value="CD">Congo, the Democratic Republic of the</option>
      <option value="CK">Cook Islands</option>
      <option value="CR">Costa Rica</option>
      <option value="CI">Côte d'Ivoire</option>
      <option value="HR">Croatia</option>
      <option value="CU">Cuba</option>
      <option value="CW">Curaçao</option>
      <option value="CY">Cyprus</option>
      <option value="CZ">Czech Republic</option>
      <option value="DK">Denmark</option>
      <option value="DJ">Djibouti</option>
      <option value="DM">Dominica</option>
      <option value="DO">Dominican Republic</option>
      <option value="EC">Ecuador</option>
      <option value="EG">Egypt</option>
      <option value="SV">El Salvador</option>
      <option value="GQ">Equatorial Guinea</option>
      <option value="ER">Eritrea</option>
      <option value="EE">Estonia</option>
      <option value="ET">Ethiopia</option>
      <option value="FK">Falkland Islands (Malvinas)</option>
      <option value="FO">Faroe Islands</option>
      <option value="FJ">Fiji</option>
      <option value="FI">Finland</option>
      <option value="FR">France</option>
      <option value="GF">French Guiana</option>
      <option value="PF">French Polynesia</option>
      <option value="TF">French Southern Territories</option>
      <option value="GA">Gabon</option>
      <option value="GM">Gambia</option>
      <option value="GE">Georgia</option>
      <option value="DE">Germany</option>
      <option value="GH">Ghana</option>
      <option value="GI">Gibraltar</option>
      <option value="GR">Greece</option>
      <option value="GL">Greenland</option>
      <option value="GD">Grenada</option>
      <option value="GP">Guadeloupe</option>
      <option value="GU">Guam</option>
      <option value="GT">Guatemala</option>
      <option value="GG">Guernsey</option>
      <option value="GN">Guinea</option>
      <option value="GW">Guinea-Bissau</option>
      <option value="GY">Guyana</option>
      <option value="HT">Haiti</option>
      <option value="HM">Heard Island and McDonald Islands</option>
      <option value="VA">Holy See (Vatican City State)</option>
      <option value="HN">Honduras</option>
      <option value="HK">Hong Kong</option>
      <option value="HU">Hungary</option>
      <option value="IS">Iceland</option>
      <option value="IN">India</option>
      <option value="ID">Indonesia</option>
      <option value="IR">Iran, Islamic Republic of</option>
      <option value="IQ">Iraq</option>
      <option value="IE">Ireland</option>
      <option value="IM">Isle of Man</option>
      <option value="IL">Israel</option>
      <option value="IT">Italy</option>
      <option value="JM">Jamaica</option>
      <option value="JP">Japan</option>
      <option value="JE">Jersey</option>
      <option value="JO">Jordan</option>
      <option value="KZ">Kazakhstan</option>
      <option value="KE">Kenya</option>
      <option value="KI">Kiribati</option>
      <option value="KP">Korea, Democratic People's Republic of</option>
      <option value="KR">Korea, Republic of</option>
      <option value="KW">Kuwait</option>
      <option value="KG">Kyrgyzstan</option>
      <option value="LA">Lao People's Democratic Republic</option>
      <option value="LV">Latvia</option>
      <option value="LB">Lebanon</option>
      <option value="LS">Lesotho</option>
      <option value="LR">Liberia</option>
      <option value="LY">Libya</option>
      <option value="LI">Liechtenstein</option>
      <option value="LT">Lithuania</option>
      <option value="LU">Luxembourg</option>
      <option value="MO">Macao</option>
      <option value="MK">Macedonia, the former Yugoslav Republic of</option>
      <option value="MG">Madagascar</option>
      <option value="MW">Malawi</option>
      <option value="MY">Malaysia</option>
      <option value="MV">Maldives</option>
      <option value="ML">Mali</option>
      <option value="MT">Malta</option>
      <option value="MH">Marshall Islands</option>
      <option value="MQ">Martinique</option>
      <option value="MR">Mauritania</option>
      <option value="MU">Mauritius</option>
      <option value="YT">Mayotte</option>
      <option value="MX">Mexico</option>
      <option value="FM">Micronesia, Federated States of</option>
      <option value="MD">Moldova, Republic of</option>
      <option value="MC">Monaco</option>
      <option value="MN">Mongolia</option>
      <option value="ME">Montenegro</option>
      <option value="MS">Montserrat</option>
      <option value="MA">Morocco</option>
      <option value="MZ">Mozambique</option>
      <option value="MM">Myanmar</option>
      <option value="NA">Namibia</option>
      <option value="NR">Nauru</option>
      <option value="NP">Nepal</option>
      <option value="NL">Netherlands</option>
      <option value="NC">New Caledonia</option>
      <option value="NZ">New Zealand</option>
      <option value="NI">Nicaragua</option>
      <option value="NE">Niger</option>
      <option value="NG">Nigeria</option>
      <option value="NU">Niue</option>
      <option value="NF">Norfolk Island</option>
      <option value="MP">Northern Mariana Islands</option>
      <option value="NO">Norway</option>
      <option value="OM">Oman</option>
      <option value="PK">Pakistan</option>
      <option value="PW">Palau</option>
      <option value="PS">Palestinian Territory, Occupied</option>
      <option value="PA">Panama</option>
      <option value="PG">Papua New Guinea</option>
      <option value="PY">Paraguay</option>
      <option value_="PE">Peru</option>
      <option value="PH">Philippines</option>
      <option value="PN">Pitcairn</option>
      <option value="PL">Poland</option>
      <option value="PT">Portugal</option>
      <option value="PR">Puerto Rico</option>
      <option value="QA">Qatar</option>
      <option value="RE">Réunion</option>
      <option value="RO">Romania</option>
      <option value="RU">Russian Federation</option>
      <option value="RW">Rwanda</option>
      <option value="BL">Saint Barthélemy</option>
      <option value="SH">Saint Helena, Ascension and Tristan da Cunha</option>
      <option value="KN">Saint Kitts and Nevis</option>
      <option value="LC">Saint Lucia</option>
      <option value="MF">Saint Martin (French part)</option>
      <option value="PM">Saint Pierre and Miquelon</option>
      <option value="VC">Saint Vincent and the Grenadines</option>
      <option value="WS">Samoa</option>
      <option value="SM">San Marino</option>
      <option value="ST">Sao Tome and Principe</option>
      <option value="SA">Saudi Arabia</option>
      <option value="SN">Senegal</option>
      <option value="RS">Serbia</option>
      <option value="SC">Seychelles</option>
      <option value="SL">Sierra Leone</option>
      <option value="SG">Singapore</option>
      <option value="SX">Sint Maarten (Dutch part)</option>
      <option value="SK">Slovakia</option>
      <option value="SI">Slovenia</option>
      <option value="SB">Solomon Islands</option>
      <option value="SO">Somalia</option>
      <option value="ZA">South Africa</option>
      <option value="GS">South Georgia and the South Sandwich Islands</option>
      <option value="SS">South Sudan</option>
      <option value="ES">Spain</option>
      <option value="LK">Sri Lanka</option>
      <option value="SD">Sudan</option>
      <option value="SR">Suriname</option>
      <option value="SJ">Svalbard and Jan Mayen</option>
      <option value="SZ">Swaziland</option>
      <option value="SE">Sweden</option>
      <option value="CH">Switzerland</option>
      <option value="SY">Syrian Arab Republic</option>
      <option value="TW">Taiwan, Province of China</option>
      <option value="TJ">Tajikistan</option>
      <option value="TZ">Tanzania, United Republic of</option>
      <option value="TH">Thailand</option>
      <option value="TL">Timor-Leste</option>
      <option value="TG">Togo</option>
      <option value="TK">Tokelau</option>
      <option value="TO">Tonga</option>
      <option value="TT">Trinidad and Tobago</option>
      <option value="TN">Tunisia</option>
      <option value="TR">Turkey</option>
      <option value="TM">Turkmenistan</option>
      <option value="TC">Turks and Caicos Islands</option>
      <option value="TV">Tuvalu</option>
      <option value="UG">Uganda</option>
      <option value="UA">Ukraine</option>
      <option value="AE">United Arab Emirates</option>
      <option value="GB">United Kingdom</option>
      <option value="US">United States</option>
      <option value="UM">United States Minor Outlying Islands</option>
      <option value="UY">Uruguay</option>
      <option value="UZ">Uzbekistan</option>
      <option value="VU">Vanuatu</option>
      <option value="VE">Venezuela, Bolivarian Republic of</option>
      <option value="VN">Viet Nam</option>
      <option value="VG">Virgin Islands, British</option>
      <option value="VI">Virgin Islands, U.S.</option>
      <option value="WF">Wallis and Futuna</option>
      <option value="EH">Western Sahara</option>
      <option value="YE">Yemen</option>
      <option value="ZM">Zambia</option>
      <option value="ZW">Zimbabwe</option>
    </select>
  </div>
</div>
```

#### Multiple Select
A multiple select is used to include several choices with one form field
```html
<div class="ui form">
  <div class="field">
    <label>Country</label>
    <select multiple class="ui dropdown">
      <option value="">Select Country</option>
      <option value="AF">Afghanistan</option>
      <option value="AX">Åland Islands</option>
      <option value="AL">Albania</option>
      <option value="DZ">Algeria</option>
      <option value="AS">American Samoa</option>
      <option value="AD">Andorra</option>
      <option value="AO">Angola</option>
      <option value="AI">Anguilla</option>
      <option value="AQ">Antarctica</option>
      <option value="AG">Antigua and Barbuda</option>
      <option value="AR">Argentina</option>
      <option value="AM">Armenia</option>
      <option value="AW">Aruba</option>
      <option value="AU">Australia</option>
      <option value="AT">Austria</option>
      <option value="AZ">Azerbaijan</option>
      <option value="BS">Bahamas</option>
      <option value="BH">Bahrain</option>
      <option value="BD">Bangladesh</option>
      <option value="BB">Barbados</option>
      <option value="BY">Belarus</option>
      <option value="BE">Belgium</option>
      <option value="BZ">Belize</option>
      <option value="BJ">Benin</option>
      <option value="BM">Bermuda</option>
      <option value="BT">Bhutan</option>
      <option value="BO">Bolivia, Plurinational State of</option>
      <option value="BQ">Bonaire, Sint Eustatius and Saba</option>
      <option value="BA">Bosnia and Herzegovina</option>
      <option value="BW">Botswana</option>
      <option value="BV">Bouvet Island</option>
      <option value="BR">Brazil</option>
      <option value="IO">British Indian Ocean Territory</option>
      <option value="BN">Brunei Darussalam</option>
      <option value="BG">Bulgaria</option>
      <option value="BF">Burkina Faso</option>
      <option value="BI">Burundi</option>
      <option value="KH">Cambodia</option>
      <option value="CM">Cameroon</option>
      <option value="CA">Canada</option>
      <option value="CV">Cape Verde</option>
      <option value="KY">Cayman Islands</option>
      <option value="CF">Central African Republic</option>
      <option value="TD">Chad</option>
      <option value="CL">Chile</option>
      <option value="CN">China</option>
      <option value="CX">Christmas Island</option>
      <option value="CC">Cocos (Keeling) Islands</option>
      <option value="CO">Colombia</option>
      <option value="KM">Comoros</option>
      <option value="CG">Congo</option>
      <option value="CD">Congo, the Democratic Republic of the</option>
      <option value="CK">Cook Islands</option>
      <option value="CR">Costa Rica</option>
      <option value="CI">Côte d'Ivoire</option>
      <option value="HR">Croatia</option>
      <option value="CU">Cuba</option>
      <option value="CW">Curaçao</option>
      <option value="CY">Cyprus</option>
      <option value="CZ">Czech Republic</option>
      <option value="DK">Denmark</option>
      <option value="DJ">Djibouti</option>
      <option value="DM">Dominica</option>
      <option value="DO">Dominican Republic</option>
      <option value="EC">Ecuador</option>
      <option value="EG">Egypt</option>
      <option value="SV">El Salvador</option>
      <option value="GQ">Equatorial Guinea</option>
      <option value="ER">Eritrea</option>
      <option value="EE">Estonia</option>
      <option value="ET">Ethiopia</option>
      <option value="FK">Falkland Islands (Malvinas)</option>
      <option value="FO">Faroe Islands</option>
      <option value="FJ">Fiji</option>
      <option value="FI">Finland</option>
      <option value="FR">France</option>
      <option value="GF">French Guiana</option>
      <option value="PF">French Polynesia</option>
      <option value="TF">French Southern Territories</option>
      <option value="GA">Gabon</option>
      <option value="GM">Gambia</option>
      <option value="GE">Georgia</option>
      <option value="DE">Germany</option>
      <option value="GH">Ghana</option>
      <option value="GI">Gibraltar</option>
      <option value="GR">Greece</option>
      <option value="GL">Greenland</option>
      <option value="GD">Grenada</option>
      <option value="GP">Guadeloupe</option>
      <option value="GU">Guam</option>
      <option value="GT">Guatemala</option>
      <option value="GG">Guernsey</option>
      <option value="GN">Guinea</option>
      <option value="GW">Guinea-Bissau</option>
      <option value="GY">Guyana</option>
      <option value="HT">Haiti</option>
      <option value="HM">Heard Island and McDonald Islands</option>
      <option value="VA">Holy See (Vatican City State)</option>
      <option value="HN">Honduras</option>
      <option value="HK">Hong Kong</option>
      <option value="HU">Hungary</option>
      <option value="IS">Iceland</option>
      <option value="IN">India</option>
      <option value="ID">Indonesia</option>
      <option value="IR">Iran, Islamic Republic of</option>
      <option value="IQ">Iraq</option>
      <option value="IE">Ireland</option>
      <option value="IM">Isle of Man</option>
      <option value="IL">Israel</option>
      <option value="IT">Italy</option>
      <option value="JM">Jamaica</option>
      <option value="JP">Japan</option>
      <option value="JE">Jersey</option>
      <option value="JO">Jordan</option>
      <option value="KZ">Kazakhstan</option>
      <option value="KE">Kenya</option>
      <option value="KI">Kiribati</option>
      <option value="KP">Korea, Democratic People's Republic of</option>
      <option value="KR">Korea, Republic of</option>
      <option value="KW">Kuwait</option>
      <option value="KG">Kyrgyzstan</option>
      <option value="LA">Lao People's Democratic Republic</option>
      <option value="LV">Latvia</option>
      <option value="LB">Lebanon</option>
      <option value="LS">Lesotho</option>
      <option value="LR">Liberia</option>
      <option value="LY">Libya</option>
      <option value="LI">Liechtenstein</option>
      <option value="LT">Lithuania</option>
      <option value="LU">Luxembourg</option>
      <option value="MO">Macao</option>
      <option value="MK">Macedonia, the former Yugoslav Republic of</option>
      <option value="MG">Madagascar</option>
      <option value="MW">Malawi</option>
      <option value="MY">Malaysia</option>
      <option value="MV">Maldives</option>
      <option value="ML">Mali</option>
      <option value="MT">Malta</option>
      <option value="MH">Marshall Islands</option>
      <option value="MQ">Martinique</option>
      <option value="MR">Mauritania</option>
      <option value="MU">Mauritius</option>
      <option value="YT">Mayotte</option>
      <option value="MX">Mexico</option>
      <option value="FM">Micronesia, Federated States of</option>
      <option value="MD">Moldova, Republic of</option>
      <option value="MC">Monaco</option>
      <option value="MN">Mongolia</option>
      <option value="ME">Montenegro</option>
      <option value="MS">Montserrat</option>
      <option value="MA">Morocco</option>
      <option value="MZ">Mozambique</option>
      <option value="MM">Myanmar</option>
      <option value="NA">Namibia</option>
      <option value="NR">Nauru</option>
      <option value="NP">Nepal</option>
      <option value="NL">Netherlands</option>
      <option value="NC">New Caledonia</option>
      <option value="NZ">New Zealand</option>
      <option value="NI">Nicaragua</option>
      <option value="NE">Niger</option>
      <option value="NG">Nigeria</option>
      <option value="NU">Niue</option>
      <option value="NF">Norfolk Island</option>
      <option value="MP">Northern Mariana Islands</option>
      <option value="NO">Norway</option>
      <option value="OM">Oman</option>
      <option value="PK">Pakistan</option>
      <option value="PW">Palau</option>
      <option value="PS">Palestinian Territory, Occupied</option>
      <option value="PA">Panama</option>
      <option value="PG">Papua New Guinea</option>
      <option value="PY">Paraguay</option>
      <option value="PE">Peru</option>
      <option value="PH">Philippines</option>
      <option value="PN">Pitcairn</option>
      <option value="PL">Poland</option>
      <option value="PT">Portugal</option>
      <option value="PR">Puerto Rico</option>
      <option value="QA">Qatar</option>
      <option value="RE">Réunion</option>
      <option value="RO">Romania</option>
      <option value="RU">Russian Federation</option>
      <option value="RW">Rwanda</option>
      <option value="BL">Saint Barthélemy</option>
      <option value="SH">Saint Helena, Ascension and Tristan da Cunha</option>
      <option value="KN">Saint Kitts and Nevis</option>
      <option value="LC">Saint Lucia</option>
      <option value="MF">Saint Martin (French part)</option>
      <option value="PM">Saint Pierre and Miquelon</option>
      <option value="VC">Saint Vincent and the Grenadines</option>
      <option value="WS">Samoa</option>
      <option value="SM">San Marino</option>
      <option value="ST">Sao Tome and Principe</option>
      <option value="SA">Saudi Arabia</option>
      <option value="SN">Senegal</option>
      <option value="RS">Serbia</option>
      <option value="SC">Seychelles</option>
      <option value="SL">Sierra Leone</option>
      <option value="SG">Singapore</option>
      <option value="SX">Sint Maarten (Dutch part)</option>
      <option value="SK">Slovakia</option>
      <option value="SI">Slovenia</option>
      <option value="SB">Solomon Islands</option>
      <option value="SO">Somalia</option>
      <option value="ZA">South Africa</option>
      <option value="GS">South Georgia and the South Sandwich Islands</option>
      <option value="SS">South Sudan</option>
      <option value="ES">Spain</option>
      <option value="LK">Sri Lanka</option>
      <option value="SD">Sudan</option>
      <option value="SR">Suriname</option>
      <option value="SJ">Svalbard and Jan Mayen</option>
      <option value="SZ">Swaziland</option>
      <option value="SE">Sweden</option>
      <option value="CH">Switzerland</option>
      <option value="SY">Syrian Arab Republic</option>
      <option value="TW">Taiwan, Province of China</option>
      <option value="TJ">Tajikistan</option>
      <option value="TZ">Tanzania, United Republic of</option>
      <option value="TH">Thailand</option>
      <option value="TL">Timor-Leste</option>
      <option value="TG">Togo</option>
      <option value="TK">Tokelau</option>
      <option value="TO">Tonga</option>
      <option value="TT">Trinidad and Tobago</option>
      <option value="TN">Tunisia</option>
      <option value="TR">Turkey</option>
      <option value="TM">Turkmenistan</option>
      <option value="TC">Turks and Caicos Islands</option>
      <option value="TV">Tuvalu</option>
      <option value="UG">Uganda</option>
      <option value="UA">Ukraine</option>
      <option value="AE">United Arab Emirates</option>
      <option value="GB">United Kingdom</option>
      <option value="US">United States</option>
      <option value="UM">United States Minor Outlying Islands</option>
      <option value="UY">Uruguay</option>
      <option value="UZ">Uzbekistan</option>
      <option value="VU">Vanuatu</option>
      <option value="VE">Venezuela, Bolivarian Republic of</option>
      <option value="VN">Viet Nam</option>
      <option value="VG">Virgin Islands, British</option>
      <option value="VI">Virgin Islands, U.S.</option>
      <option value="WF">Wallis and Futuna</option>
      <option value="EH">Western Sahara</option>
      <option value="YE">Yemen</option>
      <option value="ZM">Zambia</option>
      <option value="ZW">Zimbabwe</option>
    </select>
  </div>
</div>
```

#### HTML Select
If Javascript or ui dropdown are not a viable option, forms also can provide basic styling for select elements
```html
<div class="ui form">
  <div class="field">
    <select>
      <option value="">Gender</option>
      <option value="1">Male</option>
      <option value="0">Female</option>
    </select>
  </div>
</div>
```

#### Message
A form can contain a message
> Any `info`, `error`, `success`, or `warning` message blocks found inside a form are hidden by default.
```html
<div class="ui form">
  <div class="ui message">
    <div class="header">We had some issues</div>
    <ul class="list">
      <li>Please enter your first name</li>
      <li>Please enter your last name</li>
    </ul>
  </div>
</div>
```

## States

#### Loading
If a form is in loading state, it will automatically show a loading indicator.
```html
<div class="ui loading form">
  <div class="field">
    <label>E-mail</label>
    <input type="email" placeholder="joe@schmoe.com">
  </div>
  <div class="ui submit button">Submit</div>
</div>
```

#### Success
If a form is in an success state, it will automatically show any success message blocks.
```html
<div class="ui form success">
  <div class="field">
    <label>E-mail</label>
    <input type="email" placeholder="joe@schmoe.com">
  </div>
  <div class="ui success message">
    <div class="header">Form Completed</div>
    <p>You're all signed up for the newsletter.</p>
  </div>
  <div class="ui submit button">Submit</div>
</div>
```

#### Error
If a form is in an error state, it will automatically show any error message blocks.
```html
<div class="ui form error">
  <div class="field">
    <label>E-mail</label>
    <input type="email" placeholder="joe@schmoe.com">
  </div>
  <div class="ui error message">
    <div class="header">Action Forbidden</div>
    <p>You can only sign up for an account once with a given e-mail address.</p>
  </div>
  <div class="ui submit button">Submit</div>
</div>
```

#### Warning
If a form is in warning state, it will automatically show any warning message block.
```html
<div class="ui form warning">
  <div class="field">
    <label>E-mail</label>
    <input type="email" placeholder="joe@schmoe.com">
  </div>
  <div class="ui warning message">
    <div class="header">Could you check something!</div>
    <ul class="list">
      <li>That e-mail has been subscribed, but you have not yet clicked the verification link in your e-mail.</li>
    </ul>
  </div>
  <div class="ui submit button">Submit</div>
</div>
```

#### Field Error
Individual fields may display an error state
```html
<div class="ui form">
  <div class="two fields">
    <div class="field error">
      <label>First Name</label>
      <input placeholder="First Name" type="text">
    </div>
    <div class="field">
      <label>Last Name</label>
      <input placeholder="Last Name" type="text">
    </div>
  </div>
  <div class="field error">
    <label>Gender</label>
    <div class="ui selection dropdown">
      <div class="default text">Select</div>
      <i class="dropdown icon"></i>
      <input type="hidden" name="gender">
      <div class="menu">
        <div class="item" data-value="male">Male</div>
        <div class="item" data-value="female">Female</div>
      </div>
    </div>
  </div>
  <div class="inline field error">
    <div class="ui checkbox">
      <input type="checkbox" />
      <label>I agree to the Terms and Conditions</label>
    </div>
  </div>
</div>
```

#### Disabled Field
Individual fields may be disabled
```html
<div class="ui form">
  <div class="two fields">
    <div class="disabled field">
      <label>First Name</label>
      <input placeholder="Read Only" type="text" disabled tabindex="-1">
    </div>
    <div class="disabled field">
      <label>Last Name</label>
      <input placeholder="Disabled" type="text" disabled tabindex="-1">
    </div>
  </div>
</div>
```

#### Read-Only Field
Individual fields may be read only
```html
<div class="ui form">
  <div class="two fields">
    <div class="field">
      <label>First Name</label>
      <input placeholder="Read Only" readonly type="text">
    </div>
    <div class="field">
      <label>Last Name</label>
      <input placeholder="Read Only" readonly type="text">
    </div>
  </div>
</div>
```

## Form Variations

#### Size
A form can vary in size
```html
<div class="ui mini form">
  <div class="two fields">
    <div class="field">
      <label>First Name</label>
      <input placeholder="First Name" type="text">
    </div>
    <div class="field">
      <label>Last Name</label>
      <input placeholder="Last Name" type="text">
    </div>
  </div>
  <div class="ui submit button">Submit</div>
</div>
```
```html
<div class="ui tiny form">
  <div class="two fields">
    <div class="field">
      <label>First Name</label>
      <input placeholder="First Name" type="text">
    </div>
    <div class="field">
      <label>Last Name</label>
      <input placeholder="Last Name" type="text">
    </div>
  </div>
  <div class="ui submit button">Submit</div>
</div>
```
```html
<div class="ui small form">
  <div class="two fields">
    <div class="field">
      <label>First Name</label>
      <input placeholder="First Name" type="text">
    </div>
    <div class="field">
      <label>Last Name</label>
      <input placeholder="Last Name" type="text">
    </div>
  </div>
  <div class="ui submit button">Submit</div>
</div>
```
```html
<div class="ui large form">
  <div class="two fields">
    <div class="field">
      <label>First Name</label>
      <input placeholder="First Name" type="text">
    </div>
    <div class="field">
      <label>Last Name</label>
      <input placeholder="Last Name" type="text">
    </div>
  </div>
  <div class="ui submit button">Submit</div>
</div>
```
```html
<div class="ui big form">
  <div class="two fields">
    <div class="field">
      <label>First Name</label>
      <input placeholder="First Name" type="text">
    </div>
    <div class="field">
      <label>Last Name</label>
      <input placeholder="Last Name" type="text">
    </div>
  </div>
  <div class="ui submit button">Submit</div>
</div>
```
```html
<div class="ui huge form">
  <div class="two fields">
    <div class="field">
      <label>First Name</label>
      <input placeholder="First Name" type="text">
    </div>
    <div class="field">
      <label>Last Name</label>
      <input placeholder="Last Name" type="text">
    </div>
  </div>
  <div class="ui submit button">Submit</div>
</div>
```
```html
<div class="ui massive form">
  <div class="two fields">
    <div class="field">
      <label>First Name</label>
      <input placeholder="First Name" type="text">
    </div>
    <div class="field">
      <label>Last Name</label>
      <input placeholder="Last Name" type="text">
    </div>
  </div>
  <div class="ui submit button">Submit</div>
</div>
```

#### Equal Width Form
Forms can automatically divide fields to be equal width
```html
<div class="ui equal width form">
  <div class="fields">
    <div class="field">
      <label>Username</label>
      <input type="text" placeholder="Username">
    </div>
    <div class="field">
      <label>Password</label>
      <input type="password">
    </div>
  </div>
  <div class="fields">
    <div class="field">
      <label>First name</label>
      <input type="text" placeholder="First Name">
    </div>
    <div class="field">
      <label>Middle name</label>
      <input type="text" placeholder="Middle Name">
    </div>
    <div class="field">
      <label>Last name</label>
      <input type="text" placeholder="Last Name">
    </div>
  </div>
</div>
```

#### Inverted
A form on a dark background may have to invert its color scheme
```html
<div class="ui inverted segment">
  <div class="ui inverted form">
    <div class="two fields">
      <div class="field">
        <label>First Name</label>
        <input placeholder="First Name" type="text">
      </div>
      <div class="field">
        <label>Last Name</label>
        <input placeholder="Last Name" type="text">
      </div>
    </div>
    <div class="inline field">
      <div class="ui checkbox">
        <input type="checkbox" />
        <label>I agree to the terms and conditions</label>
      </div>
    </div>
    <div class="ui submit button">Submit</div>
  </div>
</div>
```

## Field Variations

#### Inline Field
A field can have its label next to instead of above it.
```html
<div class="ui form">
  <div class="inline field">
    <label>Last name</label>
    <input type="text" placeholder="Full Name">
  </div>
</div>
```

#### Width
A field can specify its width in grid columns
```html
<div class="ui form">
  <div class="fields">
    <div class="six wide field">
      <label>First name</label>
      <input type="text" placeholder="First Name">
    </div>
    <div class="four wide field">
      <label>Middle</label>
      <input type="text" placeholder="Middle Name">
    </div>
    <div class="six wide field">
      <label>Last name</label>
      <input type="text" placeholder="Last Name">
    </div>
  </div>
  <div class="fields">
    <div class="two wide field">
      <input type="text" placeholder="2 Wide">
    </div>
    <div class="twelve wide field">
      <input type="text" placeholder="12 Wide">
    </div>
    <div class="two wide field">
      <input type="text" placeholder="2 Wide">
    </div>
  </div>
  <div class="fields">
    <div class="eight wide field">
      <input type="text" placeholder="8 Wide">
    </div>
    <div class="six wide field">
      <input type="text" placeholder="6 Wide">
    </div>
    <div class="two wide field">
      <input type="text" placeholder="2 Wide">
    </div>
  </div>
</div>
```

#### Required
A field can show that input is mandatory
```html
<div class="ui form">
    <div class="required field">
      <label>Last name</label>
      <input type="text" placeholder="Full Name">
    </div>
    <div class="required inline field">
      <div class="ui checkbox">
        <input type="checkbox" />
        <label>I agree to the terms and conditions</label>
      </div>
    </div>
</div>
```

## Group Variations

#### Evenly Divided
Fields can have their widths divided evenly
```html
<div class="ui form">
  <div class="three fields">
    <div class="field">
      <label>First name</label>
      <input type="text" placeholder="First Name">
    </div>
    <div class="field">
      <label>Middle name</label>
      <input type="text" placeholder="Middle Name">
    </div>
    <div class="field">
      <label>Last name</label>
      <input type="text" placeholder="Last Name">
    </div>
  </div>
</div>
```

#### Grouped Fields
Fields can show related choices
```html
<div class="ui form">
  <div class="grouped fields">
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="fruit" />
        <label>Apples</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="fruit" />
        <label>Oranges</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="fruit" />
        <label>Pears</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="fruit" />
        <label>Grapefruit</label>
      </div>
    </div>
  </div>
</div>
```

#### Equal Width Fields
Fields can automatically divide fields to be equal width
```html
<div class="ui form">
  <div class="fields">
    <div class="field">
      <label>Username</label>
      <input type="text" placeholder="Username">
    </div>
    <div class="field">
      <label>Password</label>
      <input type="password">
    </div>
  </div>
  <div class="equal width fields">
    <div class="field">
      <label>First name</label>
      <input type="text" placeholder="First Name">
    </div>
    <div class="field">
      <label>Middle name</label>
      <input type="text" placeholder="Middle Name">
    </div>
    <div class="field">
      <label>Last name</label>
      <input type="text" placeholder="Last Name">
    </div>
  </div>
</div>
```

#### Inline Fields
Multiple fields may be inline in a row
```html
<div class="ui form">
  <div class="inline fields">
    <label>Phone Number</label>
    <div class="field">
      <input type="text" placeholder="(xxx)">
    </div>
    <div class="field">
      <input type="text" placeholder="xxx">
    </div>
    <div class="field">
      <input type="text" placeholder="xxxx">
    </div>
  </div>
</div>
```
```html
<div class="ui form">
  <div class="inline fields">
    <label>What's your favorite fruit?</label>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="fruit" />
        <label>Apples</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="fruit" />
        <label>Oranges</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="fruit" />
        <label>Pears</label>
      </div>
    </div>
    <div class="field">
      <div class="ui radio checkbox">
        <input type="radio" name="fruit" />
        <label>Grapefruit</label>
      </div>
    </div>
  </div>
</div>
```


## === grid.md ===

# Grid

A grid is used to harmonize negative space in a layout

## Overview

### Introduction

#### Grids
A grid is a structure with a long history used to align negative space in designs.

Using a grid makes content appear to flow more naturally on your page.

```html
<div class="ui grid">
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
</div>
```

#### Columns
Grids divide horizontal space into indivisible units called "columns". All columns in a grid must specify their width as proportion of the total available row width.

All grid systems choose an arbitrary column count to allow per row. Semantic's default theme uses **16 columns**.

The example below shows four `four wide` columns will fit in the first row, `16 / 4 = 4`, and three various sized columns in the second row. `2 + 8 + 6 = 16`

The default column count, and other arbitrary features of grids can be changed by adjusting Semantic UI's underlying theming variables.

```html
<div class="ui grid">
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="two wide column"></div>
  <div class="eight wide column"></div>
  <div class="six wide column"></div>
</div>
```

#### Rows
Rows are groups of columns which are aligned horizontally.

Rows can either be *explicit*, marked with an additional `row` element, or *implicit*, automatically occurring when no more space is left in a previous row.

After each group of columns vertical spacing is added to separate each group of columns, creating vertical rhythm.

```html
<div class="ui four column grid">
  <div class="row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
</div>
```

#### Gutters
Grid columns are separated by areas of white space referred to as "gutters". Gutters improve legibility by providing, negative space between page elements.

Gutters remain a constant size regardless of the width of the grid, or how many columns are in a row. To increase the size of gutters in a particular grid, you can use a `relaxed grid` variation.

```html
<div class="ui grid">
  <div class="three column row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
  <div class="eight column row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
</div>
<div class="ui relaxed grid">
  <div class="three column row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
  <div class="eight column row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
</div>
```

#### Negative Margins
Since all grid columns include gutters, grids use negative margins to make sure that the first and last columns sit flush with content outside the grid.

In the following example, you can see even though the top row has padding, the `attached button` still sits flush with the edge of the grid.

In some cases, like when a column or row is `colored`, you may want to avoid using negative margins. You can do this by using a `padded grid` variation.

```html
<div class="ui top attached button">Button before grid</div>
<div class="ui grid">
  <div class="sixteen wide column"></div>
  <div class="ten wide column"></div>
  <div class="six wide column"></div>
</div>
<div class="ui grid">
  <div class="sixteen wide column"></div>
</div>
<div class="ui bottom attached button">Button after grid</div>
```

#### Page Grids
Grids are fluid and will automatically flow in size to take the maximum available width.

Containers are elements designed to limit page content to a reasonable maximum width for display based on the size of the user's screen.

Using a `ui grid container` is the best way to include top-level page content inside a grid.

> In version `1.x` of Semantic UI `page grid` were used to contain the maximum width of grids holding page content. Page grid have been deprecated in favor for the simpler `container` element.

### Columns

#### Automatic Flow
Most grids do not need to specify rows. Content will automatically flow to the next row when all the grid columns are taken in the current row.

```html
<div class="ui grid">
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
</div>
```

#### Column Content
Since columns use padding to create gutters, content stylings should not be applied directly to columns, but to elements inside of columns.

```html
<div class="ui three column grid">
  <div class="column">
    <div class="ui segment">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="column">
    <div class="ui segment">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="column">
    <div class="ui segment">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

#### Column Widths
Column widths can be specified using `(x) wide` class names. If a column cannot fit in a row it will automatically flow to the next row

```html
<div class="ui grid">
  <div class="eight wide column"></div>
  <div class="eight wide column"></div>
  <div class="ten wide column"></div>
  <div class="six wide column"></div>
  <div class="four wide column"></div>
  <div class="twelve wide column"></div>
  <div class="two wide column"></div>
  <div class="fourteen wide column"></div>
  <div class="sixteen wide column"></div>
</div>
```

### Rows

#### Grouping
Row wrappers allow you to apply variations to a group of columns.

```html
<div class="ui four column grid">
  <div class="two column row">
    <div class="column"></div>
  </div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
</div>
```

#### Clearing Content
Row wrappers will automatically clear previous columns, making them useful when using `floated` variations.

```html
<div class="ui grid">
  <div class="four column row">
    <div class="left floated column"></div>
    <div class="right floated column"></div>
  </div>
  <div class="row">
    <div class="three wide column"></div>
    <div class="eight wide column"></div>
    <div class="five wide column"></div>
  </div>
</div>
```

#### Special Grids
Additionally, some types of grids, like `divided` or `celled` require row wrappers to apply formatting correctly.

```html
<div class="ui internally celled grid">
  <div class="row">
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ten wide column">
      <img class="ui wireframe image" src="/images/wireframe/centered-paragraph.png">
    </div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="row">
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ten wide column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

### Varying Grids

#### Nesting Grids
Grids can be placed inside of other grids, letting you sub-divide columns.

```html
<div class="ui two column grid">
  <div class="column">
    <div class="ui three column grid">
      <div class="column"></div>
      <div class="column"></div>
      <div class="column"></div>
    </div>
  </div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column">
    <div class="ui grid">
      <div class="ten wide column"></div>
      <div class="six wide column"></div>
    </div>
  </div>
</div>
```

#### Colored
Grids can use named **colors** variations to add background colors, but only with `padded grid` that do not include negative margins.

To include a color that is not available in the default palette its perfectly fine to use CSS

```html
<div class="ui equal width center aligned padded grid">
  <div class="row">
    <div class="olive column">
      Olive
    </div>
    <div class="black column">
      Black
    </div>
  </div>
  <div class="row" style="background-color: #869D05;color: #FFFFFF;">
    <div class="column">Custom Row</div>
  </div>
  <div class="row">
    <div class="black column">
      Black
    </div>
    <div class="olive column">
      Olive
    </div>
  </div>
</div>
```

#### Automatic Column Count
The `equal width` variation will automatically divide column width evenly. This is useful with dynamic content where you do not know the column count in advance.

```html
<div class="ui equal width grid">
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="equal width row">
    <div class="column"></div>
    <div class="column"></div>
  </div>
</div>
```

#### Centering Content
If a row does not take up all sixteen grid columns, you can use a `centered` variation to center the column contents inside the grid.

```html
<div class="ui two column centered grid">
  <div class="column"></div>
  <div class="four column centered row">
    <div class="column"></div>
    <div class="column"></div>
  </div>
</div>
```

#### Significant Word Order
Grids include many variations for adjusting things like vertical or horizontal alignment, text alignment, or default gutter sizes.

Some multi-word variations, like `left floated` or `right aligned` are word-order dependent and require you to use adjacent class names.

```html
<div class="ui right aligned grid">
  <div class="left floated right aligned six wide column">
    <div class="ui segment">
      Left floated right aligned column
    </div>
  </div>
  <div class="right floated left aligned six wide column">
    <div class="ui segment">
      Right floated left aligned column
    </div>
  </div>
  <div class="center aligned two column row">
    <div class="column">
      <div class="ui segment">
      Center aligned row
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
      Center aligned row
      </div>
    </div>
  </div>
  <div class="sixteen wide column">
    <div class="ui segment">
      Right Aligned Grid
    </div>
  </div>
</div>
```

### Responsive Grids

#### Containers
A container can be used alongside a grid to provide a responsive, fixed width container for wrapping the contents of a page.

```html
<div class="ui grid container">
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
</div>
```

#### Stackable
A `stackable grid` will automatically stack rows to a single columns on mobile devices

```html
<div class="ui stackable four column grid">
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
</div>
```

#### Reverse Order
Semantic includes special `reversed` variations that allow you to reverse the order of columns or rows by device

```html
<div class="ui mobile reversed equal width grid">
  <div class="column">
    First
  </div>
  <div class="column">
    Second
  </div>
  <div class="column">
    Third
  </div>
</div>
```

#### Doubling
A `doubling` grid will double column widths for each device jump.

```html
<div class="ui grid">
  <div class="doubling eight column row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
  <div class="doubling six column row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
  <div class="doubling four column row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
</div>
```

#### Manual Tweaks
Although design patterns like `doubling` or `stackable` are useful at simplifying responsive styling, you can also manually tweak device presentation by specifying `(x) wide device` or `device only` columns or rows.

```html
<div class="ui centered grid">
  <div class="computer only row">
    <div class="column"></div>
  </div>
  <div class="six wide tablet eight wide computer column"></div>
  <div class="six wide tablet eight wide computer column"></div>
  <div class="six wide tablet eight wide computer column"></div>
  <div class="six wide tablet eight wide computer column"></div>
  <div class="six wide tablet eight wide computer column"></div>
</div>
```

## Definition

### Types

#### Grid
A basic grid

```html
<div class="ui grid">
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
</div>
```

#### Divided
A grid can have dividers between its columns

```html
<div class="ui three column divided grid">
  <div class="row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
    </div>
  </div>
  <div class="row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
    </div>
  </div>
</div>
```

#### Vertically Divided
A grid can have dividers between rows

```html
<div class="ui vertically divided grid">
  <div class="two column row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
  <div class="three column row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
</div>
```

#### Celled
A grid can have rows divided into cells

```html
<div class="ui celled grid">
  <div class="row">
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="thirteen wide column">
      <img class="ui wireframe image" src="/images/wireframe/centered-paragraph.png">
    </div>
  </div>
  <div class="row">
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ten wide column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

#### Internally Celled
A grid can have rows divisions only between internal rows

```html
<div class="ui internally celled grid">
  <div class="row">
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ten wide column">
      <img class="ui wireframe image" src="/images/wireframe/centered-paragraph.png">
    </div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="row">
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ten wide column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

### Content

#### Rows
A row is a horizontal grouping of columns

```html
<div class="ui three column grid">
  <div class="row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
  <div class="row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
</div>
```

#### Columns
Columns each contain gutters giving them equal spacing from other columns.

```html
<div class="ui grid">
  <div class="eight wide column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
  <div class="eight wide column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
  <div class="eight wide column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
  <div class="eight wide column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
</div>
```

### Variations

#### Floated
A column can sit flush against the left or right edge of a row

```html
<div class="ui grid">
  <div class="left floated five wide column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
  <div class="right floated five wide column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
</div>
```

#### Column Width
A column can vary in width taking up more than a single grid column.

```html
<div class="ui grid">
  <div class="four wide column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="nine wide column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
  <div class="three wide column">
    <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
  </div>
</div>
```

#### Column Count
A grid can have a different number of columns per row

```html
<div class="ui grid">
  <div class="three column row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="four column row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="five column row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

#### Equal Width
A grid can automatically resize all elements to split the available width evenly

```html
<div class="ui equal width grid">
  <div class="column">
    <div class="ui segment">
      1
    </div>
  </div>
  <div class="eight wide column">
    <div class="ui segment">
      2
    </div>
  </div>
  <div class="column">
    <div class="ui segment">
      3
    </div>
  </div>
</div>
```

```html
<div class="ui equal width grid">
  <div class="row">
    <div class="column">
      <div class="ui segment">1</div>
    </div>
    <div class="column">
      <div class="ui segment">2</div>
    </div>
    <div class="column">
      <div class="ui segment">3</div>
    </div>
    <div class="column">
      <div class="ui segment">4</div>
    </div>
  </div>
  <div class="row">
    <div class="column">
      <div class="ui segment">1</div>
    </div>
    <div class="column">
      <div class="ui segment">2</div>
    </div>
    <div class="column">
      <div class="ui segment">3</div>
    </div>
  </div>
  <div class="row">
    <div class="column">
      <div class="ui segment">1</div>
    </div>
    <div class="column">
      <div class="ui segment">2</div>
    </div>
  </div>
</div>
```

#### Stretched
A row can stretch its contents to take up the entire column height

```html
<div class="ui three column divided grid">
  <div class="stretched row">
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

```html
<div class="ui equal width grid">
  <div class="stretched row">
    <div class="column">
      <div class="ui segment">
        1
      </div>
      <div class="ui segment">
        2
      </div>
    </div>
    <div class="six wide column">
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
  <div class="row">
    <div class="column">
      <div class="ui segment">
        1
      </div>
      <div class="ui segment">
        2
      </div>
    </div>
    <div class="six wide column">
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
</div>
```

#### Padded
A grid can preserve its vertical and horizontal gutters on first and last columns

The following grid has vertical and horizontal gutters

```html
<div class="ui two column padded grid">
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
</div>
```

The following grid has vertical gutters.

```html
<div class="ui two column vertically padded grid">
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
</div>
```

The following grid has horizontal gutters

```html
<div class="ui two column horizontally padded grid">
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
</div>
```

#### Relaxed
A grid can increase its gutters to allow for more negative space

```html
<div class="ui four column relaxed grid">
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
</div>
```

```html
<div class="ui four column very relaxed grid">
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
</div>
```

#### Colored
A row or column can be colored

```html
<div class="ui five column padded grid">
  <div class="red column">Red</div>
  <div class="orange column">Orange</div>
  <div class="yellow column">Yellow</div>
  <div class="olive column">Olive</div>
  <div class="green column">Green</div>
  <div class="teal column">Teal</div>
  <div class="blue column">Blue</div>
  <div class="violet column">Violet</div>
  <div class="purple column">Purple</div>
  <div class="pink column">Pink</div>
  <div class="brown column">Brown</div>
  <div class="grey column">Grey</div>
  <div class="black column">Black</div>
</div>
```

```html
<div class="ui padded grid">
  <div class="red row">
    <div class="column">Red</div>
  </div>
  <div class="orange row">
    <div class="column">Orange</div>
  </div>
  <div class="yellow row">
    <div class="column">Yellow</div>
  </div>
  <div class="olive row">
    <div class="column">Olive</div>
  </div>
  <div class="green row">
    <div class="column">Green</div>
  </div>
  <div class="teal row">
    <div class="column">Teal</div>
  </div>
  <div class="blue row">
    <div class="column">Blue</div>
  </div>
  <div class="violet row">
    <div class="column">Violet</div>
  </div>
  <div class="purple row">
    <div class="column">Purple</div>
  </div>
  <div class="pink row">
    <div class="column">Pink</div>
  </div>
  <div class="brown row">
    <div class="column">Brown</div>
  </div>
  <div class="grey row">
    <div class="column">Grey</div>
  </div>
  <div class="black row">
    <div class="column">Black</div>
  </div>
</div>
```

#### Centered
A grid can have its columns centered

```html
<div class="ui two column centered grid">
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="four column centered row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="four column row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

#### Text Alignment
A grid, row, or column can specify its text alignment

```html
<div class="ui center aligned three column grid">
  <div class="row">
    <div class="column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Cats
        </div>
      </div>
    </div>
    <div class="column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Dogs
        </div>
        <div class="item">
          Poodle
        </div>
        <div class="item">
          Cockerspaniel
        </div>
      </div>
    </div>
    <div class="column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Monkeys
        </div>
      </div>
    </div>
  </div>
</div>
```

```html
<div class="ui center aligned grid">
  <div class="three column row">
    <div class="column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Cats
        </div>
      </div>
    </div>
    <div class="left aligned column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Dogs
        </div>
        <div class="item">
          Poodle
        </div>
        <div class="item">
          Cockerspaniel
        </div>
      </div>
    </div>
    <div class="column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Monkeys
        </div>
      </div>
    </div>
  </div>
  <div class="justified row">
    <div class="column">
      <p>Justified content fits exactly inside the grid column, taking up the entire width from one side to the other. Justified content fits exactly inside the grid column, taking up the entire width from one side to the other. Justified content fits exactly inside the grid column, taking up the entire width from one side to the other. Justified content fits exactly inside the grid column, taking up the entire width from one side to the other. Justified content fits exactly inside the grid column, taking up the entire width from one side to the other.</p>
    </div>
  </div>
</div>
```

```html
<div class="ui right aligned three column grid">
  <div class="row">
    <div class="column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Cats
        </div>
      </div>
    </div>
    <div class="column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Dogs
        </div>
        <div class="item">
          Poodle
        </div>
        <div class="item">
          Cockerspaniel
        </div>
      </div>
    </div>
    <div class="column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Monkeys
        </div>
      </div>
    </div>
  </div>
</div>
```

#### Vertical Alignment
A grid, row, or column can specify its vertical alignment to have all its columns vertically centered.

```html
<div class="ui middle aligned four column centered grid">
  <div class="row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

```html
<div class="ui four column centered grid">
  <div class="top aligned row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="middle aligned row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="bottom aligned row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

### Responsive Variations

#### Doubling
A grid can double its column width on tablet and mobile sizes

> A grid will round its columns to the closest reasonable value when doubling, for example a `five column grid` will use `2 mobile, 3 tablet, 5 desktop`. To force 1 column on mobile you can add `stackable`

```html
<div class="five column doubling ui grid">
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
</div>
```

#### Stackable
A grid can have its columns stack on-top of each other after reaching mobile breakpoints

> To see a grid stack, try resizing your browser to a small width

```html
<div class="two column stackable ui grid">
  <div class="column">
    <div class="ui segment">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
  <div class="column">
    <div class="ui segment">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
</div>
```

#### Reversed
A grid or row can specify that its columns should reverse order at different device sizes

> Reversed grids are compatible with `divided` grids and other complex grid types.

```html
<div class="ui computer reversed equal width grid">
  <div class="row">
    <div class="column">
      Computer A Fourth
    </div>
    <div class="column">
      Computer A Third
    </div>
    <div class="column">
      Computer A Second
    </div>
    <div class="column">
      Computer A First
    </div>
  </div>
  <div class="row">
    <div class="column">
      Computer B Fourth
    </div>
    <div class="column">
      Computer B Third
    </div>
    <div class="column">
      Computer B Second
    </div>
    <div class="column">
      Computer B First
    </div>
  </div>
</div>
```

```html
<div class="ui tablet reversed equal width grid">
  <div class="column">
    Tablet Fourth
  </div>
  <div class="column">
    Tablet Third
  </div>
  <div class="column">
    Tablet Second
  </div>
  <div class="column">
    Tablet First
  </div>
</div>
```

```html
<div class="ui mobile reversed equal width grid">
  <div class="column">
    Mobile Fourth
  </div>
  <div class="column">
    Mobile Third
  </div>
  <div class="column">
    Mobile Second
  </div>
  <div class="column">
    Mobile First
  </div>
</div>
```

```html
<div class="ui computer vertically reversed grid">
  <div class="row">
    <div class="column">Computer Row 4</div>
  </div>
  <div class="row">
    <div class="column">Computer Row 3</div>
  </div>
  <div class="row">
    <div class="column">Computer Row 2</div>
  </div>
  <div class="row">
    <div class="column">Computer Row 1</div>
  </div>
</div>
```

```html
<div class="ui tablet vertically reversed grid">
  <div class="row">
    <div class="column">Tablet Row 4</div>
  </div>
  <div class="row">
    <div class="column">Tablet Row 3</div>
  </div>
  <div class="row">
    <div class="column">Tablet Row 2</div>
  </div>
  <div class="row">
    <div class="column">Tablet Row 1</div>
  </div>
</div>
```

```html
<div class="ui mobile vertically reversed grid">
  <div class="row">
    <div class="column">Mobile Row 4</div>
  </div>
  <div class="row">
    <div class="column">Mobile Row 3</div>
  </div>
  <div class="row">
    <div class="column">Mobile Row 2</div>
  </div>
  <div class="row">
    <div class="column">Mobile Row 1</div>
  </div>
</div>
```

#### Device Visibility
A columns or row can appear only for a specific device, or screen sizes

> See container documentation for information on breakpoint calculations

```html
<div class="ui grid">
  <div class="two column large screen only row">
    <div class="column">
      <div class="ui segment">
        Large Screen
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        Large Screen
      </div>
    </div>
  </div>
  <div class="two column large screen only row">
    <div class="column">
      <div class="ui segment">
        Widescreen
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        Widescreen
      </div>
    </div>
  </div>
  <div class="two column mobile only row">
    <div class="column">
      <div class="ui segment">
        Mobile
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        Mobile
      </div>
    </div>
  </div>
  <div class="three column row">
    <div class="computer only column">
      <div class="ui segment">
        Computer
      </div>
    </div>
    <div class="tablet mobile only column">
      <div class="ui segment">
        Tablet and Mobile
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        All Sizes
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        All Sizes
      </div>
    </div>
  </div>
  <div class="four column computer only row">
    <div class="column">
      <div class="ui segment">
        Computer
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        Computer
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        Computer
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        Computer
      </div>
    </div>
  </div>
  <div class="three column tablet only row">
    <div class="column">
      <div class="ui segment">
        Tablet
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        Tablet
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        Tablet
      </div>
    </div>
  </div>
</div>
```

#### Responsive Width
A column can specify a width for a specific device

> It's recommended to use a responsive pattern like `doubling` or `stackable` to reduce complexity when designing responsively, however in some circumstances specifying exact widths for screen sizes may be necessary.

```html
<div class="ui grid">
  <div class="sixteen wide mobile eight wide tablet four wide computer column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
  <div class="sixteen wide mobile eight wide tablet four wide computer column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
  <div class="sixteen wide mobile eight wide tablet four wide computer column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
  <div class="sixteen wide mobile eight wide tablet four wide computer column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
  <div class="sixteen wide mobile eight wide tablet four wide computer column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
</div>
```

```html
<div class="ui grid">
  <div class="four wide two wide large screen one wide widescreen column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
  <div class="four wide two wide large screen one wide widescreen column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
  <div class="four wide two wide large screen one wide widescreen column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
  <div class="four wide two wide large screen one wide widescreen column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
</div>
```


## === menu.md ===

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


## === message.md ===

# Message

A message displays information that explains nearby content

## Types

#### Message
A basic message
```html
<div class="ui message">
  <div class="header">
    Changes in Service
  </div>
  <p>We just updated our privacy policy here to better service our customers. We recommend reviewing the changes.</p>
</div>
```

#### List Message
A message with a list
```html
<div class="ui message">
  <div class="header">
    New Site Features
  </div>
  <ul class="list">
    <li>You can now have cover images on blog pages</li>
    <li>Drafts will now auto-save while writing</li>
  </ul>
</div>
```

#### Icon Message
A message can contain an icon.
```html
<div class="ui icon message">
  <i class="inbox icon"></i>
  <div class="content">
    <div class="header">
      Have you heard about our mailing list?
    </div>
    <p>Get the best news in your e-mail every day.</p>
  </div>
</div>
```
```html
<div class="ui icon message">
  <i class="notched circle loading icon"></i>
  <div class="content">
    <div class="header">
      Just one second
    </div>
    <p>We're fetching that content for you.</p>
  </div>
</div>
```

#### Dismissable Block
A message that the user can choose to hide
```html
<div class="ui message">
  <i class="close icon"></i>
  <div class="header">
    Welcome back!
  </div>
  <p>This is a special notification which you can dismiss if you're bored with it.</p>
</div>
```
> Dismissable blocks do not automatically close when using the close icon, this behavior must be defined using Javascript, for example:
> ```javascript
> $('.message .close')
>   .on('click', function() {
>     $(this)
>       .closest('.message')
>       .transition('fade')
>     ;
>   })
> ;
> ```

## States

#### Hidden
A message can be hidden
```html
<div class="ui hidden message">
  <p>You can't see me</p>
</div>
```

#### Visible
A message can be set to visible to force itself to be shown.
```html
<div class="ui visible message">
  <p>You can always see me</p>
</div>
```

## Variations

#### Floating
A message can float above content that it is related to
```html
<div class="ui floating message">
  <p>Way to go!</p>
</div>
```

#### Compact
A message can only take up the width of its content.
```html
<div class="ui compact message">
  <p>Get all the best inventions in your e-mail every day. Sign up now!</p>
</div>
```

#### Attached
A message can be formatted to attach itself to other content
```html
<div class="ui attached message">
  <div class="header">
    Welcome to our site!
  </div>
  <p>Fill out the form below to sign-up for a new account</p>
</div>
<form class="ui form attached fluid segment">
  <div class="two fields">
    <div class="field">
      <label>First Name</label>
      <input placeholder="First Name" type="text">
    </div>
    <div class="field">
      <label>Last Name</label>
      <input placeholder="Last Name" type="text">
    </div>
  </div>
  <div class="field">
    <label>Username</label>
    <input placeholder="Username" type="text">
  </div>
  <div class="field">
    <label>Password</label>
    <input type="password">
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" id="terms" />
      <label for="terms">I agree to the terms and conditions</label>
    </div>
  </div>
  <div class="ui blue submit button">Submit</div>
</form>
<div class="ui bottom attached warning message">
  <i class="icon help"></i>
  Already signed up? <a href="#">Login here</a> instead.
</div>
```

#### Warning
A message may be formatted to display warning messages.
```html
<div class="ui warning message">
  <i class="close icon"></i>
  <div class="header">
    You must register before you can do that!
  </div>
  Visit our registration page, then try again
</div>
```

#### Info
A message may be formatted to display information.
```html
<div class="ui info message">
  <i class="close icon"></i>
  <div class="header">
    Was this what you wanted?
  </div>
  <ul class="list">
    <li>It's good to see you again.</li>
    <li>Did you know it's been a while?</li>
  </ul>
</div>
```

#### Positive / Success
A message may be formatted to display a positive message.
> Positive/Success and Negative/Error messages by default use similar colors, but each has their own color  variables that can be distinguished in your theme.
```html
<div class="ui positive message">
  <i class="close icon"></i>
  <div class="header">
    You are eligible for a reward
  </div>
  <p>Go to your <b>special offers</b> page to see now.</p>
</div>
```
```html
<div class="ui success message">
  <i class="close icon"></i>
  <div class="header">
    Your user registration was successful.
  </div>
  <p>You may now log-in with the username you have chosen</p>
</div>
```

#### Negative / Error
A message may be formatted to display a negative message.
```html
<div class="ui negative message">
  <i class="close icon"></i>
  <div class="header">
    We're sorry we can't apply that discount
  </div>
  <p>That offer has expired
</div>
```
```html
<div class="ui error message">
  <i class="close icon"></i>
  <div class="header">
    There were some errors with your submission
  </div>
  <ul class="list">
    <li>You must include both a upper and lower case letters in your password.</li>
    <li>You need to select your home country.</li>
  </ul>
</div>
```

#### Colored
A message can be formatted to be different colors
```html
<div class="ui red message">Red</div>
<div class="ui orange message">Orange</div>
<div class="ui yellow message">Yellow</div>
<div class="ui olive message">Olive</div>
<div class="ui green message">Green</div>
<div class="ui teal message">Teal</div>
<div class="ui blue message">Blue</div>
<div class="ui violet message">Violet</div>
<div class="ui purple message">Purple</div>
<div class="ui pink message">Pink</div>
<div class="ui brown message">Brown</div>
<div class="ui black message">Black</div>
```

#### Size
A message can have different sizes
```html
<div class="ui mini message">
  This is a mini message.
</div>
<div class="ui tiny message">
  This is a tiny message.
</div>
<div class="ui small message">
  This is a small message.
</div>
<div class="ui large message">
  This is large
</div>
<div class="ui big message">
  This is big
</div>
<div class="ui huge message">
  This is huge
</div>
<div class="ui massive message">
  This is massive
</div>
```


## === table.md ===

# Table

A table displays a collections of data grouped into rows

## Types

#### Table
A standard table
> Tables will automatically stack their layouts for mobile devices. To disable this behavior, use the `unstackable` variation or `tablet stackable` to allow responsive adjustments for tablet.
```html
<table class="ui celled table">
  <thead>
    <th>Name</th>
    <th>Age</th>
    <th>Job</th>
  </thead>
  <tbody>
    <tr>
      <td data-label="Name">James</td>
      <td data-label="Age">24</td>
      <td data-label="Job">Engineer</td>
    </tr>
    <tr>
      <td data-label="Name">Jill</td>
      <td data-label="Age">26</td>
      <td data-label="Job">Engineer</td>
    </tr>
    <tr>
      <td data-label="Name">Elyse</td>
      <td data-label="Age">24</td>
      <td data-label="Job">Designer</td>
    </tr>
  </tbody>
</table>
```
```html
<table class="ui celled padded table">
  <thead>
    <th class="single line">Evidence Rating</th>
    <th>Effect</th>
    <th>Efficacy</th>
    <th>Consensus</th>
    <th>Comments</th>
  </thead>
  <tbody>
    <tr>
      <td>
        <h2 class="ui center aligned header">A</h2>
      </td>
      <td class="single line">
        Power Output
      </td>
      <td>
        <div class="ui star rating" data-rating="3" data-max-rating="3"></div>
      </td>
      <td class="right aligned">
        80% <br>
        <a href="#">18 studies</a>
      </td>
      <td>Creatine supplementation is the reference compound for increasing muscular creatine levels; there is variability in this increase, however, with some nonresponders.</td>
    </tr>
    <tr>
      <td>
        <h2 class="ui center aligned header">A</h2>
      </td>
      <td class="single line">
        Weight
      </td>
      <td>
        <div class="ui star rating" data-rating="3" data-max-rating="3"></div>
      </td>
      <td class="right aligned">
        100% <br>
        <a href="#">65 studies</a>
      </td>
      <td>Creatine is the reference compound for power improvement, with numbers from one meta-analysis to assess potency</td>
    </tr>
  </tbody>
  <tfoot>
    <th colspan="5">
      <div class="ui right floated pagination menu">
        <a class="icon item">
          <i class="left chevron icon"></i>
        </a>
        <a class="item">1</a>
        <a class="item">2</a>
        <a class="item">3</a>
        <a class="item">4</a>
        <a class="icon item">
          <i class="right chevron icon"></i>
        </a>
      </div>
    </th>
  </tfoot>
</table>
```
```html
<table class="ui very basic collapsing celled table">
  <thead>
    <th>Employee</th>
    <th>Correct Guesses</th>
  </thead>
  <tbody>
    <tr>
      <td>
        <h4 class="ui image header">
          <img src="/images/avatar2/small/lena.png" class="ui mini rounded image">
          <div class="content">
            Lena
            <div class="sub header">Human Resources
          </div>
        </div>
      </td>
      <td>
        22
      </td>
    </tr>
    <tr>
      <td>
        <h4 class="ui image header">
          <img src="/images/avatar2/small/matthew.png" class="ui mini rounded image">
          <div class="content">
            Matthew
            <div class="sub header">Fabric Design
          </div>
        </div>
      </td>
      <td>
        15
      </td>
    </tr>
    <tr>
      <td>
        <h4 class="ui image header">
          <img src="/images/avatar2/small/lindsay.png" class="ui mini rounded image">
          <div class="content">
            Lindsay
            <div class="sub header">Entertainment
          </div>
        </div>
      </td>
      <td>
        12
      </td>
    </tr>
    <tr>
      <td>
        <h4 class="ui image header">
          <img src="/images/avatar2/small/mark.png" class="ui mini rounded image">
          <div class="content">
            Mark
            <div class="sub header">Executive
          </div>
        </div>
      </td>
      <td>
        11
      </td>
    </tr>
  </tbody>
</table>
```
```html
<table class="ui celled striped table">
  <thead>
    <th colspan="3">
      Git Repository
    </th>
  </thead>
  <tbody>
    <tr>
      <td class="collapsing">
        <i class="folder icon"></i> node_modules
      </td>
      <td>Initial commit</td>
      <td class="right aligned collapsing">10 hours ago</td>
    </tr>
    <tr>
      <td>
        <i class="folder icon"></i> test
      </td>
      <td>Initial commit</td>
      <td class="right aligned">10 hours ago</td>
    </tr>
    <tr>
      <td>
        <i class="folder icon"></i> build
      </td>
      <td>Initial commit</td>
      <td class="right aligned">10 hours ago</td>
    </tr>
    <tr>
      <td>
        <i class="file outline icon"></i> package.json
      </td>
      <td>Initial commit</td>
      <td class="right aligned">10 hours ago</td>
    </tr>
    <tr>
      <td>
        <i class="file outline icon"></i> Gruntfile.js
      </td>
      <td>Initial commit</td>
      <td class="right aligned">10 hours ago</td>
    </tr>
  </tbody>
</table>
```

#### Definition
A table may be formatted to emphasize a first column that defines a rows content
> Definition tables are designed to display on a single background color. You can adjust this by changing `@definitionPageBackground`, or specifying a background color on the first cell
```html
<table class="ui definition table">
  <thead>
    <th></th>
    <th>Arguments</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>reset rating</td>
      <td>None</td>
      <td>Resets rating to default value</td>
    </tr>
    <tr>
      <td>set rating</td>
      <td>rating (integer)</td>
      <td>Sets the current star rating to specified value</td>
    </tr>
</table>
```
```html
<table class="ui compact celled definition table">
  <thead>
    <tr>
      <th></th>
      <th>Name</th>
      <th>Registration Date</th>
      <th>E-mail address</th>
      <th>Premium Plan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="collapsing">
        <div class="ui fitted slider checkbox">
          <input type="checkbox"> <label></label>
        </div>
      </td>
      <td>John Lilki</td>
      <td>September 14, 2013</td>
      <td>jhlilk22@yahoo.com</td>
      <td>No</td>
    </tr>
    <tr>
      <td class="collapsing">
        <div class="ui fitted slider checkbox">
          <input type="checkbox"> <label></label>
        </div>
      </td>
      <td>Jamie Harington</td>
      <td>January 11, 2014</td>
      <td>jamieharingonton@yahoo.com</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td class="collapsing">
        <div class="ui fitted slider checkbox">
          <input type="checkbox"> <label></label>
        </div>
      </td>
      <td>Jill Lewis</td>
      <td>May 11, 2014</td>
      <td>jilsewris22@yahoo.com</td>
      <td>Yes</td>
    </tr>
  </tbody>
  <tfoot class="full-width">
    <tr>
      <th></th>
      <th colspan="4">
        <div class="ui right floated small primary labeled icon button">
          <i class="user icon"></i> Add User
        </div>
        <div class="ui small button">
          Approve
        </div>
        <div class="ui small  disabled button">
          Approve All
        </div>
      </th>
    </tr>
  </tfoot>
</table>
```

#### Structured
A table can be formatted to display complex structured data
> UI tables use `border-collapse: separate` to allow for tables to receive styles that cannot usually be applied to tables like `border-radius`. However this can cause some cell borders to appear missing with complex layouts that use `rowspan` or `colspan` and rows with varying column count.
> `ui structured table` does not support some style features, but can correctly display all valid HTML table content.
```html
<table class="ui celled structured table">
  <thead>
    <tr>
      <th rowspan="2">Name</th>
      <th rowspan="2">Type</th>
      <th rowspan="2">Files</th>
      <th colspan="3">Languages</th>
    </tr>
    <tr>
      <th>Ruby</th>
      <th>JavaScript</th>
      <th>Python</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Alpha Team</td>
      <td>Project 1</td>
      <td class="right aligned">2</td>
      <td class="center aligned">
        <i class="large green checkmark icon"></i>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td rowspan="3">Beta Team</td>
      <td>Project 1</td>
      <td class="right aligned">52</td>
      <td class="center aligned">
        <i class="large green checkmark icon"></i>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>Project 2</td>
      <td class="right aligned">12</td>
      <td></td>
      <td class="center aligned">
        <i class="large green checkmark icon"></i>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>Project 3</td>
      <td class="right aligned">21</td>
      <td class="center aligned">
        <i class="large green checkmark icon"></i>
      </td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>
```

## States

#### Positive / Negative
A cell or row may let a user know whether a value is good or bad
```html
<table class="ui celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>No Name Specified</td>
      <td>Unknown</td>
      <td class="negative">None</td>
    </tr>
    <tr class="positive">
      <td>Jimmy</td>
      <td><i class="icon checkmark"></i> Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Unknown</td>
      <td class="positive"><i class="icon close"></i> Requires call</td>
    </tr>
    <tr class="negative">
      <td>Jill</td>
      <td>Unknown</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
```

### Cells

#### Error
A cell or row may call attention to an error or a negative value
```html
<table class="ui celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>No Name Specified</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr class="error">
      <td>Jimmy</td>
      <td>Cannot pull data</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td class="error"><i class="attention icon"></i> Classified</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
```

#### Warning
A cell or row may warn a user
```html
<table class="ui celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>No Name Specified</td>
      <td>Unknown</td>
      <td>None</td>
    </tr>
    <tr class="warning">
      <td>Jimmy</td>
      <td><i class="attention icon"></i> Requires Action</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Unknown</td>
      <td class="warning"><i class="attention icon"></i> Hostile</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Unknown</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
```

#### Active
A cell or row can be active or selected by a user
```html
<table class="ui celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr class="active">
      <td>John</td>
      <td>Selected</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td class="active">Jill</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
```

#### Disabled
A cell can be disabled
```html
<table class="ui celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr class="disabled">
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>John</td>
      <td>Selected</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td class="disabled">Jill</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
```

## Variations

#### Single Line
A table can specify that its cell contents should remain on a single line, and not wrap.
```html
<table class="ui single line table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Registration Date</th>
      <th>E-mail address</th>
      <th>Premium Plan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John Lilki</td>
      <td>September 14, 2013</td>
      <td>jhlilk22@yahoo.com</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Jamie Harington</td>
      <td>January 11, 2014</td>
      <td>jamieharingonton@yahoo.com</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>Jill Lewis</td>
      <td>May 11, 2014</td>
      <td>jilsewris22@yahoo.com</td>
      <td>Yes</td>
    </tr>
  </tbody>
</table>
```

#### Fixed
A table can use `table-layout: fixed` a special faster form of table rendering that does not resize table cells based on content.
```html
<table class="ui fixed table">
  <thead>
    <th>Name</th>
    <th>Status</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>John is an interesting boy but sometimes you don't really have enough room to describe everything you'd like</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Jamie is a kind girl but sometimes you don't really have enough room to describe everything you'd like</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>Jill is an alright girl but sometimes you don't really have enough room to describe everything you'd like</td>
    </tr>
  </tbody>
</table>
```
> Fixed `single line` tables will automatically ensure content that does not fit in a single line will receive "..." ellipsis
```html
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

#### Stacking
A table can specify how it stacks table content responsively
```html
<table class="ui unstackable table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th class="right aligned">Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td class="right aligned">None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td class="right aligned">Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td class="right aligned">None</td>
    </tr>
  </tbody>
</table>
```
```html
<table class="ui tablet stackable table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th class="right aligned">Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td class="right aligned">None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td class="right aligned">Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td class="right aligned">None</td>
    </tr>
  </tbody>
</table>
```

#### Selectable Row
A table can have its rows appear selectable
```html
<table class="ui selectable celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>No Action</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>None</td>
    </tr>
    <tr class="warning">
      <td>John</td>
      <td>No Action</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td class="positive">Approved</td>
      <td class="warning">Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td class="negative">Denied</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
```
```html
<table class="ui selectable inverted table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th class="right aligned">Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td class="right aligned">None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td class="right aligned">Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td class="right aligned">None</td>
    </tr>
  </tbody>
</table>
```

#### Selectable Cell
A table cell can be selectable
> Using an `a` link inside a selectable cell will automatically make the hit box the entire cell area. By default links will inherit their cell color.
```html
<table class="ui celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Edit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>No Action</td>
      <td class="selectable">
        <a href="#">Edit</a>
      </td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td class="selectable">
        <a href="#">Edit</a>
      </td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td class="selectable">
        <a href="#">Edit</a>
      </td>
    </tr>
    <tr class="warning">
      <td>John</td>
      <td>No Action</td>
      <td class="selectable warning">
        <a href="#">Requires change</a>
      </td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td class="positive">Approved</td>
      <td class="selectable positive">
        <a href="#">Approve</a>
      </td>
    </tr>
    <tr>
      <td>Jill</td>
      <td class="negative">Denied</td>
      <td class="selectable negative">
        <a href="#">Remove</a>
      </td>
    </tr>
  </tbody>
</table>
```

#### Vertical Alignment
A table header, row, or cell can adjust its vertical alignment
```html
<table class="ui striped table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr class="top aligned">
      <td>John</td>
      <td>Approved</td>
      <td class="top aligned">
        Notes<br>
        1<br>
        2<br>
      </td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td class="bottom aligned">Approved</td>
      <td>
        Notes<br>
        1<br>
        2<br>
      </td>
    </tr>
  </tbody>
</table>
```

#### Text Alignment
A table header, row, or cell can adjust its text alignment
```html
<table class="ui striped table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th class="right aligned">Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr class="center aligned">
      <td>John</td>
      <td>Approved</td>
      <td class="right aligned">None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td class="right aligned">Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td class="right aligned">None</td>
    </tr>
  </tbody>
</table>
```

#### Striped
A table can stripe alternate rows of content with a darker color to increase contrast
```html
<table class="ui striped table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Date Joined</th>
      <th>E-mail</th>
      <th>Called</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John Lilki</td>
      <td>September 14, 2013</td>
      <td>jhlilk22@yahoo.com</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Jamie Harington</td>
      <td>January 11, 2014</td>
      <td>jamieharingonton@yahoo.com</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>Jill Lewis</td>
      <td>May 11, 2014</td>
      <td>jilsewris22@yahoo.com</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>John Lilki</td>
      <td>September 14, 2013</td>
      <td>jhlilk22@yahoo.com</td>
      <td>No</td>
    </tr>
    <tr>
      <td>John Lilki</td>
      <td>September 14, 2013</td>
      <td>jhlilk22@yahoo.com</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Jamie Harington</td>
      <td>January 11, 2014</td>
      <td>jamieharingonton@yahoo.com</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>Jill Lewis</td>
      <td>May 11, 2014</td>
      <td>jilsewris22@yahoo.com</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>John Lilki</td>
      <td>September 14, 2013</td>
      <td>jhlilk22@yahoo.com</td>
      <td>No</td>
    </tr>
  </tbody>
</table>
```

#### Celled
A table may be divided each row into separate cells
```html
<table class="ui celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>None</td>
    </tr>
  </tbody>
  <tfoot>
    <th>3 People</th>
    <th>2 Approved</th>
    <th></th>
  </tfoot>
</table>
```

#### Basic
A table can reduce its complexity to increase readability.
```html
<table class="ui basic table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
```
```html
<table class="ui very basic table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
```

#### Collapsing Cell
A cell can be collapsing so that it only uses as much space as required
> To ensure icons don't wrap to a separate line you must either specify collapsing on the widest row in the collapsing column, or on all rows
```html
<table class="ui table">
  <tbody>
    <tr>
      <td class="collapsing">
        <i class="folder icon"></i> node_modules
      </td>
      <td>Initial commit</td>
      <td>10 hours ago</td>
    </tr>
    <tr>
      <td>
        <i class="folder icon"></i> test
      </td>
      <td>Initial commit</td>
      <td>10 hours ago</td>
    </tr>
    <tr>
      <td>
        <i class="folder icon"></i> build
      </td>
      <td>Initial commit</td>
      <td>10 hours ago</td>
    </tr>
  </tbody>
</table>
```

#### Column Count
A table can specify its column count to divide its content evenly
```html
<table class="ui five column table">
  <thead>
    <th>Name</th>
    <th>Status</th>
    <th>Age</th>
    <th>Gender</th>
    <th>Notes</th>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>22</td>
      <td>Male</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>32</td>
      <td>Male</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>22</td>
      <td>Female</td>
      <td>None</td>
    </tr>
  </tbody>
  <tfoot>
    <th>3 People</th>
    <th>2 Approved</th>
    <th></th>
    <th></th>
    <th></th>
  </tfoot>
</table>
```

#### Column Width
A table can specify the width of individual columns independently.
> Tables use a 16 column grid similar to ui grid
```html
<table class="ui table">
  <thead>
    <th class="ten wide">Name</th>
    <th class="six wide">Status</th>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
    </tr>
  </tbody>
  <tfoot>
    <th>3 People</th>
    <th>2 Approved</th>
  </tfoot>
</table>
```

#### Collapsing
A table can be collapsing, taking up only as much space as its rows.
```html
<table class="ui collapsing table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>None</td>
    </tr>
  </tbody>
  <tfoot>
    <th>3 People</th>
    <th>2 Approved</th>
    <th></th>
  </tfoot>
</table>
```

#### Colored
A table can be given a color to distinguish it from other tables.
```html
<table class="ui red table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui orange table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui yellow table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui olive table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui green table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui teal table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui blue table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui violet table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui purple table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui pink table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui grey table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui black table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
```

#### Inverted
A table's colors can be inverted
```html
<table class="ui inverted table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>None</td>
    </tr>
  </tbody>
  <tfoot>
    <th>3 People</th>
    <th>2 Approved</th>
    <th></th>
  </tfoot>
</table>
```
```html
<table class="ui inverted red table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted orange table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted yellow table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted olive table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted green table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted teal table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted blue table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted violet table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted purple table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted pink table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted brown table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted grey table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
```

#### Sortable
A table may allow a user to sort contents by clicking on a table header.
> Adding the class `ascending` or `descending` to the `th` will show the user the sorting direction. This example uses a modified version of the kylefox's tablesort plugin to provide the proper class names. To make sortable tables work, include this javascript into your page and call `$('table').tablesort()` when the DOM is ready.
```html
<table class="ui sortable celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>No Action</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td class="positive">Approved</td>
      <td class="warning">Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td class="negative">Denied</td>
      <td>None</td>
    </tr>
  </tbody>
  <tfoot>
    <th>3 People</th>
    <th>2 Approved</th>
    <th></th>
  </tfoot>
</table>
```

#### Full-Width Header / Footer
A definition table can have a full width header or footer, filling in the gap left by the first column
```html
<table class="ui compact celled definition table">
  <thead class="full-width">
    <tr>
      <th></th>
      <th>Name</th>
      <th>Registration Date</th>
      <th>E-mail address</th>
      <th>Premium Plan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="collapsing">
        <div class="ui fitted slider checkbox">
          <input type="checkbox"> <label></label>
        </div>
      </td>
      <td>John Lilki</td>
      <td>September 14, 2013</td>
      <td>jhlilk22@yahoo.com</td>
      <td>No</td>
    </tr>
    <tr>
      <td class="collapsing">
        <div class="ui fitted slider checkbox">
          <input type="checkbox"> <label></label>
        </div>
      </td>
      <td>Jamie Harington</td>
      <td>January 11, 2014</td>
      <td>jamieharingonton@yahoo.com</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td class="collapsing">
        <div class="ui fitted slider checkbox">
          <input type="checkbox"> <label></label>
        </div>
      </td>
      <td>Jill Lewis</td>
      <td>May 11, 2014</td>
      <td>jilsewris22@yahoo.com</td>
      <td>Yes</td>
    </tr>
  </tbody>
  <tfoot class="full-width">
    <tr>
      <th></th>
      <th colspan="4">
        <div class="ui right floated small primary labeled icon button">
          <i class="user icon"></i> Add User
        </div>
        <div class="ui small  button">
          Approve
        </div>
        <div class="ui small  disabled button">
          Approve All
        </div>
      </th>
    </tr>
  </tfoot>
</table>
```

#### Padded
A table may sometimes need to be more padded for legibility
```html
<table class="ui padded table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>He is a very nice guy and I enjoyed talking to him on the telephone. I hope we get to talk again.</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Jamie was not interested in purchasing our product.</td>
    </tr>
  </tbody>
</table>
```
```html
<table class="ui very padded table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>He is a very nice guy and I enjoyed talking to him on the telephone. I hope we get to talk again.</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Jamie was not interested in purchasing our product.</td>
    </tr>
  </tbody>
</table>
```

#### Compact
A table may sometimes need to be more compact to make more rows visible at a time
```html
<table class="ui compact table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
  </tbody>
</table>
```
```html
<table class="ui very compact table">
  <thead>
    <th>Name</th>
    <th>Status</th>
    <th>Another Status</th>
    <th>Notes</th>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
  </tbody>
</table>
```

#### Size
A table can also be small or large
```html
<table class="ui small table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
  </tbody>
</table>
```
