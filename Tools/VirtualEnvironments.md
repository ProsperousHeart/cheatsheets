# What Is A Virtual Environment?

At its core, the main purpose of Python virtual environments is to create an isolated environment for Python projects. Meaning each project can have different versions or dependencies.

Otherwise, you are bound by the version on your system. And if a new project requires a module that requires a different version of Python?

Too bad. Lots of work (or a VM spin up) required.

But why make it hard on yourself?

The number of virtual environments is limited only to the capacity of your machine.

By default, the option `--no-site-packages` is used so it does not include global packages.

# How Can I Create A Virtual Environment?

There are many ways to do so, but two of the most widely used are [virtualvenv](https://virtualenv.readthedocs.io/en/latest/).

If you are not using PYthon 3, you'll want to **install [virtualvenv](https://virtualenv.readthedocs.io/en/latest/)** with [pip](https://pip.pypa.io/en/stable/quickstart/)
`pip install virtualenv`

Otherwise, use the built-in [venv](https://docs.python.org/3/library/venv.html) module.

Be sure to check out the links on the Thank You page for additional information. My cheat sheet is going to be just that ...

A cheat sheet.

## virtualenv (Python 2)

1. Make a new directory:
- mkdir DIRECTORYNAME
- cd DIRECTORYNAME
Where DIRECTORYNAME is the name of the folder for the project you wish to create. Or it can obviously be something you cloned from GitHub.

2. Run command: `virtualenv ENVNAME`
Where ENVNAME is the name of the virtual environment you wish to create.

**NOTE:**  By default, this will not include any of your existing site packages.

## venv (Python 3)

1. Make a new directory:
- mkdir DIRECTORYNAME
- cd DIRECTORYNAME
Where DIRECTORYNAME is the name of the folder for the project you wish to create. Or it can obviously be something you cloned from GitHub.

2. Run command: `python3 -m venv ENVNAME`
Where ENVNAME is the name of the virtual environment you wish to create.

**NOTE:**
- By default, this will not include any of your existing site packages.
- venv provides benefit that you can use a different version of python if you wanted

# How Can I Lock The Virtual Environment Down?

Checkout [Using Virtual Environments](https://realpython.com/python-virtual-environments-a-primer/) section of RealPython's blog for detailed information.

The short of it - is that it is that way by default! You just need to turn it on or _activate_ it.

```
source ENVNAME/bin/activate
```

# OK, How Do I Deactivate it?

`deactivate`

# Is There Another Way To Manage My Packages?

Yes! Check out the Misc file for pipenv.

# What If I Want To Use A Different Version?

To just use a specific version for a single project:  `virtualenv -p /usr/bin/python2.7 venv` (for v2.7)

To change globally (I caution to avoid this) you can do:  `export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python2.7`

# Good To Knows

Again, checkout [this](https://realpython.com/python-virtual-environments-a-primer/) post for more info ...

But you'll also want to use virtualvenvwrapper. Click [virtualenvwrapper](https://virtualenvwrapper.readthedocs.org/en/latest/) for non-PC, and [virtualenvwrapper-win](https://pypi.python.org/pypi/virtualenvwrapper-win) for Windows.

## For Windows

Here's how to install [https://pypi.org/project/]virtualenvwrapper-win/](https://pypi.org/project/virtualenvwrapper-win/).

```python
# using pip
pip install virtualenvwrapper-win

# using easy_install
easy_install virtualenvwrapper-win

# from source
git clone git://github.com/davidmarble/virtualenvwrapper-win.git
cd virtualenvwrapper-win
python setup.py install   # or pip install .
```

# Is There An Easier Way To Work With This?

Once installed, you can actually use the [virtualenvwrapper](https://docs.python-guide.org/dev/virtualenvs/#virtualenvwrapper) that does make things a bit easier.

It provides a set of commands which makes working with virtual environments much more pleasant & places all your virtual environments in one place. (Makes it easier to manage instead of having them in all of your project folders.)

Please see the [virtualenvs process doc](https://github.com/ProsperousHeart/cheatsheets/blob/master/Processes/virtualenvs.md) for steps to install and use.

You can also do virtualenv + virtualenvwrapper in one using [virtualenv-burrito](https://docs.python-guide.org/dev/virtualenvs/#virtualenv-burrito).

One last thing - if you want to automatically activate the environment in a directory when you `cd` into it, you'll want to [check out autoenv](https://docs.python-guide.org/dev/virtualenvs/#autoenv) or even [direnv](https://direnv.net/).
