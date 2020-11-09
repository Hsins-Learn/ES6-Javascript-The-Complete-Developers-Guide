# Section 08: `const` and `let`

- [The Keyword `const` and `let`](#the-keyword-const-and-let)
- [[Exercise] A Constant Exercise of Letting Variables Be Variables](#exercise-a-constant-exercise-of-letting-variables-be-variables)
- [[Exercise] Const/Let Refactoring](#exercise-constlet-refactoring)

## The Keyword `const` and `let`

```javascript
const name = 'Jane';
let title = 'Software Engineer';
let hourlyWage = 40;

// some time later
title = 'Senior Software Engineer';
hourlyWage = 45;
```

We should always use `const` and `let` to declare variables instead of using `var`. Use the `const` and `let` make our codes more legible.

- The keyword `let` declare variables and the value of the variable will change over time.
- The keyword `const` declare variables and the value of the variable will never change.

<br/>
<div align="right">
  <b><a href="#section-08-const-and-let">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] A Constant Exercise of Letting Variables Be Variables

### Question

Imagine that you are building an application to manage a user's Facebook profile. A profile might have a `name`, `age`, and `dateOfBirth`.

Declare three variables with these same names, making sure to use `const` or `let` depending on whether you expect the value to change over time.

### Solution

```javascript
const name = 'Peter';
const dateOfBirth = '900422';
let age = 25;
```

<br/>
<div align="right">
  <b><a href="#section-08-const-and-let">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Const/Let Refactoring

### Question

The following code uses `var` instead of `const` and `let`. Refactor the function to use the new keywords. Be sure to consider whether the variable should be declared using `const` or `let` depending on whether the variable gets reassigned or not.

```javascript
var statuses = [
  { code: 'OK', response: 'Request successful' },
  { code: 'FAILED', response: 'There was an error with your request' },
  { code: 'PENDING', response: 'Your reqeust is still pending' }
];
var message = '';
var currentCode = 'OK';

for (var i = 0; i < statuses.length; i++) {
  if (statuses[i].code === currentCode) {
    message = statuses[i].response;
  }
}
```

### Solution

```javascript
const statuses = [
  { code: 'OK', response: 'Request successful' },
  { code: 'FAILED', response: 'There was an error with your request' },
  { code: 'PENDING', response: 'Your reqeust is still pending' }
];
let message = '';
let currentCode = 'OK';

for (let i = 0; i < statuses.length; i++) {
  if (statuses[i].code === currentCode) {
    message = statuses[i].response;
  }
}
```

<br/>
<div align="right">
  <b><a href="#section-08-const-and-let">[ ↥ Back To Top ]</a></b>
</div>
<br/>
