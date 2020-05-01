# waitForKeyElements.js
A utility function for userscripts that detects and handles AJAXed content. 

Forked from [the original](https://gist.github.com/BrockA/2625891) with major improvements, including:
- does not require jQuery
- avoids [the quirks](https://www.thecodeship.com/web-development/alternative-to-javascript-evil-setinterval/) associated with `setInterval()`
- optionally takes a function instead of a string for querying elements on page
