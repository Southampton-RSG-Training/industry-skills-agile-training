---
title: "2.4 Writing Unit Tests"
teaching: 0
exercises: 0
---
 
:::::::::::::::::::::::::::::::::::::: questions
 
- How do I write a unit test?
- When should I use a regression test?
- When should I write and re-run unit tests throughout development?
- What makes a good test?
 
::::::::::::::::::::::::::::::::::::::::::::::::
 
::::::::::::::::::::::::::::::::::::: objectives
 
- Implement and run unit tests to verify the correct behaviour of program functions
- Describe how and when testing fits into code development
- Write a regression test to identify if an unwanted code behaviour returns

::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::  challenge

## Solo Exercise: Add a New Test

3 mins.

Add two new tests based on the first test,
instead testing that calling `factorial` with 5 equals the expected result of `120`,
and re-run the tests.

:::::::::::::::  solution

Add to `tests/test_factorial.py`:

```python
def test_5(self):
    self.assertEqual(factorial(5), 120)
```

And then we can run it exactly as before, in the shell:

```bash
python -m pytest -v tests/test_factorial.py 
```

```output
============================= test session starts ==============================
platform linux -- Python 3.10.12, pytest-8.4.1, pluggy-1.6.0 -- /home/steve/test/ist/venv/bin/python
cachedir: .pytest_cache
rootdir: /home/steve/test/ist
collected 2 items                                                              

tests/test_factorial.py::test_3 PASSED                                   [ 50%]
tests/test_factorial.py::test_5 PASSED                                   [100%]

============================== 2 passed in 0.00s ===============================
```

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

We can see the tests pass.
So the really useful thing here,
is we can rapidly add tests and rerun all of them.
Particularly with more complex codes that are harder to reason about,
we can develop a set of tests into a suite of tests to verify the codes' correctness.
Then, whenever we make changes to our code,
we can rerun our tests to make sure we haven't broken anything.
An additional benefit is that successfully running our unit tests can also give others confidence that our code works as expected.

## Updating and Re-testing our Implementation

Let's illustrate another key advantage of having unit tests.
Let's assume during development we find an error in our code.
For example, if we run our code with `-1`:

```python
>>> from mymath.factorial import factorial
>>> factorial(-1)
```

We get a nonsensical answer of 1, since for negative numbers, factorial is undefined.
So this isn't desired behaviour!

### Implementing a Fix

Therefore, in our implementation we explicitly don't want to process negative numbers,
so we can add what is known as a *precondition* beforehand,
and this approach to checking function input data prior to processing it is considered good practice.

Let's add the following after the function's docstring in `mymath/factorial.py`,
and before `factorial = 1`:

```python
    if n < 0:
        raise ValueError('Only use non-negative integers.')
```

So if we run it with a negative input from within the Python interpreter,
we should see the error:

```python
>>> from mymath.factorial import factorial
>>> factorial(-1)
```

```output
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "/home/steve/factorial-example/mymath/factorial.py", line 9, in factorial
    raise ValueError('Only use non-negative integers.')
ValueError: Only use non-negative integers.
```

### Re-testing our Existing Code

We now have our updated implementation, but we need to make sure it all still works as intended.
Fortunately, we have our set of tests, so let's run them again:

```bash
python -m pytest -v tests/test_factorial.py
```

```output
============================= test session starts ==============================
platform linux -- Python 3.10.12, pytest-8.4.1, pluggy-1.6.0 -- /home/steve/test/ist/venv/bin/python
cachedir: .pytest_cache
rootdir: /home/steve/test/ist
collected 2 items                                                              

tests/test_factorial.py::test_3 PASSED                                   [ 50%]
tests/test_factorial.py::test_5 PASSED                                   [100%]

============================== 2 passed in 0.00s ===============================
```

And they work, which gives us some confidence - very rapidly - that our updated implementation is behaving exactly the same as before.
So again, each time we change our code,
whether it's making small or large changes,
we retest and check they all pass.

### Adding a New "Regression Test"

But since we've amended our code to correct for a known issue,
what would be helpful would be to have a test that checks for the existence of this issue.
This would verify that the fix is behaving correctly,
and also would be a check to ensure the behaviour of the code has not *regressed* to a previous bad state.
These types of test, which we introduced briefly before, are known as *regression tests*.

But how do we write a regression test for this as a unit test,
since this is an exception, and not a value?
Fortunately, unit test frameworks have ways to check for this.

Let's add a new test to `tests/test_factorial.py`:

```python
def test_negative():
    with pytest.raises(ValueError):
      factorial(-1)
```

So here, we use `pytest`'s built-in `raises()` (instead of `assert`) to test for a `ValueError` exception occurring when we run `factorial(-1)`.
We also use Python's `with` here to test for this within the call to `factorial()`.

### Re-testing with all our Tests

So if we re-run our tests again, we should see them all succeed:

```bash
python -m pytest -v tests/test_factorial.py
```

You should see:

```output
============================= test session starts ==============================
platform linux -- Python 3.10.12, pytest-8.4.1, pluggy-1.6.0 -- /home/steve/test/ist/venv/bin/python
cachedir: .pytest_cache
rootdir: /home/steve/test/ist
collected 3 items                                                              

tests/test_factorial.py::test_3 PASSED                                   [ 33%]
tests/test_factorial.py::test_5 PASSED                                   [ 66%]
tests/test_factorial.py::test_negative PASSED                            [100%]

============================== 3 passed in 0.00s ===============================
```

::::::::::::::::::::::::::::::::::::: callout

## What makes a Good Test?

Of course, we only have 3 tests so far, and it would be good to have more
But what kind of tests are good to write?
With more tests that sufficiently test our code,
the more confidence we have that our code is correct.
We could keep writing tests for e.g., 10, 15, 20, and so on.
But these become increasingly less useful,
since they're in much the same "space".
We can't test all positive numbers,
and it's fair to say at a certain point,
these types of low integers are sufficiently tested.
So what test cases should we choose?

We should select test cases that test two things:

- The paths through our code, so we can check they work as we expect.
For example, if we had a number of paths through the code dictated with if statements,
we write tests to ensure those are followed.
- We also need to test the boundaries of the input data we expect to use, known as *edge cases*.

For example, if we go back to our code.
we can see that there are some interesting edge cases to test for:

- Zero?
- Very large numbers (as we've already seen)?
- Strings?

All good candidates for further tests,
since they test the code in different ways,
and test different paths through the code.

:::::::::::::::::::::::::::::::::::::

## Commit and Push our Changes to GitHub

For the next episode, we'll need our changes in our remote GitHub repository.

Let's first commit our new set of tests to our local repository:

```bash
git add tests/test_factorial.py
git commit -m "Add tests for 5 and -1"
```

Next, in a separate commit, let's commit our updated `factorial` implementation,
and then push both commits to our remote repository on GitHub:

```bash
git add mymath/factorial.py 
git commit -m "Fix type conversion issue"
git push
```

## Brief Summary

So we now have the beginnings of a test suite!
And every time we change our code, we can rerun our tests.
So the overall process of development becomes:

- Add new functionality (or modify new functionality) to our code
- Potentially add new tests to test any new functionality
- Re-run all our tests
 
:::::::::::::::::::::::::::::::::::::: keypoints
 
- Running automated tests is generally a rapid process that takes far less time than testing code manually
- When we change our code, re-run existing tests to ensure we haven't broken anything or otherwise compromised the desired behaviour of our code
- When we change our code, consider if a new test should be added to verify it works correctly
- If we fix an error in our code, consider adding a regression test to identify if it returns
 
::::::::::::::::::::::::::::::::::::::::::::::::
