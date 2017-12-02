# Install software on your computer


### Install [git](http://git-scm.com/).

You have it installed if you can run `git --version` at the command
line and get output like `git version 2.3.5`.


### Install [Anaconda](http://continuum.io/downloads).

There are two things you can verify to check your install.

First, from the command line, all of the following should start up
some kind of Python interpreter:

```bash
python
ipython
ipython notebook
spyder
```

Second, inside any of those Python interpreters, you should be able to
do all of these without error:

```python
import numpy
import scipy
import matplotlib
import pandas
import statsmodels
import sklearn
```

### Install [Homebrew](http://brew.sh/) on Mac

If you use a Mac, install Homebrew if you don't
have it yet. You could use Homebrew to manage your `git` and `python`
installs as well, but the methods given above are very good and more
cross-platform.

---

### Q1. Python Version 2 or 3

**Course material for the bootcamp is compatible with Python versions 2.7 and 3.0. All HackerRank Python pre-work is configured for Python 3 only.  Therefore, Python 3 is the recommended version.**  

Did you install Python 2 or 3? Why?  

I currently have both installed, but will be using **Python 3.6.1** for the bootcamp, since it is the recommended version. Python 2.7.9 is installed because I am currently using it for personal & work projects.

### Q2. Which Python Version Installed   

How can you check the version of Python installed if you happen to be on an unfamiliar computer?

I confirmed my version by running the commands ```python``` and ```python3``` at the console.

```bash
chrisgiler_developer ~ $ python
Python 2.7.9 |Anaconda 2.4.0 (x86_64)| (default, Dec 15 2014, 10:37:34) 
[GCC 4.2.1 (Apple Inc. build 5577)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
Anaconda is brought to you by Continuum Analytics.
Please check out: http://continuum.io/thanks and https://binstar.org
>>> quit()
chrisgiler_developer ~ $ python3
Python 3.6.1 (v3.6.1:69c0db5050, Mar 21 2017, 01:21:04) 
[GCC 4.2.1 (Apple Inc. build 5666) (dot 3)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> quit()
```
