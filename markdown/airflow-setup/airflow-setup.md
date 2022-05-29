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

In this tutorial we are going to install [Apache Airflow](https://airflow.apache.org/docs/apache-airflow/stable/start/local.html) on your system. Furthermore, we will implement a basic pipeline. 


<img src="img/logo.png" alt="Apache Airflow logo" width="200">

- Airflow is a open source platform to programmatically author, schedule and monitor workflows.

- Airflow pipelines are defined in Python, allowing for dynamic pipeline generation. This allows for writing code that instantiates pipelines dynamically.

- Anyone with Python knowledge can deploy a workflow with Airflow. Apache Airflow does not limit the scope of your pipelines; you can use it to build ML models, transfer data, manage your infrastructure, and more.

<aside class="positive">
Monitor, schedule and manage your workflows via a robust and modern web application. 
</aside>

<!-- ------------------------ -->
## Prerequisites for Windows

Duration: 0:05:00

### Windows Subsystem for Linux 2 (WSL2)

If you have a Windows machine, you need Windows Subsystem for Linux 2 (WSL2). Here, we follow the instructions provided by Microsoft's Craig Loewen to set up WSL2 (see [this post](https://devblogs.microsoft.com/commandline/install-wsl-with-a-single-command-now-available-in-windows-10-version-2004-and-higher/) to learn more).

- Open a command prompt window with admin privileges and run 

```Bash
wsl.exe --install
```

This will automatically install the open source operating system Ubuntu and the latest WSL Linux kernel version onto your machine. 

- When it’s completed, restart your machine. 

Your distribution will start after you boot up again, completing the installation.

- You can launch the Linux terminal with one of the following options:  
  - (1) Install the Windows Terminal from the [Microsoft Store](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=de-de&gl=DE) (recommend option)
  - (2) Use the Ubuntu icon or
  - (3) enter `wsl` or `bash` in Powershell.

*You can use `wsl --update` to manually update your WSL Linux kernel, and you can use `wsl --update rollback` to rollback to a previous WSL Linux kernel version. To learn more about WSL, take a look at this post form Microsoft: ["What is the Windows Subsystem for Linux?"](https://docs.microsoft.com/en-us/windows/wsl/about#what-is-wsl-2).*



### Install Miniforge

Next, we install Miniforge (an alternative to Anaconda and Miniconda) on your Linux system.

- Launch the Linux terminal with one of the following options:  
  - (1) Install the Windows Terminal from the [Microsoft Store](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=de-de&gl=DE) (recommend option)
  - (2) Use the Ubuntu icon or
  - (3) enter `wsl` or `bash` in Powershell.


Next, we install Miniforge with `wget` (we use `wget` to download directly from the terminal).

- Get the appropriate Linux version of Miniforge3 for your machine (see [this overview](https://github.com/conda-forge/miniforge/releases); usually `x86_64 (amd64)`). Here is the example for x86_64 (amd64):

```Bash
wget https://github.com/conda-forge/miniforge/releases/download/4.12.0-0/Miniforge3-4.12.0-0-Linux-x86_64.sh
```

- Now install Miniforge from the installer script: 

```Bash
sh Miniforge3-4.12.0-0-Linux-x86_64.sh
```


<!-- ------------------------ -->
## Prerequisites for Apple

Duration: 0:05:00


### MiniForge

To start this tutorial, I recommend to use [Miniforge](https://github.com/conda-forge/miniforge) (a community-led alternative to Anaconda): 

- [Miniforge3 installation tutorial](https://kirenz.github.io/codelabs/codelabs/miniforge-setup/#0).

<!-- ------------------------ -->
## Create Virtual Environment

Duration: 0:02:00

On Windows open your Linux terminal. On macOS or Linux open a terminal window.

We create an environment with a specific version of Python and install pip. We call the environment ``airflow`` (if you don't have Python 3.10 you can replace it with 3.9 or 3.8):

```bash
conda create -n airflow python=3.10 pip
```

When conda asks you to proceed ``(proceed ([y]/n)?``), type ``y``.


<!-- ------------------------ -->
## Installation
Duration: 00:10:00

To install Airflow, we mainly follow the [ installation tutorial](https://airflow.apache.org/docs/apache-airflow/stable/start/local.html) provided by Apache Airflow. Note that we use [**pip**](https://pip.pypa.io/en/stable/) to install Airflow an some additional modules in our environment. When pip asks you to proceed ``(proceed ([y]/n)?``), simply type ``y``. 

- First, you need to activate your environment as follows:

```bash
conda activate airflow
```

- Then upgrade pip:

```bash
pip install --upgrade pip
```

- Airflow needs `virualenv` so we install it:

```bash
pip install virtualenv
```

- Next, Airflow needs a home. `your-home-directory/airflow` is the default:

*Here is the command for Mac and Linux:* 

```bash
export AIRFLOW_HOME=~/airflow
```

- Install Airflow with the following constraints file. We use Airflow Version "2.3.1" and Python "3.10."(if you don't have Python 3.10 you can replace it with 3.9 or 3.8): 

```bash
pip install "apache-airflow==2.3.1" --constraint "https://raw.githubusercontent.com/apache/airflow/constraints-2.3.1/constraints-3.10.txt"
```

- Since we will be using pandas and scikit-learn in some of our examples, we install the modules with pip:


```bash
pip install pandas
```

```bash
pip install -U scikit-learn
```

<!--
- Since we will be using PostgreSQL, we need to install the [postgres provider package](https://airflow.apache.org/docs/apache-airflow-providers-postgres/stable/index.html):

```bash
pip install apache-airflow-providers-postgres
```


- Finally, we install one additional module:

```bash
pip install apache-airflow-providers-cncf-kubernetes
```
-->

- The following `airflow standalone` command will 
  - (1) initialise a SQLite database, 
  - (2) make a user, and 
  - (3) start all components 

<br>

```bash
airflow standalone
```
  
We only run this command once when we install Airflow. If you want to run the individual parts of Airflow manually rather than using the all-in-one standalone command, check out the instructions provided [here](https://airflow.apache.org/docs/apache-airflow/stable/start/local.html).


<aside class="negative">
If you get the error message "AttributeError: 'NoneType object has no attribute is_alive"
stop the process with Ctrl + c and use the command airflow standalone one more time.
</aside>


- In the terminal output: Look for the provided `username` and `password` and store them somewhere


- Open the Airflow UI in your browser (ideally in Chrome) [http://0.0.0.0:8080](http://0.0.0.0:8080) and provide `username` and `password`.


- The Airflow UI makes it easy to monitor and troubleshoot your data pipelines. Here's a quick overview of some of the features and visualizations you can find: [Airflow UI](https://airflow.apache.org/docs/apache-airflow/stable/ui.html#) 

- If you are done:
  1. Log out from the user menu, 
  1. Go to your terminal and stop the Airflow process with `Ctrl`+`c` (this will shut down components). 
  
  <br>
  
  Later, we will restart Airflow by using different commands. 


<!-- ------------------------ -->
## Start Airflow 

Duration: 0:02:00

In this section, we take a look at how to start Airflow:

- Start your terminal and activate your `airflow` environment if needed

```Bash
conda activate airflow
```

- Export the airflow home variable

```Bash
export AIRFLOW_HOME=~/airflow
```

- Start the Airflow webserver

```Bash
airflow webserver
```

- Open the Airflow UI in your browser (ideally in Chrome) [http://0.0.0.0:8080](http://0.0.0.0:8080) and provide your `username` and `password`.

- If you are done:
  1. Log out from the user menu, 
  1. Go to your terminal and stop the Airflow process with `Ctrl`+`c` (this will shut down all components). 


<!-- ------------------------ -->
## First pipeline

Duration: 0:05:00

Here, we mainly follow the instructions provided in this [Apache Airflow tutorial](https://airflow.apache.org/docs/apache-airflow/stable/tutorial.html#tutorial):

- First, create a new folder called `dags` in you airflow home (i.e. `~/airflow/dags`). 

- Copy [this Python script](https://github.com/kirenz/airflow/blob/main/my_airflow_dag.py) and save it as `my_airflow_dag.py` in your `~/airflow/dags` folder.

<!--
- Copy [this shell script](https://github.com/kirenz/airflow/blob/main/templated_command.sh) and save it as `templated_command.sh` in your `~/airflow/dags` folder.
-->


<aside class="negative">
The file my_airflow_dag needs to be stored in the DAGs folder referenced in your airflow.cfg. The default location for your DAGs is ~/airflow/dags.
</aside>


- Open a new terminal window and activate your `airflow` environment if needed

```Bash
conda activate airflow
```

- Export the airflow home variable

```Bash
export AIRFLOW_HOME=~/airflow
```

- Now run the following command:

```bash
python ~/airflow/dags/my_airflow_dag.py
```

If the script does not raise an exception it means that you have not done anything wrong, and that your Airflow environment is somewhat sound. 

- Now proceed to the next step.


*If you want to learn more about the content of the my_airflow-dag.py script, review [the Airflow tutorial](https://airflow.apache.org/docs/apache-airflow/stable/tutorial.html).*


<!-- ------------------------ -->

## Command Line Metadata Validation

Duration: 0:04:00


First, we use the command line to do some metadata validation. Let's run a few commands in your terminal to test your script:

- Initialize the database tables

```bash
airflow db init
```

- Print the list of active DAGs (there are many example DAGs provided by Airflow)

```bash
airflow dags list
```

- Print the list of tasks in the "my_airflow_dag"

```bash
airflow tasks list my_airflow_dag
```

- Print the hierarchy of tasks in the "my_airflow_dag" DAG

```bash
airflow tasks list my_airflow_dag --tree
```


<!-- ------------------------ -->
## Testing single tasks

Duration: 0:04:00

Let's start our tests by running one actual task instance for a specific date (independent of other tasks). 

The date specified in this context is called the "logical date" (also called execution date), which simulates the scheduler running your task or DAG for a specific date and time, even though it physically will run now (or as soon as its dependencies are met).

<aside class="positive">
The scheduler runs your task for a specific date and time, not at a specific date. 
</aside>

This is because each run of a DAG conceptually represents not a specific date and time, but an interval between two times, called a *data interval*. A DAG run's logical date is the start of its data interval.

The general command layout is as follows: 

```Bash
command subcommand dag_id task_id date
```

- Testing `task_print_date`:

```bash
airflow tasks test my_airflow_dag task_print_date 2021-05-20
```

*Take a look at the last lines in the output (ignore warnings for now)*


- Testing `task_sleep`

```bash
airflow tasks test my_airflow_dag task_sleep 2021-05-20
```

- Testing `task_templated`

```Bash
airflow tasks test my_airflow_dag task_templated 2021-05-20
```

Everything looks like it's running fine so let's run a backfill.

<!-- ------------------------ -->
## Backfill

Duration: 0:04:00

`backfill` will respect your dependencies, emit logs into files and talk to the database to record status.

 If you do have a *webserver* up, you will be able to track the progress. 
 
 `airflow webserver` will start a web server if you are interested in tracking the progress visually as your backfill progresses.


- The date range in this context is a `start_date` and optionally an `end_date`, which are used to populate the run schedule with task instances from this dag.


<!--
- Start a web server in debug mode in the background (this is optional)

```Bash
airflow webserver --debug &
```
-->

- Start your backfill on a date range
```Bash
airflow dags backfill my_airflow_dag \
    --start-date 2021-05-20 \
    --end-date 2021-06-01
```    

Let's proceed to the Airflow user interface (UI) - see next step.


Note that if you use `depends_on_past=True`, individual task instances will depend on the success of their previous task instance (that is, previous according to the logical date) In that case you may want to consider to set `wait_for_downstream=True` when using `depends_on_past=True`. While `depends_on_past=True` causes a task instance to depend on the success of its previous task_instance, `wait_for_downstream=True` will cause a task instance to also wait for all task instances immediately downstream of the previous task instance to succeed.

<!-- ------------------------ -->

## Airflow UI

Duration: 0:05:00


- If the webserver is not already running, start it now:

```Bash
airflow webserver
```

Open the Airflow web interface in your browser:

- [http://0.0.0.0:8080/home](http://0.0.0.0:8080/home)


Now start experimenting with the Airflow web interface:


- Select `my_airflow_dag` from the list of DAGs.


- Click on the icon "Graph" to display the DAG 

- Explore the other options to learn more about your DAG (see this Airflow tutorial about the [Airflow UI](https://airflow.apache.org/docs/apache-airflow/stable/ui.html))


- If you are done:
  1. Log out from the user menu, 
  1. Go to your terminal and stop the Airflow process with Ctrl+c (this will shut down all components). 

<!-- ------------------------ -->
## What's next?

Duration: 0:02:00

Congratulations! You have completed the tutorial and learned how to:

✅ Install Apache Airflow  
✅ Start Apache Airflow  
✅ Create a simple pipeline 


Next, you may want to proceed with this tutorial to build another DAG (there are more examples when you scroll down):

- [Airflow DAG example](https://airflow.apache.org/docs/apache-airflow/stable/tutorial.html)


<img src="img/Jan.png" alt="Jan Kirenz" width="100">

Thank you for participating in this tutorial. If you found any issues along the way I'd appreciate it if you'd raise them by clicking the "Report a mistake" button at the bottom left of this site.

*Jan Kirenz | [kirenz.com](https://www.kirenz.com) | [CC BY-NC 2.0 License](https://creativecommons.org/licenses/by-nc/2.0/)*