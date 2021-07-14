author: Jan Kirenz
summary: How to install Anaconda and create a virtual environment for TensorFlow
id: anaconda-install
tags:
categories: data-science
environments: Web
status: Published
feedback link: https://github.com/kirenz/codelabs/blob/master/markdown/anaconda-install

# Installation of Anaconda and TensorFlow

<!-- ------------------------ -->
## Overview
Duration: 0:02:00

<img src="img/anaconda-logo.png" alt="Anaconda logo" width="200">  

In this tutorial, you'll learn how to install the [Anaconda](https://www.anaconda.com/) open source data science platform. Anaconda's package manager *Conda* makes it easy to manage multiple data environments that can be maintained and run separately without interference from each other.

Furthermore, we install [TensorFlow](https://www.tensorflow.org/), an end-to-end open source platform for machine learning.

<aside class="positive">
Anaconda is one of the most popular platforms for data science
 </aside>

<!-- ------------------------ -->
## Prerequisites

Duration: 0:02:00

To complete this tutorial, you should be aware of pathing differences between macOS, Windows and Linux:

- macOS: ``/Users/username/...``
- Windows: ``C:/Users/username/...``
- Linux: ``/home/username/...``

<aside class="negative">
Note that I used macOS to create this tutorial and therefore my code examples follow the path logic of macOS.  
</aside>


<!-- ------------------------ -->
## Install Anaconda individual
Duration: 00:10:00

Go to [anaconda.com](https://www.anaconda.com/products/individual) and choose the appropriate `Graphical Installer` for your system (Windows, MacOS or Linux). Install the software on your system:

- [Installing on macOS](https://docs.continuum.io/anaconda/install/mac-os/)
- [Installing on Windows](https://docs.continuum.io/anaconda/install/windows/)
- [https://docs.continuum.io/anaconda/install/linux/](https://docs.continuum.io/anaconda/install/linux/) 

Here some tips if you have problems installing Anaconda: [troubleshooting](https://docs.anaconda.com/anaconda/user-guide/troubleshooting/#anaconda-installer-download-problems).

<!-- ------------------------ -->
## Create a virtual environment
Duration: 00:05:00

[Conda environments](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands
) help manage dependencies and isolate projects. This is particularly useful when some packages require specific Python versions (like TensorFlow).

On Windows open the Start menu and open an Anaconda Command Prompt. On macOS or Linux open a terminal window.

We create an environment with a specific version of Python (3.8) and the **tensorflow** package. We call the environment ``tf``:

```bash
conda create -n tf python=3.8 tensorflow
```

When conda asks you to proceed ``(proceed ([y]/n)?``), type ``y``.


<!-- ------------------------ -->
## Activate TensorFlow environment
Duration: 00:02:00

You can activate your environment as follows:

```bash
conda activate tf
```

And deactivate it with:

```bash
conda deactivate
```

<!-- ------------------------ -->
## What's next?
Duration: 0:01:00

Congratulations! You have completed the tutorial and learned how to install:

✅ Anaconda  
✅ TensorFlow  

If you'd like to learn more about TensorFlow, have a look at the following suggestion:

- [TensorFlow tutorials](https://www.tensorflow.org/tutorials)

<img src="img/Jan.png" alt="Jan Kirenz" width="100">

Thank you for participating in this tutorial. If you found any issues along the way I'd appreciate it if you'd raise them by clicking the *Report a mistake* button at the bottom left of this site.

*Copyright: Jan Kirenz (2021), [kirenz.com](https://www.kirenz.com), [Creative Commons Attribution-NonCommercial 2.0 Generic (CC BY-NC 2.0) License](https://creativecommons.org/licenses/by-nc/2.0/)*
