# Section 14: Destructuring

- [Destructuring](#destructuring)
- [Destructuring Arguments Object](#destructuring-arguments-object)
- [Destructuring Arrays](#destructuring-arrays)
- [Destructuring Both](#destructuring-both)
- [[Exercise] Destructuring in Practice](#exercise-destructuring-in-practice)
- [[Exercise] Array Destructuring in Practice](#exercise-array-destructuring-in-practice)
- [[Exercise] Recursion with Destructuring](#exercise-recursion-with-destructuring)


## Destructuring

Destructuring is a convenient way of extracting multiple values from data stored in nested objects and arrays. It can be used to unpack values from arrays, or properties from objects, into distinct variables.

```javascript
let expense = {
  type: 'Businsess',
  amount: '$45 USD'
};

// assign variables without destructuring assignment
const type = expense.type;
const amount = expense.amount;

// assign variables with destructuring assignment
const { type, amount } = expense;
```

The curly braces in the destructuring syntax means when they were on the left hand side of the equals sign, it should declare variables called `type` and `amount` and want it to reference the `expense.type` and `expense.amount` propertys.

<br/>
<div align="right">
  <b><a href="#section-14-destructuring">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## Destructuring Arguments Object

```javascript
let savedFiled = {
  extension: 'jpg',
  name: 'repost',
  size: 14040
};

function fileSummary({ name, extension, size }, { color }) {
  return `${color} The file ${name}.${extension} is of size ${size}`;
}

fileSummary(saveFiled, { color: 'red' });
```

<br/>
<div align="right">
  <b><a href="#section-14-destructuring">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## Destructuring Arrays

```javascript
const companies = [
  'Google',
  'Facebook',
  'Uber'
];

const [ name, name2, ...rest ] = companies;
```

<br/>
<div align="right">
  <b><a href="#section-14-destructuring">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## Destructuring Both

```javascript
const companies = [
  { name: 'Google', location: 'Mountain View' },
  { name: 'Facebook', location: 'Menlo Park' },
  { name: 'Uber', location: 'San Francisco' }
];

// result: 'Mountain View'
const [{ location }] = companies;
console.log(location);
```

```javascript
const Google = {
  locations: ['Mountain View', 'New York', 'London']
};

// result: 'Mountain View'
const { locations: [ location ] } = Google;
console.log(location);
```

<br/>
<div align="right">
  <b><a href="#section-14-destructuring">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Destructuring in Practice

### Question

The snippet of code below duplicates references to `profile` inside of the `isEngineer` function. Perhaps we can reduce the amount of code used for referencing the `title` and `department` properties. Refactor this code to use destructuring. Can you get the body of the `isEngineer` function down to a single line?

```javascript
const profile = {
  title: 'Engineer',
  department: 'Engineering'
};

function isEngineer(profile) {
  var title = profile.title;
  var department = profile.department;
  return title === 'Engineer' && department === 'Engineering';
}
```

### Solution

```javascript
const profile = {
  title: 'Engineer',
  department: 'Engineering'
};

function isEngineer({ title, department }) {
  return title === 'Engineer' && department === 'Engineering';
}
```

<br/>
<div align="right">
  <b><a href="#section-14-destructuring">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Array Destructuring in Practice

### Question

The `classes` variable holds an array of arrays, where each array represents a single class that a student is enrolled in. Convert this array of arrays into an array of objects, where each object has the keys `subject`, `time`, and `teacher` and assign the result to `classesAsObject`.  Use array destructuring and the map helper.

An array for a class has the form `[subject, time, teacher]`.

The resulting data structure should look something like the following:

```javascript
const classesAsObject = [{ subject: 'Geography', time: '2PM', teacher: 'Mrs. Larsen' }]
```

```javascript
const classes = [
  [ 'Chemistry', '9AM', 'Mr. Darnick' ],
  [ 'Physics', '10:15AM', 'Mrs. Lithun'],
  [ 'Math', '11:30AM', 'Mrs. Vitalis' ]
];

const classesAsObject;
```

### Solution

```javascript
const classes = [
  ["Chemistry", "9AM", "Mr. Darnick"],
  ["Physics", "10:15AM", "Mrs. Lithun"],
  ["Math", "11:30AM", "Mrs. Vitalis"],
];

const classesAsObject = classes.map(([ subject, time, teacher ]) => ({ subject, time, teacher }));
```

<br/>
<div align="right">
  <b><a href="#section-14-destructuring">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Recursion with Destructuring

### Question

Use array destructuring, recursion, and the rest/spread operators to create a function `double` that will return a new array with all values inside of it multiplied by two. **Do not use any array helpers!** Sure, the `map`, `forEach`, or `reduce` helpers would make this extremely easy but give it a shot the hard way anyways:)

**Input**: `double([1, 2, 3])`
**Output**: `[2, 4, 6]`

**Hint**: Don't forget that with recursion you must add a base case so you don't get an infinite call stack. For example, if 'const `[ number, ...rest ] = numbers` and number is undefined do you need to keep walking through the array?

### Solution

```javascript
const numbers = [1, 2, 3];

function double([number, ...rest]) {
  return rest.length === 0 ? [number * 2] : [number * 2, ...double(rest)];
}
```

<br/>
<div align="right">
  <b><a href="#section-14-destructuring">[ ↥ Back To Top ]</a></b>
</div>
<br/>
