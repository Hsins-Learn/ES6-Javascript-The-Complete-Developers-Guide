# Section 09: Template Strings

- [The Template Strings](#the-template-strings)
- [[Exercise] Template Strings in Practice](#exercise-template-strings-in-practice)
- [[Exercise] Name Helpers](#exercise-name-helpers)

## The Template Strings

```javascript
function getMessage() {
  const year = new Data().getFullYear();

  return `The year is ${year}.`;
}

getMessage();
```

The template strings use back-ticks symbol rather than the single or double quotes we're used to with regular strings. We can use template strings whenever we're using strings where we have to mix tons of different variables

<br/>
<div align="right">
  <b><a href="#section-08-const-and-let">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Template Strings in Practice

### Question

Refactor the function to use template strings

```javascript
function doubleMessage(number) {
  return "Your number doubled is " + (2 * number);
}
```

### Solution

```javascript
function doubleMessage(number) {
  return `Your number doubled is ${2 * number}`;
}
```

<br/>
<div align="right">
  <b><a href="#section-08-const-and-let">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Name Helpers

### Question

Refactor the function to use template strings.

```javascript
function fullName(firstName, lastName) {
  return firstName + lastName;
}
```

### Solution

```javascript
function fullName(firstName, lastName) {
  return `${firstName} ${lastName}`;
}
```

<br/>
<div align="right">
  <b><a href="#section-08-const-and-let">[ ↥ Back To Top ]</a></b>
</div>
<br/>
