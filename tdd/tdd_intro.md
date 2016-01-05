## Test Driven Development

Test Driven Development is the process of using automated tests to drive the design of software. Put simply, the main concept of the process is to write a test first, followed by implementing just enough code to satisfy the test, then a final but important step of refactoring.

This process not only makes sure that the implemented code is fit for its purpose but it also aids you as a developer in thinking about the design of the code you write. It keeps the focus on small iterative steps that collectively build solid functionality and ultimately result in solid, working software.

```
* The suite of unit tests provides constant feedback that each component is still working.
* The unit tests act as documentation that cannot go out-of-date, unlike separate documentation, which can and frequently does.
* When the test passes and the production code is refactored to remove duplication, it is clear that the code is finished, and the developer can move on to a new test.
* Test-driven development forces critical analysis and design because the developer cannot create the production code without truly understanding what the desired result should be and how to test it.
* The software tends to be better designed, that is, loosely coupled and easily maintainable, because the developer is free to make design decisions and refactor at any time with confidence that the software is still working. This confidence is gained by running the tests. The need for a design pattern may emerge, and the code can be changed at that time.
* The test suite acts as a regression safety net on bugs: If a bug is found, the developer should create a test to reveal the bug and then modify the production code so that the bug goes away and all other tests still pass. On each successive test run, all previous bug fixes are verified.
* Reduced debugging time!
```



* Acceptance tests - check the entire stack
* Integration tests - check two or more components
* Unit tests - check a single component


