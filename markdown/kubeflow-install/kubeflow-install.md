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

In this tutorial you learn how to install Kubeflow - a popular framework for running Machine Learning workflows on [Kubernetes](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/) - on your laptop. Therefore, we use the [MiniKF](https://www.kubeflow.org/docs/distributions/minikf/minikf-vagrant/) distribution provided by Arrikto.

<img src="img/kubeflow-logo.png" alt="Kubeflow" width="100">

MiniKF is a fast and easy way to get started with Kubeflow. With just a few clicks, you are up for experimentation, and for running complete Kubeflow Pipelines.

<aside class="positive">
MiniKF - a production-ready local Kubeflow deployment that installs in minutes.
</aside>

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

```bash
vagrant up
```

MiniKF will take a few minutes to boot. When this is done, navigate to http://10.10.10.10 and follow the on-screen instructions to start Kubeflow and Rok.

Here a video-tutorial of the complete installation process on [YouTube]:(https://www.youtube.com/watch?v=rVak_NIKF88)

![https://www.youtube.com/watch?v=rVak_NIKF88](https://en.wikipedia.org/wiki/File:Example.jpg "Try Me Publisher")


<!-- ------------------------ -->
## What's next?

Duration: 0:02:00

Gongratulations! You have completed the tutorial and learned how to:

✅ Install MiniKF on your computer.

---

<img src="img/Jan.png" alt="Jan Kirenz" width="100">

Thank you for participating in this tutorial. If you found any issues along the way I'd appreciate it if you'd raise them by clicking the "Report a mistake" button at the bottom left of this site.

*Copyright: Jan Kirenz (2021) | [kirenz.com](https://www.kirenz.com) | [CC BY-NC 2.0 License](https://creativecommons.org/licenses/by-nc/2.0/)*