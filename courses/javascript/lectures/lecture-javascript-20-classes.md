### 20. JavaScript
#### Classes & OOP


---

#### Programming Paradigms

1. Procedural Programming
1. Object Oriented Programming
1. Functional Programming (Focus on this in React course).



---

#### Procedural Programming

* Top to bottom line by line.
* When project gets bigger it gets messy.
* Hard to find bugs.


---

#### Object oriented programming

* Object oriented programming follows real-world modelling.
* An application consisting of child objects which are interacting with each other to form the product.
* Real world examples - car, computer


---

#### Object oriented programming

* Encapsulate the code.
* Divides code into units (objects).
* It reduces complexity.
* The code gets easier to read.


---

#### Procedural vs OOP
<img style="width: 800px;" src="/media/javascript-images/javascript-20/proceoop.png" alt="procedural & oop">


---

#### Making Ping Pong OOP

* What parts can we encapsulate?
* What parts have functionality which belongs to them and no other?
* Which parts can have some shared functionality?
<img style="width: 600px;" src="/media/javascript-images/javascript-20/ping1.png" alt="Ping pong">


---

#### Making Ping Pong OOP

* What parts can we encapsulate?
* What parts have functionality which belongs to them and no other?
* Which parts can have some shared functionality?
<img style="width: 600px;" src="/media/javascript-images/javascript-20/ping2.png" alt="Ping pong">


---

#### JavaScript & OOP

* JavaScript is a "multi-paradigm language".
* This offers flexibility.
* You can write procedural, class-oriented, or Functional Programming-style JavaScript code.


---


#### What is an object?

* A product that can do things and contains information about its current state.
* Each Object has a purpose and a task.
* Real world examples could be  a **lamp** or a **Human**.


---

#### Properties

* A property is a variable connected to a specific object.
* A property contains information about the object.


---

#### Methods

* A method is a function connected to a specific object.
* Methods are used to give an object functionality.


---

#### Classes

* A Class is like a **blueprint.**
* For example a Lamp is created from a blueprint(class).
* Many products are created from blueprints however when created they are **individual** products(objects).


---

#### Classes

* Classes are used to create objects.
* A class encapsulates data for the object.


---

####  Declaring a class

```JavaScript
// The ‘this’ keyword refers to the current instance of the class.

class Car {
  constructor(color, maxSpeed) {
    this.color = color;
    this.maxSpeed = maxSpeed;
  }
}
```



---

#### Constructor

* All ES6 Classes has a **Constructor** method
* The constructor method is a special method for creating and initializing an object created with a class.
* The constructor always run once, and its the first thing thats happening.
* There can only be one special method with the name "constructor" in a class.
* It is not mandatory to include a constructor definition. Every class by default has a constructor by default.


---

####  Class Expression

* An expression is any valid unit of code that resolves to a value.

```JavaScript
let Car = class {
  constructor(color, maxSpeed) {
    this.color = color;
    this.maxSpeed = maxSpeed;
  }
}
```



---

####  Named class expression

```JavaScript
let Car = class Car {
  constructor(color, maxSpeed) {
    this.color = color;
    this.maxSpeed = maxSpeed;
  }
}
```



---

#### Any number of instance can be created from a class, each instance is called **Object**.


---
  

####  Creating Objects from classes

* To create an instance of the class, use the **new** keyword followed by the class name. Following is the syntax for the same.

```JavaScript
let Car = class Car {
  constructor(color, maxSpeed) {
    this.color = color;
    this.maxSpeed = maxSpeed;
  }
}

// The new keyword is responsible for instantiation.
// The right hand side of the expression invokes the constructor.
let obj = new Car('red',70);

```


---

####  Methods in classes

```JavaScript
class Car {
  constructor(color, maxSpeed) {
    this.color = color;
    this.maxSpeed = maxSpeed;
  }

  test() {
    console.log('The color of the Car is ',this.color); // red
    console.log('The maximum speed of the Car is ',this.maxSpeed); // 70
  }
}
```


---
  
####  Accessing Methods and properties

* Once the object is instanciated the variables and functions connected to the object are called Properties and Methods.
* These can be accessed using dot notation.

```JavaScript
let carObj = new Car('red',70);
let color = carObj.color; // red
let maxSpeed = carObj.maxSpeed; // 70

carObj.test();
```


---

####  Accessing methods and properties

* Properties and methods can only be accessed if the object is instanciated

```JavaScript
class Car {

  test() {
    console.log('Calling the test function');
  }
}

// Will throw an Error since Car is not instanciated and just "blueprint"
Car.test(); // TypeError: Car.test is not a functionindex.
```


