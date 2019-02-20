# Pipenv & Virtual Environments

The following steps come from [The Hitchhiker's Guide](https://docs.python-guide.org/dev/virtualenvs/).

Assume all instructions are for python 3.x version.

## [Pipenv](https://pipenv.readthedocs.io/en/latest/)

1. Ensure python is installed by running this at command prompt or Anaconda:  `python --version`

2. Ensure pip is available: `pip --version`

3. Install dependency manager for your projects:  `pip install --user pipenv`

4. When ready to install packages for your project:
   - Change into your project directory:  `cd DIRECTORY`
   - Run: `pipenv install MODULENAME` (where MODULENAME is something like **requests**)

   This installs the library & creates a Pipfile (used to track dependencies in case you need to reinstall them).

5. When looking to run your script: `pipenv run python FILENAME.py`

   Using `pipenv run` ensures your installed packages are available to your script.

## virtualenv

More on this was covered in [Virtual Environments](https://github.com/ProsperousHeart/cheatsheets/blob/updates/Tools/VirtualEnvironments.md).

Basically **virtualenv** is a tool to create isolated Python environments. It creates a folder that has all the necessary executables to use the packages your project would need.

It can also be used standalone - _in place of Pipenv_!

1. Install via pip: `pip install virtualenv`

2. Test your installation:`virtualenv --version`

3. Change into the directory of your project: `cd DIRECTORY`

4. Create a virtual environment:  `virtualenv ENVNAME`

   If you omit the name of the environment, this will **not** create a folder for all the executable files & copy of your pip library. It will just put them in the current folder.

   **NOTE:** conventional name is to use venv as it is readily available in ignore files.

For fancier commands, check out the [original MD file](https://github.com/ProsperousHeart/cheatsheets/blob/updates/Tools/VirtualEnvironments.md).

5. Activate your virtual environment
   - Linux: `source VENVNAME/bin/activate`
   - PC:  `\venv\Scripts\activate`

  The name of the current virtual environment will now appear on the left of the prompt to let you know that it’s active. From now on, any package that you install using pip will be placed in the venv folder, isolated from the global Python installation.

6. Install packages as normal

7. When you have your packages, it is best practice to "freeze" the current state of environment packages to a file: `pip freeze > requirements.txt`

   You can see the list by running: `pip list`

   You are able to install the requirements later by running: `pip install -r requirements.txt`

8. Be sure to add your venv to the gitignore list.

9. When done with venv: `deactivate`

10. To delete you just need to delete the folder of the venv: `rm -rf NAME`

# virtualenvwrapper

**virtualenvwrapper** provides tab-completion on environment names. It really helps when you have a lot of environments and have trouble remembering their names.

`workon` also deactivates whatever environment you are currently in, so you can quickly switch between environments.

## Setup

1. Ensure that python, pip, and virtualenv are installed.

2. Install the wrapper (full instructions [here](https://virtualenvwrapper.readthedocs.io/en/latest/install.html))
   - linux:
     ```
     $ pip install virtualenvwrapper
     $ export WORKON_HOME=~/Envs
     $ source /usr/local/bin/virtualenvwrapper.sh
     ```
   - PC (default PATH for WORKON_HOME is %USERPROFILE%\Envs):  `pip install virtualenvwrapper-win`

## Usage - Create & Work On

I will provide two options - and highly suggest the 2nd.

### Standard

1. Create a venv: `mkvirtualenv VENVNAME`

   This creates the VENVNAME folder inside `~/Envs`.

2. Work on the virtual environment: `workon VENVNAME`

### Alternative

You can make a project, which creates the virtual environment, and also a project directory inside `$WORKON_HOME`, which is `cd`-ed into when you `workon PROJECTNAME`.

1. Create project:  `mkproject PROJECTNAME`

   The first time you run this, you will see a similar message:
   ```
   (base) C:\Users\Kat\Documents\SOME_DIRECTORY>mkvirtualenv xlsxwriter-autofit
   C:\Users\Kat\Envs is not a directory, creating
   Using base prefix 'c:\\programdata\\anaconda3'
   New python executable in C:\Users\Kat\Envs\xlsxwriter-autofit\Scripts\python.exe
   Installing setuptools, pip, wheel...
   done.

   (xlsxwriter-autofit0) (base) C:\Users\Kat\Documents\Programming\repo\Personal-Projects\xlsxwriter-autofit>
   ```

   This is because prior to this, you did not yet have the Envs folder that is used to store these virtual environments.

   Since you do not have to be in the root of your project folder to do this, you can run while in any directory. This will (by default) also activate the environment.

2. Set your project directory by creating or navigating to the root folder of your project and then run:  `setprojectdir`

   When you set your project directory, the next time you activate your virtual environment it will:
   - activate the virtual environment
   - automatically move into this directory

3. To deactivate: `deactivate`

You can activate your virtual project to work on things again by running: `workon PROJECTNAME`

## Usage - Delete

To delete a virtual environment, run: `rmvirtualenv venv`

To delete a virtual project, (I believe - couldn't find documentation on it) run: `rmproject venv`

Additional items can be found [here](https://howchoo.com/g/nwewzjmzmjc/a-guide-to-python-virtual-environments-with-virtualenvwrapper).

## Usage - Duplicate A Virtual Environment

There may come a time where you wish to duplicate a virtual environment.

Thanks to [this medium post](https://medium.com/the-andela-way/configuring-python-environment-with-virtualenvwrapper-8745c2895745) here's how.

`cpvirtualenv ENVNAME TARGETENVNAME`

# Where Else Can I Learn About virtualenvwrapper

By reading [the docs](https://virtualenvwrapper.readthedocs.io/en/latest/command_ref.html).

# I Got An Error About PROJECT_HOME Not Being Setup!

Likely you need to set up your environment variables. Checkout the [SetEnvVars](https://github.com/ProsperousHeart/cheatsheets/blob/master/Processes/SetEnvVars.md) doc to see the steps I took to resolve on my Windows machine.
