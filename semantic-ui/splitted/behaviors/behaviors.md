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
  required: /{\$*[A-z0-9]+}/g,
  optional: /{\/\$*[A-z0-9]+}/g,
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

## === form-behavior.md ===

# Form Validation

A form validation behavior checks data against a set of criteria before passing it along to the server

## Usage

#### Specifying Validation Rules
Form validation requires passing in a validation object with the rules required to validate your form.
> A validation object includes a list of form elements, and rules to validate each field against. Fields are matched by either the `id`, `name`, or `data-validate` property (in that order) matching the identifier specified in the settings object. Validation objects must use either shorthand or longhand exclusively.
```
// Shorthand Validation
$('.ui.form')
  .form({
    fields: {
      name     : 'empty',
      gender   : 'empty',
      username : 'empty',
      password : ['minLength[6]', 'empty'],
      skills   : ['minCount[2]', 'empty'],
      terms    : 'checked'
    }
  })
;
```

```
// Full Validation Settings
$('.ui.form')
  .form({
    fields: {
      name: {
        identifier: 'name',
        rules: [
          {
            type   : 'empty',
            prompt : 'Please enter your name'
          }
        ]
      },
      skills: {
        identifier: 'skills',
        rules: [
          {
            type   : 'minCount[2]',
            prompt : 'Please select at least two skills'
          }
        ]
      },
      gender: {
        identifier: 'gender',
        rules: [
          {
            type   : 'empty',
            prompt : 'Please select a gender'
          }
        ]
      },
      username: {
        identifier: 'username',
        rules: [
          {
            type   : 'empty',
            prompt : 'Please enter a username'
          }
        ]
      },
      password: {
        identifier: 'password',
        rules: [
          {
            type   : 'empty',
            prompt : 'Please enter a password'
          },
          {
            type   : 'minLength[6]',
            prompt : 'Your password must be at least {ruleValue} characters'
          }
        ]
      },
      terms: {
        identifier: 'terms',
        rules: [
          {
            type   : 'checked',
            prompt : 'You must agree to the terms and conditions'
          }
        ]
      }
    }
  })
;
```
```html
<form class="ui form segment">
  <p>Tell Us About Yourself</p>
  <div class="two fields">
    <div class="field">
      <label>Name</label>
      <input placeholder="First Name" name="name" type="text">
    </div>
    <div class="field">
      <label>Gender</label>
      <select class="ui dropdown" name="gender">
        <option value="">Gender</option>
        <option value="male">Male</option>
        <option value="female">Female</option>
      </select>
    </div>
  </div>
  <div class="two fields">
    <div class="field">
      <label>Username</label>
      <input placeholder="Username" name="username" type="text">
    </div>
    <div class="field">
      <label>Password</label>
      <input type="password" name="password">
    </div>
  </div>
  <div class="field">
    <label>Skills</label>
    <select name="skills" multiple class="ui dropdown">
      <option value="">Select Skills</option>
      <option value="css">CSS</option>
      <option value="html">HTML</option>
      <option value="javascript">Javascript</option>
      <option value="design">Graphic Design</option>
      <option value="plumbing">Plumbing</option>
      <option value="mech">Mechanical Engineering</option>
      <option value="repair">Kitchen Repair</option>
    </select>
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" name="terms" />
      <label>I agree to the terms and conditions</label>
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui error message"></div>
</div>
</form>
```

#### Passing Parameters to Rules
Typically rules that include a parameter are written `minLength[2]` with the value being passed in as brackets.

If passing in properties as a string is not ideal, or if you are pulling values from another javascript variable, it might make sense to consider using `value` to pass in the rule value.
```
$('.ui.form').form({
  fields: {
    color: {
      identifier: 'color',
      rules: [{
        type: 'regExp',
        value: /rgb\((\d{1,3}), (\d{1,3}), (\d{1,3})\)/i,
      }]
    }
  }
});
```
```html
<form class="ui form segment">
  <div class="field">
    <label>Color</label>
    <input placeholder="Enter rgb" name="color" type="text" value="rgb(255, 255, 255)">
  </div>
  <div class="ui primary submit button">Submit</div>
</form>
```

#### Customizing Prompts
Form validation includes default error prompts for most cases, however these can be quite generic. To specify custom personalized values for a validation prompt use the `prompt` property with a rule.
> Starting in <div class="ui teal label">2.3.1</div> you can specify prompts as a function. This may be useful when returning validation for fields that require dynamic validation messages.</div>
> You can set default messages for each validation rule type by modifying `$.fn.form.settings.prompt`

Prompt also supports custom templating with the following values replaced

| **{name}** | The current text of a field's label, or if no label available its placeholder text |
|---|---|
| **{identifier}** | The identifier used to match the field |
| **{value}** | The current field value |
| **{ruleValue}** | The value passed to a rule, for example `minLength[100]` would set this value to 100 |

```
$('.ui.form')
  .form({
    fields: {
      field1: {
        rules: [
          {
            type   : 'empty'
          }
        ]
      },
      field2: {
        rules: [
          {
            type   : 'exactly[dog]',
            prompt : '{name} is set to "{value}" that is totally wrong. It should be {ruleValue}'
          }
        ]
      },
      field3: {
        rules: [
          {
            type   : 'exactly[cat]',
            prompt : function(value) {
              if(value == 'dog') {
                return 'I told you to put cat, not dog!';
              }
              return 'That is not cat';
            }
          }
        ],
      }
    }
  })
;
```
```html
<form class="ui form segment">
  <div class="two fields">
    <div class="field">
      <label>Field 1</label>
      <input type="text" name="field1">
    </div>
    <div class="field">
      <label>Field 2</label>
      <input type="text" name="field2">
    </div>
    <div class="field">
      <label>Field 3</label>
      <input type="text" name="field3">
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui error message">
  </div>
</form>
```

#### Matching Fields
By default the property name used in the validation object will match against the `id`, `name`, or `data-validate` property of each input to find the corresponding field to match validation rules against.

If you need to specify a different identifier you can use the `identifier` property on each validation rule
```
$('.ui.form')
  .form({
    fields: {
      name: {
        identifier : 'special-name',
        rules: [
          {
            type   : 'empty'
          }
        ]
      }
    }
  })
;
```
```html
<form class="ui form segment">
  <div class="field">
    <label>Special Field</label>
    <input type="text" name="special-name">
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui error message">
  </div>
</form>
```

#### Validating Programmatically
Form validation provides additional behaviors to programmatically trigger validation for either the form or an individual field, and check validation on the form or individual fields.

