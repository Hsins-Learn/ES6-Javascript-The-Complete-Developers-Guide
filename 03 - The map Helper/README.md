# Section 03: The `map` Helper

- [The `map` Helper](#the-map-helper)
- [[Exercise] Plucking Values](#exercise-plucking-values)
- [[Exercise] Calculate Values with `map()`](#exercise-calculate-values-with-map)
- [[Exercise] Implement `Pluck`](#exercise-implement-pluck)

## The `map` Helper

The `map()` method executes a provided function once for each array element and creates a new array with the results. Make sure that we have the `return` keyword in the given function.

```javascript
let numbers = [1, 2, 3];
let doubleNumbers = [];

// loop the array by using for loop
for (let i = 0; i < numbers.length; i++) {
  doubleNumbers.push(numbers[i] * 2);
}

// loop the array by using map() method
doubleNumbers = numbers.map(number => number *2);
```

Note that the `map()` method doesn't change the original array. Let's see another example which would be frequently with client side rendering frameworks like React or Angular.

```javascript
let cars = [
  { model: 'Buick', price: 'cheap' },
  { model: 'Camaro', price: 'expensive' }
];

let prices = cars.map(car => car.price);
```

<br/>
<div align="right">
  <b><a href="#section-03-the-map-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Plucking Values

### Question

Using `map()`, create a new array that contains the `height` property of each object. Assign this new array to the variable `heights`. Don't forget to use the `return` keyword in the function!

```javascript
var images = [
  { height: '34px', width: '39px' },
  { height: '54px', width: '19px' },
  { height: '83px', width: '75px' },
];

var heights;
```

### Solution

```javascript
let images = [
  { height: '34px', width: '39px' },
  { height: '54px', width: '19px' },
  { height: '83px', width: '75px' },
];

let heights = images.map(image => image.height);
```

<br/>
<div align="right">
  <b><a href="#section-03-the-map-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Calculate Values with `map()`

Using `map()`, create a new array that contains the `(distance / time)` value from each trip. In other words, the new array should contain the `(distance / time)` value. Assign the result to the variable `speeds`.

### Question

```javascript
var trips = [
  { distance: 34, time: 10 },
  { distance: 90, time: 50 },
  { distance: 59, time: 25 }
];

var speeds;
```

### Solution

```javascript
let trips = [
  { distance: 34, time: 10 },
  { distance: 90, time: 50 },
  { distance: 59, time: 25 }
];

let speeds = trips.map(trip => trip.distance / trip.time);
```

<br/>
<div align="right">
  <b><a href="#section-03-the-map-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Implement `Pluck`

### Question

Implement a `pluck` function. Pluck should accept an array and a string representing a property `name` and return an array containing that property from each object.

**Example**

```javascript
var paints = [ { color: 'red' }, { color: 'blue' }, { color: 'yellow' }];

// returns ['red', 'yellow', 'blue']
pluck(paints, 'color');
```

**Hint**

Remember that you can access a property on an object by using square bracket notation.

```javascript
var person = { name: 'Bill' };
// returns 'Bill'
person['name'];
```

### Solution

```javascript
function pluck(array, property) {
  return array.map(object => object[property]);
}
```

<br/>
<div align="right">
  <b><a href="#section-03-the-map-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>
