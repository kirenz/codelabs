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

Anaconda is a software-company which offers open-source-tools to perform Python/R data science and machine learning on a single machine. 

Their popular open-source *Anaconda Individual Edition* distribution includes Python, the package manager *conda* to install and manage Python modules as well as over 250 preinstalled modules. Since we usually only use a small fraction of these modules, we install the lightweight version of Anaconda, called *Miniconda*.

<aside class="positive">
Miniconda is a data science toolkit which includes Python and a package manager
 </aside>

Miniconda is a free minimal installer for conda. It is a small, bootstrap version of Anaconda that includes only conda, Python, the packages they depend on, and a small number of other useful packages.


<!-- ------------------------ -->
## Prerequisites

Duration: 0:05:00

To avoid compatibility problems with older versions of Anaconda, I recommend to uninstall Anaconda first. If you don't already have Anaconda installed on your system, you can skip this section.

### Windows

1. Open the file explorer.
2. Delete your environment (anaconda3\envs) and package (anaconda3\pkgs) folders in your user folder.
3. Open Add or remove programs and uninstall your Anaconda installation.


### macOS


Open your terminal ([learn how to open your terminal](https://support.apple.com/guide/terminal/open-or-quit-terminal-apd5265185d-f365-44cb-8b09-71a064a42125/mac))


You can remove your entire Anaconda directory with `rm -rf`. If you are not sure where anaconda is installed, simply enter all commands:

First try the opt folder:

```bash
rm -rf ~/opt/anaconda3
```

Then this location:

```bash
rm -rf anaconda3
```

Finally, enter:

```bash
rm -rf ~/anaconda3
```


<!-- ------------------------ -->
## Installation 

Duration: 00:05:00


### Windows

- Go to the site [latest Miniconda installer](https://docs.conda.io/en/latest/miniconda.html#latest-miniconda-installer-links): 

- Choose the appropriate version (usually 64-bit) and install the software.

### Mac

- Go to the site [latest Miniconda installer](https://docs.conda.io/en/latest/miniconda.html#latest-miniconda-installer-links): 

- Depending on your system, select the Intel or M1 version and choose the pkg-file.

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