Please see the [behaviors section](#behaviors) for an explanation on syntax.

| **validate form** | Validates entire form and displays errors if necessary |
|---|---|
| **is valid** | Returns whether a form is valid |
| **is valid(fieldName)** | Returns whether a field in a form is valid (does not update UI) |
| **validate field(fieldName)** | Validates a particular field and displays errors if necessary |

```
$('.ui.form')
  .form({
    fields: {
     email: 'empty',
     name: 'empty'
    }
  })
;
if( $('.ui.form').form('is valid', 'email')) {
  // email is valid
}
if( $('.ui.form').form('is valid')) {
  // form is valid (both email and name)
}
```

## Rules

#### Validation Rules
Validation rules are a set of conditions required to validate a field
> Validation rules are found in `$.fn.form.settings.rules`, to add new global validation rules, modify `$.fn.form.settings.rules` to include your function.
> To pass parameters to a rule, use bracket notation in your settings object. For example `type: 'not[dog]'`

### Empty

| empty | A field is empty |
|---|---|
| checked | A checkbox field is checked |

### Content Type

| email | A field is a valid email address | |
|---|---|---|
| url | A field is a url | |
| integer | A field is an integer value, or matches an integer range | `integer` or `integer[1..10]` |
| decimal | A field must be a decimal number | |
| number | A field is any number decimal or non-decimal | |
| regExp[expression] | Matches against a regular expression, when using bracketed notation RegExp values must be escaped. | `regExp[/^[a-z0-9_-]{3,16}$/gi]]` Or `regExp[/^[a-z0-9_-]{3,16}$/]]` |

### Payment

| creditCard | A field is a valid credit card | `creditCard` |
|---|---|---|
| creditCard[types] | A field matches a specified array of card types | `creditCard[visa,mastercard,unionpay]` |

### Specified Content

| contains | A field contains text (case insensitive) | `contains[foo]` |
|---|---|---|
| containsExactly | A field contains text (case sensitive) | `containsExactly[foo]` |
| doesntContain | A field doesn't contain text (case insensitive) | `doesntContain[foo]` |
| doesntContainExactly | A field doesn't contain text (case sensitive) | `doesntContainExactly[foo]` |
| is | A field is a value (case insensitive) | `is[foo]` |
| isExactly | A field is a value (case-sensitive) | `isExactly[foo]` |
| not | A field is not a value (case insensitive) | `not[foo]` |
| notExactly | A field is not a value (case sensitive) | `notExactly[foo]` |

### Length

| minLength | A field is less than a min length | `minLength[5]` |
|---|---|---|
| exactLength | A field is exactly length | `exactLength[16]` |
| maxLength | A field is less than a max length | `maxLength[50]` |

### Matching Fields

| match | A field should match the value of another validation field, for example to confirm passwords | `match[password]` |
|---|---|---|
| different | A field should be different than another specified field | `different[choice]` |

### Selection Count

| minCount | A multiple select field contains at minimum (count) selections | `minCount[count]` |
|---|---|---|
| exactCount | A multiple select field contains exactly (count) selections | `exactCount[count]` |
| maxCount | A multiple select field contains at maximum (count) selections | `maxCount[count]` |

#### Adding Custom Rules
You can extend form validation to include your own rules. Keep in mind these will need to be executed synchronously.
```
// some arbitrary business-logic
window.user = {
  name       : 'Simon',
  adminLevel : 1
};
// custom form validation rule
$.fn.form.settings.rules.adminLevel = function(value, adminLevel) {
  return (window.user.adminLevel >= adminLevel)
};
$('.ui.form')
  .form({
    fields: {
      dog: {
        identifier: 'dog',
        rules: [
          {
            type: 'adminLevel[2]',
            prompt: 'You must be at least a level-2 admin to add a dog'
          }
        ]
      }
    }
  })
;
```
```html
<form class="ui form segment">
  <p>Let's go ahead and get you signed up.</p>
  <div class="field">
    <label>Dog</label>
    <input placeholder="Dog" name="dog" type="text">
  </div>
  <div class="ui primary submit button">
    <i class="add icon"></i>
    Add Dog
  </div>
  <div class="ui error message"></div>
</form>
```

#### Built-in Events

Form will automatically attach events to specially labeled form fields

*   Fields will blur on `escape` key press
*   Fields will submit form on `enter`
*   Submit events will be attached to `click` on any element inside the form with class `submit`
*   Reset events will be attached to `click` on any element inside the form with class `reset`
*   Clear events will be attached to `click` on any element inside the form with class `clear`

```html
<form class="ui form segment">
  <div class="field">
    <label>Test Field</label>
    <input placeholder="Test Field" name="name" type="text">
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui reset button">Reset</div>
  <div class="ui clear button">Clear</div>
</form>
```

## Manipulating Forms

#### Reset / Clear Fields

Calling `$('form').form('reset')`, or clicking any reset element will return all form values to their *default value*. This is the value the form fields were set to when the page loaded.

Calling `$('form').form('clear')` will remove all values from form fields and reset dropdowns to placeholder text

> Form `reset` works by caching default values on page load. For this to work correctly any form that uses reset will need to initialize on page load.
> Reset and clear will modify all form fields, not just those which have validation rules
```html
<form class="ui form segment">
  <div class="two fields">
    <div class="field">
      <label>Name</label>
      <input placeholder="First Name" name="name" type="text">
    </div>
    <div class="field">
      <label>Gender</label>
      <div class="ui selection dropdown">
        <input name="gender" type="hidden">
        <div class="default text">Gender</div>
        <i class="dropdown icon"></i>
        <div class="menu">
          <div class="item" data-value="male">Male</div>
          <div class="item" data-value="female">Female</div>
        </div>
      </div>
    </div>
  </div>
  <div class="field">
    <label>Username</label>
    <input placeholder="Username" name="username" type="text">
  </div>
  <div class="field">
    <label>Password</label>
    <input name="password" type="password">
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input name="terms" type="checkbox">
      <label>I agree to the terms and conditions</label>
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui reset button">Reset</div>
  <div class="ui clear button">Clear</div>
</form>
```

#### Writing Values

Form includes behaviors for reading from and writing to form fields.

```javascript
$('.writing.example form')
  // set one value
  .form('set value', 'name', 'Jack')

  // set several values
  .form('set values', {
    name     : 'Jack',
    gender   : 'male',
    colors   : ['red', 'grey'],
    username : 'jlukic',
    password : 'youdliketoknow',
    terms    : true
  })
;
```
```html
<form class="ui form segment">
  <div class="two fields">
    <div class="field">
      <label>Name</label>
      <input placeholder="First Name" name="name" type="text">
    </div>
    <div class="field">
      <label>Gender</label>
      <div class="ui selection dropdown">
        <input name="gender" type="hidden">
        <div class="default text">Gender</div>
        <i class="dropdown icon"></i>
        <div class="menu">
          <div class="item" data-value="male">Male</div>
          <div class="item" data-value="female">Female</div>
        </div>
      </div>
    </div>
  </div>
  <div class="field">
    <label>Username</label>
    <input placeholder="Username" name="username" type="text">
  </div>
  <div class="field">
    <label>Password</label>
    <input name="password" type="password">
  </div>
  <div class="inline fields">
    <label for="colors">Favorite Colors</label>
    <div class="field">
      <div class="ui checkbox">
        <input type="checkbox" name="colors[]" value="red" />
        <label>Red</label>
      </div>
    </div>
    <div class="field">
      <div class="ui checkbox">
        <input type="checkbox" name="colors[]" value="blue" />
        <label>Blue</label>
      </div>
    </div>
    <div class="field">
      <div class="ui checkbox">
        <input type="checkbox" name="colors[]" value="green" />
        <label>Green</label>
      </div>
    </div>
    <div class="field">
      <div class="ui checkbox">
        <input type="checkbox" name="colors[]" value="grey" />
        <label>Grey</label>
      </div>
    </div>
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input name="terms" type="checkbox">
      <label>I agree to the terms and conditions</label>
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui clear button">Clear</div>
</form>
```

#### Getting Values

You can also read values from form fields using `get value` and `get values`

> Although `get values` allows you to use any matching identifier, returned values will always use the corresponding `name` attribute of the element.
```javascript
var
  $form = $('.get.example form'),
  // get one value
  colors = $form.form('get value', 'colors'),
  // get list of values
  fields = $form.form('get values', ['name', 'colors']),
  // get all values
  allFields = $form.form('get values')
;
console.log(colors);
console.log(fields);
console.log(allFields);
```
```html
<form class="ui form segment">
  <div class="two fields">
    <div class="field">
      <label>Name</label>
      <input placeholder="First Name" name="name" type="text">
    </div>
    <div class="field">
      <label>Gender</label>
      <div class="ui selection dropdown">
        <input name="gender" type="hidden">
        <div class="default text">Gender</div>
        <i class="dropdown icon"></i>
        <div class="menu">
          <div class="item" data-value="male">Male</div>
          <div class="item" data-value="female">Female</div>
        </div>
      </div>
    </div>
  </div>
  <div class="field">
    <label>Username</label>
    <input placeholder="Username" name="username" type="text">
  </div>
  <div class="field">
    <label>Password</label>
    <input name="password" type="password">
  </div>
  <div class="inline fields">
    <label for="colors">Favorite Colors</label>
    <div class="field">
      <div class="ui checkbox">
        <input type="checkbox" name="colors[]" value="red" />
        <label>Red</label>
      </div>
    </div>
    <div class="field">
      <div class="ui checkbox">
        <input type="checkbox" name="colors[]" value="blue" />
        <label>Blue</label>
      </div>
    </div>
    <div class="field">
      <div class="ui checkbox">
        <input type="checkbox" name="colors[]" value="green" />
        <label>Green</label>
      </div>
    </div>
    <div class="field">
      <div class="ui checkbox">
        <input type="checkbox" name="colors[]" value="grey" />
        <label>Grey</label>
      </div>
    </div>
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input name="terms" type="checkbox">
      <label>I agree to the terms and conditions</label>
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
</form>
```

## Examples

### Rule Examples

#### Empty
The following shows examples of validating different types of empty or unchecked content.
```html
<form class="ui form">
  <div class="field">
    <label>Empty</label>
    <input name="empty" type="text">
  </div>
  <div class="field">
    <label>Dropdown</label>
    <select class="ui dropdown" name="dropdown">
      <option value="">Select</option>
      <option value="male">Choice 1</option>
      <option value="female">Choice 2</option>
    </select>
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" name="checkbox" />
      <label>Checkbox</label>
    </div>
  </div>
  <div class="ui submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```
```javascript
$('.field.example form')
  .form({
    on: 'blur',
    fields: {
      empty: {
        identifier  : 'empty',
        rules: [
          {
            type   : 'empty',
            prompt : 'Please enter a value'
          }
        ]
      },
      dropdown: {
        identifier  : 'dropdown',
        rules: [
          {
            type   : 'empty',
            prompt : 'Please select a dropdown value'
          }
        ]
      },
      checkbox: {
        identifier  : 'checkbox',
        rules: [
          {
            type   : 'checked',
            prompt : 'Please check the checkbox'
          }
        ]
      }
    }
  })
;
```

#### Content Type
Inputs can match against common content types, or your own custom [regular expressions](http://www.regular-expressions.info/).
```html
<form class="ui form">
  <div class="two fields">
    <div class="field">
      <label>Integer</label>
      <input name="integer" type="text" value="101">
    </div>
    <div class="field">
      <label>E-mail</label>
      <input name="email" type="text" value="jack">
    </div>
  </div>
  <div class="two fields">
    <div class="field">
      <label>Decimal</label>
      <input name="decimal" type="text" value="1.1.1">
    </div>
    <div class="field">
      <label>Number</label>
      <input name="number" type="text" value="+200">
    </div>
  </div>
  <div class="two fields">
    <div class="field">
      <label>URL</label>
      <input name="url" type="text" value="ww.fakeurl.com">
    </div>
    <div class="field">
      <label>RegEx</label>
      <input name="regex" type="text" value="joe">
    </div>
  </div>
  <div class="ui submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```
```javascript
$('.type.example form')
  .form({
    on: 'blur',
    fields: {
      integer: {
        identifier  : 'integer',
        rules: [
          {
            type   : 'integer[1..100]',
            prompt : 'Please enter an integer value'
          }
        ]
      },
      decimal: {
        identifier  : 'decimal',
        rules: [
          {
            type   : 'decimal',
            prompt : 'Please enter a valid decimal'
          }
        ]
      },
      number: {
        identifier  : 'number',
        rules: [
          {
            type   : 'number',
            prompt : 'Please enter a valid number'
          }
        ]
      },
      email: {
        identifier  : 'email',
        rules: [
          {
            type   : 'email',
            prompt : 'Please enter a valid e-mail'
          }
        ]
      },
      url: {
        identifier  : 'url',
        rules: [
          {
            type   : 'url',
            prompt : 'Please enter a url'
          }
        ]
      },
      regex: {
        identifier  : 'regex',
        rules: [
          {
            type   : 'regExp[/^[a-z0-9_-]{4,16}$/]',
            prompt : 'Please enter a 4-16 letter username'
          }
        ]
      }
    }
  })
;
```

#### Payment
Inputs can validate credit cards and other payment types.

| Card Name | Validation Name | Test Card Number |
|---|---|---|
| Visa | `visa` | 4565340519181845 |
| American Express | `amex` | 378282246310005 |
| Mastercard | `mastercard` | 5200828282828210 |
| Discover | `discover` | 6011111111111117 |
| Unionpay | `unionpay` | 6240008631401148 |
| JCB | `jcb` | 3530111333300000 |
| Diner's Club | `dinersClub` | 38520000023237 |
| Maestro | `maestro` | 6799990100000000019 |
| Laser | `laser` | 630490017740292441 |
| Visa Electron | `visaElectron` | 4917300800000000 |

```html
<form class="ui form segment">
  <div class="two fields">
    <div class="field">
      <label>Credit Card</label>
      <input name="card" type="text" value="4444444444444444">
    </div>
    <div class="field">
      <label>Certain Type</label>
      <input name="exact-card" type="text" value="4444444444444444">
    </div>
  </div>
  <div class="ui submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```
```javascript
$('.payment.example form')
  .form({
    on: 'blur',
    fields: {
      card: {
        identifier  : 'card',
        rules: [
          {
            type   : 'creditCard',
            prompt : 'Please enter a valid credit card'
          }
        ]
      },
      exactCard: {
        identifier  : 'exact-card',
        rules: [
          {
            type   : 'creditCard[visa,amex]',
            prompt : 'Please enter a visa or amex card'
          }
        ]
      }
    }
  })
;
```

#### Matching Fields
Fields can be required to match, or not match other fields. You may consider using this with [optional fields](#optional-fields).
```html
<form class="ui form">
  <div class="two fields">
    <div class="field">
      <label>Match 1</label>
      <input name="match1" type="text" value="same">
    </div>
    <div class="field">
      <label>Match 2</label>
      <input name="match2" type="text" value="different">
    </div>
  </div>
  <div class="two fields">
    <div class="field">
      <label>Different 1</label>
      <input name="different1" type="text" value="same">
    </div>
    <div class="field">
      <label>Different 2</label>
      <input name="different2" type="text" value="same">
    </div>
  </div>
  <div class="ui submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```
```javascript
$('.match.example form')
  .form({
    on: 'blur',
    fields: {
      match: {
        identifier  : 'match2',
        rules: [
          {
            type   : 'match[match1]',
            prompt : 'Please put the same value in both fields'
          }
        ]
      },
      different: {
        identifier  : 'different2',
        rules: [
          {
            type   : 'different[different1]',
            prompt : 'Please put different values for each field'
          }
        ]
      }
    }
  })
;
```

#### Length
Inputs can match against length of content
```html
<form class="ui form">
  <div class="field">
    <label>minLength</label>
    <textarea name="minLength" cols="5"></textarea>
  </div>
  <div class="field">
    <label>Exact Length</label>
    <input name="exactLength" type="text" value="12345">
  </div>
  <div class="field">
    <label>maxLength</label>
    <textarea name="maxLength" cols="5">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla metus leo, scelerisque quis pretium non, ultricies in dolor. Vivamus pulvinar odio at nisl egestas tempor. Quisque nec diam gravida, convallis massa et, aliquam purus. Nunc eget aliquet leo. Morbi sodales mi placerat volutpat rhoncus. Pellentesque sed leo eu risus rutrum suscipit ut dapibus est. Curabitur lacus diam, viverra mollis purus ut, facilisis consectetur dui. Etiam molestie suscipit ligula, vitae lacinia mi tempor ac. Pellentesque accumsan porttitor nisi. Sed ac metus ac arcu feugiat posuere. Curabitur eget pharetra felis. Donec consectetur felis sed iaculis vulputate. Sed mollis ultrices consequat.</textarea>
  </div>
  <div class="ui submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```
```javascript
$('.length.example form')
  .form({
    on: 'blur',
    fields: {
      minLength: {
        identifier  : 'minLength',
        rules: [
          {
            type   : 'minLength[100]',
            prompt : 'Please enter at least 100 characters'
          }
        ]
      },
      exactLength: {
        identifier  : 'exactLength',
        rules: [
          {
            type   : 'exactLength[6]',
            prompt : 'Please enter exactly 6 characters'
          }
        ]
      },
      maxLength: {
        identifier  : 'maxLength',
        rules: [
          {
            type   : 'maxLength[100]',
            prompt : 'Please enter at most 100 characters'
          }
        ]
      }
    }
  })
;
```

#### Specified Content
Validation rules can specify content that should or should not appear inside an input
```html
<form class="ui form">
  <div class="two fields">
    <div class="field">
      <label>is</label>
      <input name="is" type="text" value="dogs">
    </div>
    <div class="field">
      <label>isExactly</label>
      <input name="isExactly" type="text" value="Dog">
    </div>
  </div>
  <div class="two fields">
    <div class="field">
      <label>not</label>
      <input name="not" type="text" value="Dog">
    </div>
    <div class="field">
      <label>notExactly</label>
      <input name="notExactly" type="text" value="dog">
    </div>
  </div>
  <div class="two fields">
    <div class="field">
      <label>contains</label>
      <input name="contains" type="text" value="poodle">
    </div>
    <div class="field">
      <label>containsExactly</label>
      <input name="containsExactly" type="text" value="Dogbert">
    </div>
  </div>
  <div class="two fields">
    <div class="field">
      <label>doesntContain</label>
      <input name="doesntContain" type="text" value="Dogtown">
    </div>
    <div class="field">
      <label>doesntContainExactly</label>
      <input name="doesntContainExactly" type="text" value="dognapper">
    </div>
  </div>
  <div class="ui submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```
```javascript
$('.content.example form')
  .form({
    on: 'blur',
    fields: {
      is: {
        identifier  : 'is',
        rules: [
          {
            type   : 'is[dog]',
            prompt : 'Please enter exactly "dog"'
          }
        ]
      },
      isExactly: {
        identifier  : 'isExactly',
        rules: [
          {
            type   : 'isExactly[dog]',
            prompt : 'Please enter exactly "dog"'
          }
        ]
      },
      not: {
        identifier  : 'not',
        rules: [
          {
            type   : 'not[dog]',
            prompt : 'Please enter a value, but not "dog"'
          }
        ]
      },
      notExactly: {
        identifier  : 'notExactly',
        rules: [
          {
            type   : 'notExactly[dog]',
            prompt : 'Please enter a value, but not exactly "dog"'
          }
        ]
      },
      contains: {
        identifier  : 'contains',
        rules: [
          {
            type   : 'contains[dog]',
            prompt : 'Please enter a value containing "dog"'
          }
        ]
      },
      containsExactly: {
        identifier  : 'containsExactly',
        rules: [
          {
            type   : 'containsExactly[dog]',
            prompt : 'Please enter a value containing exactly "dog"'
          }
        ]
      },
      doesntContain: {
        identifier  : 'doesntContain',
        rules: [
          {
            type   : 'doesntContain[dog]',
            prompt : 'Please enter a value not containing "dog"'
          }
        ]
      },
      doesntContainExactly: {
        identifier  : 'doesntContainExactly',
        rules: [
          {
            type   : 'doesntContainExactly[dog]',
            prompt : 'Please enter a value not containing exactly "dog"'
          }
        ]
      }
    }
  })
;
```

#### Selection Count
Multiple selects can specify how many options should be allowed.
```html
<form class="ui form">
  <div class="three fields">
    <div class="field">
      <label>Exact Count</label>
      <select name="exactCount" multiple class="ui dropdown">
        <option value="">Select Values</option>
        <option value="1" selected>1</option>
        <option value="2">2</option>
        <option value="3">3</option>
        <option value="4">4</option>
        <option value="5">5</option>
      </select>
    </div>
    <div class="field">
      <label>Minimum Count</label>
      <select name="minCount" multiple class="ui dropdown">
        <option value="">Select Values</option>
        <option value="1" selected>1</option>
        <option value="2">2</option>
        <option value="3">3</option>
        <option value="4">4</option>
        <option value="5">5</option>
      </select>
    </div>
    <div class="field">
      <label>Maximum Count</label>
      <select name="maxCount" multiple class="ui dropdown">
        <option value="">Select Values</option>
        <option value="1" selected>1</option>
        <option value="2" selected>2</option>
        <option value="3" selected>3</option>
        <option value="4">4</option>
        <option value="5">5</option>
      </select>
    </div>
  </div>
  <div class="ui submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```
```javascript
$('.multi.example form')
  .form({
    on: 'blur',
    fields: {
      minCount: {
        identifier  : 'minCount',
        rules: [
          {
            type   : 'minCount[2]',
            prompt : 'Please select at least 2 values'
          }
        ]
      },
      maxCount: {
        identifier  : 'maxCount',
        rules: [
          {
            type   : 'maxCount[2]',
            prompt : 'Please select a max of 2 values'
          }
        ]
      },
      exactCount: {
        identifier  : 'exactCount',
        rules: [
          {
            type   : 'exactCount[2]',
            prompt : 'Please select 2 values'
          }
        ]
      }
    }
  })
```

### Form Examples

#### Adding Rules Programmatically
You can use the special behaviors `add field/rule`, `remove rule` and `remove field` to dynamically add or remove fields or rules.
> <div class="ui header">Adding Multiple Rules and Complex Rules</div>
> You can specify shorthand or full rule objects when adding rules. You can also specifiy fields as an array to modify multiple fields.
```javascript
// lets only validate username to start
$('.add.example .ui.form')
  .form({
    username: ['empty', 'minLength[5]']
  })
;
```
```javascript
// lets toggle some validation based on button
$('.add.example .ui.positive.button')
  .on('click', function() {
    $('.add.example .ui.form')
      // adding longform
      .form('add rule', 'gender', {
        rules: [
          {
            type   : 'empty',
            prompt : 'Entering your gender is necessary'
          }
        ]
      })
      // adding shorthand
      .form('add rule', 'password', ['empty', 'minLength[5]'])
    ;
  })
;
```
```javascript
$('.add.example .ui.negative.button')
  .on('click', function() {
    $('.add.example .ui.form')
      // removing multiple at once
      .form('remove fields', ['gender', 'password'])
    ;
  })
;
```
```html
<div class="ui positive button">Add Additional Validation</div>
<div class="ui negative button">Remove Additional Validation</div>
<form class="ui form segment">
  <div class="two fields">
    <div class="field">
      <label>Username</label>
      <input type="text" name="username">
    </div>
    <div class="field">
      <label>Password</label>
      <input type="password" name="password">
    </div>
  </div>
  <div class="two fields">
    <div class="field">
      <label>Gender</label>
      <div class="ui fluid selection dropdown">
        <input type="hidden" name="gender">
        <div class="default text">Gender</div>
        <i class="dropdown icon"></i>
        <div class="menu">
          <div class="item" data-value="1">Male</div>
          <div class="item" data-value="0">Female</div>
        </div>
      </div>
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui clear button">Clear</div>
  <div class="ui error message"></div>
</form>
```

#### Validating Dropdowns
[Dropdowns](/modules/dropdown.html) can also be validated like other form fields. Simply match the validation rule to the `input` or `select` associated with the dropdown
```
$('.ui.dropdown')
  .dropdown()
;
$('.ui.form')
  .form({
    fields: {
      gender: 'empty',
      name: 'empty'
    }
  })
;
```
```html
<form class="ui form segment">
  <div class="two fields">
    <div class="field">
      <label>Name</label>
      <input type="text" name="name">
    </div>
    <div class="field">
      <label>Gender</label>
      <div class="ui fluid selection dropdown">
        <input type="hidden" name="gender">
        <div class="default text">Gender</div>
        <i class="dropdown icon"></i>
        <div class="menu">
          <div class="item" data-value="1">Male</div>
          <div class="item" data-value="0">Female</div>
        </div>
      </div>
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
</form>
```

#### Using Server Name Attributes
Sometimes an integration requires you to use a specific value for `name`, or `id`. In these cases, you can match a form field using the `data-validate` property.
```
$('.ui.form')
  .form(
    fields: {
      name: 'empty'
    }
  })
;
```
```html
<form class="ui form segment">
  <div class="field">
    <label>Name</label>
    <input type="text" name="SERVER_REQUIRED_NAME" data-validate="name">
  </div>
  <div class="ui primary submit button">Submit</div>
</form>
```

#### Dependent Fields
You can specify validation fields to only be used when other fields are present. Simply add `depends: 'id'` with the ID of the field that must be non-blank for this rule to evaluate.
```
$('.ui.form')
  .form({
    fields: {
      yearsPracticed: {
        identifier : 'yearsPracticed',
        depends    : 'isDoctor',
        rules      : [
          {
            type   : 'empty',
            prompt : 'Please enter the number of years you have been a doctor'
          }
        ]
      }
    }
  })
;
```
```html
<form class="ui form segment">
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" name="isDoctor" />
      <label>Are you a doctor?</label>
    </div>
  </div>
  <div class="field">
    <label>How long have you been a medical professional</label>
    <input type="text" name="yearsPracticed">
  </div>
  <div class="ui divider"></div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```

#### Optional Fields
Adding the parameter `optional: true` will only add your validation rules when the field is **not empty**.
```
$('.ui.form')
  .form({
    fields: {
      email: {
        identifier : 'email',
        rules: [
          {
            type   : 'email',
            prompt : 'Please enter a valid e-mail'
          }
        ]
      },
      ccEmail: {
        identifier : 'cc-email',
        optional   : true,
        rules: [
          {
            type   : 'email',
            prompt : 'Please enter a valid second e-mail'
          }
        ]
      }
    }
  })
;
```
```html
<form class="ui form segment">
  <p>Your tickets are all ready to print. Where would you like to send a receipt?</p>
  <div class="fields">
    <div class="ten wide field">
      <label>E-mail</label>
      <input type="text" name="email">
    </div>
    <div class="six wide field">
      <label>Additional E-mail</label>
      <input type="text" name="cc-email">
    </div>
  </div>
  <div class="ui divider"></div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```

#### Setting Site Defaults
You can specify site wide validation settings by modifying `$.fn.form.settings.defaults` that will apply on any form validation if the field appears in the form**.
```javascript
$.fn.form.settings.defaults = {
  email: {
    identifier : 'email',
    rules: [
      {
        type   : 'email',
        prompt : 'Please enter a valid e-mail'
      }
    ]
  },
  // this form doesn't have a cc email but it will not produce an error
  ccEmail: {
    identifier : 'cc-email',
    optional   : true,
    rules: [
      {
        type   : 'email',
        prompt : 'Please enter a valid second e-mail'
      }
    ]
  },
};
```
```html
<form class="ui form segment">
  <p>Your tickets are all ready to print. Where would you like to send a receipt?</p>
  <div class="ten wide field">
    <label>E-mail</label>
    <input type="text" name="email">
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```

#### Displaying Error Messages
Forms that contain a [ui message](/collections/message.html) error block will automatically be filled in with form validation information.
> The template for error messages can be modified by adjusting settings.template.error
```html
<form class="ui form segment">
  <p>Let's go ahead and get you signed up.</p>
  <div class="two fields">
    <div class="field">
      <label>First Name</label>
      <input placeholder="First Name" name="first-name" type="text">
    </div>
    <div class="field">
      <label>Last Name</label>
      <input placeholder="Last Name" name="last-name" type="text">
    </div>
  </div>
  <div class="field">
    <label>Username</label>
    <input placeholder="Username" name="username" type="text">
  </div>
  <div class="field">
    <label>Password</label>
    <input type="password" name="password">
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" name="terms" />
      <label>I agree to the Terms and Conditions</label>
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
  <div class="ui error message"></div>
</form>
```

#### Validating on Blur and other Events
Validation messages can also appear inline. UI Forms automatically format [labels](/elements/label.html) with the class name `prompt`. These validation prompts are also set to appear on input change instead of form submission.
> This example also uses a different validation event. Each element will be validated on input blur instead of the default form submit.
```javascript
$('.ui.form')
  .form({
    fields : validationRules,
    inline : true,
    on     : 'blur'
  })
;
```
```html
<form class="ui form segment">
  <p>Let's go ahead and get you signed up.</p>
  <div class="two fields">
    <div class="field">
      <label>First Name</label>
      <input placeholder="First Name" name="first-name" type="text">
    </div>
    <div class="field">
      <label>Last Name</label>
      <input placeholder="Last Name" name="last-name" type="text">
    </div>
  </div>
  <div class="field">
    <label>Username</label>
    <input placeholder="Username" name="username" type="text">
  </div>
  <div class="field">
    <label>Password</label>
    <input type="password" name="password">
  </div>
  <div class="inline field">
    <div class="ui checkbox">
      <input type="checkbox" name="terms" />
      <label>I agree to the Terms and Conditions</label>
    </div>
  </div>
  <div class="ui primary submit button">Submit</div>
</form>
```

#### Creating Custom Validation
You can use multiple arbitrary rules to validate a form
```
$('.ui.form')
  .form({
    fields: {
      dog: {
        identifier: 'dog',
        rules: [
          {
            type: 'empty',
            prompt: 'You must have a dog to add'
          },
          {
            type: 'contains[fluffy]',
            prompt: 'I only want you to add fluffy dogs!'
          },
          {
            type: 'not[mean]',
            prompt: 'Why would you add a mean dog to the list?'
          }
        ]
      }
    }
  })
;
```
```html
<form class="ui form segment">
  <p>Let's go ahead and get you signed up.</p>
  <div class="field">
    <label>Dog</label>
    <input placeholder="Dog" name="dog" type="text">
  </div>
  <div class="ui primary submit button">
    <i class="add icon"></i>
    Add Dog
  </div>
  <div class="ui error message"></div>
</form>
```

## Behaviors

All the following behaviors can be called using the syntax

```javascript
$('.ui.checkbox').checkbox(behavior, argumentOne, argumentTwo...);
```

```html
<table class="ui definition celled table">
  <tr>
    <td>toggle</td>
    <td>Switches a checkbox from current state</td>
  </tr>
  <tr>
    <td>check</td>
    <td>Set a checkbox state to checked</td>
  </tr>
  <tr>
    <td>uncheck</td>
    <td>Set a checkbox state to unchecked</td>
  </tr>
  <tr>
    <td>indeterminate</td>
    <td>Set as indeterminate checkbox</td>
  </tr>
  <tr>
    <td>determinate</td>
    <td>Set as determinate checkbox</td>
  </tr>
  <tr>
    <td>enable</td>
    <td>Enable interaction with a checkbox</td>
  </tr>
  <tr>
    <td>set checked</td>
    <td>Set a checkbox state to checked without callbacks</td>
  </tr>
  <tr>
    <td>set unchecked</td>
    <td>Set a checkbox state to unchecked without callbacks</td>
  </tr>
  <tr>
    <td>set indeterminate</td>
    <td>Set as indeterminate checkbox without callbacks</td>
  </tr>
  <tr>
    <td>set determinate</td>
    <td>Set as determinate checkbox without callbacks</td>
  </tr>
  <tr>
    <td>set enabled</td>
    <td>Enable interaction with a checkbox without callbacks</td>
  </tr>
  <tr>
    <td>set disabled</td>
    <td>Disable interaction with a checkbox without callbacks</td>
  </tr>
  <tr>
    <td>attach events(selector, behavior)</td>
    <td>Attach checkbox events to another element</td>
  </tr>
  <tr>
    <td>is radio</td>
    <td>Returns whether element is radio selection</td>
  </tr>
  <tr>
    <td>is checked</td>
    <td>Returns whether element is currently checked</td>
  </tr>
  <tr>
    <td>is unchecked</td>
    <td>Returns whether element is not checked</td>
  </tr>
  <tr>
    <td>can change</td>
    <td>Returns whether element is able to be changed</td>
  </tr>
  <tr>
    <td>should allow check</td>
    <td>Returns whether element can be checked (checking if already checked or `beforeChecked` would cancel)</td>
  </tr>
  <tr>
    <td>should allow uncheck</td>
    <td>Returns whether element can be unchecked (checking if already unchecked or `beforeUnchecked` would cancel)</td>
    </tr>
  <tr>
    <td>should allow determinate</td>
    <td>Returns whether element can be determinate (checking if already determinate or `beforeDeterminate` would cancel)</td>
  </tr>
  <tr>
    <td>should allow indeterminate</td>
    <td>Returns whether element can be indeterminate (checking if already indeterminate or `beforeIndeterminate` would cancel)</td>
  </tr>
  <tr>
    <td>can uncheck</td>
    <td>Returns whether element is able to be unchecked</td>
  </tr>
</table>
```

## Settings

#### Form Settings
Form settings modify the form validation behavior

```html
<table class="ui celled sortable definition table">
  <thead>
    <th>Setting</th>
    <th class="six wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>keyboardShortcuts</td>
      <td>true</td>
      <td>Adds keyboard shortcuts for enter and escape keys to submit form and blur fields respectively</td>
    </tr>
    <tr>
      <td>on</td>
      <td>submit</td>
      <td>Event used to trigger validation. Can be either **submit**, **blur** or **change**.</td>
    </tr>
    <tr>
      <td>revalidate</td>
      <td>true</td>
      <td>If set to true will revalidate fields with errors on input change</td>
    </tr>
    <tr>
      <td>delay</td>
      <td>true</td>
      <td>Delay from last typed letter to validate a field when using `on: change` or when revalidating a field.</td>
    </tr>
    <tr>
      <td>inline</td>
      <td>false</td>
      <td>Adds inline error on field validation error</td>
    </tr>
    <tr>
      <td>transition</td>
      <td>
        scale
      </td>
      <td>Named transition to use when animating validation errors. Fade and slide down are available without including [ui transitions](/modules/transition.html)</td>
    </tr>
    <tr>
      <td>duration</td>
      <td>150</td>
      <td>Animation speed for inline prompt</td>
    </tr>
  </tbody>
</table>
```

#### Form Prompts
Settings to modify default form prompts

```html
<table class="ui celled sortable definition table">
  <thead>
    <th class="collapsing">Setting</th>
    <th>Default</th>
  </thead>
  <tbody>
    <tr>
      <td>text</td>
      <td>
        <div class="code">
text: {
  unspecifiedRule  : 'Please enter a valid value',
  unspecifiedField : 'This field'
}
        </div>
      </td>
    </tr>
    <tr>
      <td>prompt</td>
      <td>
        <div class="code">
prompt: {
  empty                : '{name} must have a value',
  checked              : '{name} must be checked',
  email                : '{name} must be a valid e-mail',
  url                  : '{name} must be a valid url',
  regExp               : '{name} is not formatted correctly',
  integer              : '{name} must be an integer',
  decimal              : '{name} must be a decimal number',
  number               : '{name} must be a number',
  is                   : '{name} must be '{ruleValue}'',
  isExactly            : '{name} must be exactly '{ruleValue}'',
  not                  : '{name} cannot be set to '{ruleValue}'',
  notExactly           : '{name} cannot be set to exactly '{ruleValue}'',
  contain              : '{name} cannot contain '{ruleValue}'',
  containExactly       : '{name} cannot contain exactly '{ruleValue}'',
  doesntContain        : '{name} must contain  '{ruleValue}'',
}
        </div>
      </td>
    </tr>
  </tbody>
</table>

## === state.md ===

# State

State allows elements to trigger actions on a server

## Overview

#### Activate Elements Programmatically
State is designed to make the process of integrating data sources to UI components seamless, [tying State request state](#api-state-management) to UI states automatically.

For example adding an State behavior to an [input](/elements/input.html) will occur `oninput`, while a [button](/elements/button.html), will query the server `onclick`.
```html
<div class="ui icon input">
  <i class="search icon"></i>
  <input type="text" placeholder="Type here...">
</div>
<div class="ui hidden divider"></div>
<div class="ui primary button">Click Me</div>
<div class="ui disabled button">Disabled</div>
```

## Usage

## Behavior

All the following behaviors can be called using the syntax:
```javascript
$('.your.element')
  .state('behavior name', argumentOne, argumentTwo)
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
      <td>Execute query using existing State settings</td>
    </tr>
    <tr>
      <td>add url data(url, data)</td>
      <td>Adds data to existing templated url and returns full url string</td>
    </tr>
    <tr>
      <td>get request</td>
      <td>Gets promise for current State request</td>
    </tr>
    <tr>
      <td>abort</td>
      <td>Aborts current State request</td>
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
      <td>Gets event that State request will occur on</td>
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
      <td>Removes State settings from the page and all events</td>
    </tr>
  </tbody>
</table>
```

## Settings

#### Behavior
```html
<table class="ui sortable celled definition table">
  <thead>
    <th class="three wide"></th>
    <th class="three wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>automatic</td>
      <td>true</td>
      <td>Whether possible states should be determined automatically based on type of UI</td>
    </tr>
    <tr>
      <td>sync</td>
      <td>false</td>
      <td>When set to `true` and state is used on multiple elements, state will be synced across all bound elements.</td>
    </tr>
    <tr>
      <td>flashDuration</td>
      <td>1000</td>
      <td>Default duration to show text when using `flash text`.</td>
    </tr>
    <tr>
      <td>context</td>
      <td>false</td>
      <td>When set to a selector, will use a delegated pattern to bind events from this element.</td>
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
      <td>Named State action for query, originally specified in $.fn.settings.state</td>
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
      <td>mockResponse</td>
      <td>false</td>
      <td>Can be set to a javascript object which will be returned automatically instead of requesting JSON from server </td>
      <td>{} or false</td>
    </tr>
    <tr>
      <td>mockResponseAsync(settings, callback)</td>
      <td>false</td>
      <td>When specified, this function can be used to retrieve content from a server and return it asynchronously **instead of** a standard AJAX call. The callback function should return the server response.</td>
      <td>function or false</td>
    </tr>
    <tr>
      <td>method</td>
      <td>get</td>
      <td>Method for transmitting request to server</td>
      <td>post, get</td>
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
      <td>Callback that occurs when request is made. Receives both the state success promise and the xhr request promise.</td>
    </tr>
    <tr>
      <td>onResponse(response)</td>
      <td>state context</td>
      <td>Allows modifying the server's response before parsed by other callbacks to determine State event success</td>
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
      <td>State</td>
      <td>Name used in log statements</td>
    </tr>
    <tr>
      <td>namespace</td>
      <td>state</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>regExp</td>
      <td>
        <div class="code">
regExp  : {
  required: /{\$*[A-z0-9]+}/g,
  optional: /{\/\$*[A-z0-9]+}/g,
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
      <td>Metadata used to store xhr and response promise</td>
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
  exitConditions    : 'State Request Aborted. Exit conditions met',
  JSONParse         : 'JSON could not be parsed during error handling',
  legacyParameters  : 'You are using legacy State success callback names',
  missingAction     : 'State action used but no url was defined',
  missingSerialize  : 'Required dependency jquery-serialize-object missing, using basic serialize',
  missingURL        : 'No URL specified for state event',
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

## === visibility.md ===

# Visibility

Visibility provides a set of callbacks for when a content appears in the viewport

## Introduction

### Introduction
Visibility provides a set of callbacks that can be attached to any element and trigger when a specific visibility event occurs.

There are a variety of uses for attaching events to visibility. Here are some of the more common ones.

*   Infinite Scroll
    *   You want to start loading more content into a container when a user is partially finished scrolling through the content
*   Lazy Loading Images
    *   You want to start loading an image just before it is visible to a user
*   Reactive Content
    *   You want an element to change based on how far a user has scrolled
*   Sticky Headers
    *   You want an element to fix itself to the viewport when it is passed, and return to its original static position afterwards
*   Event Tracking
    *   You want to attach analytics events that match a users engagement with content, for example, to log to Google Analytics when a blog post is 30% read.

## Usage

#### How To Use
Visibility provides a set of callbacks which can be used to attach events to an element's position on screen.

Each scroll change will trigger an animation frame request that will fire callbacks for an element.

> The following examples use sticky columns to help display data alongside each example. Please consult the [sticky documentation](/modules/sticky.html) for usage examples.
```javascript
// some example callbacks
$('.demo.segment')
  .visibility({
    onTopVisible: function(calculations) {
      // top is on screen
    },
    onTopPassed: function(calculations) {
      // top of element passed
    },
    onUpdate: function(calculations) {
      // do something whenever calculations adjust
      updateTable(calculations);
    }
  })
;
```
```html
<div class="two column equal height ui grid">
  <div class="row">
    <div class="main column">
      <div class="ui first demo segment">
        <img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
    </div>
    <div class="column">
      <div class="ui sticky">
        <table class="ui basic celled sortable two column table">
          <thead>
            <th>Calculation</th>
            <th>Value</th>
          </thead>
          <tbody>
            <tr class="pixelsPassed">
              <td>pixelsPassed</td>
              <td></td>
            </tr>
            <tr class="percentagePassed">
              <td>percentagePassed</td>
              <td></td>
            </tr>
            <tr class="fits">
              <td>fits</td>
              <td></td>
            </tr>
            <tr class="width">
              <td>width</td>
              <td></td>
            </tr>
            <tr class="height">
              <td>height</td>
              <td></td>
            </tr>
            <tr class="onScreen">
              <td>onScreen</td>
              <td></td>
            </tr>
            <tr class="offScreen">
              <td>offScreen</td>
              <td></td>
            </tr>
            <tr class="passing">
              <td>passing</td>
              <td></td>
            </tr>
            <tr class="topVisible">
              <td>topVisible</td>
              <td></td>
            </tr>
            <tr class="bottomVisible">
              <td>bottomVisible</td>
              <td></td>
            </tr>
            <tr class="topPassed">
              <td>topPassed</td>
              <td></td>
            </tr>
            <tr class="bottomPassed">
              <td>bottomPassed</td>
              <td></td>
            </tr>
          </tr>
        </table>
      </div>
    </div>
  </div>
</div>
```

#### Changing Callback Frequency

Visibility's default settings will only have each callback occur **the first time** which the conditions are met. On subsequent occurences the event will not fire.

Setting `continuous: true` will make the callback fire **anytime the callback conditions are met**. So for example if you set a "top visible" callback, this callback will fire with each change in scroll when the top is visible on the page.

Setting `once: false` will make the callback fire each time a callback **becomes true**. So, using the same "top visible" example, the callback will fire each time the top of an element is passed. Even if you scroll back up and pass the element again

```html
<div class="two column equal height ui grid">
  <div class="row">
    <div class="main column">
      <div class="ui demo segment">
        <img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
        <div class="ui divider"></div>
        <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      </div>
    </div>
    <div class="column">
      <div class="ui sticky segments">
        <div class="ui segment">
          <div class="ui right floated compact clear button">
            Clear
          </div>
          <div class="ui toggle checkbox">
            <input type="checkbox" checked name="once" />
            <label>Once</label>
          </div>
          <div class="ui divider"></div>
          <div class="ui toggle checkbox">
            <input type="checkbox" name="continuous" />
            <label>Continuous</label>
          </div>
        </div>
        <div class="ui segment">
          Event Log
        </div>
        <div class="ui segment">
          <pre class="console"></pre>
        }
      </div>
    </div>
  </div>
</div>
```

#### Callbacks

Callbacks are separated into two categories. Standard events will occur the first animation frame where the conditions evaluated to true.

#### Standard Events
```html
<table class="ui celled definition table">
  <thead>
    <tr>
      <th class="three wide">Event</th>
      <th class="six wide">Occurs</th>
      <th>Pseudocode</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        onOnScreen
      </td>
      <td>
        Any part of element is in current scroll viewport
      </td>
      <td>
        <div class="code" data-type="javascript">screen.bottom >= element.top && screen.bottom <= element.bottom</div>
      </td>
    </tr>
    <tr>
      <td>
        onOffScreen
      </td>
      <td>
        No part of element is in current scroll viewport
      </td>
      <td>
        <div class="code" data-type="javascript">screen.bottom <= element.top || screen.top >= element.bottom</div>
      </td>
    </tr>
    <tr>
      <td>
        onTopVisible
      </td>
      <td>
        Element's top edge has passed bottom of screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.bottom >= element.top</div>
      </td>
    </tr>
    <tr>
      <td>
        onTopPassed
      </td>
      <td>
        Element's top edge has passed top of the screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.top >= element.top</div>
      </td>
    </tr>
    <tr>
      <td>
        onBottomVisible
      </td>
      <td>
        Element's bottom edge has passed bottom of screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.bottom >= element.top</div>
      </td>
    </tr>
    <tr>
      <td>
        onPassing
      </td>
      <td>
        Any part of an element is visible on screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.bottom >= element.top && screen.top < element.bottom</div>
      </td>
    </tr>
    <tr>
      <td>
        onBottomPassed
      </td>
      <td>
        Element's bottom edge has passed top of screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.top >= element.bottom</div>
      </td>
    </tr>
  </tbody>
</table>
```

#### Grouped Events
`onPassed` allows you to specify a collection of callbacks that occur after different percentages or pixels of an element are passed
```html
<table class="ui celled definition table">
  <thead>
    <tr>
      <th class="three wide">Event</th>
      <th class="six wide">Occurs</th>
      <th>Example</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        onPassed {}
      </td>
      <td>
        A distance from the top of an element's content has been passed, either as a percentage or in pixels
      </td>
      <td>
        <div class="code" data-type="javascript">
        onPassed: {
          40: function() {
            // do something when having passed 40 pixels.
          },
          '80%': function() {
            // do something at 80%
          }
        }
        </div>
      </td>
    </tr>
  </tbody>
</table>
```

#### Reverse Events
Reverse events will occur under the same conditions but as a user scrolls back up the page.
```html
<table class="ui celled definition table">
  <thead>
    <tr>
      <th class="three wide">Event</th>
      <th class="six wide">Occurs</th>
      <th>Pseudocode</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        onTopVisibleReverse
      </td>
      <td>
        Element's top edge has not passed bottom of screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.bottom >= element.top</div>
      </td>
    </tr>
    <tr>
      <td>
        onTopPassedReverse
      </td>
      <td>
        Element's top edge has not passed top of the screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.top >= element.top</div>
      </td>
    </tr>
    <tr>
      <td>
        onBottomVisibleReverse
      </td>
      <td>
        Element's bottom edge has not passed bottom of screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.bottom >= element.top</div>
      </td>
    </tr>
    <tr>
      <td>
        onPassingReverse
      </td>
      <td>
        Element's top has not passed top of screen but bottom has
      </td>
      <td>
        <div class="code" data-type="javascript">screen.bottom >= element.top && screen.top < element.bottom</div>
      </td>
    </tr>
    <tr>
      <td>
        onBottomPassedReverse
      </td>
      <td>
        Element's bottom edge has not passed top of screen
      </td>
      <td>
        <div class="code" data-type="javascript">screen.top >= element.bottom</div>
      </td>
    </tr>
  </tbody>
</table>
```

## Behaviors

Visibility includes several useful behaviors for interacting with the component
```html
<table class="ui celled definition table">
  <thead>
    <tr>
      <th class="three wide">Behavior</th>
      <th class="six wide">Usage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        disable callbacks
      </td>
      <td>
        Disable callbacks temporarily. This is useful if you need to adjust scroll position and do not want to trigger callbacks during the position change.
      </td>
    </tr>
    <tr>
      <td>
        enable callbacks
      </td>
      <td>
        Re-enable callbacks
      </td>
    </tr>
    <tr>
      <td>
        is on screen
      </td>
      <td>
        Returns whether element is on screen
      </td>
    </tr>
    <tr>
      <td>
        is off screen
      </td>
      <td>
        Returns whether element is off screen
      </td>
    </tr>
    <tr>
      <td>
        get pixels passed
      </td>
      <td>
        Returns number of pixels passed in current element from top of element
      </td>
    </tr>
    <tr>
      <td>
        get element calculations
      </td>
      <td>
        Returns element calculations as object
      </td>
    </tr>
    <tr>
      <td>
        get screen calculations
      </td>
      <td>
        Returns screen calculations as object
      </td>
    </tr>
    <tr>
      <td>
        get screen size
      </td>
      <td>
        Returns screen size as object
      </td>
    </tr>
  </tbody>
</table>
```

## Examples

#### Infinite Scroll
As an alternative to pagination you can use `onBottomVisible` to load content automatically when the bottom of a container is reached.

```javascript
$('.infinite.example .demo.segment')
  .visibility({
    once: false,
    // update size when new content loads
    observeChanges: true,
    // load content on bottom edge visible
    onBottomVisible: function() {
      // loads a max of 5 times
      window.loadFakeContent();
    }
  })
;
```
```html
<div class="ui demo segment">
  <h3 class="ui dividing center aligned header">Infinite Scroll Example</h3>
  <img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
  <div class="ui divider"></div>
  <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
  <div class="ui divider"></div>
  <img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
  <div class="ui divider"></div>
  <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
  <div class="ui divider"></div>
  <div class="ui large centered inline text loader">
    Adding more content...
  </div>
</div>
```

#### Lazy Loading Images
Visibility includes several shortcuts for setting up common visibility events. Using the setting `type: 'image'` will automatically attach events to an images `topVisible` to load the contents of `data-src` as `src`.

You can specify a placeholder image as the current `src` to make sure content doesn't jump when an image loads, or you can specify no placeholder and have the image appear.

By default images will appear without animation, however you can also specify a named [transition](/modules/transition.html), and a duration that should be used for animating the image into view

```javascript
$('.demo.items .image img')
  .visibility({
    type       : 'image',
    transition : 'fade in',
    duration   : 1000
  })
;
```
```html
<div class="ui divided demo items">
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/elliot.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Elliot Fu</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/helen.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Helen Troy</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    }
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/jenny.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Jenny Hess</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/veronika.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Veronika Ossi</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/stevie.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Stevie</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/steve.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Steve Jobes</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/ade.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Ade</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/chris.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Chris</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/joe.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Joe Henderson</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
  <div class="item">
    <div class="image">
      <img src="/images/wireframe/square-image.png" data-src="/images/avatar/large/laura.jpg">
    </div>
    <div class="content">
      <h2 class="ui header">Laura</h2>
      <img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
      <div class="ui primary button">Add Friend</div>
      <div class="ui right floated button">View <i class="right chevron icon"></i></div>
    </div>
  </div>
</div>
```

#### Gradual Changes
Each callback receives all calculated values as its first parameter, allowing you to adjust an element using

```javascript
$('.changing.example .demo.segment')
  .visibility({
    once       : false,
    continuous : true,
    onPassing  : function(calculations) {
      var newColor = 'rgba(0, 0, 0, ' + calculations.percentagePassed +')';
      $(this)
        .css('background-color', newColor)
      ;
    }
  })
;
```
```html
<div class="ui demo segment" style="height: 1000px;"></div>
```

#### Fixing Content To Viewport
Visibility provides a lightweight method for sticking content to a page's viewport. Using `type: fixed` will add the class `fixed` after an element is passed in the viewport. Using this class name you can assign special layout conditions to an item once it is passed.

Using the special visibility type `fixed` will automatically create a placeholder element, which will be shown or hidden after an element is passed, to ensure that the page's position does not change when the element is "fixed" and removed from normal layout flow.

In this example, when an element is passed we fix it to the viewport, add a background color and box shadow so that it can float above other content. We also show an adjacent placeholder element which makes sure that content stays offset the same as if the menu was still in content flow

> You may need to adjust your fixed content's `z-index` to ensure it appears above other page content.
```javascript
$('.overlay.example .overlay')
  .visibility({
    type   : 'fixed',
    offset : 15 // give some space from top of screen
  })
;
```
```css
.visibility.example .overlay {
  background-color: #FFFFFF;
  padding: 0em;
  box-shadow: 0px 0px 0px rgba(0, 0, 0, 0);
  transition: all 0.5s ease;
  background: transparent;
}
/* change style */
.visibility.example .fixed.overlay {
  position: fixed;
  padding: 1em;
  box-shadow: 0px 0px 6px rgba(0, 0, 0, 0.2);
}
```
```html
<div class="overlay">
  <div class="ui secondary menu">
    <a class="item">
      <i class="sidebar icon"></i> Menu
    </a>
    <a class="item">Option 1</a>
    <a class="item">Option 2</a>
    <a class="item">Option 3</a>
  </div>
</div>
<div class="ui clearing divider"></div>
<img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
<div class="ui divider"></div>
<img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
<div class="ui divider"></div>
<img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
<div class="ui divider"></div>
<img src="/images/wireframe/paragraph.png" class="ui wireframe image">
<div class="ui divider"></div>
<img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
<div class="ui divider"></div>
<img src="/images/wireframe/centered-paragraph.png" class="ui wireframe image">
<div class="ui divider"></div>
<img src="/images/wireframe/short-paragraph.png" class="ui wireframe image">
<div class="ui divider"></div>
<img src="/images/wireframe/media-paragraph.png" class="ui wireframe image">
<div class="ui divider"></div>
<img src="/images/wireframe/paragraph.png" class="ui wireframe image">
```

## Settings

#### Functionality
Settings to configure visibility behavior
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th>Setting</th>
    <th class="four wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>once</td>
      <td>true</td>
      <td>When set to false a callback will occur each time an element **passes the threshold** for a condition.</td>
    </tr>
    <tr>
      <td>continuous</td>
      <td>false</td>
      <td>When set to true a callback will occur anytime an element **passes a condition**  not just immediately after the threshold is met.</td>
    </tr>
    <tr>
      <td>type</td>
      <td>false</td>
      <td>Set to `image` to load images when on screen. Set to `fixed` to add class name `fixed` when passed.</td>
    </tr>
    <tr>
      <td>initialCheck</td>
      <td>true</td>
      <td>Whether visibility conditions should be checked immediately on init</td>
    </tr>
    <tr>
      <td>context</td>
      <td>window</td>
      <td>The scroll context visibility should use.</td>
    </tr>
    <tr>
      <td>refreshOnLoad</td>
      <td>true</td>
      <td>Whether visibility conditions should be checked on window `load`. This ensures that after images load content positions will be updated correctly.</td>
    </tr>
    <tr>
      <td>refreshOnResize</td>
      <td>true</td>
      <td>Whether visibility conditions should be checked on window `resize`. Useful when content resizes causes continuous changes in position</td>
    </tr>
    <tr>
      <td>checkOnRefresh</td>
      <td>true</td>
      <td>Whether visibility conditions should be checked on calls to `refresh`. These calls can be triggered from either `resize`, `load` or manually calling `$('.foo').visibility('refresh')`</td>
    </tr>
    <tr>
      <td>zIndex</td>
      <td>1</td>
      <td>Specify a z-index when using `type: 'fixed'`. <div class="ui teal horizontal label">New in 2.2</div></td>
    </tr>
    <tr>
      <td>offset</td>
      <td>0</td>
      <td>Value that context `scrollTop` should be adjusted in pixels. Useful for making content appear below content fixed to the page.</td>
    </tr>
    <tr>
      <td>includeMargin</td>
      <td>false</td>
      <td>Whether element calculations should include its margin</td>
    </tr>
    <tr>
      <td>throttle</td>
      <td>false</td>
      <td>When set to an integer, scroll position will be debounced using this ms value. `false` will debounce with `requestAnimationFrame`.</td>
    </tr>
    <tr>
      <td>observeChanges</td>
      <td>true</td>
      <td>Whether to automatically refresh content when changes are made to the element's DOM subtree </td>
    </tr>
    <tr>
      <td>transition</td>
      <td>false</td>
      <td>When using `type: image` allows you to specify transition when showing a loaded image</td>
    </tr>
    <tr>
      <td>duration</td>
      <td>1000</td>
      <td>When using `type: image` allows you to specify transition duration</td>
    </tr>
  </tbody>
</table>
```

#### Visibility Callbacks
Callbacks that occur on named visibility events
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <tr>
      <th class="four wide"></th>
      <th>Context</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>onTopVisible</td>
      <td>$element</td>
      <td>Element's top edge has passed bottom of screen</td>
    </tr>
    <tr>
      <td>onTopPassed</td>
      <td>$element</td>
      <td>Element's top edge has passed top of the screen</td>
    </tr>
    <tr>
      <td>onBottomVisible</td>
      <td>$element</td>
      <td>Element's bottom edge has passed bottom of screen</td>
    </tr>
    <tr>
      <td>onPassing</td>
      <td>$element</td>
      <td>Any part of an element is visible on screen</td>
      </td>
    </tr>
    <tr>
      <td>onBottomPassed</td>
      <td>$element</td>
      <td>Element's bottom edge has passed top of screen</td>
    </tr>
    <tr>
      <td>onTopVisibleReverse</td>
      <td>$element</td>
      <td>Element's top edge has not passed bottom of screen</td>
    </tr>
    <tr>
      <td>onTopPassedReverse</td>
      <td>$element</td>
      <td>Element's top edge has not passed top of the screen</td>
    </tr>
    <tr>
      <td>onBottomVisibleReverse</td>
      <td>$element</td>
      <td>Element's bottom edge has not passed bottom of screen</td>
    </tr>
    <tr>
      <td>onPassingReverse</td>
      <td>$element</td>
      <td>Element's top has not passed top of screen but bottom has</td>
      </td>
    </tr>
    <tr>
      <td>onBottomPassedReverse</td>
      <td>$element</td>
      <td>Element's bottom edge has not passed top of screen</td>
    </tr>
  </tbody>
</table>
```

#### Image Callbacks
Callbacks that occur only when using [type: 'fixed'](#lazy-loading-images)

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <tr>
      <th class="four wide"></th>
      <th>Context</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>onLoad</td>
      <td>img</td>
      <td>Occurs after an image has completed loading</td>
    </tr>
    <tr>
      <td>onAllLoaded</td>
      <td>last loaded img</td>
      <td>Occurs after all `img` initialized at the same time have loaded.</td>
    </tr>
  </tbody>
</table>
```

#### Fixed Callbacks
Callbacks that occur only when using [type: 'fixed'](#fixing-content-to-viewport)

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <tr>
      <th class="four wide"></th>
      <th>Context</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>onFixed</td>
      <td>$element</td>
      <td>Occurs after element has been assigned position fixed</td>
    </tr>
    <tr>
      <td>onUnfixed</td>
      <td>$element</td>
      <td>Occurs after element has been removed from fixed position</td>
    </tr>
  </tbody>
</table>
```

#### Utility Callbacks
Callbacks that occur on named visibility events

```html
<table class="ui celled sortable definition table segment">
  <thead>
    <tr>
      <th class="four wide"></th>
      <th>Context</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>onUpdate(calculations)</td>
      <td>$element</td>
      <td>Occurs each time an elements calculations are updated</td>
    </tr>
    <tr>
      <td>onRefresh</td>
      <td>$element</td>
      <td>Occurs whenever element's visibility is refreshed</td>
    </tr>
  </tbody>
</table>
```

#### DOM Settings
DOM settings specify how this module should interface with the DOM
```html
<table class="ui celled sortable definition table segment">
  <thead>
    <th class="three wide">Setting</th>
    <th class="six wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>namespace</td>
      <td>visibility</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
className : {
  fixed     : 'fixed',
}
        </div>
      </td>
      <td>Class names used to attach style to state</td>
    </tr>
  </tbody>
</table>
```

#### Debug Settings
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
      <td>Visibility</td>
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
error : {
  method : 'The method you called is not defined.',
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
