# Section 07: The `reduce` Helper

- [The `reduce` Helper](#the-reduce-helper)
- [About The Reducer Function](#about-the-reducer-function)
- [[Exercise] Distance Traveled](#exercise-distance-traveled)
- [[Exercise] Reducing Properties](#exercise-reducing-properties)
- [[Exercise] Custom `Unique` Helper](#exercise-custom-unique-helper)

## The `reduce` Helper

The `reduce()` method executes the provided **reducer function** on each array element and return the value from the accumulator. It would reduces the array to a single value.

```javascript
let numbers = [ 10, 20 , 30 ];

// loop the array by using for loop
let sum = 0;
for (let i = 0; i < numbers.length; i++) {
  sum += numbers[i];
}

// loop the array by using reduce helper
let sum = numbers.reduce((value, number) => value + number, 0);
```

Note that the `reduce()` method doesn't change the original array. Let's try the more complicated example.

```javascript
let primaryColors = [
  { color: 'red' },
  { color: 'yellow' },
  { color: 'blue' }
];

let colors = primaryColors.reduce((previous, primaryColor) => {
  previous.push(primaryColor.color);
  return previous;
}, []);
```

<br/>
<div align="right">
  <b><a href="#section-07-the-reduce-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## About The Reducer Function

The reducer function takes four arguments:

- Accumulator: `accumulator`
- Current Value: `currentValue`
- Current Index: `currentIndex` (Optional)
- Source Array: `array` (Optional)

The first time the callback function is called, `accumulator` and `currentValue` can be one of two values.

- If `initialValue` is provided in the call to `reduce()`, then `accumulator` will be equal to `initialValue`, and `currentValue` will be equal to the first value in the array.
- If no `initialValue` is provided, then `accumulator` will be equal to the first value in the array, and currentValue will be equal to the second.

<br/>
<div align="right">
  <b><a href="#section-07-the-reduce-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Distance Traveled

### Question

Use the `reduce` helper to find the sum of all the distances traveled. Assign the result to the variable `totalDistance`.

```javascript
var trips = [{ distance: 34 }, { distance: 12 } , { distance: 1 }];

var totalDistance;
```

### Solution

```javascript
let trips = [{ distance: 34 }, { distance: 12 } , { distance: 1 }];

let totalDistance = trips.reduce((total, trip) => total + trip.distance, 0);
```

<br/>
<div align="right">
  <b><a href="#section-07-the-reduce-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Reducing Properties

### Question

Use the `reduce` helper to create an object that tallies the number of sitting and standing desks. The object returned should have the form `{ sitting: 3, standing: 2 }`. The initial value has been provided to you.

```javascript
var desks = [
  { type: 'sitting' },
  { type: 'standing' },
  { type: 'sitting' },
  { type: 'sitting' },
  { type: 'standing' }
];

var deskTypes = desks.reduce(function() {

}, { sitting: 0, standing: 0 });
```

### Solution

```javascript
let desks = [
  { type: 'sitting' },
  { type: 'standing' },
  { type: 'sitting' },
  { type: 'sitting' },
  { type: 'standing' }
];

let deskTypes = desks.reduce((obj, desk) => {
  obj[Object.values(desk)] += 1;
  return obj;
}, { sitting: 0, standing: 0 });
```

<br/>
<div align="right">
  <b><a href="#section-07-the-reduce-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>


## [Exercise] Custom `Unique` Helper

### Question

Write a function called `unique` that will remove all the duplicate values from an array. For example, given the following array `var numbers = [1, 1, 2, 3, 4, 4];`. Your function should return `[1, 2, 3, 4]`.

**Hint*: Use the `reduce` and `find` helpers.

### Solution

```javascript
function unique(array) {
  return array.reduce((acc, num) => {
    acc.find(existNum => num === existNum) ? acc : acc.push(num);
    return acc;
  }, []);
}
```

<br/>
<div align="right">
  <b><a href="#section-07-the-reduce-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>
