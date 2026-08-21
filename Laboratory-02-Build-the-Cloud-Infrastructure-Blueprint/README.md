## Mission Overview

Congratulations,
Your onboarding has been successfully completed, and your Cloud Computing Portfolio has been approved by
your supervisor.
CloudNova Technologies has now assigned you to your first official project.
Before deploying cloud services, every cloud engineer must understand the infrastructure that powers modern
cloud computing. Your mission is to investigate the components of cloud infrastructure, identify how compute,
storage, networking, and identity services work together, and document your findings as if you were preparing
technical documentation for a client. 

## Objectives

The objectives of this laboratory activity were to:

 Explain the major components of cloud infrastructure.
 Investigate the hardware and software resources available in a Linux environment.
 Differentiate compute, storage, networking, and identity resources.
 Interpret the relationship between cloud infrastructure components.
 Create professional technical documentation using Markdown.
 Continue building a structured GitHub Cloud Computing Portfolio.

## Cloud Infrastructure Components

The main cloud infrastructure components identified in the KillerCoda environment were:

### Compute Resources

The server uses an **Intel Xeon E312xx virtual CPU** with **1 available CPU core**. Compute resources provide the processing power required to execute commands, run applications, and process data.

### Storage Resources

The primary storage resource is the **`/dev/vda1`** partition with a capacity of **19 GB**. Storage resources provide space for the operating system, applications, configuration files, and other data.

### Networking Resources

The server has network connectivity with the IP addresses **`172.30.1.2`** and **`172.17.0.1`**. The hostname of the server is **`ubuntu`**. Networking allows the server and other resources to communicate.

### Operating System

The server runs **Ubuntu 24.04.4 LTS (Noble)** with Linux kernel version **`6.8.0-138-generic`**. The operating system manages the available compute, memory, storage, and networking resources.

## Tools Used

The following tools were used during the laboratory activity:

* KillerCoda Playground
* Ubuntu Linux Terminal
* Git
* GitHub
* draw.io
* Markdown

## Linux Commands Executed

The following Linux commands were used to investigate the cloud server:

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

Git commands were also used to manage and submit the laboratory files:

```bash
git status
git add
git commit
git push
```

## Skills Learned

Through this laboratory activity, I learned how to inspect a Linux cloud environment and identify its basic infrastructure resources. I practiced using Linux commands to obtain information about the operating system, CPU, memory, storage, hostname, and network configuration.

I also learned how to compare equivalent services between AWS, Microsoft Azure, and Google Cloud Platform. In addition, I gained experience creating a simple cloud architecture diagram and organizing technical documentation using Markdown and GitHub.

## Challenges Encountered

One challenge I encountered was understanding the different Linux commands needed to obtain specific server information. I also needed to carefully organize the required screenshots and files according to the laboratory folder structure.

Another challenge was understanding that AWS, Azure, and Google Cloud provide similar infrastructure capabilities but use different service names. Researching and comparing the services helped me understand how the major cloud providers approach compute, storage, networking, and identity management.

## Laboratory Deliverables

The completed laboratory folder contains the following files:

```text
Laboratory-02-Build-the-Cloud-Infrastructure-Blueprint
├── README.md
├── infrastructure-report.md
├── cloud-components.md
├── cloud-provider-comparison.md
├── reflection.md
└── screenshots
    
```

## Conclusion

This laboratory provided practical experience in investigating cloud infrastructure and documenting technical findings. The activity demonstrated how compute, storage, networking, and operating system resources work together to create a functional cloud environment. It also strengthened my Linux, Git, GitHub, cloud infrastructure, research, and technical documentation skills.
