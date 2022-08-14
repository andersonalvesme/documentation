---
description: >-
  Basically there are four ways to declare variables in JS. Using var, let,
  const or nothing.
---

# Variables

The <mark style="color:red;">var</mark> keyword is used to declare variables in **global scope** or **function scope**.\
Example:

```javascript
var hi = "hi!"; // global scope
function say () {
    var hello = "hello!"; // function scope
}
console.log(hi);     // result: hi!
console.log(hello);  // result: Uncaught ReferenceError: hello is not defined
```

The <mark style="color:red;">let</mark> keyword is used to declare variables in **block scope**, basically the code inside a {}.\
Example:

```javascript
let hi = "hi!";
if (true) {
    let hi = "other hi!"; // block scope
    console.log(hi);      // result: other hi!
}
console.log(hi); // result: hi!
```

The <mark style="color:red;">const</mark> keyword is used to declare in **block scope** and maintain it **values constants**, you cannot change and needs to be initialized.\
Example:

```javascript
const hi = "hi!";
hi = "other hi!"; // result: Uncaught TypeError: Assignment to constant variable.
```

{% hint style="info" %}
JavaScript identifiers are **case-sensitive**.

Declaring variables using the **dollar sign** is not very common in JavaScript, but professional programmers often use it as an **alias for the main function** in a JavaScript library.

Declaring variables using the **underscore** is not very common in JavaScript, but a convention among professional programmers is to use it as an alias for "**private (hidden)**" variables.
{% endhint %}
