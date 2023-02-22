author: Jan Kirenz
summary: Miniconda Installation
id: miniconda
tags:
categories: tools
environments: Web
status: Published
feedback link: https://github.com/kirenz/codelabs/blob/master/markdown/miniconda

# Miniconda installation

## Overview
Duration: 0:02:00

<img src="img/anaconda-logo.png" alt="Anaconda logo" width="200">  

Anaconda is a software-company which offers various tools to perform data science tasks on a single machine. Their popular open-source *Anaconda Individual Edition* distribution includes 

- Python and R, 
- the package manager *conda* to install packages 
- as well as over 250 preinstalled packages. 

Note that Anaconda is quite large -the base install requires around 2GB- and we usually only use a small fraction of the preinstalled packages. Therefore, we will install the lightweight version of Anaconda, called *Miniconda*.

<aside class="positive">
Miniconda is a data science toolkit which includes Python and the package manager conda
</aside>

Miniconda is a free minimal installer for conda. It is a small, bootstrap version of Anaconda that includes only conda, Python, the packages they depend on, and a small number of other useful packages.


## Prerequisites

Duration: 0:05:00

- You should be familiar with the shell. If not, take a look at this tutorial.

- If you have an old Anaconda version installed on your system, you may uninstall it first to avoid compatibility problems.


### Uninstall Anaconda

You can skip this section if you don't already have Anaconda installed on your machine.


#### Windows

1. Open the file explorer.
2. Delete your environment (anaconda3\envs) and package (anaconda3\pkgs) folders in your user folder.
3. Open Add or remove programs and uninstall your Anaconda installation.


#### macOS

Open your terminal ([learn how to open your terminal](https://support.apple.com/guide/terminal/open-or-quit-terminal-apd5265185d-f365-44cb-8b09-71a064a42125/mac))

Anaconda is usually located in your home directory inside a folder called "opt". You can remove your entire Anaconda directory by typing the following command in your terminal: 


```bash
rm -rf ~/opt/anaconda3
```

<!--
Then this location:

```bash
rm -rf anaconda3
```

Finally, enter:

```bash
rm -rf ~/anaconda3
```
-->


## Installation 

Duration: 00:05:00


### Windows

- Go to the site [latest Miniconda installer links](https://docs.conda.io/en/latest/miniconda.html#latest-miniconda-installer-links): 

- Choose the appropriate Windows version (usually 64-bit) and download the file

- Go to your Downloads folder, right-click on the file and choose "as Administrator"

- Install the software

- During the installation process, choose: "Just Me"


### MacOS with Intel 

- Download the `Graphical Installer` and install the software: [Miniconda3 macOS Intel x86 64-bit pkg](https://repo.anaconda.com/miniconda/Miniconda3-py310_23.1.0-1-MacOSX-x86_64.pkg)

- During the installation process, choose: "Just Me"

### MacOS with M1

- Download the software: [Miniconda3 macOS Apple M1 ARM 64-bit bash](https://repo.anaconda.com/miniconda/Miniconda3-py310_23.1.0-1-MacOSX-arm64.sh)

- Open a terminal and `cd` into the directory where the file is located.

- In your terminal:

```bash
sh ./Miniconda3-py310_23.1.0-1-MacOSX-arm64.sh
```
- Scroll to the bottom and type `yes`to install the software.

- If asked, agree to initialize Miniconda



## Miniconda Setup 
Duration: 00:05:00


During the installation process, Miniconda created the so called `base` environment. Let`s take a look at this environment:

- On *Windows* open the Start menu and open "Anaconda Powershell Prompt" or "Anaconda Prompt". 
- On *macOS* or *Linux* open a terminal window.


<!--
First we initialize conda for shell interaction. Type the following command in your shell and press enter:


```bash
conda init
```
-->

Usually, the `base` environment is already activated (and you can see the word `base` in your shell). 

<!--
If not, type: 


```bash
conda activate base
```

-->


Update your version of conda by running:


```bash
conda update -n base -c defaults conda

```

When conda asks you to proceed ``(proceed ([y]/n)?``), type ``y``.



## From where to install packages
Duration: 00:05:00

The conda team, from Anaconda, Inc., provides various packages to all users free of charge in their defaults channel. However, to get more up-to-date modules, it's better to use the popular community-led alternative conda-forge. 

Type this in your shell to add the conda-forge channel to conda:

```base
conda config --add channels conda-forge
```

<!--
Warning: 'conda-forge' already in 'channels' list, moving to the top
-->

Then make conda-forge the priority channel:

```bash
conda config --set channel_priority strict
```

This ensures that conda will always try to install packages from the conda-forge channel first instead of other channels.   

In the next step, we install some Python module with conda.


## What is a virtual environment?
Duration: 00:05:00

Anaconda's package manager `conda` makes it easy to manage multiple data environments that can be maintained and run separately without interference from each other in so called *virtual environments*. A virtual environment in Python is a separate and isolated environment where you can install packages and dependencies without affecting other Python installations or the system's environment.

Installing Python modules in a virtual environment is recommended for several reasons:

- Isolation: By using virtual environments, you can isolate your project's dependencies from the system-wide Python installation. This means that you can have different versions of the same library for different projects without causing conflicts.

- Reproducibility: By specifying dependencies in a virtual environment, you can ensure that the project will always run with the same versions of libraries, regardless of system-wide installations or updates.

- Compatibility: Different projects may have different requirements, and installing modules in a virtual environment prevents compatibility issues between projects.

- Easy Management: Virtual environments make it easier to manage dependencies, as you can easily install, update or remove them without affecting other projects or the system.



## Install packages in a virtual environment
Duration: 00:05:00

If you install a new module with `conda`, it analyses the current environment including everything currently installed, and, together with any version limitations specified (e.g. the user may wish to have a package in version 2.0 or higher), works out how to install a compatible set of dependencies, and shows a warning if this cannot be done. 

You can take a look at all available packages on this website: <https://anaconda.org/>. 


- Let's create a new environment:
  - Call the new environment `ds` (short for data science) 
  - Use Python 3.10
  - Install some packages (pandas etc.)

```bash
conda create --name ds python=3.10 pandas scikit-learn altair vega vega_datasets
```

When conda asks you to proceed ``(proceed ([y]/n)?``), type ``y``.


- You can activate the new environment as follows:

```bash
conda activate ds
```

You are now inside your virtual environment ds (you should notice that base is replaced by ds in your shell)

- Take a look at all the modules in your `ds` environment:

```bash
conda list
```

You should see a list of modules with their name, version, build (more detaild information about the package) and channel (from which the packages were installed).

- If you want to switch back to your `base` environment simply type:

```bash
conda deactivate
```



## Update Anaconda environments
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

- Let's make sure that you use the machine learning module `scikit-learn` in version 1.2.1 or higher:

```terminal
conda list scikit-learn
```

- It's also possible to install a specific version of a module:


```bash
conda install -c anaconda scikit-learn=1.2.1
```


## What's next?
Duration: 0:01:00

Congratulations! You have completed the tutorial and learned how to:

✅ install Miniconda  

✅ use conda-forge

✅ create a virtual environment 

✅ install modules

✅ update modules

<img src="img/Jan.png" alt="Jan Kirenz" width="100">

Thank you for participating in this tutorial. If you found any issues along the way I'd appreciate it if you'd raise them by clicking the *Report a mistake* button at the bottom left of this site.

*Copyright: Jan Kirenz (2023), [kirenz.com](https://www.kirenz.com), [Creative Commons Attribution-NonCommercial 2.0 Generic (CC BY-NC 2.0) License](https://creativecommons.org/licenses/by-nc/2.0/)*