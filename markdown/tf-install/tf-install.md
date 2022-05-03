author: Jan Kirenz
summary:
id: tf-install
tags:
categories:
environments: Web
status: Published
feedback link: https://github.com/kirenz/codelabs/blob/master/markdown/tf-install

# Install TensorFlow


## Overview
Duration: 0:01:00

In this tutorial, we will install [TensorFlow](https://www.tensorflow.org/), which is an end-to-end open source platform for machine learning.

Important note on **Apple Metal (ARM64)**: 

- This tutorial works fine for Apple Metal. However, if you want to accelerate machine learning on Apple ARM machines, you need to follow [these instructions](https://developer.apple.com/metal/tensorflow-plugin/) from Apple. Start the instructions at "arm64: Apple Silicon". If you choose this option, you can skip the following steps and jump right to step 5: "Install additional modules".

 
<!-- ------------------------ -->
## Prerequisites

Duration: 00:01:00

<img src="img/anaconda-logo.png" alt="Anaconda logo" width="200">  

- To start this tutorial, you need [Anaconda](https://kirenz.github.io/python-basics/docs/programming-toolkit.html#anaconda). 

<!-- ------------------------ -->
## Create TensorFlow environment
Duration: 00:02:00

<img src="img/tf-logo.png" alt="TensorFlow logo" width="300">  

[Conda environments](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands
) help manage dependencies and isolate projects. This is particularly useful when some packages require specific Python versions (like TensorFlow).

On Windows open the Start menu and open an Anaconda Command Prompt. On macOS or Linux open a terminal window.

We create an environment with a specific version of Python (3.9). We call the environment ``tf``:

```bash
conda create -n tf python=3.9
```

When conda asks you to proceed ``(proceed ([y]/n)?``), type ``y``.


<!-- ------------------------ -->
## Install TensorFlow
Duration: 00:02:00

First of all, you have to activate the `tf` environment:

```bash
conda activate tf
```

Installation:


```bash
conda install -c conda-forge tensorflow 
```

<!-- ------------------------ -->
## Install additional modules
Duration: 00:01:00

We install some additional modules:

```bash
conda install pandas 
```

```bash
conda install seaborn 
```

```bash
conda install jupyter 
```

<!-- ------------------------ -->
## What's next?
Duration: 0:01:00

Congratulations! You have completed the tutorial and learned how to install:

✅ TensorFlow  

If you'd like to learn more about Deep Learning with TensorFlow, have a look at the following suggestion:

- [Deep Learning in Python with TensorFlow and Keras](https://kirenz.github.io/deep-learning/docs/intro.html)

If you want to switch back to your Anaconda base environment, just use:

```bash
conda deactivate
```

<img src="img/Jan.png" alt="Jan Kirenz" width="100">

Thank you for participating in this tutorial. If you found any issues along the way I'd appreciate it if you'd raise them by clicking the *Report a mistake* button at the bottom left of this site.

*Copyright: Jan Kirenz (2021), [kirenz.com](https://www.kirenz.com), [Creative Commons Attribution-NonCommercial 2.0 Generic (CC BY-NC 2.0) License](https://creativecommons.org/licenses/by-nc/2.0/)*