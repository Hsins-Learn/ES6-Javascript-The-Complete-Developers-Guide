# Section 02: The `forEach` Helper

- [The `forEach` Helper](#the-foreach-helper)
- [[Exercise] Moving Away From For Loops](#exercise-moving-away-from-for-loops)
- [[Exercise] Processing Values](#exercise-processing-values)

## The `forEach` Helper

The `forEach()` method executes a provided function once for each array element.

```javascript
let colors = ['red', 'blue', 'green'];

// loop the array by using for loop
for (let i = 0; i < colors.legnth; i++) {
  console.log(colors[i]);
}

// loop the array by using forEach method
colors.forEach(color => console.log(color));
```

Let's see another example, we're going to use `forEach()` helper to calculate the sum of a list of numbers.

```javascript
let sum = 0                     // create a variable to hold the sum
let numbers = [1, 2, 3, 4, 5];  // create an array of numbers to be added

// loop over the array with forEach() helper
numbers.forEach(num => sum += num);
```

Note that the `forEach()` helper is kind of Swiss Army Knife of array helpers and every other helpers could be reimplemented using `forEach()` helper.

<br/>
<div align="right">
  <b><a href="#section-02-the-foreach-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Moving Away From For Loops

### Question

The code below is calling `savePost` three times, but it is doing so using a for loop. This implementation works, but the for loop makes it more challenging to understand the purpose of the function. Rather than using a for loop, refactor the code below to instead use the forEach helper.

```javascript
function handlePosts() {
  var posts = [
    { id: 23, title: 'Daily JS News' },
    { id: 52, title: 'Code Refactor City' },
    { id: 105, title: 'The Brightest Ruby' }
  ];

  for (var i = 0; i < posts.length; i++) {
    savePost(posts[i]);
  }
}
```

### Solution

```javascript
function handlePosts() {
  let posts = [
    { id: 23, title: 'Daily JS News' },
    { id: 52, title: 'Code Refactor City' },
    { id: 105, title: 'The Brightest Ruby' }
  ];

  posts.forEach(post => savePost(post));
}
```

<br/>
<div align="right">
  <b><a href="#section-02-the-foreach-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Processing Values

### Question

The array below contains an array of objects, each of which is a representation of an image. Using the `forEach()` helper, calculate the area of each image and store it in a new array called `areas`. The area of an image can be calculated as `image.height * image.width`.

```javascript
var images = [
  { height: 10, width: 30 },
  { height: 20, width: 90 },
  { height: 54, width: 32 }
];
var areas = [];
```

### Solution

```javascript
let images = [
  { height: 10, width: 30 },
  { height: 20, width: 90 },
  { height: 54, width: 32 }
];

let areas = [];
images.forEach(image => areas.push(image.height * image.width));
```

<br/>
<div align="right">
  <b><a href="#section-02-the-foreach-helper">[ ↥ Back To Top ]</a></b>
</div>
<br/>