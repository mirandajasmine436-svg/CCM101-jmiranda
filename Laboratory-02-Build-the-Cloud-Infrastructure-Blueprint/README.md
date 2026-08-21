# Technical Documentation

## Mission Overview

CloudNova Technologies has assigned this project to investigate the infrastructure that supports modern cloud computing. Before deploying cloud services, a cloud engineer must understand how compute, storage, networking, and operating system resources work together.

In this laboratory activity, I investigated a Linux server environment using the KillerCoda Playground, documented the server's infrastructure information, researched major cloud providers, created a simple cloud architecture diagram, and organized the results in a GitHub Cloud Computing Portfolio.

## Objectives

The objectives of this laboratory activity were to:

* Explain the major components of cloud infrastructure.
* Investigate the hardware and software resources available in a Linux environment.
* Differentiate compute, storage, networking, and identity resources.
* Interpret the relationship between cloud infrastructure components.
* Create professional technical documentation using Markdown.
* Continue building a structured GitHub Cloud Computing Portfolio.

## Cloud Infrastructure Components

The main cloud infrastructure components identified in the KillerCoda environment were:

### Compute Resources

The server uses an **Intel Xeon E312xx virtual CPU** with **1 available CPU core**. Compute resources provide the processing power required to execute commands, run applications, and process data.

### Storage Resources

The primary storage resource identified is the **`/dev/vda1`** partition with a capacity of approximately **19 GB**. Storage resources provide space for the operating system, applications, configuration files, and other data.

### Networking Resources

The server has network connectivity through the IP addresses **`172.30.1.2`** and **`172.17.0.1`**. The hostname of the server is **`ubuntu`**. Networking resources allow the server and other resources to communicate with each other and with external networks.

### Operating System

The server runs **Ubuntu 24.04.4 LTS (Noble)** with Linux kernel version **`6.8.0-138-generic`**. The operating system manages and coordinates the available compute, memory, storage, and networking resources.

## Tools Used

The following tools were used during the laboratory activity:

* KillerCoda Playground
* Ubuntu Linux Terminal
* Git
* GitHub
* draw.io
* Markdown

## Linux Commands Executed

The following Linux commands were used to create, navigate, inspect, and document the cloud environment.

### Directory and File Commands

```bash
cd ~/CCM101-cbadongen
mkdir -p Laboratory-02-Build-the-Cloud-Infrastructure-Blueprint
cd Laboratory-02-Build-the-Cloud-Infrastructure-Blueprint
mkdir screenshots
touch README.md infrastructure-report.md cloud-components.md cloud-provider-comparison.md reflection.md
pwd
ls -la
ls -la screenshots
```

### Editing and Viewing Files

The `nano` text editor was used to create and edit the Markdown documentation files.

```bash
nano README.md
nano infrastructure-report.md
nano cloud-components.md
nano cloud-provider-comparison.md
nano reflection.md
```

The `cat` command was used to view file contents and check system information.

```bash
cat README.md
cat infrastructure-report.md
cat cloud-components.md
cat cloud-provider-comparison.md
cat reflection.md
```

### Linux Server Investigation

The following commands were used to investigate the Linux cloud server:

```bash
lsb_release -a
uname -r
lscpu | grep "Model name"
nproc
free -h
df -h
hostname
hostname -I
```

These commands were used to identify the operating system, kernel version, CPU model, number of CPU cores, RAM, disk capacity, mounted file systems, hostname, and IP address.

### Git Commands

Git commands were used to manage the laboratory files and submit the completed work to GitHub.

```bash
git status
git add .
git commit -m "Complete Laboratory 2 cloud infrastructure blueprint"
git push
```

## Skills Learned

Through this laboratory activity, I learned how to inspect a Linux cloud environment and identify its basic infrastructure resources. I practiced using Linux commands to obtain information about the operating system, CPU, memory, storage, mounted file systems, hostname, and network configuration.

I also learned how to compare equivalent services between AWS, Microsoft Azure, and Google Cloud Platform. In addition, I gained experience creating a simple cloud architecture diagram and organizing technical documentation using Markdown and GitHub.

## Challenges Encountered

One challenge I encountered was understanding the different Linux commands needed to obtain specific server information. I also needed to carefully organize the required screenshots and files according to the laboratory folder structure.

Another challenge was understanding that AWS, Microsoft Azure, and Google Cloud Platform provide similar infrastructure capabilities but use different service names. Researching and comparing these services helped me understand how the major cloud providers approach compute, storage, networking, and identity management.

## Laboratory Deliverables

The completed laboratory folder contains the following files:

```text
Laboratory-02-Build-the-Cloud-Infrastructure-Blueprint/
├── README.md
├── infrastructure-report.md
├── cloud-components.md
├── cloud-provider-comparison.md
├── reflection.md
└── screenshots/
    ├── server-information.png
    ├── network-information.png
    ├── storage-information.png
    └── cloud-architecture.png
```

## Conclusion

This laboratory provided practical experience in investigating cloud infrastructure and documenting technical findings. The activity demonstrated how compute, storage, networking, and operating system resources work together to create a functional cloud environment.

It also strengthened my Linux, Git, GitHub, cloud infrastructure, research, and technical documentation skills. By completing the laboratory, I gained a better understanding of how cloud infrastructure is investigated, documented, compared, and prepared before deployment.
