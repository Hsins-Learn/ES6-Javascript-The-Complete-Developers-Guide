# Section 10: Arrow Functions

- [Fat Arrow Functions](#fat-arrow-functions)
- [When to Use Arrow Functions?](#when-to-use-arrow-functions)
- [[Exercise] Refactoring Keyword Functions](#exercise-refactoring-keyword-functions)
- [[Exercise] Arrow Functions Aren't Always a Solution](#exercise-arrow-functions-arent-always-a-solution)

## Fat Arrow Functions

We used to write the ECMAScript 5 function with `function` keyword. In the ECMAScript 6, we can use the arrow function instead.

```javascript
// ECMAScript 5: The `funcion` keyword
const add = function(a, b) {
  return a + b;
}

// ECMAScript 6: Arrow Functions
const add = (a, b) => a + b;
```

Also, we can use arrow functions with the array methods.

```javascript
const numbers = [1, 2, 3];
numbers.map(number => 2 * number);
```

<br/>
<div align="right">
  <b><a href="#section-10-arrow-functions">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## When to Use Arrow Functions?

Note that the arrow functions will **bind the value of `this` to the surrounding context**. Let's write an object that's going to represent a team of people.

```javascript
// the value of `this` of function is lost
const team = {
  members: ['Jane', 'Bill'],
  teamName: 'Super Squad',
  teamSummary: function() {
    return this.members.map(function(member) {
      return `${member} is on team ${this.teamName}`;
    });
  }
}
```

In above codes, the value of `this` of function is lost and we have to use `bind` helper. The `bind(this)` will bind the context to the current context. Let's refactor the function-keyword function using the arrow function.

```javascript
const team = {
  members: ['Jane', 'Bill'],
  teamName: 'Super Squad',
  teamSummary: function() {
    return this.members.map(member => {
      return `${member} is on team ${this.teamName}`;
    });
  }
}
```

In the above codes, the arrow funtions make use of what is called **Lexical This**. (The word `lexical` means the placement of `this` term depends on how it's interpreted or how it's evaluated.)

Note that `this` is automatically set equal to `this` in the surrounding context which in our case is equal to the `team`.

<br/>
<div align="right">
  <b><a href="#section-10-arrow-functions">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Refactoring Keyword Functions

### Question

The function below uses the `function` keyword. There's nothing wrong with using the `function` keyword here, but it might look a bit nicer if we refactor it to use the fat arrow syntax instead.

Refactor the code below to use a fat arrow function. Remember the rules of fat arrow functions:

1. If the function has a single expression in its body, the curly braces and `return` keyword can be removed.
2. If the function has a single argument, the parentheses around the argument list can be removed

```javascript
const fibonacci = function(n) {
  if (n < 3) return 1;
  return fibonacci(n - 1) + fibonacci(n - 2);
}
```

### Solution

```javascript
const fibonacci = n => (n < 3) ? 1 : fibonacci(n - 1) + fibonacci(n - 2);
```

<br/>
<div align="right">
  <b><a href="#section-10-arrow-functions">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Arrow Functions Aren't Always a Solution

### Question

Arrow functions bind the value of `this` to the surrounding context, and sometimes this isn't the behavior we expect.

The code below has an object that represents a users profile. The profile has a `name` currently. Add another key to this object called `getName`.  `getName` should be a function that returns the profiles name, using `this.name`. Does the solution work with a fat arrow function or will you have to use a function keyword instead?

```javascript
const profile = {
  name: 'Alex'
};
```

### Solution

```javascript
const profile = {
  name: 'Alex',
  getName: function() { return this.name; }
};
```

<br/>
<div align="right">
  <b><a href="#section-10-arrow-functions">[ ↥ Back To Top ]</a></b>
</div>
<br/>