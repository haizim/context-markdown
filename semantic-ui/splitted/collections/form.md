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
