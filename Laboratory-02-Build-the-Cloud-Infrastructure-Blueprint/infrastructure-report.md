# Cloud Infrastructure  Report

## 1. Operating System

The cloud server is running **Ubuntu 24.04.4 LTS** with the codename **Noble**.

## 2. Kernel Version

The Linux kernel version is:

**6.8.0-138-generic**

## 3. CPU Model

The CPU model detected on the server is:

**Intel Xeon E312xx (Sandy Bridge, IBRS update)**

The system has **1 CPU core** available.

## 4. Total RAM

The server has approximately **1.9 GiB of RAM**.

| Memory    |  Amount |
| --------- | ------: |
| Total RAM | 1.9 GiB |
| Used      | 453 MiB |
| Free      | 747 MiB |
| Available | 1.4 GiB |
| Swap      | 1.0 GiB |

## 5. Disk Capacity

The main disk partition `/dev/vda1` has a total capacity of **19 GB**.

| File System | Size | Used | Available | Usage | Mount Point |
| ----------- | ---: | ---: | --------: | ----: | ----------- |
| `/dev/vda1` |  19G | 5.4G |       13G |   30% | `/`         |

## 6. Mounted File Systems

The following mounted file systems were observed:

| File System  | Size | Used | Available | Usage | Mounted On  |
| ------------ | ---: | ---: | --------: | ----: | ----------- |
| `tmpfs`      | 191M | 996K |      190M |    1% | `/run`      |
| `/dev/vda1`  |  19G | 5.4G |       13G |   30% | `/`         |
| `tmpfs`      | 952M |  84K |      952M |    1% | `/dev/shm`  |
| `tmpfs`      | 5.0M |    0 |      5.0M |    0% | `/run/lock` |
| `/dev/vda16` | 881M | 117M |      703M |   15% | `/boot`     |
| `/dev/vda15` | 105M | 6.2M |       99M |    6% | `/boot/efi` |

## 7. Hostname

The hostname of the cloud server is:

**ubuntu**

## 8. IP Address

The server reported the following IP addresses:

* **172.30.1.2**
* **172.17.0.1**

## 9. Linux Commands Executed

The following Linux commands were used to investigate the cloud environment:

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

## 10. Summary

The KillerCoda environment provides a virtualized **Ubuntu 24.04.4 LTS** cloud server. The server has an **Intel Xeon E312xx processor**, **1 CPU core**, approximately **1.9 GiB of RAM**, and a **19 GB main disk partition**. The system also contains mounted file systems used for the operating system, boot files, EFI files, and temporary system data. The hostname is **ubuntu**, and the server has the IP addresses **172.30.1.2** and **172.17.0.1**.
