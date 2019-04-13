<a href='https://www.learntocodeonline.com/'>![Learn To Code Online By Clicking Here](../Images/learn-to-code-online.png?raw=true "Learn To Code Online")</a>

Testing is something that too often goes over looked and is the best thing to ensure you do not have old bugs come back.

Plus - it doesn't have to (and shouldn't) be manual. You can automate!

# Python's [DocTest](https://docs.python.org/3.6/library/doctest.html)

This is a built-in python module that allows you to search for pieces of text in your docstring that look like interactive python sessions.

Why is this so cool? Because it can execute those sessions to see how your code will respond.

## How To Use DocTest

- To check that a module’s docstrings are up-to-date by verifying that all interactive examples still work as documented.

- To perform regression testing by verifying that interactive examples from a test file or a test object work as expected.

- To write tutorial documentation for a package, liberally illustrated with input-output examples. Depending on whether the examples or the expository text are emphasized, this has the flavor of “literate testing” or “executable documentation”.

### The Simple Way

It's not necessarily the best way, but to get started here's the simple/easiest way.

Add this to the end of each module:

```python
if __name__ == "__main__":
    import doctest
    doctest.testmod()
```

[doctest](https://docs.python.org/3.6/library/doctest.html#module-doctest) then examines docstrings in that module.

### How Do I Run This Test?

If you don't care to know anything except if it fails, you can run:  `python M.py`

Where `M` is the name of the module you wish to test. This particular option will print the failing examples & cause of failures to stdout, with the final line of putput being something like:  `***Test Failed*** N failures.`

... Where N is the number of failures.

Otherwise, if you are looking for details? Run this:  `python M.py -v`

Another command line shortcut for running [testmod()](https://docs.python.org/3.6/library/doctest.html#doctest.testmod) is to use:  `python -m doctest -v M.py`

This imports it as a standalone module instead of running your whole program to test. GREAT for when you make a change to one file.

There are other ways to implement this verbose option - please see documentation for API [here](https://docs.python.org/3.6/library/doctest.html#doctest-basic-api).

## How Does It Work?

You'll want to [check this out](https://docs.python.org/3.6/library/doctest.html#how-it-works).

## Are There Any Options For This?

You betcha. Right [here](https://docs.python.org/3.6/library/doctest.html#option-flags).

## How Do I Handle Exceptions?

You'll want to [check this out](https://docs.python.org/3.6/library/doctest.html#what-about-exceptions).

## Examples

Here are a few examples to check out for utilizing doctest.

- Checking examples [in a text file](https://docs.python.org/3.6/library/doctest.html#simple-usage-checking-examples-in-a-text-file) using [testfile()](https://docs.python.org/3.6/library/doctest.html#doctest.testfile) that requires 0 python code within it

Like [testmod()](https://docs.python.org/3.6/library/doctest.html#doctest.testmod), [testfile()](https://docs.python.org/3.6/library/doctest.html#doctest.testfile)’s verbosity can be set with the -v command-line switch or with the optional keyword argument verbose.

## Things To Remember

The test **will fail** if the output is not EXACTLY as written. Learn more warnings [here](https://docs.python.org/3.6/library/doctest.html#warnings).

You will also find the [Basic API](https://docs.python.org/3.6/library/doctest.html#basic-api) helpful as well.

## Using doctest Objects

- DocTest objects info is [here](https://docs.python.org/3.6/library/doctest.html#doctest-objects):  a collection of Examples that should be run in a single namespace
- Exmaple objects found [here](https://docs.python.org/3.6/library/doctest.html#example-objects):  a single interactive example consisting of a python statement & it's expected output
- [DocTestFinder](https://docs.python.org/3.6/library/doctest.html#doctestfinder-objects):  A processing class used to extract the [DocTests](https://docs.python.org/3.6/library/doctest.html#doctest.DocTest) that are relevant to a given object, from its docstring and the docstrings of its contained objects. [DocTests](https://docs.python.org/3.6/library/doctest.html#doctest.DocTest) can be extracted from modules, classes, functions, methods, staticmethods, classmethods, and properties.
- [DocTestParser](https://docs.python.org/3.6/library/doctest.html#doctestparser-objects):  A processing class used to extract interactive examples from a string, and use them to create a [DocTest](https://docs.python.org/3.6/library/doctest.html#doctest.DocTest) object.

# Python's [UnitTest](https://docs.python.org/3.6/library/unittest.html)

This particular built-in module supports automated testing, sharing of setup and shutdown of code for tests, aggregation of tests into collections, as well as independence of the tests from the reporting network.

Basically you can test on small or large scale for your program.

And again ... AUTOMATED!
