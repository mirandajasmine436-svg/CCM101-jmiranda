# Cloud Infrastructure Components

## 1. Compute Resources

In the KillerCoda environment, the compute resource is the **Intel Xeon E312xx virtual CPU**, featuring **1 available CPU core**. These compute resources supply the necessary processing power for running applications, executing commands, processing data, and conducting other computational tasks.

In cloud computing, compute resources are offered through virtual machines or other virtualized services, allowing organizations to run applications without the need for physical servers. This enables cloud providers to allocate resources based on workload needs.

KillerCoda's virtualized Linux server with an Intel Xeon processor supports the execution of Linux commands, software installations, and file management.

## 2. Storage Resources

The primary storage resource is the **`/dev/vda1`** partition with a total capacity of **19 GB**, containing approximately **5.4 GB used** and **13 GB available**. Other storage-related file systems include **`/dev/vda16`** mounted at `/boot` and **`/dev/vda15`** mounted at `/boot/efi`.

Storage resources are essential for saving operating system files, applications, and user data, ensuring data availability even when applications are inactive. In cloud computing, reliable storage locations for data are crucial and are utilized for various purposes such as operating systems and backups.

The KillerCoda environment utilizes virtual disk partitions to store the Ubuntu operating system and essential system files, with **`/dev/vda1`** functioning as the root file system.

## 3. Networking Resources

The KillerCoda server features network connectivity with the following IP addresses:

- `172.30.1.2`
- `172.17.0.1`

The hostname is **`ubuntu`**.

Networking resources facilitate communication among computers, applications, and users. These resources include IP addresses and network interfaces.

Networking is vital in cloud computing for secure and reliable communication between cloud services and their users or resources. In KillerCoda, IP addresses enable communication within the cloud-based environment, while commands such as `hostname` and `ip` are used to identify the server and examine its network configuration.

## 4. Operating System

The operating system on the KillerCoda server is **Ubuntu 24.04.4 LTS (Noble)**, running the **6.8.0-138-generic** Linux kernel.

Operating systems manage hardware and software resources, creating an environment for applications and users to interact with hardware. They are critical in cloud computing because they manage compute, memory, storage, and networking resources.

KillerCoda's Ubuntu environment oversees the virtual CPU, memory, storage, and networking, enabling users to perform cloud infrastructure tasks through the terminal.

## Relationship Between the Components

The interplay of these four components establishes a functional cloud environment:

- **Compute** provides processing power.
- **Storage** provides space for data and system files.
- **Networking** enables communication between systems and users.
- **Operating System** manages the available hardware and software resources.

In the KillerCoda environment, these components collectively form the essential infrastructure needed to operate a cloud-based Linux server.
