# Types of Cloud Storage Research

## Comparison Table

| Storage Type | 📖 Description | 🎯 Primary Use Case | ☁️ Cloud Provider Example |
|---|---|---|---|
| 🧱 **Block Storage** | Splits data into fixed-size blocks, each with its own unique address. The operating system treats it like a raw hard drive and manages the file system on top of it. | Databases, virtual machine disks, and boot volumes that need fast, low-latency random read/write access. | AWS EBS, Azure Disk, Google Persistent Disk |
| 📁 **File Storage** | Stores data in a hierarchical folder-and-file structure and shares it across a network using protocols like NFS or SMB. | Shared documents, home directories, and team drives where many users need concurrent access to the same files. | AWS EFS, Azure Files, Google Filestore |
| 📦 **Object Storage** | Stores data as self-contained objects, each containing the data itself, rich metadata, and a globally unique identifier. Objects live in a flat namespace and are accessed via HTTP/REST APIs. | Unstructured data at massive scale  images, videos, backups, logs, and static web assets. | AWS S3, Azure Blob Storage, Google Cloud Storage, MinIO |

---

## 💡 Why Object Storage Is Best for the Client

For a photo-sharing application storing millions of user-uploaded images, **Object Storage is the ideal choice**. Unlike block storage, which is limited by the size of a single attached disk, object storage scales horizontally without practical limits, so the platform can grow as the user base grows. Each image is stored as an independent object with its own metadata and unique URL, making it easy to retrieve, serve over the web, and manage through APIs. This combination of **unlimited scalability, HTTP accessibility, and rich metadata** makes object storage the most cost-effective and operationally efficient option for unstructured media at scale.
