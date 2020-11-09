# Section 06: The `every` and `some` Helper

- [The `every` and `some` Helper](#the-every-and-some-helper)
- [`every()` and `some()` in Practice](#every-and-some-in-practice)
- [[Exercise] Finding Submitted Users](#exercise-finding-submitted-users)
- [[Exercise] In Progress Network Requests](#exercise-in-progress-network-requests)

## The `every` and `some` Helper

The `every()` and `some()` helper will checks the elements in an array pass the provided function or not.

- The `every()` method checks if all elements in an array pass a test (provided as a function).
- The `some()` method checks if any of the elements in an array pass a test (provided as a function).

The `every()` method executes the provided function once for each array element and returns the **value of the first element passing the test by provided function**. Otherwise it returns `undefined`.

```javascript
let computers = [
  { name: 'Apple', ram: 24 },
  { name: 'Compaq', ram: 4 },
  { name: 'Acer', ram: 32}
];

// loop the array by using for loop
let allComputersCanRunProgram = true;
let onlySomeComputersCanRunProgram = false;

for (let i = 0; i < computers.length; i++) {
  let computer = computers[i];

  if (computer.ram < 16) {
    allComputersCanRunProgram = false;
  } else {
    onlySomeComputersCanRunProgram = true;
  }
}

// loop the array by using every() and some() method
let allComputersCanRunProgram = computers.every(computer => computer.ram > 16);
let onlySomeComputersCanRunProgram = computers.some(computer => computer.ram > 16);
```

Note that the `every()` and `some()` methods don't change the original array. Moreover, the `some()` method will return and doesn't check remaining element whenever there is an element in that array pass the test.

<br/>
<div align="right">
  <b><a href="#section-06-the-every-and-some-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## `every()` and `some()` in Practice

We would use `every()` or `some()` method to create the criteria for if-statement in practice.

```javascript
class Field(value) {
  constructor(value) {
    this.value = value;
  }

  validate() {
    return this.value.length > 0;
  }
}

let username = new Field("2cool");
let password = new Field("my_password");
let birthdate = new Field("10/10/2010");

let fields = [username, password, birthdate];
let formIsValid = fields.every(field => return field.validate());

if (formIsValid) {
  // allow user to submit!
} else {
  // show an error message.
}
```

<br/>
<div align="right">
  <b><a href="#section-06-the-every-and-some-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Finding Submitted Users

### Question

Given an array of users, return `true` if every user has submitted a request form. Assign the result to the variable `hasSumbmitted`.

```javascript
var users = [
  { id: 21, hasSubmitted: true },
  { id: 62, hasSubmitted: false },
  { id: 4, hasSubmitted: true }
];

var hasSubmitted;
```

### Solution

```javascript
let users = [
  { id: 21, hasSubmitted: true },
  { id: 62, hasSubmitted: false },
  { id: 4, hasSubmitted: true }
];

let hasSubmitted = users.every(user => user.hasSubmitted);
```

<br/>
<div align="right">
  <b><a href="#section-06-the-every-and-some-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] In Progress Network Requests

### Question

Given an array of network objects representing network requests, assign the boolean `true` to the variable `inProgress` if any network request has a `status` of `pending`.

```javascript
var requests = [
  { url: '/photos', status: 'complete' },
  { url: '/albums', status: 'pending' },
  { url: '/users', status: 'failed' }
];

var inProgress;
```

### Solution

```javascript
let requests = [
  { url: '/photos', status: 'complete' },
  { url: '/albums', status: 'pending' },
  { url: '/users', status: 'failed' }
];

let inProgress = requests.some(request => request.status === 'pending');
```

<br/>
<div align="right">
  <b><a href="#section-06-the-every-and-some-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>