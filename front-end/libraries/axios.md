---
description: Promise based HTTP client for browser and node.js
---

# Axios

{% embed url="https://axios-http.com/" %}

### What is Axios?

Axios is a [promise-based](https://javascript.info/promise-basics) HTTP Client for `node.js` and the browser. It is [isomorphic](https://www.lullabot.com/articles/what-is-an-isomorphic-application) (=it can run in the browser and nodejs with the same codebase). On the server-side it uses the native node.js `http` module, while on the client (browser) it uses XMLHttpRequests

### Features

* Make XMLHttpRequests from the browser;
* Make http requests from node.js;
* Supports the Promise API;
* Intercept request and response;
* Transform request and response data;
* Cancel requests;
* Automatic transforms for JSON data;
* Client side support for protecting against XSRF.

### Installing

You can install using npm or yarn:

```shell
npm install axios
// or
yarn add axios
```

### Example

```javascript
const axios = require('axios');

// Make a request for a user with a given ID
axios.get('/user?ID=12345')
  .then(function (response) {
    // handle success
    console.log(response);
  })
  .catch(function (error) {
    // handle error
    console.log(error);
  })
  .then(function () {
    // always executed
  });

// Optionally the request above could also be done as
axios.get('/user', {
    params: {
      ID: 12345
    }
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  })
  .then(function () {
    // always executed
  });  

// Want to use async/await? Add the `async` keyword to your outer function/method.
async function getUser() {
  try {
    const response = await axios.get('/user?ID=12345');
    console.log(response);
  } catch (error) {
    console.error(error);
  }
}
```
