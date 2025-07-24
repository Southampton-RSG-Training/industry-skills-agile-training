---
title: "2.3 Writing Unit Tests"
teaching: 0
exercises: 0
---
 
:::::::::::::::::::::::::::::::::::::: questions
 
- How do I write a unit test?
 
::::::::::::::::::::::::::::::::::::::::::::::::
 
::::::::::::::::::::::::::::::::::::: objectives
 
- Implement and run unit tests to verify the correct behaviour of program functions

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

## Change our Implementation, and Re-test

Let's illustrate another key advantage of having unit tests.
Let's assume during development we find an error in our code.
For example, if we run our code with `factorial(10000)` our Python program from within the Python interpreter, on Python version 3.10.7 or later it will crash with an exception:

```python
>>> from mymath.factorial import factorial
>>> factorial(10000)
```

```output
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: Exceeds the limit (4300) for integer string conversion; use sys.set_int_max_str_digits() to increase the limit
```

It turns out that version of 3.10.7 of Python introduced a breaking change,
preventing large integer to string conversions due to [a vulnerability](https://github.com/python/cpython/issues/95778).

However, we can sidestep this vulnerability by adding the following at the beginning of `mymath/factorial.py`,
which will disable this conversion limit:

```python
import sys
sys.set_int_max_str_digits(0)
```

Make sure you replace the code in the `factorial.py` file,
and not the `test_factorial.py` file.

We now have our updated implementation, but we need to make sure it works as intended.
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

## Testing for an Exception

In our implementation we explicitly don't want to process negative numbers,
since that would lead to undefined results which we cannot compute,
so we have added what is known as a *precondition*.

The precondition will check the validity of our input data before we do any processing on it,
and this approach to checking function input data is considered good practice:

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

Sure enough, we get our exception as desired.
But how do we test for this in a unit test,
since this is an exception, not a value?
Fortunately, unit test frameworks have ways to check for this.

Let's add a new test to `tests/test_factorial.py`:

```python
def test_negative(self):
    with self.assertRaises(ValueError):
      factorial(-1)
```

So here, we use `unittest`'s built-in `assertRaises()` (instead of `assertEquals()`) to test for a `ValueError` exception occurring when we run `factorial(-1)`.
We also use Python's `with` here to test for this within the call to `factorial()`.
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
 
- FIXME
 
::::::::::::::::::::::::::::::::::::::::::::::::
