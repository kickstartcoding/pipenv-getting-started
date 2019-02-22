![Kickstart Coding Logo](./logo.png)

# Kickstart Pipenv: Getting Started

Tutorial for downloading packages from PyPI. Teaches how to install  Pipenv to
create and manage virtualenvs and download packages.

## Who is this guide for

* This is for **brand new Python users**, including **coding class students**
  who want a simple and to-the-point guide on getting Pipenv working on their
  system.

* This guide assumes you already have some fundamental Python and Bash
  knowledge.

* This guide *does not* support Windows. It assumes you use either **macOS** or
  **Ubuntu GNU/Linux**.

> This was original created for Kickstart Coding, the affordable,
> inclusive, and intensive coding course teaching cutting-edge Python /
> Django and JavaScript / React web development in Oakland, CA.
> [Learn more and enroll here.](http://kickstartcoding.com/?utm_source=github&utm_campaign=cheatsheets)


# What is Pipenv?


**Pipenv** is a tool for downloading software packages from **PyPI** (the
website and repository). It downloads them into directories known as a
**virtualenv**. It is best practice to make one of these for each project you
work on, to keep the different downloads separate. This is because each project
might have different needs from PyPI.

### Key Terms


* **package** - A (usually) free/open source library of programming code, that
  others have published to the internet for you to download and use.

* **PyPI** - A giant repository of free, open source libraries that various
  people around the world have written, for use in your code.

* **Pipenv** - A command-line tool for downloading software (like `git`, or
  `brew`, or `apt`). One of several tools available for downloading and using
  packages from PyPI. This guide uses it since it requires the fewest steps for
  beginners.

* **virtualenv** - The place on your computer where third party libraries go
  when downloaded from PyPI. Pipenv automatically creates one of these for each
  project you are working on. This helps keep your projects working
  independently of each other, no matter what each one might need downloaded to
  work.

### (Less) Key Terms

* **Pipfile** - Pipenv keeps track of what you have downloaded using it in a
  file called *Pipfile*. This is in case you forget, or in case a team-member
  needs to download the same packages as you.

* **pip** (or **pip3**) -- Another (older) tool used to download packages from
  PyPI. Pipenv (essentially) uses this "behind the scenes".

* **dependencies** -- The list of packages (e.g. code libraries, modules etc)
  that you have to download to get a given application to run. Pipenv records
  the dependencies of each project in a file called "Pipfile" (mentioned
  above).

# Guide

Now that you know a little about Pipenv, it's time to install it on your system
and get used to using it.

## Installing Pipenv

Ubuntu Linux users, run the following command:

```bash
sudo apt-get install python3-pip -y && sudo pip3 install pipenv
```

macOS users, run the following command:

```bash
brew install pipenv
```

## Using Pipenv

Broad concepts:

* Whenever you *create* a new Python project, you will want to create a new
  virtualenv for it

* Whenever you go back to working on a Python project, you will have to "enter"
  the virtualenv for it

* In summary: You will create a virtualenv once (typically for each project you
  are working on), but you may enter it many times, every time you are working
  on it.

## Creating a new virtualenv

Every time you want to do a new Python project, you will need to create a new
virtualenv for it.  These steps are to create a "pipenv project directory".
Much like a "git-enabled directory" is signified by a hidden `.git` file
(revealed with `ls -a`), a "pipenv project directory" will be signified with a
Pipfile.

1. In a terminal, create a new directory for this activity. It could be
anywhere.  Change into the directory for the subsequent steps.  For example:

```bash
mkdir pipenv_test
cd pipenv_test
```

2. Create a Pipfile along with a new pipenv "virtualenv" as follows:

```bash
pipenv --python 3
```

## Entering a virtualenv

Whenever you go back to working on a Python project, you will have to activate
(i.e. "enter") the virtualenv for it.

To activate the "virtualenv" so that you can start installing PyPI packages, go
to the directory where you crated it if you aren't there already, and type in:

```bash
pipenv shell
```

You know you have a virtualenv activated when your bash prompt has the name of
the virtualenv in parenthesis. If you see that, you know that all subsequent
uses of Python and pipenv will be using the right versions and directories of
everything.



## Trying out Pipenv

Once you have "activated" your virtualenv, it's time to try out pipenv. In this
tutorial, we'll install and test a package called `silly`.

To install `silly`:

```bash
pipenv install silly
```

### Using `silly`

Try using silly. You can use it either from the interactive prompt
Python prompt (remember, just type "python3" then hit enter), or by creating a
new Python code file that includes the code you want to use, as you would any
other Python program. Test it out with the following:

```python
import silly
silly.thing()
silly.paragraph()
```

Try out all the features of silly!


Silly was just an example. Read more about the silly package at:
https://github.com/classam/silly


# Extra challenges

1. Look through PyPI for another package

2. Try installing it with pipenv

3. Read its documentation and see if you can get it working

# Pipenv Tips

* You know you are inside a *virtualenv* when there are parenthesis next to
  your bash prompt.

* Don't ever run `pipenv` commands directly from your home directory! This
  could cause creating a `virtualenv` that is associated with your home
  directory, which is very confusing. Instead, you should only run them within
  your project directories, e.g., next to the `README.md` if you have a GitHub
  cloned repo, or next to the `manage.py` if you are using Django or another
  Python web framework.

* Closing a terminal will "exit" the virtualenv. This also means if you get
  your bash terminal in some weird state and it's not letting you enter (or
  exit the  virtualenv with `deactivate`), the most sure-proof way of "getting
  out" is simply closing your terminal window and starting a new window!
