## Unit testing with MochaJS and Node.js

---

#### What is unit testing?

* Unit testing is the process of testing the implemented code at a module / component level.
* Unit tests are done to validate that each unit of the software performs as designed.
* A unit is the smallest testable part of any software.

---

#### Automated unit tests

* Unit tests are typically automated tests written and run by software developers.

---

#### Why unit testing?

* Unit testing increases confidence in changing/ maintaining code.
* If the unit tests are written in a good way and we run them every time any code is changed, we will be able to promptly catch any defects introduced due to the change. 

---

#### JavaScript Unit Testing Framework and Tools
* MochaJS
* Jasmine
* JEST
* KARMA
* ChaiJS
* QUnit
* and many more..

---

#### Testing with [MochaJS](https://mochajs.org/)

Global
```
$ npm install --global mocha
```

As a development dependency for your project:
```
$ npm install --global mocha
```

We install it as a development dependency since the we only run the tests before something is deployed.

---

#### Running tests

Place in package.json
```JSON
"scripts": {
  "test": "mocha"
}
```

```Shell
$ npm run test
```

Now mocha will look for test that are named ```test.js``` och files in a folder called ```test```.

---

#### MochaJS - describe function

* ```describe()``` is a way to group our tests in Mocha.

```
describe('some name', function(){
  // can nest more describe()'s here, or tests go here
});
```

```
describe('some name', function(){
  describe('some name', function(){
    // can nest more describe()'s here, or tests go here
  });
});
```

#### MochaJS - it function

```
it('should blah blah blah', function(){
  // place test here
});
```

```
describe('some name', function(){
  it('should blah blah blah', function(){
    // place test here
  });
});
```

#### Assertions libraries

* An assertion library is a tool to verify things are correct 
* Node.js has a built-in assert module.
* The assert module provides a set of assertion functions for verifying invariants.
* [Complete list of nodejs assertion functions](https://nodejs.org/api/assert.html)

```
var assert = require('assert');
```

```
assert.equal(actual, expected[, message])
assert.match(string, regexp[, message])
```

---

#### Assert.equal

```
assert.equal(1, 1);
// OK, 1 == 1
assert.equal(1, '1');
// OK, 1 == '1'

assert.equal(1, 2);
// AssertionError: 1 == 2

```

---

#### assert.equal

```
var users = ['john', 'jane', 'kitty'];

describe('users test', function(){
  it('should always be 3 users', () => {
    assert.equal(users.length, 3);
  })
});