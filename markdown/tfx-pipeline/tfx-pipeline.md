author: Jan Kirenz
summary: Building a TFX pipeline locally
id: tfx-pipeline
tags: tfx, pipeline
categories: mlops
environments: Web
status: Published
feedback link: https://github.com/kirenz/codelabs/blob/master/markdown/tfx-pipeline

# Build a TFX Pipeline

<!-- ------------------------ -->
## Overview

Duration: 0:01:00

### What we cover

<img src="img/tfx-hero.svg" alt="TFX" width="200">


- Google's open-source software **TensorFlow Extended (TFX)** is an end-to-end platform for deploying production ML pipelines. When you’re ready to move your models to production, use TFX to create and manage a production pipeline.

- A **TFX pipeline** is a sequence of components that implement an ML pipeline which is specifically designed for scalable, high-performance machine learning tasks. Components are built using TFX libraries which can also be used individually.

- **TFX pipeline templates** make it easy to get started with pipeline development by providing a prebuilt set of pipeline definitions that you can customize for your use case.

In our example, we mainly follow the instructions provided by this TensorFlow tutorial: [Building a TFX Pipeline Locally](https://www.tensorflow.org/tfx/guide/build_local_pipeline?hl=en) to build a pipeline from a prebuilt template.

<aside class="positive">
You will learn how to build a TFX-pipeline from a template
</aside>


<!-- ------------------------ -->
## Prerequisites

Duration: 0:05:00

To complete this tutorial, you need the following environment:

- Code editor (e.g., [Visual Studio Code](https://code.visualstudio.com/))
- Miniforge or Anaconda
- Virtual conda environment (preferably named "tf") with:
  - TensorFlow Extended
  
<aside class="positive">
Review this <a href="https://kirenz.github.io/codelabs/codelabs/tfx-install/index.html#0" >tutorial</a>
to create the environment.
</aside>

Furthermore, you should be aware of pathing differences between macOS, Windows and Linux:

- macOS: ``/Users/username/...``
- Windows: ``C:/Users/username/...``
- Linux: ``/home/username/...``

<aside class="negative">
Note that I used macOS to create this tutorial and therfore my code examples follow the path logic of macOS.  
</aside>

<!-- ------------------------ -->
## Environment setup

Duration: 0:07:00

We first need to set up our environment and create new folders:

1. On *Windows* open the Start menu and open an Anaconda Command Prompt. On *macOS* or *Linux* open a terminal window.
  
2. Activate the virtual Anaconda environment (in my case "tf"):

```bash
conda activate tf
```

3. Create a project folder **tfx-files** with ``mkdir`` (make directory):

```bash
mkdir tfx-files
```

4. Create a sub-folder inside **tfx-files** called **output**. Therefore, we first need to change directory (``cd``) into the **tfx-files** directory:

```bash
cd your-path-to-txf-files
```

- On my machine, the command is ``cd /Users/jankirenz/tfx-files``.

5. Create the new sub-folder **output**:  

```bash
mkdir output
```


<!-- ------------------------ -->
## Pipeline template

Duration: 0:05:00

### Create a copy of the pipeline template

In the next steps, we use the [TFX command-line interface (CLI)](https://www.tensorflow.org/tfx/guide/cli) which is a part of the TFX package. All commands start with ``tfx``.

First, we use ``tfx template`` which are commands for listing and copying TFX pipeline templates.

1. List the currently available TFX pipeline templates:

```bash
tfx template list
```

2. We copy the **penguin** template to our local machine (you have to change the following code):

```bash
tfx template copy --model=penguin --pipeline_name=pipeline-tutorial \
--destination_path=your-path-to-txf-files
```

Only change the entry for destination_path:

- model: The name of the template you want to copy (we use the penguin template).
- pipeline_name: The name of the pipeline to create (we call it pipeline-tutorial).
- destination_path: The path to copy the template into (**you need to provide this information**).

<aside class="negative">
If you should have troubles finding the path, you can open your file explorer and drag the folder tfx-files into the terminal to show the path.
</aside>

- On my machine, the code is: ``tfx template copy --model=penguin --pipeline_name=pipeline-tutorial \
--destination_path=/Users/jankirenz/tfx-files``

3. A copy of the pipeline template has been created at the path you specified.

<!-- ------------------------ -->
## Explore pipeline template

Duration: 0:07:00

Explore the directories and files that were copied to your pipeline's project directory **tfx-files**:

- A **pipeline** directory with

  - **pipeline.py** - defines the pipeline, and lists which components are being used
  - **configs.py** - holds configuration details such as where the data is coming from or which orchestrator is being used

- A **data** directory

  - This typically contains a data.csv file, which is the default source for the TFX-component ExampleGen. You can change the data source in configs.py.
  
- A **models** directory with preprocessing code and model implementations

- The template copies directed acyclic graph (DAG) runners --which runs the components one by one in DAG's topological order-- for local environment and [Kubeflow](https://www.kubeflow.org/). The file is called **local.runner.py**.

<aside class="negative">
Note that the file <b>local.runner.py</b> needs to be moved from the sub-folder data into the project folder tfx-files.
</aside>

<!-- ------------------------ -->
## Create a pipeline

Duration: 0:10:00

Before we can create our pipeline, we first need to change some code in the file **local_runner.py**. This script creates a pipeline run and specifies the run's parameters, such as the ``DATA_PATH`` and ``OUTPUT_DIR``.

*Note that you don't necessarily have to change the variable definition of ``DATA_PATH`` since the given expression returns the full path name in a multiplatform-safe way.*

1. Open the file with your code editor and define the variables ``OUTPUT_DIR`` (in line 32) and ``DATA_PATH``:

```python
OUTPUT_DIR = 'your-path-to-tfx-files/output'
```

- On my machine, the variable would be defined as: ``OUTPUT_DIR = /Users/jankirenz/tfx-files/output``

```python
DATA_PATH = 'your-path-to-tfx-files/data/'
```

- On my machine, the variable would be defined as: ``DATA_PATH = '/Users/jankirenz/tfx-files/data/'``

2. We can save all changes and close the file.

3. In your terminal, change directory (``cd``) into the project directory of ``tfx-files``:

```bash
cd your-path-to-txf-files
```

- On my machine: ``cd /Users/jankirenz/tfx-files/``  

4. Run the following commands in your pipeline directory:

```bash
tfx pipeline create --pipeline_path=your-path-to-txf-files/local_runner.py
```

In my case this would be ``tfx pipeline create --pipeline_path=/Users/jankirenz/tfx-files/local_runner.py``

If you run the code, the last output line should display ``Pipeline "pipeline-tutorial" created successfully.``

5. Finally, run this command:

```bash
tfx run create --pipeline_name=pipeline-tutorial
```

- The command creates a pipeline run using [LocalDagRunner](https://www.tensorflow.org/tfx/api_docs/python/tfx/orchestration/local/local_dag_runner/LocalDagRunner), which adds the following directories to your pipeline (in your sub-folder ``output``:
  - A **tfx_metadata** directory which contains the ML Metadata store used locally.
  - A **tfx_pipeline_output** directory which contains the pipeline's file outputs.

<!-- ------------------------ -->
## Customize the template

Duration: 0:10:00

Open your pipeline's **pipeline/configs.py** file and review the contents:

- This script defines the configuration options used by the pipeline and the component functions.
- This is where you would specify things like the location of the datasource or the number of training steps in a run.

Open your pipeline's **pipeline/pipeline.py** file and review the contents:

- This script creates the TFX pipeline.
- Initially, the pipeline contains only an ExampleGen component.
- You may follow the instructions in the **TODO** comments in **pipeline.py** to add more steps to the pipeline.

<!-- ------------------------ -->
## Congratulations!

Duration: 0:07:00

Gongratulations! You have completed the tutorial and learned how to:

✅ Install a TFX pipeline template  
✅ Created a local TFX pipeline run  
✅ Reviewed the pipeline components  

<aside class="positive">
After you have reviewed the scaffolding created by the template and created a pipeline run using LocalDagRunner you could now proceed to customize the template to fit your requirements.
</aside>

---

<img src="img/Jan.png" alt="Jan Kirenz" width="100">

Thank you for participating in this tutorial. If you found any issues along the way I'd 
appreciate it if you'd raise them by clicking the "Report a mistake" button at the bottom left of this site.

*Copyright: Jan Kirenz (2021) | [kirenz.com](https://www.kirenz.com) | [CC BY-NC 2.0 License](https://creativecommons.org/licenses/by-nc/2.0/)*