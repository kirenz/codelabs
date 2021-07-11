author: Jan Kirenz
summary: A fast and easy way to deploy Kubeflow on your laptop
id: kubeflow-install
tags: kubeflow
categories: mlops
environments: Web
status: Published
feedback link: https://github.com/kirenz/codelabs/blob/master/markdown/kubeflow-install

# Kubeflow Installation Tutorial

<!-- ------------------------ -->
## Overview

Duration: 0:02:00

### What we cover

In this tutorial you learn how to install Kubeflow on your local machine. We use Mini Kubeflow[(MiniKF)](https://www.kubeflow.org/docs/distributions/minikf/minikf-vagrant/) which is based on Kubernetes using minikube.

<aside class="positive">
 MiniKF is a single-node instance of Kubeflow, Kale, and Rok Data Management. It builds ML models for free on your laptop with Vagrant. However, it is possible to move to serving at scale with the same code on GCP, AWS, or Azure.
</aside>

<!-- ------------------------ -->
## Technology overview

Duration: 0:10:00

### Kubeflow

<iframe width="560" height="315" src="https://www.youtube.com/embed/cTZArDgbIWw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<img src="img/kubeflow-logo.png" alt="Kubeflow" width="50">

The Kubeflow project is dedicated to making deployments of machine learning (ML) workflows on Kubernetes simple, portable and scalable. It's goal is not to recreate other services, but to provide a straightforward way to deploy best-of-breed open-source systems for ML to diverse infrastructures. Anywhere you are running Kubernetes, you should be able to run Kubeflow ([Kubeflow documentation](https://www.kubeflow.org/docs/about/kubeflow/).



### Kubernetes

[Kubernetes](https://kubernetes.io/) (also known as K8s or "kube") is an open-source system for automating deployment, scaling, and management of containerized applications. A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another. 

<img src="img/what-is-container.png" alt="Docker container" width="300">


For example, [Docker](https://www.docker.com/) can be used as a container runtime that Kubernetes orchestrates. A Docker container image is a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools, system libraries and settings.

Kubernetes groups containers that make up an application into logical units for easy management and discovery. In other words, you can cluster together groups of hosts running Linux® containers, and Kubernetes helps you easily and efficiently manage those clusters. Kubernetes builds upon 15 years of experience of running production workloads at Google, combined with best-of-breed ideas and practices from the community.



### minikube


https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/

minikube is local Kubernetes, focusing on making it easy to learn and develop for Kubernetes.



**MiniKF** is the easiest way to get started with Kubeflow and comes bundled with [Kale](https://github.com/kubeflow-kale/kale) for automating MLOps workflow and [Rok](https://www.arrikto.com/rok-data-management-platform/) for ML data management.

With MiniKF, you can start building models in your Jupyter notebook and run them easily in Kubeflow Pipelines. When you’re ready to go into production, you can move to a multi-node Kubeflow cloud deployment on GCP, AWS, or Azure with one click. No extra coding or knowledge of containers needed.

A MiniKF (Mini Kubeflow) VM on GCP that automatically installs:

Kubernetes (using Minikube)
Kubeflow
Kale, a tool to convert general purpose Jupyter Notebooks to Kubeflow Pipelines workflows (GitHub)
Arrikto Rok data management platform for data versioning and reproducibility


<!-- ------------------------ -->
## System requirements

Duration: 0:01:00

Your system should meet the following requirements:

- 12GB RAM
- 2 CPUs
- 50GB disk space

MiniKF runs on:

- Linux
- macOS
- Windows


<!-- ------------------------ -->
## Software prerequisites

Duration: 0:10:00

Before installing MiniKF, you need to have Vagrant and VirtualBox installed on your laptop.

### Vagrant

Vagrant is a tool for building and managing virtual machine environments in a single workflow.

- [Install Vagrant](https://www.vagrantup.com/downloads)

### VirtualBox

[Oracle VM VirtualBox](https://www.virtualbox.org/manual/ch01.html) is a cross-platform virtualization application. It extends the capabilities of your existing computer so that it can run multiple OSes, inside multiple virtual machines, at the same time. As an example, you can run Windows and Linux on your Mac, run Windows Server 2016 on your Linux server, run Linux on your Windows PC, and so on, all alongside your existing applications. You can install and run as many virtual machines as you like. 

- [Download VirtualBox](https://www.virtualbox.org/wiki/Downloads)

If you have **macOS**:  

After the installation, you need to [change Security & Privacy General preferences on Mac](https://support.apple.com/de-de/guide/mac-help/mh11784/mac) to unblock VirtualBox: 

- To change these preferences on your Mac, choose Apple menu  > System Preferences, click Security & Privacy, then click General.

- If the lock at the bottom left of the pane is locked, click it to unlock the preference pane.

- Click allow to load system extensions from the developer of the software.


<!-- ------------------------ -->
## MiniKF installation

Duration: 0:20:00

- Open a terminal on your laptop and create a new directory:

```bash
mkdir minikf
```

- Switch into it:

```bash
cd minikf
```

- Run the following commands to install MiniKF:

```bash
vagrant init arrikto/minikf
```

- This command creates and configures your virtual machine:

```bash
vagrant up
```

- MiniKF will take a few minutes to boot.  

- When this is done, open a browser and navigate to [http://10.10.10.10](http://10.10.10.10).  
  
- Follow the on-screen instructions to start Kubeflow (press Enter on your keyboard to start MiniKF).  

Here a video-tutorial of the complete installation process on [YouTube](https://www.youtube.com/watch?v=rVak_NIKF88)

<!-- ------------------------ -->
## Start MiniKF

Duration: 0:05:00

To start MiniKf, follow these instructions:

- Open a terminal on your laptop and switch to your MiniKF directory (minikf):

```bash
cd minikf
```

- Run the following command to start MiniKF:


```bash
vagrant up
```



<!-- ------------------------ -->
## What's next?

Duration: 0:02:00

Gongratulations! You have completed the tutorial and learned how to:

✅ Install MiniKF on your computer.

---

<img src="img/Jan.png" alt="Jan Kirenz" width="100">

Thank you for participating in this tutorial. If you found any issues along the way I'd appreciate it if you'd raise them by clicking the "Report a mistake" button at the bottom left of this site.

*Copyright: Jan Kirenz (2021) | [kirenz.com](https://www.kirenz.com) | [CC BY-NC 2.0 License](https://creativecommons.org/licenses/by-nc/2.0/)*