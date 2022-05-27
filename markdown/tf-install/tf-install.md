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

 
<!-- ------------------------ -->
## Prerequisites

Duration: 00:01:00

To start this tutorial, I recommend to use [Miniforge](https://github.com/conda-forge/miniforge) (a community-led alternative to Anaconda): 

- [Miniforge3 installation tutorial](https://kirenz.github.io/codelabs/codelabs/miniforge-setup/#0).

<!-- ------------------------ -->
## Create TensorFlow environment
Duration: 00:02:00

<img src="img/tf-logo.png" alt="TensorFlow logo" width="300">  

- On Windows open the Start menu and open an Anaconda Command Prompt. 
- On macOS or Linux open a terminal window.

We create a new environment and call it ``tf``. We also install TensorFlow and additional packages in this new environment:


```bash
conda create -n tf tensorflow matplotlib pandas jupyter pydot
```

When conda asks you to proceed ``(proceed ([y]/n)?``), type ``y``.

We also need to install [graphviz](https://graphviz.gitlab.io/download/).



<!--
## Install TensorFlow
Duration: 00:05:00


First of all, you have to activate the `tf` environment:

```bash
conda activate tf
```


Upgrade pip:

```bash
pip install --upgrade pip
```

- Install TensorFlow

```bash
pip install tensorflow
```


We install some additional modules:

```bash
pip install pandas 
```

```bash
pip install seaborn 
```

```bash
pip install jupyter 
```

```bash
pip install pydot 
```
We also need to install graphviz: see instructions at https://graphviz.gitlab.io/download/



## Install TensorFlow on Mac Intel
Duration: 00:05:00


Starting with certain models introduced in late 2020, Apple began the transition from Intel processors to Apple silicon in Mac computers. Here is a list with [Mac computers with Apple silicon](https://support.apple.com/en-us/HT211814).  

Follow these instructions if you have an Intel processor:

Upgrade pip:

```bash
pip install --upgrade pip
```

- Install TensorFlow

```bash
pip install tensorflow
```


We install some additional modules:

```bash
pip install pandas 
```

```bash
pip install seaborn 
```

```bash
pip install jupyter 
```

```bash
pip install pydot 
```

We also need to install graphviz: see instructions at https://graphviz.gitlab.io/download/


## Install TensorFlow on Apple silicon
Duration: 00:05:00


Starting with certain models introduced in late 2020, Apple began the transition from Intel processors to Apple silicon in Mac computers. Here is a list with [Mac computers with Apple silicon](https://support.apple.com/en-us/HT211814).  

Follow these instructions if you have an Apple processor:

We install TensorFlow and the tensorflow-metal PluggableDevice to accelerate training with Metal on Mac GPUs. 

We mainly follow [these instructions](https://developer.apple.com/metal/tensorflow-plugin/) provided by Apple:

- Install the Tensorflow dependencies:

```bash
conda install -c apple tensorflow-deps
```

- Install base TensorFlow

```
pip install tensorflow-macos
```

- Install tensorflow-metal plugin:

```bash
pip install tensorflow-metal
```

We install some additional modules:

```bash
conda install pandas 
```

```bash
conda install jupyter 
```

```bash
conda install pydot 
```

We also need to install graphviz: see instructions at https://graphviz.gitlab.io/download/

-->

<!-- ------------------------ -->
## What's next?
Duration: 0:01:00

Congratulations! You have completed the tutorial and learned how to install:

✅ TensorFlow   

If you'd like to learn more about Deep Learning with TensorFlow, have a look at the following suggestion:

- [Deep Learning in Python with TensorFlow and Keras](https://kirenz.github.io/deep-learning/docs/intro.html)

If you want to switch back to your base environment, just use:

```bash
conda deactivate
```

<img src="img/Jan.png" alt="Jan Kirenz" width="100">

Thank you for participating in this tutorial. If you found any issues along the way I'd appreciate it if you'd raise them by clicking the *Report a mistake* button at the bottom left of this site.

*Jan Kirenz (2022) | [kirenz.com](https://www.kirenz.com) | Made with [Codelabs](https://github.com/googlecodelabs/tools)*
