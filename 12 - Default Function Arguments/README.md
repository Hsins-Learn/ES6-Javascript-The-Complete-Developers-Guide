# Section 12: Default Function Arguments

- [Specifying or Using Cases of Default Arguments](#specifying-or-using-cases-of-default-arguments)
- [[Exercise] Using Default Arguments](#exercise-using-default-arguments)
- [[Exercise] Dumping Unused Code](#exercise-dumping-unused-code)

## Specifying or Using Cases of Default Arguments

The default arguments is the syntax sugar for us to initialize functions with default values and the default values will be used when the arguments is either omitted or `undefined` in a function call.

```javascript
function makeAjaxRequest(url, method = 'GET') {
  // logic to make the request
  ...
}

makeAjaxRequest('https://www.google.com/');
makeAjaxRequest('https://www.google.com/', 'POST');
```

There is a more complex usage of default arguments.

```javascript
function User(id) {
  this.id = id;
}

function generateId() {
  return Math.random * 9999999;
}

function createAdminUser(user = new User(generateId())) {
  user.admin = true;
  return user;
}

// create a new user when call function
createAdminUser();

// use the given user instead of creating new one
const user = new User(generateId());
createAdminUser(user);
```

<br/>
<div align="right">
  <b><a href="#section-12-default-function-arguments">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Using Default Arguments

### Question

Refactor the following code to use default function arguments.  Be sure to remove any unused code after you refactor it.

```javascript
function sum(a, b) {
  if (a === undefined) { a = 0; }
  if (b === undefined) { b = 0; }

  return a + b;
}
```

### Solution

```javascript
function sum(a = 0, b = 0) {
  return a + b;
}
```

<br/>
<div align="right">
  <b><a href="#section-12-default-function-arguments">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Dumping Unused Code

### Question

Refactor the following code to use default function arguments.  Be sure to remove any unused code after you refactor it.

```javascript
function addOffset(style) {
  if (!style) { style = {}; }

  style.offset = '10px';
  return style;
}
```

### Solution

```javascript
function addOffset(style = {}) {
  style.offset = '10px';

  return style;
}
```

<br/>
<div align="right">
  <b><a href="#section-12-default-function-arguments">[ ↥ Back To Top ]</a></b>
</div>
<br/>