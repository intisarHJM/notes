---
title: "Client Side Programming Using JavaScript"
author: "Abdulla Ebrahim Subah"
institute: "University of Bahrain"
topic: "Introduction"
theme: "CambridgeUS"
colortheme: "beaver"
fonttheme: "professionalfonts"
fontsize: 10pt
linkstyle: bold
aspectratio: 169
dpi: 300
navigation: frame
# titlegraphic: 
# logo: 
date: \today{}
lang: en-US
section-titles: false
header-includes:
  - \usepackage{setspace}
  - \setstretch{1.5}
---

# Introduction

JavaScript is a core web programming language alongside HTML and CSS, used by 99% of websites for client-side behavior.

JavaScript engines in web browsers execute client code and are also used in servers and applications, with Node.js being the most popular non-browser runtime.

Key characteristics of JavaScript:

- High-level programming language
- Follows ECMAScript standard
- Features dynamic typing
- Supports prototype-based object-orientation
- Enables multiple programming paradigms (event-driven, functional, imperative)
- Provides APIs for text, dates, regular expressions, data structures, and DOM manipulation

The language itself doesn't include I/O capabilities (networking, storage, graphics) - these are provided by browsers or runtime systems through APIs.

Note: Despite similar names and syntax, JavaScript is entirely different from Java in design and purpose.

[source](https://en.wikipedia.org/wiki/JavaScript)

# Where to Write JavaScript?

## Basic Script Tag Example
```html
<script>
document.getElementById("demo").innerHTML = "Welcome to JavaScript";
</script>
```
The code changes the content of an HTML element with id "demo" using JavaScript placed directly in the HTML file between script tags.

## JavaScript in Head Section
```html
<!DOCTYPE html>
<html>
<head>
<script>
function showMessage() {
  document.getElementById("message").innerHTML = "Text has been updated.";
}
</script>
</head>
<body>
<h2>JavaScript in Head Demo</h2>
<p id="message">Original text</p>
<button type="button" onclick="showMessage()">Click here</button>
</body>
</html>
```
Places JavaScript code in the head section. When the button is clicked, it calls the showMessage function that changes the paragraph text. Placing scripts in the head section means they load before the page content.

## JavaScript in Body Section
```html
<!DOCTYPE html>
<html>
<body>
<h2>JavaScript in Body Demo</h2>
<p id="message">Original text</p>
<button type="button" onclick="displayText()">Click here</button>
<script>
function displayText() {
  document.getElementById("message").innerHTML = "Text has been updated.";
}
</script>
</body>
</html>
```
Places JavaScript code at the bottom of the body section. This improves page load performance since the content loads before the scripts.

## External JavaScript File (myScript.js)
```javascript
function updateContent() {
  document.getElementById("message").innerHTML = "Text has been updated.";
}
```
The code is saved in a separate .js file and can be reused across multiple web pages.

## Including External JavaScript
```html
<script src="myScript.js"></script>
<script src="/scripts/myScript.js"></script>
<script src="https://www.example.com/scripts/myScript.js"></script>
```
Three different ways to include external JavaScript files: without path, with a folder path, and with a full URL. External scripts keep code organized and enable browser caching for better performance.

Here are the modified JavaScript examples with Arabic names from the content:

# Common Use Cases

## Changing HTML Content
```javascript
document.getElementById("message").innerHTML = "Welcome to Our Website";
```
This code finds an HTML element with id="message" and changes its content to the specified text. You can use either single or double quotes for the text.

## Changing HTML Element Source
```javascript
function turnOnLight() {
    document.getElementById("bulb").src = "bulbon.gif";
}

function turnOffLight() {
    document.getElementById("bulb").src = "bulboff.gif";
}
```
These functions modify an image source attribute, creating an interactive effect like switching a light bulb on and off.

## Modifying CSS Styles
```javascript
document.getElementById("textBlock").style.fontSize = "28px";
```
Changes the font size of an HTML element with id="textBlock". You can modify any CSS property using this approach.

## Hiding Elements
```javascript
function hideContent() {
    document.getElementById("content").style.display = "none";
}
```
Makes an HTML element invisible by changing its display property to "none".

## Showing Elements
```javascript
function showContent() {
    document.getElementById("content").style.display = "block";
}
```
Makes a hidden HTML element visible by changing its display property to "block".

## Complete Interactive Example
```html
<!DOCTYPE html>
<html>
<body>
<div id="content">
    <h1>Welcome</h1>
    <p id="message">Hello Visitor</p>
    <button onclick="changeText()">Click Me</button>
</div>

<script>
function changeText() {
    let element = document.getElementById("message");
    element.innerHTML = "Welcome to JavaScript";
    element.style.fontSize = "24px";
}
</script>
</body>
</html>
```
This example combines multiple JavaScript features: changing content, modifying styles, and handling a button click event. When the button is clicked, it changes both the text and its size.

# Output

## Using innerHTML
```html
<!DOCTYPE html>
<html>
<body>
<h2>Welcome Message</h2>
<p id="greeting"></p>
<script>
document.getElementById("greeting").innerHTML = "Welcome " + (10 + 5);
</script>
</body>
</html>
```
Modifies the content of an HTML element by accessing its innerHTML property. The example adds text and performs a calculation to display "Welcome 15".

## Using document.write()
```html
<!DOCTYPE html>
<html>
<body>
<h2>Daily Report</h2>
<p>Sales Summary</p>
<script>
document.write("Total Sales: $" + (1500 + 2300));
</script>
</body>
</html>
```
Writes content directly to the HTML document. Note that using document.write() after the page loads will overwrite the entire document.

## Using Alert Box
```html
<!DOCTYPE html>
<html>
<body>
<script>
let name = "Hassan";
window.alert("Welcome back " + name);
// The window prefix is optional:
alert("Your balance is $" + (2000 - 500));
</script>
</body>
</html>
```
Displays pop-up alert boxes with messages. Both window.alert() and alert() work the same way since window is the global object.

## Using Console Log
```html
<!DOCTYPE html>
<html>
<body>
<script>
let user = "Malik";
console.log("User logged in: " + user);
console.log("Session started at: " + new Date());
</script>
</body>
</html>
```
Outputs messages to the browser's console, useful for debugging and development purposes.

## Print Page Function
```html
<!DOCTYPE html>
<html>
<body>
<h2>Order Summary</h2>
<p>Customer: Amir</p>
<button onclick="window.print()">Print Invoice</button>
</body>
</html>
```
Creates a print button that triggers the browser's print dialog. This is the only way JavaScript can interact with printing functionality.