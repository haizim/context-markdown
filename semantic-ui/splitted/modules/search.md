# Search

A search module allows a user to query for results from a selection of data

## Definition

#### Standard
A search can display a set of results
```html
<div class="ui search">
  <input class="prompt" type="text" placeholder="Common passwords...">
  <div class="results"></div>
</div>
```
> Using a [ui input](/elements/input.html) allows you to use additional input types, like this icon input
```html
<div class="ui search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Common passwords...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```

#### Category
A search can display results from remote content ordered by categories
```html
<div class="ui category search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search animals...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```

#### Local Search
A search can look for results inside a static local source.
> By default, results will return content first that begin with the query text, but also afterward content that matches the query anywhere inside. To disable full text search you can specify in settings `fullTextSearch: false`.
```html
<div class="ui search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search countries...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```
```javascript
$('.ui.search')
  .search({
    source: content
  })
;
```
```javascript
var content = [
  { title: 'Andorra' },
  { title: 'United Arab Emirates' },
  { title: 'Afghanistan' },
  { title: 'Antigua' },
  { title: 'Anguilla' },
  { title: 'Albania' },
  { title: 'Armenia' },
  { title: 'Netherlands Antilles' },
  { title: 'Angola' },
  { title: 'Argentina' },
  { title: 'American Samoa' },
  { title: 'Austria' },
  { title: 'Australia' },
  { title: 'Aruba' },
  { title: 'Aland Islands' },
  { title: 'Azerbaijan' },
  { title: 'Bosnia' },
  { title: 'Barbados' },
  { title: 'Bangladesh' },
  { title: 'Belgium' },
  { title: 'Burkina Faso' },
  { title: 'Bulgaria' },
  { title: 'Bahrain' },
  { title: 'Burundi' }
  // etc
];
```

#### Local Category Search
A search can look for category results inside a static local source.
> By default, results will return content first that begin with the query text, but also afterward content that matches the query anywhere inside. To disable full text search you can specify in settings `fullTextSearch: false`.
```html
<div class="ui search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search countries...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```
```javascript
$('.ui.search')
  .search({
    type: 'category',
    source: categoryContent
  })
;
```
```javascript
var categoryContent = [
  { category: 'South America', title: 'Brazil' },
  { category: 'South America', title: 'Peru' },
  { category: 'North America', title: 'Canada' },
  { category: 'Asia', title: 'South Korea' },
  { category: 'Asia', title: 'Japan' },
  { category: 'Asia', title: 'China' },
  { category: 'Europe', title: 'Denmark' },
  { category: 'Europe', title: 'England' },
  { category: 'Europe', title: 'France' },
  { category: 'Europe', title: 'Germany' },
  { category: 'Africa', title: 'Ethiopia' },
  { category: 'Africa', title: 'Nigeria' },
  { category: 'Africa', title: 'Zimbabwe' },
];
```

## States

#### Loading
A search can show a loading indicator
```html
<div class="ui loading search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```

## Variations

#### Disabled
A search can show it is currently unable to be interacted with
```html
<div class="ui disabled category search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search animals...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```

#### Fluid
A search can have its results take up the width of its container
```html
<div class="ui fluid category search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search animals...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```

#### Aligned
A search can have its results aligned to its left or right container edge
```html
<div class="ui right aligned category search">
  <div class="ui icon input">
    <input class="prompt" type="text" placeholder="Search animals...">
    <i class="search icon"></i>
  </div>
  <div class="results"></div>
</div>
```

## Usage

### Initializing

> Search is built ontop of Semantic [API](/behaviors/api.html) behaviors to allow for URL templating, and UI state management. Please check out the API documentation for more information on adjusting API settings.

#### Automatic Routing
By default search will automatically route to the named [API endpoint](/behaviors/api.html) 'search'
```javascript
// initializes with default endpoint /search/{query}
$('.ui.search')
  .search({
    type: 'category'
  })
;
```

#### Named URL
You can specify custom API settings to adjust the url, callback settings, or specify a different API action.
```javascript
$('.ui.search')
  .search({
    // change search endpoint to a custom endpoint by manipulating apiSettings
    apiSettings: {
      url: 'custom-search/?q={query}'
    },
    type: 'category'
  })
;
```

#### Local Object
Local search results allow you to search across specified properties of a javacript object literal looking for matching values

