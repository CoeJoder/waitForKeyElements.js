# waitForKeyElements()
A utility function for userscripts that detects and handles AJAXed content. 

Forked from [the original](https://gist.github.com/BrockA/2625891) with major improvements, including:
- does not require jQuery
- avoids [the quirks](https://www.thecodeship.com/web-development/alternative-to-javascript-evil-setinterval/) associated with `setInterval()`
- optionally takes a function instead of a string for querying elements on page

## Installation
Add the following to your userscript's metadata block:
```javascript
// @require https://cdn.jsdelivr.net/gh/CoeJoder/waitForKeyElements.js@v1.2/waitForKeyElements.js
```
If your userscript was already installed, you'll have to reinstall it to pickup the change. See [documentation](https://sourceforge.net/p/greasemonkey/wiki/Metadata_Block/#require).

## Usage
### With selector string
```javascript
waitForKeyElements("div.comments", (element) => {
  element.innerHTML = "This text inserted by waitForKeyElements().";
});
```
### With selector function
```javascript
waitForKeyElements(() => {
  const iframe = document.querySelector('iframe');
  if (iframe) {
    const iframeDoc = iframe.contentDocument || iframe.contentWindow.document;
    return iframeDoc.querySelectorAll("div.comments");
  }
  return null;
}, callbackFunc);
```
