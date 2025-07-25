---
title: "2.2 Introduction to Automated Testing"
teaching: 0
exercises: 0
---
 
:::::::::::::::::::::::::::::::::::::: questions
 
- Why should I test my code?
- What is the role of automated testing?
- What are the different types of automated tests?
- What is the structure of a unit test?
- What is test "mocking"?
- How can I run unit tests?
 
::::::::::::::::::::::::::::::::::::::::::::::::
 
::::::::::::::::::::::::::::::::::::: objectives
 
- Explain the reasons why testing is important
- Describe the three main types of tests and what each are used for
- Describe the practice of test "mocking" and when to use it
- Obtain example code repository and run existing unit tests
- Describe the format of a unit test written for the Pytest testing framework

::::::::::::::::::::::::::::::::::::::::::::::::

Testing is a critical part of writing reliable, maintainable code — especially in collaborative or research environments where reproducibility and correctness are key.

In this session, we will explore why testing matters, and introduce different levels of testing — from small, focused unit tests, to broader integration and system tests that check how components work together. We will also look at testing approaches such as regression testing (to ensure changes do not break existing behavior) and property-based testing (to test a wide range of inputs automatically). Finally, we will cover mocking, a technique used to isolate code during tests by simulating the behavior of external dependencies.


## Introduction to testing

Code testing is the process of verifying that your code behaves as expected and continues to do so as it evolves. It helps catch bugs early, ensures changes do not unintentionally break existing functionality, and supports the development of more robust and maintainable software. Whether you’re working on a small script or a large application, incorporating testing into your workflow builds confidence in your code and makes collaboration and future updates much easier.

### Why test your code?

Being able to demonstrate that a process generates the right results is important in any field of research, whether it is software generating those results or not. So when writing software we need to ask ourselves some key questions:

- Does the code we develop works as expected?
- To what extent are we confident of the accuracy of results that software produces?
- Can we and others verify these assertions for themselves?

If we are unable to demonstrate that our software fulfills these criteria, why would anyone use it? 

As a codebase grows, debugging becomes more challenging, and new code may introduce bugs or unexpected behavior in parts of the system it does not directly interact with. Tests can help catch issues before they become runtime bugs, and a failing test can pinpoint the source of the problem. Additionally, tests serve as invocation examples for other developers and users, making it easier for them to reuse the code effectively.

Having well-defined tests for our software helps ensure your software works correctly, reliably, and consistently over time. By identifying bugs early and confirming that new changes do not break existing functionality, testing improves code quality, reduces the risk of errors in production, and makes future development and long-term maintenance faster and safer. 


### Types of Testing - Levels

Testing can be performed at different code levels, each serving a distinct purpose to ensure software behaves correctly at various stages of execution. Together, these testing levels provide a structured approach to improving software quality and reliability.

*Unit testing* is the most granular level, where individual components—like functions or classes—are tested in isolation to confirm they behave correctly under a variety of inputs. This makes it easier to identify and fix bugs early in the development process.

*Integration testing* builds on unit testing by checking how multiple components or modules work together. This level of testing helps catch issues that arise when components interact — such as unexpected data formats, interface mismatches, or dependency problems.

At the highest level, system testing evaluates the software as a complete, integrated system. This type of testing focuses on validating the entire application's functionality from end to end, typically from the user’s perspective, including inputs, outputs, and how the system behaves under various conditions. 

### Types of Testing - Approaches 

Different approaches to code testing help ensure that software behaves as expected under a range of conditions. When the expected output of a function or program is known, tests can directly check that the results match fixed values or fall within a defined confidence interval. 

However, for cases where exact outputs are not predictable — such as simulations with random elements — *property-based testing* is useful. This method tests a wide range of inputs to ensure that certain properties or patterns hold true across them. 

Another important approach is *regression testing*, which helps detect when previously working functionality breaks due to recent changes in the code. By rerunning earlier tests, developers can catch and address these regressions early, maintaining software stability over time.

#### Mocking