You can set which fields are searchable using the `searchFields` setting. Local object search can only display standard search results (not categories).

```javascript
// searches across any array/object of searchable objects
var
  content = [
    {
      title: 'Horse',
      description: 'An Animal',
    },
    {
      title: 'Cow',
      description: 'Another Animal',
    }
  ]
;
$('.ui.search')
  .search({
    source : content,
    searchFields   : [
      'title'
    ],
    fullTextSearch: false
  })
;
```

## Server Responses

> You may also consider adding a top level property like `success: true` and using API's `successTest` parameter to determine whether a server response is actually succesful, even if it returns the correct HTTP code

#### Standard
```
{
  "results": [
    {
      "title": "Result Title",
      "url": "/optional/url/on/click",
      "image": "optional-image.jpg",
      "price": "Optional Price",
      "description": "Optional Description"
    },
    {
      "title": "Result Title",
      "description": "Result Description"
    }
  ],
  // optional action below results
  "action": {
    "url": '/path/to/results',
    "text": "View all 202 results"
  }
}
```

#### Category
```
{
  "results": {
    "category1": {
      "name": "Category 1",
      "results": [
        {
          "title": "Result Title",
          "url": "/optional/url/on/click",
          "image": "optional-image.jpg",
          "price": "Optional Price",
          "description": "Optional Description"
        },
        {
          "title": "Result Title",
          "url": "/optional/url/on/click",
          "image": "optional-image.jpg",
          "price": "Optional Price",
          "description": "Optional Description"
        }
      ]
    },
    "category2": {
      "name": "Category 2",
      "results": [
        {
          "title": "Result Title",
          "url": "/optional/url/on/click",
          "image": "optional-image.jpg",
          "price": "Optional Price",
          "description": "Optional Description"
        }
      ]
    }
  },
  // optional action below results
  "action": {
    "url": '/path/to/results',
    "text": "View all 202 results"
  }
}
```

## Retreiving Results

#### Unique IDs
If no `id` property is included on a result, a key will automatically be generated when your results are returned for each result.

IDs are generated using the position in the results, for example the first element will receive the id `1`, and the first category result will receive the id `a1`.

An `id` or search result title can then be used with `get result(value)` to return the result object.

```javascript
// get result from current query results with the title cat
$('.ui.search')
  .search('get result', 'cat')
;
// get first result from first category with category search
$('.ui.search')
  .search('get result', 'a1')
;
// get first result from standard search
$('.ui.search')
  .search('get result', '1')
;
```

## Behaviors

All the following behaviors can be called using the syntax:
```javascript
$('.your.element')
  .search('behavior name', argumentOne, argumentTwo)
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
      <td>query (callback)</td>
      <td>Search for value currently set in search input</td>
    </tr>
    <tr>
      <td>display message(text, type)</td>
      <td>Displays message in search results with text, using template matching type</td>
    </tr>
    <tr>
      <td>cancel query</td>
      <td>Cancels current remote search query</td>
    </tr>
    <tr>
      <td>search local(query)</td>
      <td>Search local object for specified query and display results</td>
    </tr>
    <tr>
      <td>has minimum characters</td>
      <td>Whether has minimum characters</td>
    </tr>
    <tr>
      <td>search remote(query, callback)</td>
      <td>Search remote endpoint for specified query and display results</td>
    </tr>
    <tr>
      <td>search object(query, object, searchFields)</td>
      <td>Search object for specified query and return results</td>
    </tr>
    <tr>
      <td>cancel query</td>
      <td>Cancels current remote search request</td>
    </tr>
    <tr>
      <td>is focused</td>
      <td>Whether search is currently focused</td>
    </tr>
    <tr>
      <td>is visible</td>
      <td>Whether search results are visible</td>
    </tr>
    <tr>
      <td>is empty</td>
      <td>Whether search results are empty</td>
    </tr>
    <tr>
      <td>get value</td>
      <td>Returns current search value</td>
    </tr>
    <tr>
      <td>get result(value)</td>
      <td>Returns JSON object matching searched title or id (see above)</td>
    </tr>
    <tr>
      <td>set value(value)</td>
      <td>Sets search input to value</td>
    </tr>
    <tr>
      <td>read cache(query)</td>
      <td>Reads cached results for query</td>
    </tr>
    <tr>
      <td>clear cache(query)</td>
      <td>Clears value from cache, if no parameter passed clears all cache</td>
    </tr>
    <tr>
      <td>write cache(query)</td>
      <td>Writes cached results for query</td>
    </tr>
    <tr>
      <td>add results(html)</td>
      <td>Adds HTML to results and displays</td>
    </tr>
    <tr>
      <td>show results(callback)</td>
      <td>Shows results container</td>
    </tr>
    <tr>
      <td>hide results(callback)</td>
      <td>Hides results container</td>
    </tr>
    <tr>
      <td>generate results(response)</td>
      <td>Generates results using parser specified by `settings.template`</td>
    </tr>
    <tr>
      <td>destroy</td>
      <td>Removes all events</td>
    </tr>
  </tbody>
</table>
```

