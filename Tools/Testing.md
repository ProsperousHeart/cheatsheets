Testing is something that too often goes over looked and is the best thing to ensure you do not have old bugs come back.

Plus - it doesn't have to (and shouldn't) be manual. You can automate!

# Python's [DocTest](https://docs.python.org/3.6/library/doctest.html)

This is a built-in python module that allows you to search for pieces of text in your docstring that look like interactive python sessions.

Why is this so cool? Because it can execute those sessions to see how your code will respond.

## How To Use DocTest

- To check that a module’s docstrings are up-to-date by verifying that all interactive examples still work as documented.

- To perform regression testing by verifying that interactive examples from a test file or a test object work as expected.

- To write tutorial documentation for a package, liberally illustrated with input-output examples. Depending on whether the examples or the expository text are emphasized, this has the flavor of “literate testing” or “executable documentation”.

# Python's [UnitTest](https://docs.python.org/3.6/library/unittest.html)

This particular built-in module supports automated testing, sharing of setup and shutdown of code for tests, aggregation of tests into collections, as well as independence of the tests from the reporting network.

Basically you can test on small or large scale for your program.

And again ... AUTOMATED!
