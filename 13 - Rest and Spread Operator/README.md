# Section 13: Rest and Spread Operators

- [The Rest Operators `...`](#the-rest-operators-)
- [The Spread Operators](#the-spread-operators)
- [[Exercise] Many, Many Arguments](#exercise-many-many-arguments)
- [[Exercise] Spreadin' Arrays](#exercise-spreadin-arrays)
- [[Exercise] Mixing Rest and Spread](#exercise-mixing-rest-and-spread)

## The Rest Operators `...`

The rest operator `...` is used to gathering together variables. It can be used in function arguments whenever we want to capture a list of variables or a list of arguments.

```javascript
function addNumbers(...numbers) {
  return numbers.reduce((sum, number) => sum + number, 0);
}

addNumbers([1, 2, 3, 4, 5]);
```

<br/>
<div align="right">
  <b><a href="#section-13-rest-and-spread-operators">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## The Spread Operators

The spread operator `...` is used to flattening or spreading gathering variables.

```javascript
const defaultColors = ['red', 'green'];
const userFavoriteColors = ['orange', 'yellow'];

// use concat() method
// ['red', 'green', 'orange', 'yellow']
colors = defaultColors.concat(userFavoriteColors);

// use spread operators
colors = [...defaultColors, ...userFavoriteColors];
```

We can also mix and match the spread and rest operators.

```javascript
function validShoppingList(...items) {
  if (item.indexOf('milk') < 0) {
    return ['milk', ...items];
  }
  return items;
}

validShoppingList('oranges', 'bread', 'eggs');
```

Imaging that we're going to update the legacy API in a JavaScript library. We can also use rest and spread operators to catch the balance.

```javascript
const MathLibrary = {
  calculateProduct(...rest) {
    console.log('Please use the multiply method instead');
    return .this.multiply(...rest);
  },
  multiply(a, b) {
    return a * b;
  }
}
```

<br/>
<div align="right">
  <b><a href="#section-13-rest-and-spread-operators">[ ↥ Back To Top ]</a></b>
</div>
<br/>


## [Exercise] Many, Many Arguments

### Question

Refactor the following function to use the rest operator. Remember, an argument using the rest operator does **not** need to be called `'rest'`.

```javascript
function product(a, b, c, d, e) {
  var numbers = [a, b, c, d, e];

  return numbers.reduce(function(acc, number) {
    return acc * number;
  }, 1)
}
```

### Solution

```javascript
function product(...numbers) {
  return numbers.reduce(function(acc, number) {
    return acc * number;
  }, 1)
}
```

<br/>
<div align="right">
  <b><a href="#section-13-rest-and-spread-operators">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Spreadin' Arrays

### Question

Refactor the following to use the spread operator.

```javascript
function join(array1, array2) {
  return array1.concat(array2);
}
```

### Solution

```javascript
function join(array1, array2) {
  return [...array1, ...array2];
}
```

<br/>
<div align="right">
  <b><a href="#section-13-rest-and-spread-operators">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Mixing Rest and Spread

### Question

Refactor the following to use only the rest operator.

```javascript
function unshift(array, a, b, c, d, e) {
  return [a, b, c, d, e].concat(array);
}
```

### Solution

```javascript
function unshift(array, ...rest) {
  return [...rest, ...array];
}
```

<br/>
<div align="right">
  <b><a href="#section-13-rest-and-spread-operators">[ ↥ Back To Top ]</a></b>
</div>
<br/>