## Examples

#### Using Different Response Fields
Search expects a very specific API response, however you can easily modify the mapping of server response to displayed field using the `fields` parameter.
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
    apiSettings: {
      url: '//api.github.com/search/repositories?q={query}'
    },
    fields: {
      results : 'items',
      title   : 'name',
      url     : 'html_url'
    },
    minCharacters : 3
  })
;
```

#### Using API Settings
[API](/behaviors/api.html) provides a callback [onResponse](/behaviors/api.html#response-callbacks) that can be used to restructure third party APIs to match the expected server response for search.

You can also use [mockResponseAsync](/behaviors/api.html#mocking-responses) to use a custom backend for fullfilling searches.
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
      onResponse: function(githubResponse) {
        var
          response = {
            results : {}
          }
        ;
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
      },
      url: '//api.github.com/search/repositories?q={query}'
    }
  })
;
```

## Settings

### Search

#### Behavior
```html
<table class="ui sortable celled definition table">
  <thead>
    <th class="three wide"></th>
    <th class="five wide">Default</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>apiSettings</td>
      <td>
      <div class="code">
      {
        action: 'search'
      }
      </div>
      </td>
      <td>Settings for [API](/behaviors/api.html#/usage) call.</td>
    </tr>
    <tr>
      <td>minCharacters</td>
      <td>1</td>
      <td>Minimum characters to query for results</td>
    </tr>
    <tr>
      <td>searchOnFocus</td>
      <td>true</td>
      <td>Whether search should show results on focus (must also match min character length)</td>
    </tr>
    <tr>
      <td>transition</td>
      <td>
        fade
      </td>
      <td>Named transition to use when animating menu in and out. Fade and slide down are available without including [ui transitions](/modules/transition.html)</td>
    </tr>
    <tr>
      <td>duration</td>
      <td>
        300
      </td>
      <td>Duration of animation events</td>
    </tr>
    <tr>
      <td>maxResults</td>
      <td>7</td>
      <td>Maximum results to display when using local and simple search, maximum category count for category search</td>
    </tr>
    <tr>
      <td>cache</td>
      <td>true</td>
      <td>Caches results locally to avoid requerying server</td>
    </tr>
    <tr>
      <td>source</td>
      <td>false</td>
      <td>Specify a Javascript object which will be searched locally</td>
    </tr>
    <tr>
      <td>selectFirstResult</td>
      <td>false</td>
      <td>Whether the search should automatically select the first search result after searching</td>
    </tr>
    <tr>
      <td>showNoResults</td>
      <td>false</td>
      <td>Whether a "no results" message should be shown if no results are found. (These messages can be modified using the `template` object specified below)</td>
    </tr>
    <tr>
      <td>fullTextSearch</td>
      <td>'exact'</td>
      <td>Specifying to "true" will use a fuzzy full text search, setting to "exact" will force the exact search to be matched somewhere in the string, setting to `false` will only match to start of string. (This setting was previously called `searchFullText`.)</td>
    </tr>
    <tr>
      <td>fields</td>
      <td>
        <div class="code">
fields: {
  categories      : 'results',     // array of categories (category view)
  categoryName    : 'name',        // name of category (category view)
  categoryResults : 'results',     // array of results (category view)
  description     : 'description', // result description
  image           : 'image',       // result image
  price           : 'price',       // result price
  results         : 'results',     // array of results (standard)
  title           : 'title',       // result title
  action          : 'action',      // "view more" object name
  actionText      : 'text',        // "view more" text
  actionURL       : 'url'
}
        </div>
      </td>
      <td>List mapping display content to JSON property, either with API or `source`.</td>
    </tr>
    <tr>
      <td>searchFields</td>
      <td>
        <div class="code">
          [
            'title',
            'description'
          ]
        </div>
      </td>
      <td>Specify object properties inside local source object which will be searched</td>
    </tr>
    <tr>
      <td>hideDelay</td>
      <td>0</td>
      <td>Delay before hiding results after search blur</td>
    </tr>
    <tr>
      <td>searchDelay</td>
      <td>100</td>
      <td>Delay before querying results on inputchange</td>
    </tr>
    <tr>
      <td>easing</td>
      <td>
        easeOutExpo
      </td>
      <td>Easing equation when using fallback Javascript animation</td>
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
      <td>onSelect(result, response)</td>
      <td>module</td>
      <td>Callback on element selection by user. The first parameter includes the filtered response results for that element. The function should return false to prevent default action (closing search results and selecting value).</td>
    </tr>
    <tr>
      <td>onResultsAdd(html)</td>
      <td>module</td>
      <td>Callback after processing element template to add HTML to results. Function should return false to prevent default actions.</td>
    </tr>
    <tr>
      <td>onSearchQuery(query)</td>
      <td>module</td>
      <td>Callback on search query</td>
    </tr>
    <tr>
      <td>onResults(response)</td>
      <td>module</td>
      <td>Callback on server response</td>
    </tr>
    <tr>
      <td>onResultsOpen</td>
      <td>results element</td>
      <td>Callback when results are opened</td>
    </tr>
    <tr>
      <td>onResultsClose</td>
      <td>results element</td>
      <td>Callback when results are closed</td>
    </tr>
  </tbody>
</table>
```

