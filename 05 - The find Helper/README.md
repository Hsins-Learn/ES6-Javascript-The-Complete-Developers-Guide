# Section 05: The `find` Helper

- [The `find` Helper](#the-find-helper)
- [Usind `find()` to Match posts and comment](#usind-find-to-match-posts-and-comment)
- [[Exercise] Finding Admin Users](#exercise-finding-admin-users)
- [[Exercise] What's Your Balance?](#exercise-whats-your-balance)
- [[Exercise] Custom `findWhere` Helper](#exercise-custom-findwhere-helper)

## The `find` Helper

The `map()` method executes the provided function once for each array element and returns the **value of the first element passing the test by provided function**. Otherwise it returns `undefined`.

```javascript
let users = [
  { name: 'Jill' },
  { name: 'Alex' },
  { name: 'Bill' }
];

// loop the array by using for loop
let user = '';
for (let i = 0; i < users.length; i++) {
  if (users[i].name === 'Alex') {
    user = users[i];
    break;
  }
}

// loop the array by using find() method
let user = users.find(user => user.name === 'Alex');
```

Note that the `find()` method doesn't change the original array. Let's see another example dealing objects with `find()`.

```javascript
function Car(model) {
  this.model = model;
}

let cars = [
  new Car('Buick'),
  new Car('Camaro'),
  new Car('Focus')
];

cars.find(car => car.model === 'Focus');
```

<br/>
<div align="right">
  <b><a href="#section-05-the-find-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## Usind `find()` to Match posts and comment

```javascript
let posts = [
  { id: 1, title: 'New Post' },
  { id: 2, title: 'Old Post' }
];

let comment = { postId:1, content: 'Great Post' };

function postForComment(posts, comments) {
  return posts.find(post => post.id === comment.postId);
}
```

<br/>
<div align="right">
  <b><a href="#section-05-the-find-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Finding Admin Users

### Question

Find the user in the users's array who is an admin. Assign this user to the variable `admin`.

```javascript
var users = [
  { id: 1, admin: false },
  { id: 2, admin: false },
  { id: 3, admin: true }
];

var admin;
```

### Solution

```javascript
let users = [
  { id: 1, admin: false },
  { id: 2, admin: false },
  { id: 3, admin: true }
];

let admin = users.find(user => user.admin === true);
```

<br/>
<div align="right">
  <b><a href="#section-05-the-find-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] What's Your Balance?

### Question

Find the account with a balance of 12 and assign it to the variable `account`.

```javascript
var accounts = [
  { balance: -10 },
  { balance: 12 },
  { balance: 0 }
];

var account;
```

### Solution

```javascript
let accounts = [
  { balance: -10 },
  { balance: 12 },
  { balance: 0 }
];

let account = accounts.find(account => account.balance === 12);
```

<br/>
<div align="right">
  <b><a href="#section-05-the-find-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Custom `findWhere` Helper

### Question

The most common `find` operation is to an object that has a given property. Rather than writing out a full function every time, it would be great if we has a shorthand syntax to find an object like this: `findWhere(ladders, { height: '20 feet' });`

The object `{ ladders: '20 feet' }` should be used as the search criteria - we would want to find a ladder whose `height` property was `20 feet`;

Write a `findWhere` function that achieves this shorthand approach. The `findWhere` should return the found object.

```javascript
var ladders = [
  { id: 1, height: 20 },
  { id: 3, height: 25 }
];

// result: { id: 3, height: 25 }
findWhere(ladders, { height: 25 });
```

**Hint**:

The hard part of this is figuring out the name of the proeprty on the criteria. You can use `Object.keys(criteria)[0]` to figure out the name of the property on the object. For example, `Object.keys({ height: '20 feet' })` would return `height`. You could then check to see if a given element in the array had a property equal to the criteria's value with something like `element[property] === criteria[property]`.

### Solution

```javascript
function findWhere(array, criteria) {
  let prop = Object.keys(criteria)[0];  // keep the criteria value

  return array.find(element => element[prop] === criteria[prop]);
}
```

<br/>
<div align="right">
  <b><a href="#section-05-the-find-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>