---

#### Inheritance

* A class can inherit methods and properties from its parent.
* And if we make a change in the parent class, all who inherits from it will also get the change.
<img style="width: 600px;" src="/media/javascript-images/javascript-20/classes1.png" alt="inheritance">


---

#### Inheritance

* A class can inherit methods and properties from its parent.
* And if we make a change in the parent class, all who inherits from it will also get the change.
<img style="width: 600px;" src="/media/javascript-images/javascript-20/classes2.png" alt="inheritance">


---

#### Inheritance

* A class can inherit methods and properties from its parent.
* And if we make a change in the parent class, all who inherits from it will also get the change.
<img style="width: 600px;" src="/media/javascript-images/javascript-20/classes3.png" alt="inheritance">


---

#### Inheritance
<img style="width: 300px;" src="/media/javascript-images/javascript-20/classes4.png" alt="inheritance">
  
```JavaScript
// cow is the new instance and Cow is the class(blueprint)
let cow = new Cow('muuuh');

console.log(cow); // { sound: 'muuuh', eat: function, fart: function }

cow.eat(); // works since it inherits this method
cow.fart();
```


---

####  Inheritance

```JavaScript
class Vehicle {
  constructor (type) {
    this.type = type;
  }
 
  getType () {
    return this.type;
  }
}

class Car extends Vehicle {
  constructor (type) {
    super(type);
  }
 
  getType () {
    return 'It is a car: ' + super.getType();
  }
}

let car = new Car('Tesla');
console.log(car.getType()); // It is a car: Tesla
```



---

####  Inheritance

```JavaScript
class Vehicle {
  constructor (type) {
    this.type = type;
  }
 
  drive () {
    console.log('They see me rollin in my' + this.type);
  }
}

class Car extends Vehicle {
  constructor (type) {
    super(type);
  }
}

let car = new Car('Tesla');
car.drive(); // They see me rollin in my Tesla
```


---

####  Getters & Setters

```JavaScript
class Person {
  constructor(name) {
    this._name = name;
  }

  get name() {
    return this._name.toUpperCase();
  }

  set name(newName) {
    this._name = newName;   // validation could be checked here such as only allowing non numerical values
  }
}
         
let bob = new Person('Bob');
console.log(bob.name);  // Outputs 'BOB'
bob.name = 'John';
```


---

#### No private properties in ES6


---

#### Static keyword

* The static keyword defines static methods for a class.
<br>
* Static methods are called without instantiating their class.
* Static methods are also not callable when the class is instantiated.
* Static methods are often used to create utility functions for an application.


---

####  Using Static

```JavaScript
class Car {
  static test() {
    console.log('Calling the static test function');
  }
}

Car.test(); // "Calling the static test function"

let carObj = new Car();
carObj.test(); //TypeError: obj.test is not a function
```


---

####  This in events in classes

```JavaScript
class Person {
  constructor(){
    // we have to bind this to access it in callOnClick otherwise it will be the document
    this.callOnClick = this.callOnClick.bind(this);

    this.name = 'Jane Doe';
    this.initEvents();
  }

  initEvents(){
    document.addEventListener('click', this.callOnClick);
  }

  callOnClick(){
    console.log(this.name);
  }
}
```


---

####  This in events in classes

* Arrow Function DOES NOT bind it's own this.
* The this value of the enclosing execution context is used since they lexically bind their context so this actually refers to the originating context.
* Results in that we do not have to bind it.

```JavaScript
class Person {
  constructor(){
    this.name = 'Jane Doe';
    this.initEvents();
  }

  initEvents(){
    document.addEventListener('click', this.callOnClickArrow);
  }

  callOnClickArrow = () => {
    console.log(this.name);
  }
}
```


---

####  Descriptive Blocks - Commenting Classes

```JavaScript
/** 
  * @desc this class will hold functions for user interaction
  * examples include user_pass(), user_username(), user_age(), user_regdate()
  * @author John Doe johndoe@email.com
  * @required settings.php
*/
class myWebClass { }
```


---

#### So it seems like JavaScript have OOP syntax..

* Yep, they came with came with ES6.
* But how did you write OOP before 2015?


---

#### Prototypes!

* Under the hood, JavaScript works differently.
* The class syntaxes it just a layer on top.
* JavaScript uses something called prototype pattern.
* We will take a look at this later on, but the main focus will be on OOP JavaScript
* The reason for this is that many other languages leans towards OOP and JavaScript classes are used both in React and Angular.


---

### <a href="https://github.com/SofthouseVxo/Education" target="_blank">Github examples!</a>