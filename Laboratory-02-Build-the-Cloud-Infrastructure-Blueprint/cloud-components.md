
# Cloud Infrastructure Components

## 1. Compute Resources

In the KillerCoda environment, the compute resource is the **Intel Xeon E312xx virtual CPU**, featuring **1 available CPU core**. These compute resources supply the necessary processing power for running applications, executing commands, processing data, and conducting other computational tasks.

In cloud computing, compute resources are offered through virtual machines or other virtualized services, allowing organizations to run applications without the need for physical servers and enabling providers to allocate resources based on workload needs.

KillerCoda's virtualized Linux server with an Intel Xeon processor supports the execution of Linux commands, software installations, and file management.

## 2. Storage Resources

The primary storage resource is the **`/dev/vda1`** partition with a total capacity of **19 GB**, containing approximately **5.4 GB used** and **13 GB available**.

Other storage-related file systems include `/dev/vda16` mounted at `/boot` and `/dev/vda15` mounted at `/boot/efi`.

Storage resources are essential for saving operating system files, applications, and user data. In cloud computing, reliable storage is important for storing operating systems, applications, databases, and backups.

The KillerCoda environment uses virtual disk partitions to store the Ubuntu operating system and essential system files, with `/dev/vda1` functioning as the root file system.

## 3. Networking Resources

The KillerCoda server features network connectivity with the following IP addresses:

- `172.30.1.2`
- `172.17.0.1`

The hostname of the server is **`ubuntu`**.

Networking resources facilitate communication among computers, applications, and users. They include IP addresses, network interfaces, routing, and other networking configurations.

Networking is important in cloud computing because it allows cloud services and resources to communicate securely and reliably with users and other systems.

In KillerCoda, the IP addresses enable communication within the cloud-based environment. Commands such as `hostname`, `hostname -I`, and `ip addr` can be used to identify the server and examine its network configuration.

## 4. Operating System

The operating system on the KillerCoda server is **Ubuntu 24.04.4 LTS (Noble)**, running the **`6.8.0-138-generic`** Linux kernel.

The operating system manages hardware and software resources and provides an environment where applications and users can interact with the system.

Operating systems are critical in cloud computing because they manage compute, memory, storage, and networking resources.

KillerCoda's Ubuntu environment manages the virtual CPU, memory, storage, and networking resources, allowing users to perform cloud infrastructure tasks through the terminal.

## Relationship Between the Components

The four infrastructure components work together to create a functional cloud environment:

- **Compute** provides processing power.
- **Storage** provides space for data and system files.
- **Networking** provides communication between resources and users.
- **Operating System** manages the hardware and software resources.

In the KillerCoda environment, these components work together to provide a functional cloud-based Linux server that can be investigated and managed through the terminal.
