## === api.md ===

# API

API allows elements to trigger actions on a server

## Overview

#### Integrates Seamlessly with UI
API is designed to make the process of integrating data sources to UI components seamless, [tying API request state](#api-state-management) to UI states automatically.

For example adding an API behavior to an [input](/elements/input.html) will occur `oninput`, while a [button](/elements/button.html), will query the server `onclick`.
```html
<div class="ui icon input">
  <i class="search icon"></i>
  <input type="text" placeholder="Type here...">
</div>
<div class="ui hidden divider"></div>
<div class="ui primary button">Click Me</div>
<div class="ui disabled button">Disabled</div>
```

#### Preserve Templated URLs
API helps you decouple URLs from your code. Use named API actions like `get followers` instead of URLs like `http://foo.com/get/1.0/followers.json` in your code.
```javascript
$('.button')
  .api({
    action: 'get followers'
  })
;
```
Centrally manage your entire API making sure you aren't caught modifying urls across your codebase. Define your endpoints using an [intuitive templating system](#api-actions) that [automatically passes data](#passing-data) found in your UI.
```javascript
$.fn.api.settings.api = {
  'get followers' : '/followers/{id}?results={count}',
  'create user'   : '/create',
  'add user'      : '/add/{id}',
  'follow user'   : '/follow/{id}',
  'search'        : '/query/{query}/{/sort}'
};
```

#### HTTP 200 is Not Success
Parse your JSON for `success` conditions before callbacks fire, making sure server errors caught correctly, still trigger error conditions in your front end code.
```
// Responses without this status will trigger error conditions
$.fn.api.settings.successTest = function(response) {
  return response.status == 'OK';
}
```

#### Translate APIs on the Fly
Using a third party API that uses some unruly code? Not a problem! API lets you [modify an APIs raw JSON response](/introduction/new.html#translates-any-api) before it is consumed by your code.

#### Tools for Third-Party Integrations & Mocking
New powerful callbacks like [response](#fulfilling-responses) and [responseAsync](#using-custom-backends) let you asynchronously mock responses and trigger the same callbacks as your API.

## Usage

### Creating an API

#### API Actions
**API** works by defining a set of server actions which interface elements can query. Actions are usually represented by short phrases, things like `save profile`, or `get followers` which correspond to a templated URL resource on the server.

URL variables specified in actions are substituted at run-time allowing individual components to query different URLs.

URLs listed in your API can include **required parameters** and **optional parameters** which may be adjusted for each call.

#### Required Parameters

*   Uses format `{variable}`
*   **Will abort the request** if they cannot be found.

```javascript
/* Two required variables */
$.fn.api.settings.api = {
  'get followers' : '/followers/{id}?results={count}'
};
```

#### Optional Parameters

*   Uses format `{/variable}`
*   Will **not** abort the request if they cannot be found.
*   **Will be removed** from the URL automatically if not available.
*   Any preceding slash before an optional parameter will be removed from the URL, allowing you to include them in resource paths.

```javascript
/* One required, one optional variable */
$.fn.api.settings.api = {
  'get followers' : '/followers/{id}/{/sort}'
};
```

#### Creating your API
You should define your endpoints **once in your application**. Usually this is done in a central configuration file included on each page.

These named API endpoints are stored globally in `$.fn.api.settings.api`.

Keeping your endpoints defined in one place makes sure when you update your application you will only need to update a single location with new URLs.
```javascript
/* Define API endpoints once globally */
$.fn.api.settings.api = {
  'get followers' : '/followers/{id}?results={count}',
  'create user'   : '/create',
  'add user'      : '/add/{id}',
  'follow user'   : '/follow/{id}',
  'search'        : '/search/?query={value}'
};
```

#### Using URLs
Named API actions are not required to use API, you can also manually specify the URL for a request and use the same templating:
```
$('.search.button')
  .api({
    url: 'http://www.google.com?q={value}'
  })
;
```

## Querying API Actions

> <p>The following examples work best while viewing `console` logs in your web console.</p>

#### Attaching API Events

API events are triggered by attaching named actions to elements on your page. These actions look up named endpoints in your API translating templated values from your element for each call.

Any element can have an API action attached directly to it. By default the action will occur on the most appropriate event for the type of element. For example a button will call your server `onclick`, an input `oninput`, or a form `onsubmit`.

API actions and data can be specified in Javascript on initialization:
```html
<div class="ui follow button">
  Follow
</div>
```
```javascript
// translates '/follow/{id}' to 'follow/22'
$('.follow.button')
  .api({
    action: 'follow user',
    urlData: {
      id: 22
    }
  })
;
```

API actions and data can also be specified in metadata:
```html
<div class="ui follow button" data-action="follow user" data-id="22">
  Follow
</div>
```
```
// also calls '/follow/22'
$('.follow.button')
  .api()
;
```

#### Specifying DOM Events
If you need to override what action an API event occurs on you can use the `on` parameter.
> API requests for the following demos have been faked using API's `response` setting to avoid rate throttling from public APIs. No actual data is returned.
```javascript
$('.follow.button')
  .api({
    action: 'follow user',
    on: 'mouseenter'
  })
;
```

#### Calling Immediately
If you require API action to occur immediately use `on: 'now'`. This will still trigger the same state updates to the invoked element, but will occur immediately.

```javascript
$('.follow.button')
  .api({
    action: 'follow user',
    on: 'now'
  })
;
```
Keep in mind passing a new settings object will destroy the previous instance, and all its settings and events. If you want to preserve the previous instance, you can trigger a new request with the `query` behavior.
```javascript
// set-up API button with events
$('.follow.button')
  .api({
    action: 'follow user'
  })
;
// do an immediate query
$('.follow.button')
  .api('query')
;
```

## Setting-up Requests

#### Routing Data to URLs
If your API URLs include templated variables they will be replaced during your request by one of four possible ways, listed in of inheritance.

All parameters used in a URL are encoded using [encodeURIComponent](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent) by default, to prevent from malicious strings from affecting your query. To disable this feature you can set [encodeParameters: false](#settings).

#### 1. Automatically Routed URL Variables
Some special values will be automatically replaced if specified in URL actions.

| Variable | Description | Available for |
|---|---|---|
| text | current text value of element | All elements |
| value | current input value of element | Input elements |

```html
<div class="ui search icon input">
  <i class="search icon"></i>
  <input type="text" class="search">
</div>
```
```javascript
$.fn.api.settings.api.search = '/search/?query={value}';

$('.routed.example .search input')
  .api({
    action       : 'search',
    stateContext : '.ui.input'
  })
;
```

#### 2. URL Variables Specified in Data Attributes
You can include URL values as HTML5 metadata attributes.

This is often the easiest way to include unique URL data for each triggering element. For example, many follow buttons will trigger the same endpoint, but each will have its own user id.

> Only variables specified in your API's URL will be searched for in metadata.
```html
<div class="ui button" data-id="11">
  Follow Sally
</div>
<div class="ui button" data-id="22">
  Follow Jenny
</div>
```
```javascript
// requests different URLs for each button
$('.follow.button')
  .api({
    action: 'follow user'
  })
;
```

#### 3. Settings Specified in Javascript
URL variables and GET/POST data can be specified at run-time in the Javascript object.
```javascript
$('.follow.button')
  .api({
    action : 'follow user',
    method : 'POST',
    // Substituted into URL
    urlData: {
      id: 22
    },
    // passed via POST
    data: {
      name: 'Joe Henderson'
    }
  })
;
```

#### 4. Settings Returned from beforeSend
All run settings, not just URL data, can be adjusted in a special callback `beforeSend` which occurs before the API request is sent.
> An additional callback `beforeXHR` lets you modify the XHR object before sending. This is different than beforeSend which is used **to modify settings** before send.
```javascript
$('.follow.button')
  .api({
    action: 'follow user',
    beforeSend: function(settings) {
      settings.urlData = {
        id: 22
      };
      return settings;
    }
    beforeXHR: function(xhr) {
      // adjust XHR with additional headers
      xhr.setRequestHeader ('Authorization', 'Basic XXXXXX');
      return xhr;
    }
  })
;
```

## Adjusting Requests

#### Modifying XHR
An additional callback `beforeXHR` lets you modify the XHR object before sending. This is useful for adjusting properties of the XHR request like modifying headers, before sending a request.
```javascript
$('.follow.button')
  .api({
    action: 'follow user',
    beforeXHR: function(xhr) {
      // adjust XHR with additional headers
      xhr.setRequestHeader ('Authorization', 'Basic XXXXXX');
      return xhr;
    }
  })
;
```

#### Disabling Requests
As a convenience, API will automatically prevent requests from occurring on elements that are currently disabled.
```html
<div class="ui disabled button">Disabled</div>
```
```javascript
// this will never occur
$('.disabled.button')
  .api({
    action: 'follow user'
  })
;
```

#### Cancelling Requests
BeforeSend can also be used to check for special conditions for a request to be made. If the `beforeSend` callback returns false, the request will be cancelled.
```javascript
// set somewhere in your code
window.isLoggedIn = false;

$('.follow.button')
  .api({
    action: 'follow user',
    beforeSend: function(settings) {
      // cancel request
      if(!isLoggedIn) {
        $(this).state('flash text', 'Requires Login!');
        return false;
      }
    }
  })
;
```

## Passing Data

#### 1. Routed Form Data
When you use the `serializeForm` setting or attach API events on a form, API will automatically include the closest form in data sent to the server.

Structured form data is beneficial over [jQuery's serialize](https://api.jquery.com/serialize/) for several reasons:

*   [Serialize Object](https://github.com/macek/jquery-serialize-object) correctly converts structured form names like `name="name[first]"` into nested object literals.
*   Structured form data can be modified in Javascript in `beforeSend`.
*   Form data will automatically be converted to their Javascript equivalents, for instance, checkboxes will be converted to `boolean` values.

> Structured form data requires including [macek's serialize object.](https://github.com/macek/jquery-serialize-object)

#### Structured Data Example
The following form shows some of the advantages of structured form data mentioned above.
```html
<form class="ui form">
  <div class="two fields">
    <div class="field">
      <label>Name</label>
      <div class="two fields">
        <div class="field">
          <input type="text" name="name[first]" placeholder="First Name">
        </div>
        <div class="field">
          <input type="text" name="name[last]" placeholder="Last Name">
        </div>
      </div>
    </div>
    <div class="field">
      <label>Gender</label>
      <div class="ui selection dropdown">
        <input type="hidden" name="gender">
        <div class="default text">Gender</div>
        <i class="dropdown icon"></i>
        <div class="menu">
          <div class="item" data-value="male">Male</div>
          <div class="item" data-value="female">Female</div>
        </div>
      </div>
    </div>
  </div>
  <div class="two fields">
    <div class="required field">
      <label>Username</label>
      <div class="ui icon input">
        <input type="text" name="username" placeholder="Username">
        <i class="user icon"></i>
      </div>
    </div>
    <div class="required field">
      <label>Password</label>
      <div class="ui icon input">
        <input type="password" name="password">
        <i class="lock icon"></i>
      </div>
    </div>
  </div>
  <div class="ui submit button">Submit</div>
</form>
```
```javascript
$('form .submit.button')
  .api({
    action: 'create user',
    serializeForm: true,
    data: {
      foo: 'baz'
    },
    beforeSend: function(settings) {
      // form data is editable in before send
      if(settings.data.username == '') {
        settings.data.username = 'New User';
      }
      // open console to inspect object
      console.log(settings.data);
      return settings;
    }
  })
;
```

#### 2. Data Routed in Javascript
Server data can be specified directly when initializing an API requests.
```javascript
$('.form .submit')
  .api({
    data: {
      session: 22,
      name: 'Baz'
    }
  })
;
```

#### 3. Data Added in beforeSend
POST or GET data can be specified using a special callback `beforeSend`, which can be used to retrieve data before sending a request.
```javascript
$('.form .submit')
  .api({
    action: 'create user',
    serializeForm: true,
    // arbitrary POST/GET same across all requests
    data: {
      session: 22
    },
    // modify data PER element in callback
    beforeSend: function(settings) {
      // cancel request if no id
      if(!$(this).data('id')) {
        return false;
      }
      settings.data.userID = $(this).data('id');
      return settings;
    }
  })
;
```

## Server Responses

#### Response Callbacks
Successful responses from the server will trigger `onSuccess`, invalid results `onFailure`.

`onError` will only trigger on [XHR](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) errors, but not on invalid JSON responses.

You can use the `onResponse` callback to adjust the JSON response before being parsed against a success test.
```javascript
$('.follow.button')
  .api({
    onResponse: function(response) {
      // make some adjustments to response
      return response;
    },
    successTest: function(response) {
      // test whether a JSON response is valid
      return response.success || false;
    },
    onComplete: function(response) {
      // always called after XHR complete
    },
    onSuccess: function(response) {
      // valid response and response.success = true
    },
    onFailure: function(response) {
      // request failed, or valid response but response.success = false
    },
    onError: function(errorMessage) {
      // invalid response
    },
    onAbort: function(errorMessage) {
      // navigated to a new page, CORS issue, or user canceled request
    }
  })
;
```

#### Determining JSON Success
API has special success conditions for JSON responses. Instead of providing success and failure callbacks based on the HTTP response of the request, a request is considered successful only if the server's response tells you the action was successful. The response is passed to a validation test `successTest` which can be used to check the JSON for a valid response.

For example, you might expect all successful JSON responses to return a top level property signifying the success of the response:

> You can use the `onResponse` callback to modify a server's response by returning a new translated response value before it is parsed by a success test.
```json
{
  "success": true,
  "message": "We've retrieved your data from the server"
  "data": {
    // payload here
  }
}
```
You can specify a success test to check for this `success` value. This most likely will be set globally for all API requests.
```javascript
$.fn.api.settings.successTest = function(response) {
  if(response && response.success) {
    return response.success;
  }
  return false;
};
```

#### Modifying Response JSON
Since version 2.0, API includes an `onResponse` callback which lets you adjust a server's response before a response is validated, allowing you to transform your response before other callbacks fire. This is useful for situations where an API response cannot be modified, but you need the response to conform with a required JSON structure.
```html
<div class="ui search">
  <div class="ui left icon input">
    <input class="prompt" type="text" placeholder="Search GitHub">
    <i class="github icon"></i>
  </div>
</div>
```
```javascript
$('.ui.search')
  .search({
    type          : 'category',
    minCharacters : 3,
    apiSettings   : {
      url        : '//api.github.com/search/repositories?q={query}',
      onResponse : function(githubResponse) {
        var
          response = {
            results : {}
          }
        ;
        if(!githubResponse || !githubResponse.items) {
          return;
        }
        // translate GitHub API response to work with search
        $.each(githubResponse.items, function(index, item) {
          var
            language   = item.language || 'Unknown',
            maxResults = 8
          ;
          if(index >= maxResults) {
            return false;
          }
          // create new language category
          if(response.results[language] === undefined) {
            response.results[language] = {
              name    : language,
              results : []
            };
          }
          // add result to category
          response.results[language].results.push({
            title       : item.name,
            description : item.description,
            url         : item.html_url
          });
        });
        return response;
      }
    }
  })
;
```

## Controlling State

#### UI State

API will automatically add class names for `loading` and `error`. This will let you trigger different UI states automatically as an API call progresses.

If you need a different element than the triggering API element to receive state class names, you can specify a different selector using `settings.stateContext`.

Using `stateContext` allows you to easily do things like trigger a loading state on a form when a submit button is pressed.

### States Included in API Module

| State | Description | API event |
|---|---|---|
| loading | Indicates a user needs to wait | XHR has initialized |
| error | Indicates an error has occurred | XHR Request returns error (does not trigger onAbort caused by page change, or if successTest fails). Stays visible for `settings.errorDuration` |
| disabled | prevents API action | none |

#### Text State
Initializing an API action with the state module gives you more granular control over UI states, like setting an activated or de-activated state and the ability to adjust text values for each state:

```javascript
$('.follow.button')
  .api({
    action: 'follow user'
  })
  .state({
    onActivate: function() {
      $(this).state('flash text');
    },
    text: {
      inactive   : 'Follow',
      active     : 'Followed',
      deactivate : 'Unfollow',
      flash      : 'Added follower!'
    }
  })
;
```

### States Included in State Module

| State | Description | Occurs on |
|---|---|---|
| inactive | Default state | |
| active | Selected state | Toggled on succesful API request |
| activate | Explains activating action | On hover if inactive |
| deactivate | Explains deactivating action | On hover if active |
| hover | Explains interaction | On hover in all states, overrides activate/deactivate |
| disabled | Indicates element cannot be interacted | Triggered programatically. Blocks API requests. |
| flash | Text-only state used to display a temporary message | Triggered programatically |
| success | Indicates user action was a success | Triggered programatically |
| warning | Indicates there was an issue with a user action | Triggered programatically |

## Advanced Use

#### Fulfilling Responses
Since version 2.0, API includes two new parameter `response` and `responseAsync` which allows you to specify a Javascript object or a function for returning an API response. (These were previously `mockResponse` and `mockResponseAsync`.)
```javascript
$('.sync.mocked .button')
  .api({
    response: {
      success: true
    }
  })
  .state({
    text: {
      inactive   : 'Off',
      active     : 'On'
    }
  })
;
```
```html
<div class="ui toggle button">
  Off
</div>
```

#### Using Custom Backends
Using `responseAsync` you can specify a function which can execute your API request. This allows for you to use custom backends or wrappers outside of `$.ajax` for integrating API requests.
```javascript
$('.async.mocked .button')
  .api({
    responseAsync: function(settings, callback) {
      var response = {
        success: true
      };
      // do any asynchronous task here
      setTimeout(function() {
        callback(response);
      }, 500);
    }
  })
  .state({
    text: {
      inactive   : 'Off',
      active     : 'On'
    }
  })
;
```
```html
<div class="ui toggle button">
  Off
</div>
```

## Behaviors

All the following behaviors can be called using the syntax:
```javascript
$('.your.element')
  .api('behavior name', argumentOne, argumentTwo)
;
```

```html
<table class="ui definition celled sortable table segment">
  <thead>
    <th>Behavior</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>query</td>
      <td>Execute query using existing API settings</td>
    </tr>
    <tr>
      <td>add url data(url, data)</td>
      <td>Adds data to existing templated url and returns full url string</td>
    </tr>
    <tr>
      <td>get request</td>
      <td>Gets promise for current API request</td>
    </tr>
    <tr>
      <td>abort</td>
      <td>Aborts current API request</td>
    </tr>
    <tr>
      <td>reset</td>
      <td>Removes loading and error state from element</td>
    </tr>
    <tr>
      <td>was cancelled</td>
      <td>Returns whether last request was cancelled</td>
    </tr>
    <tr>
      <td>was failure</td>
      <td>Returns whether last request was failure</td>
    </tr>
    <tr>
      <td>was successful</td>
      <td>Returns whether last request was successful</td>
    </tr>
    <tr>
      <td>was complete</td>
      <td>Returns whether last request was completed</td>
    </tr>
    <tr>
      <td>is disabled</td>
      <td>Returns whether element is disabled</td>
    </tr>
    <tr>
      <td>is mocked</td>
      <td>Returns whether element response is mocked</td>
    </tr>
    <tr>
      <td>is loading</td>
      <td>Returns whether element is loading</td>
    </tr>
    <tr>
      <td>set loading</td>
      <td>Sets loading state to element</td>
    </tr>
    <tr>
      <td>set error</td>
      <td>Sets error state to element</td>
    </tr>
    <tr>
      <td>remove loading</td>
      <td>Removes loading state to element</td>
    </tr>
    <tr>
      <td>remove error</td>
      <td>Removes error state to element</td>
    </tr>
    <tr>
      <td>get event</td>
      <td>Gets event that API request will occur on</td>
    </tr>
    <tr>
      <td>get url encoded value(value)</td>
      <td>Returns `encodeURIComponent` value only if value passsed is not already encoded
    </tr>
    <tr>
      <td>read cached response(url)</td>
      <td>Reads a locally cached response for a URL</td>
    </tr>
    <tr>
      <td>write cached response(url, response)</td>
      <td>Writes a cached response for a URL</td>
    </tr>
    <tr>
      <td>create cache</td>
      <td>Creates new cache, removing all locally cached URLs</td>
    </tr>
    <tr>
      <td>destroy</td>
      <td>Removes API settings from the page and all events</td>
    </tr>
  </tbody>
</table>
```

## Settings

### API

#### AJAX
> You can pass in any standard [jQuery AJAX setting](http://api.jquery.com/jquery.ajax/) like `timeout` or `contentType` to API's settings and it will be automatically passed to the request's AJAX call.

#### API
```html
<table class="ui sortable celled definition table">
  <thead>
    <th class="three wide"></th>
    <th class="three wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>on</td>
      <td>auto</td>
      <td>When API event should occur</td>
    </tr>
    <tr>
      <td>cache</td>
      <td>true</td>
      <td>Can be set to 'local' to cache **successful** returned AJAX responses when using a JSON API. This helps avoid server roundtrips when API endpoints will return the same results when accessed repeatedly. Setting to `false`, will add cache busting parameters to the URL.</td>
    </tr>
    <tr>
      <td>stateContext</td>
      <td>this</td>
      <td>UI state will be applied to this element, defaults to triggering element.</td>
    </tr>
    <tr>
      <td>encodeParameters</td>
      <td>true</td>
      <td>Whether to encode parameters with `encodeURIComponent` before adding into url string</td>
    </tr>
    <tr>
      <td>defaultData</td>
      <td>true</td>
      <td>Whether to automatically include default data like {value} and {text}</td>
    </tr>
    <tr>
      <td>serializeForm</td>
      <td>false</td>
      <td>Whether to serialize closest form and include in request</td>
    </tr>
    <tr>
      <td>throttle</td>
      <td>
        0
      </td>
      <td>How long to wait when a request is made before triggering request, useful for rate limiting `oninput`</td>
    </tr>
    <tr>
      <td>throttleFirstRequest</td>
      <td>
        true
      </td>
      <td>When set to false will not delay the first request made, when no others are queued</td>
    </tr>
    <tr>
      <td>interruptRequests</td>
      <td>
        false
      </td>
      <td>Whether an API request can occur while another request is still pending</td>
    </tr>
    <tr>
      <td>loadingDuration</td>
      <td>0</td>
      <td>Minimum duration to show loading indication</td>
    </tr>
    <tr>
      <td>hideError</td>
      <td>auto</td>
      <td>The default `auto` will automatically remove error state after error duration, unless the element is a `form`</td>
    </tr>
    <tr>
      <td>errorDuration</td>
      <td>2000</td>
      <td>Setting to `true`, will not remove error. Setting to a duration in milliseconds to show error state after request error.</td>
    </tr>
  </tbody>
</table>
```

#### Request Settings
```html
<table class="ui sortable celled definition table">
  <thead>
    <th class="three wide"></th>
    <th class="three wide">Default</th>
    <th>Description</th>
    <th>Possible Values</th>
  </thead>
  <tbody>
    <tr>
      <td>action</td>
      <td>false</td>
      <td>Named API action for query, originally specified in $.fn.settings.api</td>
      <td>String or false</td>
    </tr>
    <tr>
      <td>url</td>
      <td>false</td>
      <td>Templated URL for query, will override specified action</td>
      <td>String or false</td>
    </tr>
    <tr>
      <td>urlData</td>
      <td>false</td>
      <td>Variables to use for replacement</td>
      <td></td>
    </tr>
    <tr>
      <td>response</td>
      <td>false</td>
      <td>Can be set to a Javascript object which will be returned automatically instead of requesting JSON from server </td>
      <td>{} or false</td>
    </tr>
    <tr>
      <td>responseAsync(settings, callback)</td>
      <td>false</td>
      <td>When specified, this function can be used to retrieve content from a server and return it asynchronously **instead of** a standard AJAX call. The callback function should return the server response.</td>
      <td>function or false</td>
    </tr>
    <tr>
      <td>mockResponse</td>
      <td>false</td>
      <td>Alias of `response`</td>
      <td></td>
    </tr>
    <tr>
      <td>mockResponseAsync</td>
      <td>false</td>
      <td>Alias of `responseAsync`</td>
      <td></td>
    </tr>
    <tr>
      <td>method</td>
      <td>get</td>
      <td>Method for transmitting request to server</td>
      <td>Any valid http method</td>
    </tr>
    <tr>
      <td>dataType</td>
      <td>JSON</td>
      <td>Expected data type of response </td>
      <td>xml, json, jsonp, script, html, text</td>
    </tr>
    <tr>
      <td>data</td>
      <td>{}</td>
      <td>POST/GET Data to Send with Request</td>
      <td></td>
    </tr>
  </tbody>
</table>
```

#### Callbacks

```html
<table class="ui sortable celled definition table">
  <thead>
    <th class="three wide"></th>
    <th class="three wide">Context</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>beforeSend(settings)</td>
      <td>initialized element</td>
      <td>Allows modifying settings before request, or cancelling request</td>
    </tr>
    <tr>
      <td>beforeXHR(xhrObject)</td>
      <td></td>
      <td>Allows modifying XHR object for request</td>
    </tr>
    <tr>
      <td>onRequest(promise, xhr)</td>
      <td>state context</td>
      <td>Callback that occurs when request is made. Receives both the API success promise and the XHR request promise.</td>
    </tr>
    <tr>
      <td>onResponse(response)</td>
      <td>state context</td>
      <td>Allows modifying the server's response before parsed by other callbacks to determine API event success</td>
    </tr>
    <tr>
      <td>successTest(response)</td>
      <td></td>
      <td>Determines whether completed JSON response should be [treated as successful](#determining-json-success)
      </td>
    </tr>
    <tr>
      <td>onSuccess(response, element, xhr)</td>
      <td>state context</td>
      <td>Callback after successful response, JSON response must pass `successTest`</td>
    </tr>
    <tr>
      <td>onComplete(response, element, xhr)</td>
      <td>state context</td>
      <td>Callback on request complete regardless of conditions</td>
    </tr>
    <tr>
      <td>onFailure(response, element)</td>
      <td>state context</td>
      <td>Callback on failed response, or JSON response that fails `successTest`</td>
    </tr>
    <tr>
      <td>onError(errorMessage, element, xhr)</td>
      <td>state context</td>
      <td>Callback on server error from returned status code, or XHR failure.</td>
    </tr>
    <tr>
      <td>onAbort(errorMessage, element, xhr)</td>
      <td>state context</td>
      <td>Callback on abort caused by user clicking a link or manually cancelling request.</td>
    </tr>
  </tbody>
</table>
```

## Module

These settings are native to all modules, and define how the component ties content to DOM attributes, and debugging settings for the module.

```html
<table class="ui sortable celled definition table">
  <thead>
    <th></th>
    <th class="six wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>API</td>
      <td>Name used in log statements</td>
    </tr>
    <tr>
      <td>namespace</td>
      <td>api</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>regExp</td>
      <td>
        <div class="code">
regExp  : {
  required: /\{\$*[A-z0-9]+\}/g,
  optional: /\{\/\$*[A-z0-9]+\}/g,
}
        </div>
      </td>
      <td>Regular expressions used for template matching</td>
    </tr>
    <tr>
      <td>selector</td>
      <td>
        <div class="code">
selector: {
  disabled : '.disabled',
  form     : 'form'
}
        </div>
      </td>
      <td>Selectors used to find parts of a module</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
className: {
  loading : 'loading',
  error   : 'error'
}
        </div>
      </td>
      <td>Class names used to determine element state</td>
    </tr>
    <tr>
      <td>metadata</td>
      <td>
        <div class="code">
metadata: {
  action  : 'action',
  url     : 'url'
}
        </div>
      </td>
      <td>Metadata used to store XHR and response promise</td>
    </tr>
    <tr>
      <td>silent</td>
      <td>False</td>
      <td>Silences all console output including error messages, regardless of other debug settings.</td>
    </tr>
    <tr>
      <td>debug</td>
      <td>false</td>
      <td>Debug output to console</td>
    </tr>
    <tr>
      <td>performance</td>
      <td>true</td>
      <td>Show `console.table` output with performance metrics</td>
    </tr>
    <tr>
      <td>verbose</td>
      <td>false</td>
      <td>Debug output includes all internal behaviors</td>
    </tr>
    <tr>
      <td>errors</td>
      <td colspan="2">
        <div class="code">
// errors
error : {
  beforeSend        : 'The before send function has aborted the request',
  error             : 'There was an error with your request',
  exitConditions    : 'API Request Aborted. Exit conditions met',
  JSONParse         : 'JSON could not be parsed during error handling',
  legacyParameters  : 'You are using legacy API success callback names',
  missingAction     : 'API action used but no url was defined',
  missingSerialize  : 'Required dependency jquery-serialize-object missing, using basic serialize',
  missingURL        : 'No URL specified for API event',
  noReturnedValue   : 'The beforeSend callback must return a settings object, beforeSend ignored.',
  parseError        : 'There was an error parsing your request',
  requiredParameter : 'Missing a required URL parameter: ',
  statusMessage     : 'Server gave an error: ',
  timeout           : 'Your request timed out'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```