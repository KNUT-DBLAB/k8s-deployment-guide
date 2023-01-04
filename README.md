# k8s deployment guide

This guide explains how to deploy k8s(Kubernetes) cluster.

- (Optional) Install Windows terminal and latest Powershell 7.
- Deploy k8s cluster into local machine's virtual machines, using Hyper-V in Windows.
- Make a VM for connect and develop, which is outside of the k8s cluster
- Deploy k8s with _[Kubespray](https://kubespray.io/)_ for convenience

---

## Contents

- [k8s deployment guide](#k8s-deployment-guide)
  - [Contents](#contents)
  - [Environment](#environment)
  - [Step by step guide](#step-by-step-guide)
    - [1. (Optional but recommended) Install _Windows Terminal_ and _Powershell 7_](#1-optional-but-recommended-install-windows-terminal-and-powershell-7)
    - [2. Install Hyper-V](#2-install-hyper-v)
    - [3. Setup NAT](#3-setup-nat)
    - [4. Create VMs](#4-create-vms)
    - [5. Prepare VMs](#5-prepare-vms)
    - [6. Prepare Kubespray](#6-prepare-kubespray)
    - [7. Deploy k8s cluster](#7-deploy-k8s-cluster)
    - [8. Access and use the k8s cluster from _Dev_ VM](#8-access-and-use-the-k8s-cluster-from-dev-vm)

---

## Environment

- Host PC
  - RAM: More than 10GB
  - OS: Windows 10 (Maybe 11 also supports Hyper-V)
  - Virtualization function on BIOS should be turned on
- Virtual machine(VM) hypervisor: **Hyper-V**
  - Reason for using Hyper-V
    - Easy to install in Windows
    - Easy to manage with GUI
    - Supports backup function called "Checkpoint", and it's handy
    - Supports powershell command to handle, we will use some commands to handle checkpoints in multiple VMs at once
  - Network (Guide is explained below)
    - Require NAT
    - VMs require static MAC, static IP
- Virtual machines
  - _"Development"_ machine: we will connect and develop in this machine
    - OS: Latest LTS Ubuntu Server (22.04.1 LTS for now)
    - CPU: more than 2 cores for convenience
    - Memory: more than 2 GB for convenience
  - _"Control Plane"_ machine (Control Plane, CP in short, means "Master" node)
    - OS: Latest LTS Ubuntu Server (22.04.1 LTS for now)
    - CPU: 2 cores will be enough
    - Memory: 2 GB will be enough
  - _"Worker Node"_ machines (Worker node means "Slave" node)
    - OS: Latest LTS Ubuntu Server (22.04.1 LTS for now)
    - CPU: 2 cores will be enough
    - Memory: 2 GB will be enough

## Step by step guide

### 1. (Optional but recommended) Install _Windows Terminal_ and _Powershell 7_

If you're using Windows 11, _Windows Terminal_ might be already installed.

1. From _Microsoft Store_, install _Windows Terminal_: [Link here](https://www.microsoft.com/store/productId/9N0DX20HK701)
2. From _Microsoft Store_, install _PowerShell_: [Link here](https://www.microsoft.com/store/productId/9MZ1SNWT0N5D)
3. Reboot maybe required after installations
4. Open _Run_ with <kbd>Windows</kbd> + <kbd>R</kbd>, type `wt` and run
5. Open the _PowerShell_ tab, and make sure you're running version above 7

    ![01-01.png](images/01-01.png)

### 2. Install Hyper-V

1. In _Control panel_, _Programs and Features_, click _Turn Windows features on or off_

    ![02-01.png](images/02-01.png)

2. Find _Hyper-V_, and check all of them

    ![02-02.png](images/02-02.png)

3. Press _OK_, then the install process will begin. Reboot may required.
4. After the installation finished, check the program installed. in _Start menu_, type `hyper-v` will show _Hyper-V Manager_. Click that and check the program opens up.

    ![02-03.png](images/02-03.png)
    ![02-04.png](images/02-04.png)

### 3. Setup NAT

Refer _[This link](https://learn.microsoft.com/en-us/virtualization/hyper-v-on-windows/user-guide/setup-nat-network)_

1. Open a PowerShell console as Administrator
    - <kbd>Windows</kbd>+<kbd>R</kbd>

### 4. Create VMs

### 5. Prepare VMs

### 6. Prepare Kubespray

### 7. Deploy k8s cluster

### 8. Access and use the k8s cluster from _Dev_ VM
