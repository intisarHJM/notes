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

# Basic Variable Declarations and Operations
```javascript
let price, tax, total;    
price = 100;          
tax = 15;          
total = price + tax;    
```
Multiple statements that declare variables and perform calculations. Each statement ends with a semicolon for proper separation.

# Writing to HTML Element
```javascript
document.getElementById("result").innerHTML = "Welcome to our store.";
```
A single statement that changes the content of an HTML element with id="result".

# Multiple Statements on One Line
```javascript
let salary = 5000; let bonus = 1000; let total = salary + bonus;
```
Multiple statements can be written on the same line when separated by semicolons, though this is not recommended for readability.

# Code Blocks in Functions
```javascript
function calculateTotal() {
    let name = "Fatima";
    document.getElementById("greeting").innerHTML = "Hello " + name;
    document.getElementById("total").innerHTML = "Your total is $1500";
}
```
Groups related statements within a function using curly brackets. The statements are executed together when the function is called.

# Line Breaks in Long Statements
```javascript
document.getElementById("longMessage").innerHTML = 
    "Welcome to our online store. " +
    "We hope you enjoy your shopping experience!";
```
Breaks a long statement into multiple lines after operators for better readability. The logical meaning remains the same.

# Variable Declaration and Assignment
```javascript
var price;
let quantity;
price = 100;
quantity = 5;
let total = price * quantity;
```
Demonstrates variable declaration using 'var' and 'let', followed by assignment of values and a calculation using these variables.

# Number and String Literals
```javascript
15.75
"Welcome to our store"
'Welcome to our store'
```
Shows how to write number literals (with decimals) and string literals (using either single or double quotes).

# Variable Assignment with Arithmetic
```javascript
let cost, profit;
cost = 50;
profit = 25;
```
Illustrates declaring multiple variables and assigning values, which could be used in further calculations.

# Arithmetic Operations
```javascript
(10 + 5) * 3
```
Demonstrates the use of arithmetic operators and parentheses to control the order of operations.

# String Concatenation
```javascript
"Ahmed" + " " + "Hassan"
```
Shows how to combine strings using the '+' operator, resulting in "Ahmed Hassan".

# Variable Creation with 'let' Keyword
```javascript
let revenue, expenses;
revenue = 1000 + 500;
expenses = revenue * 0.3;
```
Uses 'let' to declare variables, then assigns values using both literal numbers and an expression.

# Comments in JavaScript
```javascript
let salary = 5000;   // This is the base salary
// salary = 6000;   This line is not executed
```
Demonstrates single-line comments. The first comment explains code, while the second comment prevents a line from executing.

# Case Sensitivity in Variables
```javascript
let employeeName, employeename;
employeeName = "Fatima";
employeename = "Zainab";
```
Showcases that JavaScript treats differently cased variables as distinct, even if the spelling is the same.

# Single Line Comments Before Code
```javascript
// Update welcome message:
document.getElementById("welcome").innerHTML = "Welcome to Our Store";
// Update price display:
document.getElementById("price").innerHTML = "Total: $150";
```
Uses single-line comments to describe what each line of code does before the code itself.

# Single Line Comments After Code
```javascript
let salary = 5000;      // Define base salary
let bonus = salary + 1000;  // Add bonus to base salary
```
Places single-line comments at the end of each code line to explain the purpose of each operation.

# Multi-line Comment Block
```javascript
/*
This code section handles the user profile update:
- Changes the user name
- Updates the display picture
- Refreshes the profile section
*/
document.getElementById("userName").innerHTML = "Kareem";
document.getElementById("userPicture").src = "profile.jpg";
```
Uses a multi-line comment block to provide detailed information about several related code lines.

# Preventing Code Execution with Single-line Comments
```javascript
let user = "Amir";
//document.getElementById("greeting").innerHTML = "Welcome " + user;
document.getElementById("status").innerHTML = "Online";
```
Uses a single-line comment to temporarily disable one line of code while letting other code execute.

# Preventing Multiple Lines with Comment Block
```javascript
/*
let user = "Zainab";
let role = "Admin";
document.getElementById("userInfo").innerHTML = user + " - " + role;
document.getElementById("accessLevel").innerHTML = "Full Access";
*/
```
Uses a multi-line comment block to temporarily disable multiple lines of code during testing or debugging.

# Basic Variable Declaration
```javascript
let name = "Amir";
let age = 25;
let total = age + 5;
```
Shows three ways to declare variables: with a string value, number value, and calculation. Variables declared with 'let' can be reassigned later.

# Constant Values
```javascript
const TAX_RATE = 0.15;
const COMPANY_NAME = "Global Tech";
const MAX_USERS = 100;
```
Uses const for values that shouldn't change throughout the program. Common for configuration values and constants.

# Block Scope with Let
```javascript
let salary = 5000;
{
    let salary = 6000;
    let bonus = 1000;
    // salary inside block is 6000
}
// salary outside block is still 5000
```
Demonstrates block scope - variables declared with 'let' inside a block are only accessible within that block.

# Object Declaration with Const
```javascript
const employee = {
    name: "Malik",
    position: "Developer",
    salary: 5000
};
employee.salary = 6000; // Allowed
// employee = {} // Not allowed - can't reassign const object
```
Shows that const objects can have their properties modified, but the object itself cannot be reassigned.

# Multiple Variable Declaration
```javascript
let firstName = "Hassan",
    lastName = "Ahmad",
    age = 30;
```
Declares multiple variables in a single statement, making code more concise.

# Variable Type Flexibility
```javascript
let value = "Welcome";
value = 42; // Valid - JavaScript is dynamically typed
```
Shows that variables can hold different types of values, even after initial declaration (except for const).

# Const with Arrays
```javascript
const numbers = [1, 2, 3];
numbers.push(4); // Allowed
numbers[0] = 10; // Allowed
// numbers = [5, 6, 7]; // Not allowed - can't reassign const array
```
Demonstrates that const arrays can be modified but not reassigned entirely.

# Block Scope Comparison
```javascript
var globalVar = "Accessible everywhere";
let blockLet = "Block scoped";
const blockConst = "Also block scoped";

{
    var globalVar = "Still accessible";
    let blockLet = "New variable in block";
    const blockConst = "New constant in block";
}
```
Shows the difference between var (function/global scope) versus let/const (block scope).