## Templates

These templates are used to generate the HTML structures for search results

> By specifying a search as `type: 'customType'`, and a custom template under `$.fn.search.settings.templates.customType` you can create custom search results. Keep in mind that `.title` will be used for matching results `onSelect`
```html
<table class="ui sortable celled definition table">
  <thead>
    <th></th>
    <th class="twelve wide">Functions</th>
  </thead>
    <tr>
      <td>templates</td>
      <td>
        <div class="code">
        $.fn.search.settings.templates : {
          escape: function(string) {
            // returns escaped string for injected results
          },
          message: function(message, type) {
           // returns html for message with given message and type
          },
          category: function(response) {
           // returns results html for category results
          },
          standard: function(response) {
           // returns results html for standard results
          }
        }
        </div>
      </td>
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
      <td>Search</td>
      <td>Name used in log statements</td>
    </tr>
    <tr>
      <td>namespace</td>
      <td>search</td>
      <td>Event namespace. Makes sure module teardown does not effect other events attached to an element.</td>
    </tr>
    <tr>
      <td>regExp</td>
      <td>
        <div class="code">
regExp: {
  escape     : /[\-\[\]\/\{\}\(\)\*\+\?\.\\\^\$\|]/g,
  beginsWith : '(?:\s|^)'
}
        </div>
      </td>
      <td>Regular expressions used for matching</td>
    </tr>
    <tr>
      <td>selector</td>
      <td>
        <div class="code">
selector : {
  prompt       : '.prompt',
  searchButton : '.search.button',
  results      : '.results',
  category     : '.category',
  result       : '.result'
}
        </div>
      </td>
      <td>Selectors used to find parts of a module</td>
    </tr>
    <tr>
      <td>metadata</td>
      <td>
        <div class="code">
metadata: {
  cache   : 'cache',
  results : 'results'
}
        </div>
      </td>
      <td>HTML5 metadata attributes used internally</td>
    </tr>
    <tr>
      <td>className</td>
      <td>
        <div class="code">
className: {
  active  : 'active',
  empty   : 'empty',
  focus   : 'focus',
  loading : 'loading',
  pressed : 'down'
}
        </div>
      </td>
      <td>Class names used to determine element state</td>
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
error : {
  source      : 'Cannot search. No source used, and Semantic API module was not included',
  noResults   : 'Your search returned no results',
  logging     : 'Error in debug logging, exiting.',
  noTemplate  : 'A valid template name was not specified.',
  serverError : 'There was an issue with querying the server.',
  maxResults  : 'Results must be an array to use maxResults setting',
  method      : 'The method you called is not defined.'
}
        </div>
      </td>
    </tr>
  </tbody>
</table>
```