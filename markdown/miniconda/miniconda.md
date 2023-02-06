author: Jan Kirenz
summary: Miniconda Installation
id: miniconda
tags:
categories: tools
environments: Web
status: Published
feedback link: https://github.com/kirenz/codelabs/blob/master/markdown/miniconda

# Miniconda installation

<!-- ------------------------ -->
## Overview
Duration: 0:02:00

<img src="img/anaconda-logo.png" alt="Anaconda logo" width="200">  

The open-source [Anaconda Individual Edition](https://www.anaconda.com/products/individual) distribution is one of the easiest ways to perform data science projects. It already includes Python and the most important modules we need. 

<aside class="positive">
Anaconda is a data science toolkit which already includes most of the data science modules we need.
 </aside>


*If you already have Anaconda on your machine, make sure that you use the latest version (in our course, we use Python 3.9 but Python 3.8 or 3.7 is also fine). In your terminal, type `python --version` to see which Python version you are using in your Anaconda base environment.* 

*You may also uninstall your current Anaconda environment from your machine and install the latest version: here a guide of how to [uninstall Anaconda](https://docs.anaconda.com/anaconda/install/uninstall/).*

<!-- ------------------------ -->
## Prerequisites

Duration: 0:02:00

- To start this tutorial, you should have some understanding of the **command line interface** (other names for the command line are: cmd, CLI, prompt, console or terminal). 

If you aren't familiar with the terminal, read this [introduction to the command-line interface](https://tutorial.djangogirls.org/en/intro_to_command_line/).


<aside class="positive">
The terminal is a text-based application for viewing, handling, and manipulating files on your computer
</aside>  


<!-- ------------------------ -->
## Installation 

Duration: 00:05:00

- Go to [anaconda.com](https://www.anaconda.com/products/individual) 


- Scroll to the bottom of the page (until you see "Anaconda Installers")


- Choose the appropriate `Graphical Installer` for your system (Windows, MacOS or Linux) and install the software.


<!-- ------------------------ -->
## Virtual environments
Duration: 00:05:00


During the first installation, Anaconda installed the so called `base` environment. Let`s take a look at this environment:

- On *Windows* open the Start menu and open an "Anaconda Command Prompt". 
- On *macOS* or *Linux* open a terminal window.

Usually, the `base` environment is already activated (and you can see the word `base` in your terminal). If not, type: 

```bash
conda activate base
```

- Now take a look at all the modules in your `base` environment:

```bash
conda list
```

You should see a list of modules with their name, version, build (more detaild information about the package) and channel (from which the packages were installed).

<!-- ------------------------ -->

## Create a virtual environment
Duration: 00:05:00

Anaconda's package manager `conda` makes it easy to manage multiple data environments that can be maintained and run separately without interference from each other (in so called *virtual environments*). 

[Conda environments](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands
) help manage dependencies and isolate projects. This is particularly useful when some packages require specific Python versions. 

- Let's create an environment with a specific version of Python (3.9). We call the environment ``myenv``:

```bash
conda create -n myenv python=3.9
```

When conda asks you to proceed ``(proceed ([y]/n)?``), type ``y``.

- You can activate the new environment as follows:

```bash
conda activate myenv
```

- Now take a look at all the modules in your `myenv` environment:

```bash
conda list
```

- If you want to switch back to your `base` environment simply type:

```bash
conda deactivate
```

<!-- ------------------------ -->
## Update anaconda environments
Duration: 00:05:00


If you want to update a specific Anaconda environment (this will update all packages in the selected environment to the latest version but will not update Python), use this command: `conda update --all`

*Make sure to activate the right environment first. In our example, we use the base environment so we don't have to activate it*

- Update all

```terminal
conda update --all
```

- If you only want to update specific modules, use conda update and the name of the module (e.g., scikit-learn)

```bash
conda update scikit-learn
```

- Let's make sure that you use the machine learning module `scikit-learn` in version 1.0.2 or higher:

```terminal
conda list scikit-learn
```

- It's also possible to install a specific version of a module:


```bash
conda install -c anaconda scikit-learn=1.0.2
```

<!-- ------------------------ -->
## Installation of modules 
Duration: 00:05:00

There are several options how to install modules in a Anaconda environment.


### Conda

[conda](https://docs.anaconda.com/anaconda/user-guide/tasks/install-packages/) is the official Anaconda module manager. 

If you install a new module with `conda`, it analyses the current environment including everything currently installed, and, together with any version limitations specified (e.g. the user may wish to have TensorFlow version 2.0 or higher), works out how to install a compatible set of dependencies, and shows a warning if this cannot be done. 

The conda team, from Anaconda, Inc., packages a multitude of packages and provides them to all users free of charge in their default channel.

But what if a package you are looking for is not in the default channel? One option is to use conda-forge (see below).

### Conda-forge

[Conda-forge](https://conda-forge.org/docs/user/introduction.html) is a community-led collection of recipes, build infrastructure and distributions for the conda package manager.

### Pip

Instead of conda, you can also use `pip` (the standard package installer for Python) to install packages. 

Note that we will use `pip`in this environment to install packages (and not conda). Therefore, we install pip in this environment.




<aside class="negative">
Note that you should only use either conda or pip in one environment
 </aside>

Let`s install some additional modules in our base environment.  




<!-- ------------------------ -->



## Create a virtual environment
Duration: 00:05:00

Furthermore, Anaconda's package manager `conda` makes it easy to manage multiple data environments that can be maintained and run separately without interference from each other (in so called **virtual environments**). 
 
`conda` analyses the current environment including everything currently installed, and, together with any version limitations specified (e.g. the user may wish to have TensorFlow version 2.0 or higher), works out how to install a compatible set of dependencies, and shows a warning if this cannot be done. Instead of conda, you can also use `pip` (the standard package installer for Python) to install packages. 


<aside class="negative">
Note that you should only use either conda or pip in one environment
 </aside>



[Conda environments](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands
) help manage dependencies and isolate projects. This is particularly useful when some packages require specific Python versions. Note that we will use `pip`in this environment to install packages (and not conda). Therefore, we install pip in this environment.

On Windows open the Start menu and open an Anaconda Command Prompt. On macOS or Linux open a terminal window.

We create an environment with a specific version of Python (3.9) and the **TensorFlow** package. We call the environment ``tf``:

```bash
conda create -n tf python=3.9 pip
```

When conda asks you to proceed ``(proceed ([y]/n)?``), type ``y``.


<!-- ------------------------ -->
## Activate TensorFlow environment
Duration: 00:02:00

You can activate your environment as follows:

```bash
conda activate tf
```


<!-- ------------------------ -->
## Install TensorFlow 
Duration: 00:02:00

You can install TensorFlow as follows (see [documentation](https://www.tensorflow.org/install)):

Step 1: upgrade pip:

```bash
pip install --upgrade pip
```

Step 2: install TensorFlow:

```bash
pip install tensorflow
```

<!-- ------------------------ -->
## What's next?
Duration: 0:01:00

Congratulations! You have completed the tutorial and learned how to install:

✅ TensorFlow  

If you'd like to learn more about TensorFlow, have a look at the following suggestion:

- [TensorFlow tutorials](https://www.tensorflow.org/tutorials)

If you want to switch back to your Anaconda base environment, just use:

```bash
conda deactivate
```


<img src="img/Jan.png" alt="Jan Kirenz" width="100">

Thank you for participating in this tutorial. If you found any issues along the way I'd appreciate it if you'd raise them by clicking the *Report a mistake* button at the bottom left of this site.

*Copyright: Jan Kirenz (2021), [kirenz.com](https://www.kirenz.com), [Creative Commons Attribution-NonCommercial 2.0 Generic (CC BY-NC 2.0) License](https://creativecommons.org/licenses/by-nc/2.0/)*