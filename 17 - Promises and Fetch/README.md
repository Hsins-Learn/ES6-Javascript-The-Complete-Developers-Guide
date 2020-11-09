# Section 17: Promises and Fetch

- [Code Execution in JavaScript](#code-execution-in-javascript)
- [Terminology of Promises](#terminology-of-promises)
- [Use Promises](#use-promises)
- [Ajax Requests with `fetch`() Helper](#ajax-requests-with-fetch-helper)

## Code Execution in JavaScript

Before answer the question about "What's Promise?", we need to know how does JavaScript execute codes.

<br/>
<div align="right">
  <b><a href="#section-17-promises-and-fetch">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## Terminology of Promises

<p align="center">
  <img src="https://i.imgur.com/NJBcnWP.png" alt="Three States of Promises" height="250px">
</p>

- `unresolved`
- `resolved`
- `rejected`

<br/>
<div align="right">
  <b><a href="#section-17-promises-and-fetch">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## Use Promises

The vast majority of use promises is working with Ajax requests but we can make promises without Ajax requests. Moreover, the promises are used to solve the issue of asynchronous code. Note that the trick to dealing with asynchronous code is through **how we call `resolve()` and `reject()`**.

```javascript
let promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    // reject()
    resolve();
  }, 3000);
});

promise
  .then(() => console.log("Finally finished!"))
  .then(() => console.log("I was also ran!"))
  .catch(() => console.log("uh oh!!"));
```

<br/>
<div align="right">
  <b><a href="#section-17-promises-and-fetch">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## Ajax Requests with `fetch`() Helper

The `fetch()` helper is the feature that is just like promises implemented inside the browsers already.

```javascript
url = 'http://jsonplaceholder.typicode.com/posts/'

fetch(url)
  .then(response => response.json())
  .then(data => console.log(data));
```

Because the `fetch()` helper only catch when the network request flat out fails. It's really highly recommend that still use Ajax utility libraries like `axios` or `jQuery`.

<br/>
<div align="right">
  <b><a href="#section-17-promises-and-fetch">[ ↥ Back To Top ]</a></b>
</div>
<br/>
