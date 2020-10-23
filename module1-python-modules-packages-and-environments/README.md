# Python Modules, Packages, and Environments

Places for your code (and dependencies) to live.

## Learning Objectives

- Understand and follow Python namespaces and imports
- Create a Python package and install dependencies in a dedicated environment

## Before Lecture

Install `pipenv` and `git` on your local machine if you haven't already, and
read the official documentation for
[Python modules](https://docs.python.org/3.7/tutorial/modules.html).

## Live Lecture Task

We're going to start our own Python package the right way - by making an
environment with `pipenv`, installing our dependencies, and making some classes.

## Assignment

1) Create your own lambdata-yourusername package, as shown in lecture
2) Implement at least 2 of the following "helper" utility functions:

* Check a dataframe for nulls and return the number of missing values.
* Create a Train/Test split function for a dataframe and returns both the Training and Testing sets.  
* Develop a randomization function that randomizes all of a dataframes cells then returns that randomized dataframe. 
* Split addresses into three columns (df['city], df['state'], and df['zip']) - you can use regexes to detect the format and pull out important pieces.
* Return a new column with the full name from a State abbreviation column -> An input of FL would return Florida. 
* Single function to take a list and dataframe then turn the list into a series and add it to the inputted dataframe as a new column.
* A 1.5*Interquartile range outlier detection/removal function that gets rid of outlying rows and returns that outlier cleaned dataframe.
* Function to split dates of format "MM/DD/YYYY" into multiple columns (df['month'], df['day'], df['year']) and then return the same dataframe with those additional columns.

3) Register for a test PyPI account
4) Publish your package as lambdata-yourusername (to avoid conflicts)
5) Start a Python notebook, and install your package with
!pip install --index-url https://test.pypi.org/simple/ lambdata-yourusername
6) import lambdata_yourusername as lambdata in your notebook, and try it out!

We'll step through in lecture - building and publishing a package requires
twine, and is generally done with these commands:

python setup.py sdist bdist_wheel (builds the actual package)
twine upload --repository-url https://test.pypi.org/legacy/ dist/*

twine itself can be installed with pipenv install -d twine so it is a
development dependency.

Many of the utility functions can be implemented with the right clever calls
to pandas, numpy, and other libraries - that's fine! Use those as
dependencies. There's still value in a package that encapsulates more
complicated libraries and exposes streamlined functionality with a simplified
API. If you would like to generate some fake data check out the Faker python package to craft specific data types.

Also note - there's a lot more than 2 ideas above. Throughout the week, whenever you have finished the daily assignment baseline, you can always come back and add more functionality to your lambdata (including ideas of your own)!

## Resources and Stretch Goals

The [official Python packaging tutorial](https://packaging.python.org/tutorials/packaging-projects/)
can help you if you get stuck with the assignment. Make sure to use Test PyPI!
If you get through all the steps, try some of the following stretch goals:

- Check out the source code for [pandas](https://github.com/pandas-dev/pandas),
  and see if you can make sense of it. Try to find the actual logic behind
  specific functions you use (e.g. `pd.DataFrame`, `df.replace`, etc.). Reading
  source code is challenging, especially from large codebases, but it's a skill
  that will help you debug and fix real issues in professional situations.

- Explore [PyPI](https://pypi.org), the Python Package Index - this is where
  `pip` (the official base Python package installer, which both Anaconda and
  `pipenv` build on) gets things from by default. For now stick with Test PyPI
  for your own publishing, but you can work to make things "real"!
