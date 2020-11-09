# Section 16: Generators

- [Section 16: Generators](#section-16-generators)
  - [The `for ... of ... ` Loop](#the-for--of---loop)
  - [Create a Generator](#create-a-generator)

## The `for ... of ... ` Loop

The `for ... of ...` loop iterate through arrays of data.

```javascript
// Example 1
const colors = ['red', 'green', 'blue'];

for (let color of colors) {
  console.log(color);
}

// Example 2
const numbers = [1, 2, 3, 4];
let total = 0;

for (let number of numbers) {
  total += number;
}
```

<br/>
<div align="right">
  <b><a href="#section-16-generators">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## Create a Generator

A Generator is a function that can be entered and exited multiple times. We can create a generator by adding an asterisk symbol `*` right after the `function` keyword or left before the function name.

```javascript
function* shopping() {
  // stuff on the sidewalk
  // walking down the sidewalk
  // go into the store with cash
  const stuffFromStore = yield 'cash';

  // walking to laundry place
  const cleanClothes = yield 'laundry';

  // walking back home
  return [stuffFromStore, cleanClothes];
}

// stuff in the store
const gen = shopping();
gen.next(); // leaving our house
// walked into the store
// walking up and down the aisles...
// purchase our stuff

gen.next('groceries'); // leaving the store with groceries
gen.next('clean clothes');
```

Note that the `yield` let us define the different execution state inside the generator. Each `yield` will return an object like `{value: anyType, done: boolean}`.

<br/>
<div align="right">
  <b><a href="#section-16-generators">[ ↥ Back To Top ]</a></b>
</div>
<br/>