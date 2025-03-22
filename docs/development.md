# Book Development

This book was developed over several years with a number of people.

In 2024 the book was upgraded to include Python interactivity via Sphinx-Thebe.


## Pre-2024 README

_The contents below are from the README prior to the 2024 upgrade._

### Interactive Python Elements

As of Summer 2023, this course uses two methods for providing students the ability to run Python in their internet browser: an IPython console (JupyterLite and Pyodide) and a 3rd party cloud kernel to run a `*.ipynb` file (Binder and Colab). The IPython console is provided in the associated repositor `TUDelft-CITG/learn-python-calculator`. There is also a package that is loaded into the notebooks and IPython console to check student answers, which can be found in `TUDelft-CITG/learn-python-package`.

We decided that with the in-browser Python capabilities, there is no longer a requirement to provide separate notebooks for students to run locally (and consequently, no need to install any software!). However, since it is nice to be able to run the cells in the theory and exercise pages, links to open each page with a working Python kernel via Binder and Colab are included (the rocket icon {fa}`rocket` at the top right). Colab initializes much faster and more reliably, but due to GDPR concerns with Google products, Binder is offerred as an alternative. Neither platform will save modifications to the notebook, unless they are downloaded or imported individually.

An overview of the interactive elements by Chapter:

- Exercises in Chapters 1 and 2 are evaluated using JupyterQuiz only; no execution of Python code is required
- Exercises in Chapters 3, 4 and 6 use a JupyterLite REPL; the answer-checking package is used here
- Exercises in Chapter 5 use a mix of JupyterQuiz and a JupyterLite REPL; the answer-checking package is used here
- Exercises in Chapter 7 use a JupyterLite REPL (separate web page); the answer-checking package is *not* used here 

#### IPython Console

An HTML link is created and can be customized to initialize the console fora particular page.

To use the IPython console with a bit of front-end setup, use this [link](https://tudelft-citg.github.io/learn-python-calculator/repl/index.html?toolbar=1&kernel=python&code=print(%27You%20may%20begin!%27)), which adds the following to the URL: `?toolbar=1&kernel=python&code=print(%27You%20may%20begin!%27)`.

The example below chooses the kernel, imports pandas and the answer-checker and gives a message to begin.
 
````md
```{admonition} Open the Python Calculator for this page
:class: tip, dropdown
Click this <a href="https://tudelft-citg.github.io/learn-python-calculator/repl/index.html?toolbar=1&kernel=python&code=import pandas as pd; import data.check_answers as check; print('You may begin!')" target="_blank">link</a> and wait until the message "<tt>You may begin!</tt>" is printed to start evaluating code. More information about this tool can be found [here](calculator). 

Remember that most pages in this course can also be run interactively using the {fa}rocket icon above (read more about it [here](toolbox)).
```
````

#### Jupyter notebooks

Notebooks are set up using built-in features of Jupyter Book and links to Binder and Colab are provided. This automatically uses the notebook to generate the page, and the following cell needs to be added to the notebooks (remember to make it a hidden cell in the Jupyter Book so that it does not display on the website):
```
# ##-On Google colab uncomment and run the following code
# ## to install and import the function that will be used to check your answers.
# !pip install learn-python-ceg-test

# ##-On Binder just uncomment and run the following line
# import learn_python_ceg_test.check_answers as check
```

#### Decision-making notes

This section summarizes some key information that led up to the final decision of whether (and how) to include a Python kernel directly in the Jupyter Book (i.e., an interactive page directly in the book) for the Summer 2023 version, which was not trivial. These tools change quickly, so the information may already be out of date or irrelevant.

Remember that JupyterLite provides a Jupyter-like interface (Lab, classic notebook, REPL/console) and can be used with one of two kernels: Xeus or Pyodide. The biggest implication for us seems to be that Xeus does not allow dynamic import of packages at runtime (conda-forge only), whereas Pyodide does (via pip). On the other hand, Xeus allows pre-loading packages, whereas Pyodide does not. Future development may combine these two kernels, so it is only a matter of time until something breaks. Stay tuned...

Option 1:
- JupyterLite REPL to create iPython console in a frame on the page, supported by a Xeus kernel
- Allows conda forge packages (no pip) installed during the build process (not dynamically installed via frontend)
- Can specify code to run on init but it is visible as the first cell command (no hiding of code)
- conda forge package only visible in error traceback (important for answer-checking)

Option 1.5: same as Option 1 with a notebook, but must include the nb as a separate file in the book repo

Option 2:
- Binder (creates an image) and Colab creates a nb interface on google server (not same container as binder)
- displays page as nb with live kernel
- can use pip (conda-forge not sure)
- cannot hide cells (this is JB only, and all cells need to run and be not hidden)
- all cells are active
- need to hide cell in JB for colab pip install (not remove) and run this cell when using nb in colab

Option 3: JupyterLite kernel with Thebe to support an interactive Jupyter notebook page. We did not pursue this because it's not fully implemented yet via Jupyter Book (javascript stuff). Although Thebe is functional with a Binder kernel, in our opinion this is too slow and unreliable.

In the end, there was a problem with getting `matplotlib` to import when JupyterLite was included in the book build (see [Issue #35](https://github.com/TUDelft-CITG/learn-python/issues/35)). We also realized that it is possible (and much easier!) to create a separate JupyterLite website that uses Lab, classic nb or REPL via GitHub pages (see the [JupyterLite](https://jupyterlite.readthedocs.io/en/latest/) demos), which was a good alternative to complicated workflows and buggy kernel installations required for building the kernel directly into the book.

