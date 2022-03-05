author: Jan Kirenz
summary: How to use Anaconda to create a virtual environment for TensorFlow
id: anaconda-install
tags:
categories: data-science
environments: Web
status: Published
feedback link: https://github.com/kirenz/codelabs/blob/master/markdown/anaconda-install

# Installation of TensorFlow

<!-- ------------------------ -->
## Overview
Duration: 0:02:00

<img src="img/anaconda-logo.png" alt="Anaconda logo" width="200">  

In this tutorial, you'll learn how to install [TensorFlow](https://www.tensorflow.org/), an end-to-end open source platform for machine learning.

<aside class="positive">
Anaconda is one of the most popular platforms for data science
 </aside>

<!-- ------------------------ -->
## Prerequisites

Duration: 0:02:00

To start this tutorial, you need [**Anaconda**](https://kirenz.github.io/python-basics/docs/programming-toolkit.html#anaconda) and you should be familiar with the **command line interface** (other names for the command line are: cmd, CLI, prompt, console or terminal). If you aren't familiar with the terminal, read this [introduction to the command-line interface](https://tutorial.djangogirls.org/en/intro_to_command_line/).


<aside class="positive">
The terminal is a text-based application for viewing, handling, and manipulating files on your computer
</aside>  

Please note that there are pathing differences between macOS, Windows and Linux:

- macOS: ``/Users/username/...``
- Windows: ``C:/Users/username/...``
- Linux: ``/home/username/...``

<aside class="negative">
I used macOS to create this tutorial and therefore my code examples follow the path logic of macOS.  
</aside>


<!-- ------------------------ -->
## Create a virtual environment
Duration: 00:05:00

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