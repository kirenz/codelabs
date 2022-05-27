author: Jan Kirenz
summary:
id: miniforge-setup
tags:
categories:
environments: Web
status: Published
feedback link: https://github.com/kirenz/codelabs/blob/master/markdown/miniforge-setup


# Miniforge setup

<!-- ------------------------ -->
## Overview
Duration: 0:02:00

The open-source project [Miniforge](https://github.com/conda-forge/miniforge) is one of the easiest ways to get started with data science projects. It is a small, bootstrap version of the data science platform [Anaconda](https://www.anaconda.com/products/distribution) (like [Minconda](https://docs.conda.io/en/latest/miniconda.html)) that includes only Python, the open source package management system [conda](https://docs.conda.io/en/latest/) and a small number of other useful packages. 

<aside class="positive">
Miniforge is an community-led alternative to the data science platforms Anaconda and Miniconda, provided by Anaconda, Inc.
 </aside>



<!-- ------------------------ -->
## Prerequisites

Duration: 0:02:00

- If you already have Anaconda on your machine, you should uninstall it first (Miniforge is an alternative to Anaconda): how to [uninstall Anaconda](https://docs.anaconda.com/anaconda/install/uninstall/).


- To start this tutorial, you should have some basic understanding of the command line interface (other names for the command line are: cmd, CLI, prompt, console or terminal.   
  - If you aren't familiar with the terminal, read this [introduction to the command-line interface](https://tutorial.djangogirls.org/en/intro_to_command_line/).

<aside class="positive">
The terminal is a text-based application for viewing, handling, and manipulating files on your computer
</aside>  

- If you have a Mac, [install Homebrew](https://brew.sh/) (the missing package manager for macOS). Homebrew makes it easy to install software you need that Apple didn’t.



<!-- ------------------------ -->
## Installation 

Duration: 00:05:00

- If you have **Windows**: Open the [Miniforge GitHub page](https://github.com/conda-forge/miniforge#miniforge3), choose the appropriate installer for your system and install the software.

- If you have **MacOs**: Open your terminal and use `brew` to install Miniforge:


```Bash
brew install miniforge
```

- Then run this command:

```Bash
conda init zsh
```

- Now restart your terminal.


<!-- ------------------------ -->
## Virtual environments
Duration: 00:05:00


During the first installation, Miniforge installed the so called `base` environment. Let`s take a look at this environment:

- On *Windows* open the Start menu and open an "Anaconda Command Prompt". 
- On *macOS* or *Linux* open a terminal window.

Usually, the `base` environment is already activated (and you can see the word `base` in your terminal. If not, type: `conda activate base`)

- Now take a look at all the modules in your `base` environment:

```bash
conda list
```

You should see a list of modules with their name, version, build (more detaild information about the package) and channel (from which the packages were installed).

<!-- ------------------------ -->

## Create a virtual environment
Duration: 00:05:00

The package manager `conda` makes it easy to manage multiple data environments that can be maintained and run separately without interference from each other (in so called *virtual environments*). 

[Conda environments](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands
) help manage dependencies and isolate projects. This is particularly useful when some packages require specific module versions. 

### Environment for scikit-learn

In this example we will install the module [scikit-learn](https://scikit-learn.org/stable/) with conda. See step "Installation of modules" for more information about this topic.

- Let's create a new environment for scikit-learn:
  - `conda create -n` creats a new environment
  - `sklearn-env` is the name we choose
  - `-c conda-forge scikit-learn` installs the module scikit-learn with conda


```bash
conda create -n sklearn-env -c conda-forge scikit-learn
```

When conda asks you to proceed ``(proceed ([y]/n)?``), type ``y``.

- You can activate the new environment as follows:

```bash
conda activate sklearn-env
```

- Now take a look at all the modules in your `sklearn-env` environment:

```bash
conda list
```

- If you want to switch back to your `base` environment simply type:

```bash
conda deactivate
```


<!-- ------------------------ -->
## Update environments
Duration: 00:05:00


If you want to update a specific environment (this will update all packages in the selected environment to the latest version but will not update Python), use this command: `conda update --all`

*Make sure to activate the right environment first. In our example, we use the sklearn-env environment so we first activate it*


- Activate enironment

```Bash
conda activate sklearn-env
```

- Update all modules

```terminal
conda update --all
```

- If you only want to update specific modules, use conda update and the name of the module (e.g., scikit-learn)

```bash
conda update scikit-learn
```

<!-- ------------------------ -->
## Installation of modules 
Duration: 00:05:00

There are two options of how to install modules in an environment: with `conda` or `pip`. Note however, that ideally you should always use one of the two methods in one environment.


### Conda-forge

As a first option, you should always try to download a package from [conda-forge](https://conda-forge.org/docs/user/introduction.html). Here is a list of [conda-forge packages](https://anaconda.org/conda-forge/repo).


- Since we installed Miniforge, we can simply use `conda install` and type the name of the package we want to install (always keep in mind that you first need to activate the environment of your choice):

```bash
conda install package-name
```

As an example, let's install some additional modules in our `sklearn-env` environment:

- Activate environment:

```Bash
conda activate sklearn-env
```

- Install pandas:

```Bash
conda install pandas
```


### Pip

Instead of `conda`, you can also use [pip](https://pip.pypa.io/en/stable/) (the standard package installer for Python) to install packages. Use this option if the package you want to install isn't available in conda. 

Note that you should always create a new environment and only use `pip` to install new modules in this environment.

- You can install packages like this:

```Bash
pip install package-name
```

<!-- ------------------------ -->
## Congratulations
Duration: 0:01:00

Congratulations! You have completed the tutorial and learned how to: 

✅ install Miniforge 
✅ create virtual environments  
✅ install modules using conda



<img src="img/Jan.png" alt="Jan Kirenz" width="100">

Thank you for participating in this tutorial. If you found any issues along the way I'd appreciate it if you'd raise them by clicking the *Report a mistake* button at the bottom left of this site.

*Jan Kirenz (2022) | [kirenz.com](https://www.kirenz.com) | Made with [Codelabs](https://github.com/googlecodelabs/tools)*