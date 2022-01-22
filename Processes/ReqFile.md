# About

In this process cheatsheet, you will learn:
1. [what is a requirements file](https://www.idkrtm.com/what-is-the-python-requirements-txt) & why you need it
2. how to create a requirements file
3. how to use a requirements file

**PLEASE NOTE:**
Everything shared here is from my experience on a Windows (PC) machine using `virtualenvwrapper-win`. However, the pip and python commands should still be the same. 

# The What And Why

## What Is a Requirements File?

A **requirements file** is the file used when telling python what modules to install for your local or virtual environment. Otherwise known as the [requirement specifier](https://pip.pypa.io/en/latest/cli/pip_install/#requirement-specifiers).

The format of this **TXT** file is used by **pip** to install packages from a Package index. The format of each line has:
- project name
- [optional] [version specifiers](https://packaging.python.org/en/latest/glossary/#term-Version-Specifier)

Be sure to check out [PEP 508](https://www.python.org/dev/peps/pep-0508) for full specs regarding formatting.

Examples might be:

```python
projectA
pRojectb==0.1
projectC>4.2, <5
ProjectD~=1.2.3
```

And they can et more complicated from there.

We'll just stick with some basics for now.

This file is typically located in the root directory of your project.

# Why You Should Always Have A Requirements File

**Always** may be a strong word, especially if you have virtual environments with only 1 or two special packages installed.

However,in this day and age you want to maximize your time and automate whatever you can. And **this** is an easy way to do so. Because you will never have to worry about what packages you might need to install on a new machine.

That and it allows for people who may need to work on the same project be able to get up to speed quickly as well.

This file is used for specifying what packages are required (or at least currently installed) for a project.

# how to create a requirements file

## From Current Project

1. Start your virtual environment by running `workon EnvNameHere`
2. If you set it up properly, it will bring you into the root directory of your project. If not, change directory now.
3. Run the following command:  `pip freeze > requirements.txt`

And that's it! You've saved the packages and their versions to a new file for later use.

It doesn't have to be `requirements.txt` but it does need to be a **TXT** file. And you'll need to remember what you called it when you go to install the packages.

Most people just use `requirements.txt` as a standard practice.

## From Scratch

There are 3 things to know about creating your own requirements file:
1. comments use `#` just like python
2. you can specify versions using comparison operators - if version omitted, the latest version is installed
3. multiple conditions can be specified by using a `,` to separate them:  `packageName >= 1.0, <=2.0`

Here is what an example might look like:

```
##### Reqs Without Version Specifiers #####
jinja2
xlsxwriter
beautifulsoup4

##### With Version Specifiers #####
docopt == 0.6.1             # Version Matching. Must be version 0.6.1
keyring >= 4.1.1            # Minimum version 4.1.1
coverage != 3.5             # Version Exclusion. Anything except version 3.5
Mopidy-Dirble ~= 1.1        # Compatible release. Same as >= 1.1, == 1.*
```

# how to use a requirements file

After you've created your [virtual environment](https://github.com/ProsperousHeart/cheatsheets/blob/master/Processes/virtualenvs.md#virtualenvwrapper), it's time to install your packages!

1. If not already running, start your virtual environment by running `workon EnvNameHere`
2. If you set it up properly, it will bring you into the root directory of your project. If not, change directory now.
3. Run the following:
   1. If file is located in the root of the project directory:  `pip install -r requirements.txt`
   2. If file is located elsewhere:  `pip install -r path/to/requirements.txt` _(If there are spaces n your directory, surround the path in quotes!)_

Remember - the file name does not have to be `requirements.txt` but it _does_ have to be a **TXT** file.

# Additional Resources

In addition to the different links provided above, I felt like these sites had great info!

- [How to install Python packages with pip and requirements.txt](https://note.nkmk.me/en/python-pip-install-requirements/)