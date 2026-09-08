# Mission 3 – Become a Multi-Cloud Explorer

## Mission Overview

Congratulations!

Your successful completion of the Cloud Infrastructure Assessment has earned you a promotion to the Cloud Evaluation Team at CloudNova Technologies.

A new client plans to migrate its existing IT infrastructure to the cloud. However, the client is unsure whether to adopt Amazon Web Services (AWS), Microsoft Azure, or Google Cloud Platform (GCP).

As part of the Cloud Evaluation Team, your mission is to explore the world's leading cloud platforms, compare their services, and recommend the most appropriate provider for different business scenarios.

---

## Mission Objectives

At the end of this laboratory activity, you should be able to:

- Explore the major public cloud platforms.
- Identify the core services offered by AWS, Microsoft Azure, and Google Cloud Platform.
- Compare cloud services across different providers.
- Analyze business requirements and recommend appropriate cloud solutions.
- Create professional technical documentation using Markdown.
- Continue developing a well-organized GitHub Cloud Computing Portfolio.

---

# Checkpoint 7 – Continue Your Linux Investigation

## Linux Investigation

A KillerCoda Playground was launched to investigate the Linux environment. Linux commands were used to identify the operating system, CPU information, memory, and disk space.

---

## Operating System

The Linux environment is running:

- **Operating System:** Ubuntu 24.04.4 LTS
- **Codename:** Noble
- **Kernel:** 6.8.0-138-generic

## CPU Information 
The Linux server uses:
- **Architecture:** x86_64
- **CPU(s):** 1
- **On-line CPU(s) list:** 0
- **Model name:** Intel Xeon E312xx (Sandy Bridge, IBRS update)
- **BIOS Model name:** RHEL-9.6.0 PC (Q35 + ICH9, 2009)  CPU @ 2.0GHz
- **NUMA node0 CPU(s):** 0

## Memory

The Linux environment has approximately:

- **Total RAM:** 1.9 GiB
- **Used Memory:** 453 MiB
- **Free Memory:** 747 MiB
- **Available Memory:** 1.4 GiB
- **Swap:** 1.0 GiB

## Disk Space

The main disk is:

- **Device:** `/dev/vda1`
- **Total Capacity:** approximately 19 GB


### Command Used

```bash
cat /etc/os-release
lscpu | grep -E 'Model name|CPU\(s\)|Architecture'
free -h
df -h /
