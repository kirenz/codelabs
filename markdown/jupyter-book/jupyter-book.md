author: Jan Kirenz
summary:
id: jupyter-book
tags:
categories:
environments: Web
status: Published
feedback link: https://github.com/kirenz/codelabs/blob/master/markdown/jupyter-book

# Jupyter book installation tutorial

<!-- ------------------------ -->
## Overview

Duration: 0:01:00

### What we cover

In this tutorial we are going to create and publish a `Jupyter book`. [Jupyter Book](https://jupyterbook.org/intro.html) is an open source project for building publication-quality books and documents from computational material.

<img src="img/logo.png" alt="Dash Dashboard" width="200">

Building a Jupyter Book broadly consists of these steps:

1. **Create your book’s content**. You structure your book with a collection of folders, files, and configuration. 

1. **Build your book**. Using Jupyter Book’s command-line interface you can convert your pages into either an HTML or a PDF book. 

1. **Publish your book online**. Once your book is built, you can share it with others. Most common is to build HTML, and host it as a public website (we use GitHub pages).


<aside class="positive">
Jupyter Book lets you quickly generate a book structure from templates.
</aside>

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

[Conda environments](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands) help manage dependencies and isolate projects. This is particularly useful when some packages require specific Python versions. Since there is a known incompatibility for Windows OS notebook execution when using Python 3.8., we will use Python 3.7.

On Windows open the Start menu and open an Anaconda Command Prompt. On macOS or Linux open a terminal window.

We create an environment with a specific version of Python (3.7). We call the environment ``jbook``:

```bash
conda create -n jbook python=3.7
```

<!-- ------------------------ -->
## Installation of modules
Duration: 00:05:00

First, you need to activate your environment as follows:

```bash
conda activate jbook
```

Now we can install modules in our environment. To do this, we use [**pip**](https://pip.pypa.io/en/stable/) (pip is the standard package installer for Python). 

```bash
pip install -U jupyter-book
```

<!-- ------------------------ -->
## Creation of a book
Duration: 00:05:00

We are going to follow these [instructions](https://jupyterbook.org/basics/create.html#create-a-template-book) to quickly create a sample book:

- create a new folder of your choice (I created a folder with the name `books`).

- `cd`into your folder

´´´bash
cd books
´´´

- Create the book:

```bash
jupyter-book create mynewbook/
```

This will generate a mini Jupyter Book that you can both build and explore locally. 

It will have a few decisions made for you, and you can explore the configuration of the book in `_config.yml` and its structure in `_toc.yml`. 

Use this book as inspiration, or as a starting point to work from.


<!-- ------------------------ -->
## Book structure
Duration: 00:05:00

All of the configuration for your book is in a [YAML](https://en.wikipedia.org/wiki/YAML) file called `_config.yml`.

You can define metadata for your book (such as its title), add a book logo, turn on different “interactive” buttons (such as a GitHub button), and more. To get an overview about all options, visit the [documentation](https://jupyterbook.org/start/create.html). Here, we just make some minor changes:

- Open the file `_config.yml`in your code editor.

- change the title and author.

Now that you’ve got a Jupyter Book folder structure, you can create the HTML (or PDF) for each of your book’s pages. That’s covered in the next section.


<!-- ------------------------ -->
## Add to GitHub 
Duration: 00:05:00

Next, we add your book project to [GitHub](https://github.com/). I use [GitHub Desktop](https://desktop.github.com) to create a new repository:

- In the GitHub Desktop drop-down menu, click **File** and choose **New Repository**.

- Use the name of your Jupyter book (*mynewbook*). 

- Choose your local path (*/books*).

- Click on **Create Repository**.

- In GitHub Desktop, click **Publish repository** (if you want to create a public repo, uncheck the option "Keep this code private").

<!-- ------------------------ -->
## Add to GitHub 
Duration: 00:05:00

Next, we add the folder to GitHub. I use [GitHub Desktop](https://desktop.github.com) to create a new repository:

- In the GitHub Desktop drop-down menu, click **File** and choose **New Repository**

- Use the name of your Jupyter book (*mynewbook*) 

- Choose your local path (*/books*)

- Click on **Create Repository**

- In GitHub Desktop, click **Publish repository** and choose to create a public repo (not private).


<!-- ------------------------ -->
## What's next?

Duration: 0:02:00

Congratulations! You have completed the tutorial and learned how to:

✅ Create a virtual environment for your Jupyter book  
✅ Install Jupyter book in your virtual environment
✅ Create a Jupyter book

Next, you may want to proceed with this tutorial to explore the structure of your book:

- [Jupyter book tutorial](https://jupyterbook.org/basics/organize.html)


<img src="img/Jan.png" alt="Jan Kirenz" width="100">

Thank you for participating in this tutorial. If you found any issues along the way I'd appreciate it if you'd raise them by clicking the "Report a mistake" button at the bottom left of this site.

*Copyright: Jan Kirenz (2021) | [kirenz.com](https://www.kirenz.com) | [CC BY-NC 2.0 License](https://creativecommons.org/licenses/by-nc/2.0/)*