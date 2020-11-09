# Section 11: Enhanced Object Literals

- [Enhanced Object Literals](#enhanced-object-literals)
- [[Exercise] Multiple Properties with Enhanced Notation](#exercise-multiple-properties-with-enhanced-notation)
- [[Exercise] Condensing Code with Enhanced Literals](#exercise-condensing-code-with-enhanced-literals)
- [[Exercise] Literals in Functions](#exercise-literals-in-functions)
- [[Exercise] Refactor to Use Enhanced Literal Notation](#exercise-refactor-to-use-enhanced-literal-notation)

## Enhanced Object Literals

With the Enhanced Object Literals feature, we can make object handling even easier in all modern browsers. Let's see the example below.

```javascript
// without Enhanced Object Literals
function createBookShop(inventory) {
  return {
    inventory: inventory,
    inventoryValue: function() {
      return this.inventory.reduce((total, book) => total + book.price, 0);
    },
    priceForTitle: function(title) {
      return this.inventory.find(book => book.title === title).price;
    }
  };
}

// with Enhanced Object Literals
function createBookShop(inventory) {
  return {
    inventory,
    inventoryValue() {
      return this.inventory.reduce((total, book) => total + book.price, 0);
    },
    priceForTitle(title) {
      return this.inventory.find(book => book.title === title).price;
    }
  };
}

const inventory = [
  { title: 'Harry Potter', price: 10 },
  { title: 'Eloquent JavaScript', price: 15 }
];

const bookShop = createBookShop(inventory);
```

<br/>
<div align="right">
  <b><a href="#section-11-enhanced-object-literals">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Multiple Properties with Enhanced Notation

### Question

Refactor to use enhanced literal notation.

```javascript
const red = '#ff0000';
const blue = '#0000ff';

const COLORS = { red: red, blue: blue };
```

### Solution

```javascript
const red = '#ff0000';
const blue = '#0000ff';

const COLORS = { red, blue };
```

<br/>
<div align="right">
  <b><a href="#section-11-enhanced-object-literals">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Condensing Code with Enhanced Literals

### Question

Refactor the following to use enhance object literal syntax.

```javascript
const fields = ['firstName', 'lastName', 'phoneNumber'];
const props = { fields: fields };
```

### Solution

```javascript
const fields = ['firstName', 'lastName', 'phoneNumber'];
const props = { fields };
```

<br/>
<div align="right">
  <b><a href="#section-11-enhanced-object-literals">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Literals in Functions

### Question

Refactor to use enhanced literal notation.

```javascript
const canvasDimensions = function(width, initialHeight) {
  const height = initialHeight * 9 /16;
  return {
    width: width,
    height: height
  };
}
```

### Solution

```javascript
const canvasDimensions = function(width, initialHeight) {
  const height = initialHeight * 9 /16;
  return { width, height };
}
```

<br/>
<div align="right">
  <b><a href="#section-11-enhanced-object-literals">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Refactor to Use Enhanced Literal Notation

### Question

Refactor to use enhanced literal notation.

```javascript
const color = 'red';

const Car = {
  color: color,
  drive() {
    return 'Vroom!';
  },
  getColor() {
    return this.color;
  }
};
```

### Solution

```javascript
const color = 'red';

const Car = {
  color,
  drive() { return 'Vroom!' },
  getColor() { return this.color }
};
```

<br/>
<div align="right">
  <b><a href="#section-11-enhanced-object-literals">[ ↥ Back To Top ]</a></b>
</div>
<br/>