When running tests, you often want to focus on testing a specific piece of functionality, but dependencies on external objects or functions can complicate this, as you cannot always be sure they work as expected. Mocking addresses this by allowing you to replace those dependencies with "mocked" objects or functions that behave according to your instructions. So, *mocking* is a testing approach used to isolate the unit of code being tested by replacing its dependencies with simplified, controllable versions — known as *mocks*. 

Mocks mimic the behavior of real components (such as databases, APIs, or external services) without requiring their full functionality or availability. This allows developers to test specific code paths, simulate error conditions, or verify how a unit interacts with other parts of the system. Mocking is especially useful in unit and integration testing to ensure tests remain focused, fast and reliable.

For example, if a function modifies data and writes it to a file, you can mock the file-writing object, so instead of creating an actual file, the mocked object stores the "written" data. This enables you to verify that the data written is as expected, without actually creating a file, making tests more controlled and efficient.


## Creating a Copy of the Example Code Repository

For this lesson we'll need to create a new GitHub repository based on the contents of another repository.

1. Once logged into GitHub in a web browser,
go to https://github.com/softwaresaved/industry-skills-testing
1. Select `Use this template`, and then select `Create a new repository` from the dropdown menu
1. On the next screen, ensure your personal GitHub account is selected in the `Owner` field, and fill in `Repository name` with `industry-skills-testing`
1. Ensure the repository is set to `Public`
1. Select `Create repository`

You should be presented with the new repository's main page.
Next, we need to clone this repository onto our own machines,
using the Bash shell.
So firstly open a Bash shell (via Git Bash in Windows or Terminal on a Mac).
Then, on the command line,
navigate to where you'd like the example code to reside,
and use Git to clone it.
For example, to clone the repository in our home directory (replacing `github-account-name` with our own account),
and change directory to the repository contents:

```bash
cd
git clone https://github.com/github-account-name/industry-skills-testing
cd industry-skills-testing
```

## Examining the Example Code

Next, let's take a look at the code, which is in the `industry-skills-testing/mymath directory`, called `factorial.py`,
so open this file in an editor.

The example code is a basic Python implementation of Factorial.
Essentially, it multiplies all the whole numbers from a given number down to 1
e.g. given 3, that's 3 x 2 x 1 = 6 - so the factorial of 3 is 6.

We can also run this code from within Python to show it working.
In the shell,
ensure you are in the root directory of the repository,
then type:

```bash
python
```

```python
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```

Then at the prompt, import the `factorial` function from the `mymath` library and run it:

```python
>>> from mymath.factorial import factorial
>>> factorial(3)
```

Which gives us 6 - which gives us some evidence that this function is working.
Of course, in practice, our functions may well be more complicated than this,
and of course, they may call other separate functions.
Now we could just come up with a list of known input numbers and expected outputs and run each of these manually to test the code,
but this would take some time.
Computers are really good at one thing - automation - so let's use that and automate our tests,
to make it easy for ourselves.

## Setting up a Virtual Environment for `pytest`

So how do we run these tests?
Well, we need to create a virtual environment,
since we're using a unit test framework that's supplied by another Python library which we need to have access to.

So in summary, we need to:

- Create a new virtual environment to hold Python packages
- Activate that new virtual environment
- Install `pytest` into our new virtual environment

So, from a Bash prompt:

```bash
python -m venv venv
```

Then to activate it:

```bash
[Linux] source venv/bin/activate
[Mac] source venv/bin/activate
[Windows] source venv/Scripts/activate
```

To install `pytest`:

```bash
python -m pip install pytest
```

If we wish to deactivate a virtual environment, we can use `deactivate` on the command line,
and reactivate it later using the same command we did before.

## Running the Tests

As it turns out, this code repository already has a test.
Navigate to the repository's `tests` directory, and open a file called `test_factorial.py`:

```python
import pytest
from mymath.factorial import factorial


def test_3():
    assert factorial(3) == 6
```

Now, we using a Python unit test framework called `pytest`.
There are other such frameworks for Python, including `unittest` (which is built-in to Python) and `nose`,
but `pytest` is regarded as the most popular.

