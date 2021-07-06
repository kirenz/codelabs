summary: How to install TensorFlow and TensorFlow Extended with Anaconda
id: install-tfx
categories: mlops
tags: tfx
status: Published
authors: Jan Kirenz
Feedback Link: https://www.kirenz.com

# Installation of Anaconda, TensorFlow & TFX

<!-- ------------------------ -->
## Overview
Duration: 0:01:00

### What we cover
We start with an overview of the software we will install in this tutorial: Anaconda, TensorFlow & TensorFlow Extended.

<aside class="positive">
We use the data science platform Anaconda to install TFX
</aside>

<img src="assets/tf-logo.png" alt="TensorFlow logo" width="200">

- [TensorFlow](https://www.tensorflow.org/) is an end-to-end open source platform for machine learning.

<img src="assets/tfx-logo.png" alt="TensorFlow Extended logo" width="200">

- [TensorFlow Extended (TFX)](https://www.tensorflow.org/tfx) is a Google-production-scale machine learning platform based on TensorFlow.

<img src="assets/anaconda-logo.png" alt="Anaconda logo" width="200">

- We will use the [Anaconda](https://www.anaconda.com/) open source data science platform to install TensorFlow and TensorFlow Extended. Anaconda's package manager *Conda* makes it very easy to manage multiple data environments that can be maintained and run separately without interference from each other.

<!-- ------------------------ -->
## Install Anaconda individual
Duration: 00:05:00

Go to [anaconda.com](https://www.anaconda.com/products/individual) and choose the appropriate `Graphical Installer` for your system (Windows, MacOS or Linux).

![https://www.anaconda.com/products/individual](https://www.anaconda.com/products/individual "Anaconda")

Install the software on your system.

<aside class="negative">
Here are some tips if you have problems installing Anaconda: [troubleshooting](https://docs.anaconda.com/anaconda/user-guide/troubleshooting/#anaconda-installer-download-problems)
</aside>

<!-- ------------------------ -->
## Create TensorFlow environment
Duration: 00:05:00

[Conda environments](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands
) help manage dependencies and isolate projects. This is particularly useful when some packages require specific Python versions (like TensorFlow).

On Windows open the Start menu and open an Anaconda Command Prompt. On macOS or Linux open a terminal window.

We create an environment with a specific version of Python (3.8) and the **tensorflow** package. We call the environment ``tf``:

```bash
conda create -n tf python=3.8 tensorflow
```

When conda asks you to proceed ``(proceed ([y]/n)?``), type ``y``.

This creates the ``tf`` environment in ``/envs/``.

<!-- ------------------------ -->
## Activate TensorFlow environment
Duration: 00:01:00

You can activate your environment as follows:

```bash
conda activate tf
```

And deactivate it with:

```bash
conda deactivate
```

<!-- ------------------------ -->
## Install TensorFlow Extended
Duration: 00:02:00

First of all, you have to activate the `tf` environment:

```bash
conda activate tf
```

Now we have to use `pip` (pip is the package installer for Python) to install TFX in our `tf` environment:

```bash
pip install tfx
```

<!-- ------------------------ -->
## Gongratulations!
Duration: 00:01:00

I hope this helps you get up and running quickly with TensorFlow and TensorFlow Extended. Happy coding!

### What's next?

If you'd like to learn more about TensorFlow Extended, have a look at the following suggestions.

Tutorial: Build your first TFX pipeline.