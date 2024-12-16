# Uncommon HTML Bug: Race Condition in DOM Manipulation

This repository demonstrates a subtle race condition that can occur when working with JavaScript and the DOM in HTML. The bug arises because JavaScript attempts to access and modify a DOM element before the browser has completely finished parsing and rendering the HTML. This leads to unexpected behavior, specifically, in this case, the element not being manipulated as intended.

## Bug Description

The `bug.html` file contains a simple HTML page with a div element.  A JavaScript snippet tries to change the display style of this div to "none". However, the script runs *before* the browser has fully loaded the div element into the DOM.  Therefore, the `getElementById` method returns null, causing a silent failure and the div remains visible.

## Solution

The `solution.html` file demonstrates how to resolve this race condition by ensuring the script executes *after* the DOM is fully loaded using the DOMContentLoaded event listener.