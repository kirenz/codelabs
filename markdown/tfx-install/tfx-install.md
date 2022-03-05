author: Jan Kirenz
summary: How to install TensorFlow and TensorFlow Extended
id: tfx-install
tags: tfx
categories: mlops
environments: Web
status: Published
feedback link: https://github.com/kirenz/codelabs/blob/master/markdown/tfx-install

# Installation of Anaconda, TensorFlow & TFX

<!-- ------------------------ -->
## Overview
Duration: 0:02:00

We start with an overview of the software we will install in this tutorial: TensorFlow & TensorFlow Extended.

<aside class="positive">
We use the data science platform Anaconda to install TFX
</aside>

- [TensorFlow](https://www.tensorflow.org/) is an end-to-end open source platform for machine learning.
- [TensorFlow Extended (TFX)](https://www.tensorflow.org/tfx) is an end-to-end platform for deploying production ML pipelines. When you’re ready to move your models to production, use TFX to create and manage a production pipeline.
- We will use the [Anaconda](https://www.anaconda.com/) open source data science platform to install TensorFlow and TensorFlow Extended. 

<!-- ------------------------ -->
## Prerequisites

Duration: 00:02:00

<img src="img/anaconda-logo.png" alt="Anaconda logo" width="200">  

- To start this tutorial, you need [**Anaconda**](https://kirenz.github.io/python-basics/docs/programming-toolkit.html#anaconda). 

<!-- ------------------------ -->
## Create TensorFlow environment
Duration: 00:05:00

<img src="img/tf-logo.png" alt="TensorFlow logo" width="300">  

[Conda environments](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands
) help manage dependencies and isolate projects. This is particularly useful when some packages require specific Python versions (like TensorFlow). Note that we will use `pip`in this environment to install packages (and not conda). Therefore, we install pip in this environment.

On Windows open the Start menu and open an Anaconda Command Prompt. On macOS or Linux open a terminal window.

We create an environment with a specific version of Python (3.8). We call the environment ``tf``:

```bash
conda create -n tf python=3.8 pip
```

When conda asks you to proceed ``(proceed ([y]/n)?``), type ``y``.


<!-- ------------------------ -->
## Install TensorFlow and TFX
Duration: 00:03:00

<img src="img/tfx-logo.png" alt="TensorFlow Extended logo" width="300">  

First of all, you have to activate the `tf` environment:

```bash
conda activate tf
```

Upgrade pip:

```bash
pip install --upgrade pip
```

Now we have to use `pip` (pip is the package installer for Python) to install TFX. [This table](https://pypi.org/project/tfx/) describes how the tfx package versions are compatible with its major dependency PyPI packages. 

```bash
pip install tfx
```

TensorFlow is already included in tfx.

Install one additional module:

```bash
pip install tensorflow-datasets
```

<!-- ------------------------ -->
## What's next?
Duration: 0:01:00

Congratulations! You have completed the tutorial and learned how to install:

✅ TensorFlow Extended  

If you'd like to learn more about TensorFlow Extended, have a look at the following suggestion:

- 💻[Build your first TFX pipeline](https://kirenz.github.io/codelabs/codelabs/tfx-pipeline)

If you want to switch back to your Anaconda base environment, just use:

```bash
conda deactivate
```

<img src="img/Jan.png" alt="Jan Kirenz" width="100">

Thank you for participating in this tutorial. If you found any issues along the way I'd appreciate it if you'd raise them by clicking the *Report a mistake* button at the bottom left of this site.

*Copyright: Jan Kirenz (2021), [kirenz.com](https://www.kirenz.com), [Creative Commons Attribution-NonCommercial 2.0 Generic (CC BY-NC 2.0) License](https://creativecommons.org/licenses/by-nc/2.0/)*
