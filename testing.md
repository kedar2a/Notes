ref[https://realpython.com/python-testing/]:

## Automated vs. Manual Testing:
- **Manual Testing**: To have a complete set of manual tests, all you need to do is make a list of all the features your application has, the different types of input it can accept, and the expected results. Now, every time you make a change to your code, you need to go through every single item on that list and check it.
    + Exploratory Testing: A form of testing that is done without a plan. In an exploratory test, you’re just exploring the application.
        * e.g: when you ran your application and used it for the first time, check the features and experiment using them.

- **Automated Testing**: Automated testing is the execution of your test plan (the parts of your application you want to test, the order in which you want to test them, and the expected responses) by a script instead of a human.

---

## Unit Tests vs. Integration Tests:
- **Integration Testing**: Testing multiple components is known as integration testing. 
- **Unit Test**: A unit test is a smaller test, one that checks that a single component operates in the right way. A unit test helps you to isolate what is broken in your application and fix it faster.
- You have just seen two types of tests:
    1. An integration test checks that components in your application operate with each other.
    2. A unit test checks a small component in your application.


## Test Runner:
> The test runner is a special application designed for running tests, checking the output, and giving you tools for debugging and diagnosing tests and applications.

The three most popular test runners are:
- unittest (builtin)
- nose or nose2
- pytest


## Good articles:
- fixtures: 
    + http://pythontesting.net/framework/pytest/pytest-fixtures-nuts-bolts/
    + http://devork.be/talks/advanced-fixtures/advfix.html
