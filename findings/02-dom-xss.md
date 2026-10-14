# Finding 02: DOM-Based Cross-Site Scripting

## Summary

The OWASP Juice Shop search feature accepted user-controlled input and inserted it into the page without safely handling it. This allowed JavaScript to execute inside the browser.

## Test Payload

```html
<iframe src="javascript:alert(`xss`)">
