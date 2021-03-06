### 9. Backend APIs
#### Testing Web APIs

---

#### Purpose and Scope

* What is software testing.
* Why do we test.
* What kinds of testing do we do.
* What does it actually look like in real life.


---

#### What is and Why we test

“Software testing is an investigation conducted to provide stakeholders with information about the quality of the software product or service under test.”

* It’s about Control
* Knowing your quality has value
* No (known) faults is not a good thing


---

#### What kinds of testing do we do

Testing is an integrated part of development
* Unit testing
  * Test Driven Design
  * Behavior Driven Design
* Integration testing
* Verification and Validation



---

#### Unit Tests

Test individual units of source code, together with associated control data, usage procedures, and operating procedures, to determine whether they are fit for use.

* Testing individual classes or functions
* Isolate code under test by mocking or stubbing dependent systems
* Developers write this as part of the code
  * Code coverage - is every line of code tested by unit tests
  * Design for Testability
  * Unit test names can be a bit cryptic to understand
  * Executed as part of the build step
* Sometimes referred to as “white box” testing
  * Testing the inside of the service boundary


---

#### Unit Tests - Test Driven Development (TDD)

Write tests first, then code

* Variant of unit testing that promotes full code coverage
* Helps you break down problems into testable chunks
* Architecture and consistency as an afterthought



---

#### Unit Tests - Behavior Driven Development (BDD)

An Agile software development process that encourages collaboration between developers, QA and non-technical or business participants in a software project


* Write tests as plain text that can be understood by everyone.
  * Each line of text is parsed to execute test code.

* ```Given``` that a customer previously bought a black sweater from me
* ```And``` I have three black sweaters in stock
* ```When``` they return the black sweater for a refund
* ```Then``` I should have four black sweaters in stock.


---

#### Integration Testing

When testing for the complete behavior of a product. Where all individual software modules are combined and tested as a group.

* Sometimes referred to as “black box” testing
  * Testing the outside of the service boundary.
* May be automated
  * Sometimes written together with the code.
  * More often written separately.


---

#### Verification and Validation

Before Software is Released into Production
* Validation: Assurance that a product, service, or system meets the needs of the customer.
* Verification: The evaluation of whether or not a product, service, or system complies with a regulation, requirement, specification, or imposed condition.



---

#### In Real Life

Depends on the size and testing maturity of the company.
* The bigger the company
  * The more customers they have and faults are more costly.
  * Bigger testing budget.
* Testing Maturity
  * Repetitive testing should be automated.
  * Testing should focus on user value.
* Common setup
  * Tester is part of the team, responsible for driving quality and test awareness in the team.
  * Developers write code with unit tests, integration tests and validation usually done by tester.


---
				

#### Why do we need testers

* Developers are focused on “how” and “what should”
* Testers are focused on “what” and “what shouldn’t”
* Switching mindsets isn’t easy

<a href="https://youtu.be/IGQmdoK_ZfY?t=4" target="_blank">Movie time</a>


---

#### Conclusion

* Testing is about software value.
* Different stages of testing test for different things.
* TDD is about testability and coverage.
* BDD is about being able to communicate test results across organisations.
* Testers are part of the team.
* We need different roles in teams because mindset switching is hard.