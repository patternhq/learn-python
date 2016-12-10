Anaconda is an environment manager.  On OS-X and Linux, there is usually a
default python installation.  You _can_ use that, however, if you do something
that messes it up, then you're in a bit of a tight spot.  Also, you might find
yourself working on multiple projects that require different versions of the
same project.  The solution is to install an environment manager so you can
easily switch between different environments.  The two most popular python
environment managers are [Anaconda](https://www.continuum.io/anaconda-overview) and [virtualenv](http://docs.python-guide.org/en/latest/dev/virtualenvs/).

For this p-learn, you'll want to install Anaconda from [here](https://www.continuum.io/downloads).

Once you have anaconda, you'll want to set up an environment for this class.

```
conda create --name plearn python=3.5
```

Once the environment has been created, then you need to activate it:

```
source activate plearn  # plearn is the name set up in the previous line.
```

Every time you start a new shell, you'll want to activate whatever environment
you want to work in.  To see what environments you have available to you:

```
conda env list
```

If you're done with working in a particular environment, you can deactivate it:

```
source deactivate plearn
```

Once you have an environment set up, we can test to see if it is working by
invoking the interactive interpreter...

```
python
```

You should get something that looks like:

```
Python 3.5.2 |Continuum Analytics, Inc.| (default, Jul  2 2016, 17:52:12)
[GCC 4.2.1 Compatible Apple LLVM 4.2 (clang-425.0.28)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

From here, you can issue commands just as you would in a python script.  It's
super nice for just messing around with things to see how it works.  You can
also quickly check what python version you are working with (python 3.5.2 for
me!).

I tend to use [this cheat-sheet](http://conda.pydata.org/docs/_downloads/conda-cheatsheet.pdf) when I want to look up commands for anaconda.

Now that we have python set up, lets look at a [very basic python program](hello-world/README.md).
