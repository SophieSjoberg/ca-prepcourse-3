## Test Driven Development

Test Driven Development is the process of using automated tests to drive the design of software. Put simply, the main concept of the process is to write a test first, followed by implementing just enough code to satisfy the test, then a final but important step of refactoring.

This process not only makes sure that the implemented code is fit for its purpose but it also aids you as a developer in thinking about the design of the code you write. It keeps the focus on small steps that ultimately result in solid, working software.

#### Benefits of TDD

* The suite of tests provides constant feedback that the code is still working. You cannot break one part of your program without knowing about it.
* Documentation can quickly go out of date - if no one is actively maintaining the instructions. Testing never can get "old" as it is always testing real, active code. Your tests are always monitoring whether and how your code works.
* When the test passes, you know that you have completed the assignment.
* Test-driven development forces us to think about what we want our code to do before we start working. This makes us more efficient as developers.
* We gain confidence in our code because we know we haven't broken anything with new features. If the new test passes and none of the old tests break, we can be confident our program works.
* If a bug is found - that is, unexpected flaws not revealed by tests - the programmer can write a new test to "expose" the bug. Then she fixes her code to remove the bug. If none of the other tests break, the code is working.
* Reduced debugging time!


#### Types of tests

* Acceptance tests - check the entire stack. They mimic an application user clicking around the site and performing actions.
* Integration tests - check two or more parts of our code together to make sure they can work in combination.
* Unit tests - check a single part of our code to make sure it is functioning on its own.