In this example, we have a single unit test, which we've called `test_3`.
Within that test method, we are essentially doing what we did when we ran it manually earlier:
we're running factorial with the argument 3, and checking it equals 6.
We use a Python `assert` statement to verify the two are the same,
and if not, the test will fail.

So how do we run this test?
In the shell, we can run this test by ensuring we're in the repository's root directory, and running:

```bash
python -m pytest tests/test_factorial.py 
```

```output
============================= test session starts ==============================
platform linux -- Python 3.10.12, pytest-8.4.1, pluggy-1.6.0
rootdir: /home/steve/test/ist
collected 1 item                                                               

tests/test_factorial.py .                                                [100%]

============================== 1 passed in 0.00s ===============================
```

So what happens?
The single dot next to the test script filename means the single test we have was successfully run,
so our test passes!

But how does unittest know what to run exactly?
Unit test frameworks like `pytest` follow a common pattern of finding tests and running them.
When we give a single file argument to `pytest`,
it searches the Python file functions starting with `test_`, and runs them.
So we could add more tests to this file in the same way,
and it would run each of these tests in turn.

## Testing for Failure

We've seen what happens if a test succeeds,
but what happens if a test fails?
Let's deliberately change our test to be wrong and find out,
by editing the `tests/test_factorial.py` file,
changing the expected result of `factorial(3)` to be `10`, and saving the file.

We'll rerun our tests slightly differently than last time:

```bash
python -m pytest -v tests/test_factorial.py
```

In this case, we add `-v` for more verbose output,
giving us detailed results test-by-test.

```output
============================= test session starts ==============================
platform linux -- Python 3.10.12, pytest-8.4.1, pluggy-1.6.0 -- /home/steve/test/ist/venv/bin/python
cachedir: .pytest_cache
rootdir: /home/steve/test/ist
collected 1 item                                                               

tests/test_factorial.py::test_3 FAILED                                   [100%]

=================================== FAILURES ===================================
____________________________________ test_3 ____________________________________

    def test_3():
>       assert factorial(3) == 10
E       assert 6 == 10
E        +  where 6 = factorial(3)

tests/test_factorial.py:6: AssertionError
=========================== short test summary info ============================
FAILED tests/test_factorial.py::test_3 - assert 6 == 10
============================== 1 failed in 0.02s ===============================
```

In this instance we get a `FAILED` instead of a `.` for our test,
and we see an `AssertionError` that `6` is not equal to `10`,
which is clearly true.

Let's now change our faulty test back by editing the file again,
changing the `10` back to `6`,
and re-run our tests:

```bash
python -m pytest -v tests/test_factorial.py
```

```output
============================= test session starts ==============================
platform linux -- Python 3.10.12, pytest-8.4.1, pluggy-1.6.0 -- /home/steve/test/ist/venv/bin/python
cachedir: .pytest_cache
rootdir: /home/steve/test/ist
collected 1 item                                                               

tests/test_factorial.py::test_3 PASSED                                   [100%]

============================== 1 passed in 0.00s ===============================
```

This illustrates an important point with our tests:
it's important to make sure your tests are correct too.
So make sure you work with known 'good' test data which has been verified to be correct!
 
:::::::::::::::::::::::::::::::::::::: keypoints
 
- Testing code is the process of verifying that your code behaves as expected and continues to do so as it evolves
- Code complexity often increases beyond our ability to fully understand it
- Code testing allows us to discover the existence of issues before they become a potentially much larger issue when using the code in its intended environment
- Unit tests verify in isolation that a small code component, such as a function or class, behaves correctly with known inputs
- Integration tests verify correct behaviour of multiple components or modules working together, at a higher level
- System tests evaluate software as a complete, integrated system, focuses on validating the entire application’s functionality from end to end, typically from a user's perspective
- Test mocking involves replacing a code component, such as a function or class, with a simplified, controllable version - known as a mock - to make testing easier by mimicing how the real component works
- Tests written in `pytest` are defined as functions that return either true or false, and have a function name beginning with `test_`
- Using `pytest`, we can run a set of tests using `python -m pytest` followed by a specific file containing a set of tests, or a directory containing many test files with filenames beginning with `test_`

::::::::::::::::::::::::::::::::::::::::::::::::
