# Cloud Provider Comparison

## Overview

Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP) are major public cloud providers that offer similar infrastructure services under different names. Their services cover essential cloud infrastructure areas such as compute, storage, networking, and identity and access management.

## Cloud Infrastructure Service Comparison

| Infrastructure Component                 | Amazon Web Services (AWS) | Microsoft Azure                     | Google Cloud Platform (GCP) |
| ---------------------------------------- | ------------------------- | ----------------------------------- | --------------------------- |
| **Compute**                              | **Amazon EC2**            | **Azure Virtual Machines**          | **Compute Engine**          |
| **Storage**                              | **Amazon S3**             | **Azure Blob Storage**              | **Cloud Storage**           |
| **Networking**                           | **Amazon VPC**            | **Azure Virtual Network**           | **Google Cloud VPC**        |
| **Identity and Access Management (IAM)** | **AWS IAM**               | **Azure RBAC / Microsoft Entra ID** | **Cloud IAM**               |

### Compute

AWS provides **Amazon EC2**, which offers resizable compute capacity for different workloads. Azure provides **Azure Virtual Machines**, which are scalable virtualized computing resources. Google Cloud provides **Compute Engine**, which offers configurable virtual machines for different workloads.

### Storage

AWS provides **Amazon S3**, an object storage service designed for storing and retrieving large amounts of data. Azure provides **Azure Blob Storage**, which is designed for massive amounts of unstructured data. Google Cloud provides **Cloud Storage**, a scalable managed object storage service that stores data in buckets.

### Networking

AWS provides **Amazon VPC**, which allows users to create a logically isolated virtual network and configure IP ranges, subnets, and routing. Azure provides **Azure Virtual Network**, which enables Azure resources to communicate securely with each other, the internet, and on-premises networks. Google Cloud provides **VPC**, which provides virtual networking across Google Cloud resources and can span multiple regions.

### Identity and Access Management

AWS provides **AWS IAM**, which controls authentication and authorization for AWS resources. Azure uses **Azure RBAC** for fine-grained access management of Azure resources, together with **Microsoft Entra ID** for identity management. Google Cloud provides **Cloud IAM**, which controls which identities have which roles and permissions on Google Cloud resources.

---

## Guide Questions

### 1. Which cloud provider offers the broadest range of services? Explain your answer.

**AWS** is my choice for the provider with the broadest range of services. AWS provides a very extensive collection of cloud services across compute, storage, networking, databases, security, analytics, AI, machine learning, and other areas. Its EC2 platform alone offers many different instance options for various workloads.

### 2. Which cloud platform would you recommend for an organization that primarily uses Microsoft products? Why?

I would recommend **Microsoft Azure** for an organization that primarily uses Microsoft products. Azure provides strong integration with Microsoft technologies, including Windows Server, SQL Server, .NET, and Microsoft Entra ID, making it a natural choice for organizations already using the Microsoft ecosystem.

### 3. Which platform is widely recognized for Artificial Intelligence (AI), Machine Learning (ML), and Kubernetes services?

**Google Cloud Platform (GCP)** is widely recognized for its strengths in AI, machine learning, and Kubernetes. Google Cloud provides AI and machine learning services and offers **Google Kubernetes Engine (GKE)** as a managed Kubernetes service. Google Cloud's product catalog also includes specialized AI infrastructure such as GPUs and TPUs.

### 4. What similarities did you observe among the three cloud providers?

All three cloud providers offer equivalent core infrastructure services for **compute, storage, networking, and identity management**. Although the service names and specific features differ, each provider allows organizations to create virtual computing resources, store data, configure networks, and control user access to cloud resources.

## Conclusion

AWS, Azure, and Google Cloud provide similar foundational cloud infrastructure capabilities while using different service names and approaches. AWS has a particularly broad service portfolio, Azure is especially suitable for organizations invested in Microsoft technologies, and Google Cloud has strong offerings in AI, machine learning, and Kubernetes. Understanding these equivalent services helps cloud engineers select the appropriate platform for a specific organization's technical requirements.
