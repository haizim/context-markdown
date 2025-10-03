# Nag

A nag is an important message that persists until dismissed by a user

## Current Progress
```html
<div class="ui indicating progress">
  <div class="bar" style="width: 60%;">
    <div class="progress">60%</div>
  </div>
  <div class="label">Needs Documentation / Re-coding</div>
</div>
```

## Usage

Nags are used to present a user with a one time message which will persist until a user acknowledges the message. This can be used for providing notices like the site's use of cookies, an important change to a site like a security breach.

Semantic's nag component provides built in options for ensuring a nag is only displayed once. You can trigger an API endpoint on dismissal, in order to store a value in your database, or you can use localstorage or cookie value to make sure that a particular computer does not receive the nag again.

## Example

```javascript
// Wont re-appear unless cleared
$('.cookie.nag')
  .nag('show')
;
```
```javascript
// Clears cookie so nag shows again
$('.cookie.nag')
  .nag('clear')
;
```
```html
<div class="ui inline cookie nag">
  <span class="title">
    We use cookies to ensure you get the best experience on our website
  </span>
  <i class="close icon"></i>
</div>
```
```javascript
// Automatically shows on init if cookie isnt set
$('.cookie.nag')
  .nag({
    key      : 'accepts-cookies',
    value    : true
  })
;
```

## Support Development

You can help support the future development of the Semantic UI project, and help boost the priority of this component by donating to Semantic UI development.

Please be sure to leave a note in the comments to indicate that you are interested in the development of this particular component.
