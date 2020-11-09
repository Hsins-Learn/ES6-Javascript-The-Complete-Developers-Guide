# Section 04: The `filter` Helper

- [The `filter` Helper](#the-filter-helper)
- [[Exercise] Filtering Values](#exercise-filtering-values)
- [[Exercise] Handling Permissions with Filter](#exercise-handling-permissions-with-filter)
- [[Exercise] Implementing `reject`](#exercise-implementing-reject)

## The `filter` Helper

The `filter()` method executes the provided function once for each array element and returns **all the elements passing the test by provided function**. Otherwise it returns `undefined`.

```javascript
let products = [
  { name: 'cucumber', type: 'vegetable' },
  { name: 'banana', type: 'fruit' },
  { name: 'celery', type: 'vegetable' },
  { name: 'orange', type: 'fruit' },
];

// loop the array by using for loop
let filteredProducts = [];
for (let i = 0; i < products.length; i++) {
  if (products[i].type === 'fruit') {
    filteredProducts.push(products[i]);
  }
}

// loop the array by using filter() method
let filteredProducts = products.filter(product => product.type === 'fruit');
```

Note that the `filter()` method doesn't change the original array. Let's see the example with multi-conditions.

```javascript
let products = [
  { name: 'cucumber', type: 'vegetable', quantity: 0, price: 1 },
  { name: 'banana', type: 'fruit', quantity: 10, price: 15 },
  { name: 'celery', type: 'vegetable', quantity: 30, price: 9 },
  { name: 'orange', type: 'fruit', quantity: 3, price: 5 },
];

// Filter out:  (1) 'vegetable' Type
//              (2) quantity is greater than 0
//              (3) price is less than 10
let products = [
  { name: 'cucumber', type: 'vegetable', quantity: 0, price: 1 },
  { name: 'banana', type: 'fruit', quantity: 10, price: 15 },
  { name: 'celery', type: 'vegetable', quantity: 30, price: 9 },
  { name: 'orange', type: 'fruit', quantity: 3, price: 5 },
];

// Filter out:  (1) 'vegetable' Type
//              (2) quantity is greater than 0
//              (3) price is less than 10
let filteredProducts = products.filter(
  (product) =>
    product.type === "vegetable" && product.quantity > 0 && product.price < 10
);

```

<br/>
<div align="right">
  <b><a href="#section-04-the-filter-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Filtering Values

### Question

Filter the array of numbers using the filter helper, creating a new array that only contains numbers greater than 50.  Assign this new array to a variable called `filteredNumbers`. Don't forget to use the `return` keyword in the function!

```javascript
var numbers = [15, 25, 35, 45, 55, 65, 75, 85, 95];

var filteredNumbers;
```

### Solution

```javascript
let numbers = [15, 25, 35, 45, 55, 65, 75, 85, 95];

let filteredNumbers = numbers.filter(number => number > 50);
```

<br/>
<div align="right">
  <b><a href="#section-04-the-filter-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Handling Permissions with Filter

### Question

Filter the array of users, only returning users who have admin level access. Assign the result to the variable `filteredUsers`. Don't forget to use the `return` keyword in the function!

```javascript
var users = [
 { id: 1, admin: true },
 { id: 2, admin: false },
 { id: 3, admin: false },
 { id: 4, admin: false },
 { id: 5, admin: true },
];

var filteredUsers;
```

### Solution

```javascript
let users = [
 { id: 1, admin: true },
 { id: 2, admin: false },
 { id: 3, admin: false },
 { id: 4, admin: false },
 { id: 5, admin: true },
];

let filteredUsers = users.filter(user => user.admin);
```

<br/>
<div align="right">
  <b><a href="#section-04-the-filter-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Implementing `reject`

### Question

Create a function called `reject`. Reject should work in the opposite way of `filter` - if a function returns `true`, the item should *not* be included in the new array. 

**Hint**: you can reuse filter.

**Example**:

```javascript
var numbers = [10, 20, 30];
var lessThanFifteen = reject(numbers, function(number) {
  return number > 15;
});

// returns: [10]
lessThanFifteen()
```

### Solution

```javascript
function reject(array, iteratorFunction) {
  return array.filter(item => !iteratorFunction(item));
}
```

<br/>
<div align="right">
  <b><a href="#section-04-the-filter-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>
