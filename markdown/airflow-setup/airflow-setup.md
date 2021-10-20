author: Jan Kirenz
summary:
id: airflow-setup
tags:
categories:
environments: Web
status: Published
feedback link: https://github.com/kirenz/codelabs/blob/master/markdown/airflow-setup


# Airflow installation tutorial

<!-- ------------------------ -->
## Overview

Duration: 0:01:00

### What we cover

In this tutorial we are going to install [Apache Airflow](https://airflow.apache.org/) on your system.

<img src="img/logo.png" alt="Apache Airflow logo" width="200">

- Airflow is a open source platform to programmatically author, schedule and monitor workflows.

- Airflow pipelines are defined in Python, allowing for dynamic pipeline generation. This allows for writing code that instantiates pipelines dynamically.

- Anyone with Python knowledge can deploy a workflow with Airflow. Apache Airflow does not limit the scope of your pipelines; you can use it to build ML models, transfer data, manage your infrastructure, and more.

<aside class="positive">
Monitor, schedule and manage your workflows via a robust and modern web application. 
</aside>

<!-- ------------------------ -->
## Prerequisites

Duration: 0:07:00

To start this tutorial, you need Anaconda. If you don't already have Anaconda, go to [anaconda.com](https://www.anaconda.com/products/individual) and choose the appropriate `Graphical Installer` for your system (Windows, MacOS or Linux). Install the software on your system:

- [Installing on macOS](https://docs.continuum.io/anaconda/install/mac-os/)
- [Installing on Windows](https://docs.continuum.io/anaconda/install/windows/)
- [https://docs.continuum.io/anaconda/install/linux/](https://docs.continuum.io/anaconda/install/linux/) 

Here some tips if you have problems installing Anaconda: [troubleshooting](https://docs.anaconda.com/anaconda/user-guide/troubleshooting/#anaconda-installer-download-problems).

<!-- ------------------------ -->
## Create Virtual Environment

Duration: 0:05:00

[Conda environments](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands) help manage dependencies and isolate projects. This is particularly useful when some packages require specific Python versions.

On Windows open the Start menu and open an Anaconda Command Prompt. On macOS or Linux open a terminal window.

We create an environment with a specific version of Python (3.9). We call the environment ``airflow``:

```bash
conda create -n airflow python=3.9
```

When conda asks you to proceed ``(proceed ([y]/n)?``), type ``y``.


<!-- ------------------------ -->
## Installation of modules
Duration: 00:05:00

To install Airflow, we simply follow the [ installation tutorial](https://airflow.apache.org/docs/apache-airflow/stable/start/local.html) provided by Apache Airflow. Note that we use [**pip**](https://pip.pypa.io/en/stable/) (pip is the standard package installer for Python) to install Airflow in our environment. When pip asks you to proceed ``(proceed ([y]/n)?``), simply type ``y``. 

(1) First, you need to activate your environment as follows:

```bash
conda activate airflow
```

(2) Airflow needs `virualenv` so we install it first:

```bash
pip install virtualenv
```

(3) Next, Airflow needs a home. `your-home-directory/airflow` is the default, but you can put it somewhere else if you prefer (optional). 

*Here is the command for **Mac** and **Linux**:* 

```bash
export AIRFLOW_HOME=~/airflow
```

*If you use **Windows**, either provide the full path:*

```bash
SET AIRFLOW_HOME=C:\Users\<YourUserName>\airflow
```

*or (alternatively to the full path) use this approach*

```ba
sh
SET AIRFLOW_HOME=%USERPROFILE%\airflow
```

(4) Install Airflow with the following constraints file. We use Airflow Version "2.2.0" and Python "3.9.": 

```bash
pip install "apache-airflow==2.2.0" --constraint "https://raw.githubusercontent.com/apache/airflow/constraints-2.2.0/constraints-3.9.txt"
```

(5) Since we will be using PostgreSQL, we need to install the [postgres provider package](https://airflow.apache.org/docs/apache-airflow-providers-postgres/stable/index.html):

```bash
pip install apache-airflow-providers-postgres
```

(6) The Standalone command will initialise the database, make a user, and start all components for you.

```bash
airflow standalone
```

*If you should get the error message "AttributeError: 'NoneType' object has no attribute 'is_alive'" stop the process with `Ctrl` + `c` and use the command `airflow standalone` one more time.

(7) In the terminal output: Look for the provided `username` and `password`

(8) Visit this site in your browser: [http://0.0.0.0:8080](http://0.0.0.0:8080) and provide `username` and `password`.

(9) Enable the example_bash_operator dag in the home page and start experimenting with Airflow.

<!-- ------------------------ -->
## What's next?

Duration: 0:02:00

Congratulations! You have completed the tutorial and learned how to:

✅ Install Apache Airflow  
✅ Start Apache Airflow  

Next, you may want to proceed with this tutorial to build your first DAG:

- [First Airflow DAG](https://airflow.apache.org/docs/apache-airflow/stable/tutorial.html#)


<img src="img/Jan.png" alt="Jan Kirenz" width="100">

Thank you for participating in this tutorial. If you found any issues along the way I'd appreciate it if you'd raise them by clicking the "Report a mistake" button at the bottom left of this site.

*Copyright: Jan Kirenz (2021) | [kirenz.com](https://www.kirenz.com) | [CC BY-NC 2.0 License](https://creativecommons.org/licenses/by-nc/2.0/)*