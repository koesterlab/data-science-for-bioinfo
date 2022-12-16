# python 

> [Python](https://www.python.org/) is a programming language that lets you work quickly and integrate systems more effectively.

That is how [`python.org`](https://www.python.org/) puts it.
We can maybe add that python comes with a great Open Source community around it, including a large package ecosystem with packages for everything from data science, to bioinformatics or machine learning.
We suggest some below, but whenever you need to do something in python (like parsing a particular file format or running some machine learning method), it usually makes sense to go first check whether there is a package that will provide you with all the functionality for this.

## learning programming with python

The [software carpentries](https://software-carpentry.org/) provide a great [**Programming with Python** course](https://swcarpentry.github.io/python-novice-inflammation/) that you can also work through self-paced.
It includes linkouts for how to set up for the course, so you should be able to get yourself up and learning in no time.

## python coding style

`python` is known for its [rigorous style guide](https://peps.python.org/pep-0008/), some of which (like indentation) is also rigorously enforced.
There's a lot to learn from the style guide, so it's well worth a read!

## pandas: the standard for tabular data

[`pandas`](https://pandas.pydata.org/) is the current *de facto* standard package for working with tabular data (a.k.a. 95% of all of data science / bioinformatics).
Its documentation provides a number of [resources for **Getting Started**](https://pandas.pydata.org/docs/getting_started/index.html), just see which material fits you best (for example, have you used `R` or `Excel` in the past...?).

Generally, there are often multiple ways of achieving the same thing with `pandas`.
To be consistent and make your life a bit easier, there's a [suggestion for **Minimally Sufficient Pandas**](https://github.com/tdpetrou/Minimally-Sufficient-Pandas), a subset of all pandas functionality.
It makes sense to familiarize with that subset early on while learning to use `pandas`.

## polars: the future for tabular data

There's also a newer `python` library for tabular data, called [`polars`](https://pola-rs.github.io/polars-book/user-guide/).
It has a more efficient implementation and a cleaner usage syntax.
However, it is not as widely adopted and will not work on some older computers, so the current go-to recommendation is still `pandas`.
And while `polars` is probably the future for tabular data in python, a transition from `pandas` to `polars` won't be too difficult.