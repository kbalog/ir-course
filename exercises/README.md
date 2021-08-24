# Exercises

These exercises are solved and discussed during the classroom sessions (Wednesdays).

The exercises build on the preceding lectures; therefore, it is expected that for exercise **E{n}**, you have covered lectures **L{1}**..**L{n}**.

The solutions will be posted the same day after the class session.

## Prerequisites

Exercises are provided as Jupyter notebooks.

It is strongly recommended to have Python 3.7+ installed from an [Anaconda distribution](https://www.anaconda.com/products/individual#Downloads).

Additionally, you need to install the `ipython-ipytest` package (it adds magic commands that make it easier to define tests directly inside a notebook using the standard `pytest` framework).  You can install it either using [conda](https://anaconda.org/conda-forge/ipytest) or using pip: `pip install ipytest`.


## Workflow

You may use git to get the exercise files or download them from the GitHub website directly.

When using git, the repository is supposed to be used in read-only mode, that is, you only pull changes and make changes locally without committing them.

### Specific steps

  * **First time (if using git)**: Clone the repository `https://github.com/kbalog/ir-course` to your computer.
    - Note: unless you're a git guru and you know what you're doing, simply clone it and don't fork it. 
  * **At the beginning of each class session**: Pull changes from the repository or download the files from the `exercises/E{n}` folder manually..
  * **Complete the exercises in the Jupyter notebook(s)**
    - Easiest is to navigate to the `[YOUR_LOCAL_FOLDER]/exercises` folder and issue `jupyter notebook` in a terminal/command line window. (`YOUR_LOCAL_FOLDER` either refers to the folder where you cloned the git repo or where you saved the files manually.)
    - Complete the exercises by making the tests pass. 
    - Do *NOT* commit/push changes, as you won't be able to submit them.
  * **Study the reference solutions** (posted [here](solutions/)) after the class session.
