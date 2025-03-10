(toolbox)=
# Python Toolbox

This page describes several ways to write and execute Python code, some of which don't require any installation on your computer and work entirely in a web browser! These approaches are described in the sections below, and are based on the tools IPython and Jupyter Notebooks.

**IPython** is an interactive Python interpreter that adds features that are useful for engineering, such as command history or inline display of figures. As you will see below, you can enter multiple lines of text and evaluate them at once; this is often referred to as a *cell* of code. In a nutshell, if you string many of these cells together into a single digital document, you more or less end up with a **Jupyter Notebook**; this leverages the power of IPython by allowing you to type, run and save the cells in any order, as well as type formatted text in between. Together, these two tools make up our toolbox for this course, and, as you will see, both of them can run in your internet browser, so there is no need to install special software!

## Interactive Pages

This course is powered by a special software (the [Sphinx-Thebe](https://github.com/executablebooks/sphinx-thebe) that allows you to run Python code in your browser and gives you an experience that is more or less identical the the "standard" Jupyter Notebook experience you would have on your own computer if you installed the dedicated software. You can access this tool by clicking on the rocket icon ({fa}`rocket`) at the top right of a page where this is enabled. 

(calculator)=
## IPython: Your Primary Python Calculator

Below is an example of an IPython interpreter embedded in this webpage, which we refer to as our **Python Calculator**. Note that the square brackets with numbers (e.g, `[1]: ...`) are a feature of IPython that keeps track of the cells you have run: the first (pre-loaded) command is a print statement that executes once the interpreter is ready for use. You can try entering code yourself (for example, type `x=2`) and executing it using `Shift+Enter`. You just defined a variable! Note that typing `Enter` in the interpreter adds extra lines, it does not execute the cell. Try entering multiple lines, for example, `3*x`, `Enter` and `print(x)`, then execute. Can you tell what happened?

<iframe
    src="https://tudelft-citg.github.io/learn-python-calculator/repl/index.html?toolbar=1&kernel=python&code=print(%27You%20may%20begin!%27)"
    width="750"
    height="400"
    style="border:2px solid powderblue"
></iframe>

The simple exercise above should be all you need to get started with this course. Throughout this course we encourage you to the Python Calculator in a new browser tab, which will allow you to read the exercise and run code side by side. You can test it <a href="https://tudelft-citg.github.io/learn-python-calculator/repl/index.html?toolbar=1&kernel=python&code=print(%27You%20may%20begin!%27)" target="_blank">here</a> in a new tab. When the console is critical for completing the exercises in a certain chapter, a drop-down note will be added that includes a special link inside, just like this:

`````{admonition} Open the Python Calculator for this page
:class: tip, dropdown
Click this <a href="https://tudelft-citg.github.io/learn-python-calculator/repl/index.html?toolbar=1&kernel=python&code=print('You may begin!')" target="_blank">link</a> and wait until the message "<tt>You may begin!</tt>" is printed to start evaluating code. More information about this tool can be found [here](calculator). 

Remember that most pages in this course can also be run interactively using the {fa}rocket icon above (read more about it [here](toolbox)).
`````

All exercises in this course can be completed using only the Python Calculator. We hope you find it to be a simple but useful way to practice and learn the Python programming language.

```{note}
A special instance of the Python Calculator is set up for each page which pre-loads a few packages needed to complete the exercise. Make sure you use link that is on the page of the exercises you are working on. 
```

## Anaconda: Python on Your Computer

If you want to explore Python programming and Jupyter ecosystems beyond the exercises covered in this course, it might be worthwhile to install a Python distribution on your own computer. The most common and easiest way to do this is with [Anaconda](https://www.anaconda.com/download). Installation instructions are not included in this course, but you can find plenty of website of videos that cover this, as well as using the Anaconda Navigator to open a Jupyter Lab or Jupyter Notebook environment. Most of the pages in this online textbook can be downloaded in the form of a Jupyter Notebook file (a file ending with `.ipynb`): open it via one of the Jupyter environments and you are ready to go!