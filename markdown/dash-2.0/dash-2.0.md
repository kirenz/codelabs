author: Jan Kirenz
summary:
id: dash-2.0
tags:
categories:
environments: Web
status: Published
feedback link: https://github.com/kirenz/codelabs/blob/master/markdown/dash-2.0

# Dash installation tutorial

<!-- ------------------------ -->
## Overview

Duration: 0:01:00

### What we cover

In this tutorial we are going to install the preview version on Dash 2.0.


<!-- ------------------------ -->
## Prerequisites

Duration: 0:07:00

To start this tutorial, you need Anaconda. If you don't already have Anaconda, go to [anaconda.com](https://www.anaconda.com/products/individual) and choose the appropriate `Graphical Installer` for your system (Windows, MacOS or Linux). Install the software on your system:

- [Installing on macOS](https://docs.continuum.io/anaconda/install/mac-os/)
- [Installing on Windows](https://docs.continuum.io/anaconda/install/windows/)
- [https://docs.continuum.io/anaconda/install/linux/](https://docs.continuum.io/anaconda/install/linux/) 

Here some tips if you have problems installing Anaconda: [troubleshooting](https://docs.anaconda.com/anaconda/user-guide/troubleshooting/#anaconda-installer-download-problems).

<!-- ------------------------ -->
## Create Virtual Environment

Duration: 0:05:00

[Conda environments](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands) help manage dependencies and isolate projects. This is particularly useful when some packages require specific Python versions.

On Windows open the Start menu and open an Anaconda Command Prompt. On macOS or Linux open a terminal window.

We create an environment with a specific version of Python (3.9) . We call the environment ``dash``:

```bash
conda create -n dash2 python=3.9
```

When conda asks you to proceed ``(proceed ([y]/n)?``), type ``y``.


<!-- ------------------------ -->
## Installation of modules
Duration: 00:05:00

First, you need to activate your environment as follows:

```bash
conda activate dash2
```

Now we can install modules in our environment. 

To do this, we use [**pip**](https://pip.pypa.io/en/stable/) (pip is the standard package installer for Python) or **conda** (open source package management system from Anaconda). To learn the differences between the two options, see this article ["Understanding Conda and Pip"](https://www.anaconda.com/blog/understanding-conda-and-pip).  

Here, we use conda to install dash-labs and some additional modules. 

- [Dash 2.0](https://anaconda.org/conda-forge/dash):

```bash
conda install -c conda-forge dash
```

- [pandas](https://pandas.pydata.org/docs/index.html): We also install pandas, which is required by some dash modlues (like Plotly Express).

```bash
conda install pandas
```

- [Jupyter Dash](https://github.com/plotly/jupyter-dash): This library makes it easy to develop Plotly Dash apps interactively from within Jupyter environments (e.g. classic Notebook, JupyterLab, Visual Studio Code notebooks, PyCharm notebooks, etc.)

```bash
conda install -c plotly jupyter-dash
```

<!-- ------------------------ -->
## What's next?

Duration: 0:02:00

Congratulations! You have completed the tutorial and learned how to:

✅ Create a virtual environment for dash  
✅ Install Python modules in your virtual dash environment

Next, you may want to proceed with this tutorial provided by plotly to build your first dash app:

- [Dash tutorial](https://dash.plotly.com/layout)


<img src="img/Jan.png" alt="Jan Kirenz" width="100">

Thank you for participating in this tutorial. If you found any issues along the way I'd appreciate it if you'd raise them by clicking the "Report a mistake" button at the bottom left of this site.

*Copyright: Jan Kirenz (2021) | [kirenz.com](https://www.kirenz.com) | [CC BY-NC 2.0 License](https://creativecommons.org/licenses/by-nc/2.0/)*