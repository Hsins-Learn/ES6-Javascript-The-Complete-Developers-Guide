# Section 15: Classes

- [Prototype Inheritance](#prototype-inheritance)
- [Refactor with `class` Keyword](#refactor-with-class-keyword)
- [[Exercise] Game Classes](#exercise-game-classes)
- [[Exercise] Subclassing Monsters](#exercise-subclassing-monsters)

## Prototype Inheritance

JavaScript doesn't really have the true object inheritance and it has what is called **"Prototype Inheritance"**. Let's see what we need to do whenever we want inherit an object from another object.

```javascript
// create the Car object
function Car(options) {
  this.title = options.title;
}

Car.prototype.drive = function() {
  return 'vroom';
}

// create the Toyota object and make inheritance from Car object
function Toyota(options) {
  Car.call(this, options);
  this.color = options.color;
}

Toyota.prototype = Object.create(Car.prototype);
Toyota.prototype.constructor = Toyato;
Toyota.prototype.honk = function() {
  return 'beep';
}

const car = new Car({ title: 'Focus' });
const toyota = new Toyota({ color: 'red', title: 'Daily Driver' });
car.drive();
toyota.drive();
```

<br/>
<div align="right">
  <b><a href="#section-15-classes">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## Refactor with `class` Keyword

ECMAScript 6 provides us the `class` keyword to implement inheritance easily. But it's important to know that whenever we use `class` keyword, we're still making use of prototype inheritance under the hood.

```javascript
// create the Car class
class Car {
  constructor({ title }) {
    this.title = title;
  }

  drive() {
    return 'vroom';
  }
}

// create the Toyota class and make inheritance from Car class
class Toyota extends Car {
  constructor(options) {
    super(options);
    this.title = options.title;
  }

  honk() {
    return 'beep';
  }
}

const car = new Car({ title: 'Focus' });
const toyota = new Toyota({ color: 'red', title: 'Daily Driver' });
car.drive();
toyota.drive();
```

The subclass `Toyota` is inheriting or extending from class `Car`. Both `Toyota` and `Car` have defined the constructor method and we need to call the `super()` method inside the constructor of subclass `Toyota`. The `super()` method will execute a method on the parent class with same exact name.

<p align="center">
  <img src="https://i.imgur.com/XxOu5Nz.png" alt="Class Inheritance and Super() Method" height="250px">
</p>

<br/>
<div align="right">
  <b><a href="#section-15-classes">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Game Classes

### Question

You are a game developer tasked with setting up some basic classes for a new game you are working on. Create a class called `Monster`.  In the constructor, you'll need to do some basic setup for Monster whenever they are created.

- Initialize the Monster's health to `100`.
- The constructor will be called with an `options` object that has a `name` property. Assign the `name` to the Monster

### Solution

```javascript
class Monster {
  constructor(options) {
    this.health = 100;
    this.name = options.name;
  }
}
```

<br/>
<div align="right">
  <b><a href="#section-15-classes">[ ↥ Back To Top ]</a></b>
</div>
<br/>

## [Exercise] Subclassing Monsters

### Question

Now that you have a monster created, create a subclass of the `Monster` called `Snake`.

- The Snake should have a `bite` method. The only argument to this method is another instance of a Snake.
- The instance of Snake that is passed in should have their health deducated by 10.

### Solution

```javascript
class Monster {
  constructor(options) {
    this.health = 100;
    this.name = options.name;
  }
}

class Snake extends Monster {
  constructor(options) {
    super(options);
  }

  bite(snake) {
    snake.health -= 10;
  }
}
```

<br/>
<div align="right">
  <b><a href="#section-15-classes">[ ↥ Back To Top ]</a></b>
</div>
<br/>
