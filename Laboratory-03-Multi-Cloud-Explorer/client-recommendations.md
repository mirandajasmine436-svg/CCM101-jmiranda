# Cloud Platform Recommendations

## Scenario 1 – Startup Company

### Client Scenario
A startup company is developing a mobile application and needs a cloud platform that is affordable, scalable, and easy to expand as the number of users grows.

### Recommended Platform: Amazon Web Services (AWS)
AWS offers scalable cloud services ideal for startups, allowing them to start with minimal resources, manage costs effectively, and expand services as their mobile application attracts more users.


### Recommended Services

| Service | Purpose |
|---|---|
| Amazon EC2 | Runs the application's servers |
| Amazon S3 | Stores images, files, and application data |
| Amazon VPC | Creates a secure private network |

### Recommendation
AWS is ideal for startups, allowing initial resource use and scalability as applications grow, making it budget-friendly and future-oriented.


---

## Scenario 2 – University

### Client Scenario
A university already uses Windows Server, Microsoft 365, and Active Directory. The university wants to move some of its existing services to the cloud while maintaining compatibility with its current Microsoft environment.

### Recommended Platform: Microsoft Azure
Microsoft Azure integrates well with existing Microsoft technologies, simplifying the transition to cloud services, particularly with Windows Server, Microsoft 365, and Active Directory.

### Recommended Services

| Service | Purpose |
|---|---|
| Azure Virtual Machines | Runs Windows Server workloads |
| Microsoft Entra ID | Manages user identities and access |
| Azure Virtual Network | Connects cloud resources securely |

### Recommendation

Azure is recommended because the university already depends on Microsoft technologies. Using Azure can make it easier to connect existing systems with cloud-based services and gradually migrate workloads.


---

## Scenario 3 – AI Research Company

### Client Scenario
An AI research company needs powerful computing resources for Artificial Intelligence and Machine Learning workloads. The company also needs storage for large datasets and a platform for developing and deploying AI models.

### Recommended Platform: Google Cloud Platform (GCP)
Google Cloud Platform is a strong choice for the AI research company because it provides services designed for Artificial Intelligence, Machine Learning, and data processing. The company can use cloud computing resources for demanding workloads without maintaining all of the physical hardware itself.

### Recommended Services

| Service | Purpose |
|---|---|
| Google Compute Engine | Provides computing resources for research workloads |
| Google Cloud Storage | Stores datasets and research files |
| Google Kubernetes Engine (GKE) | Runs containerized applications |

### Recommendation
GCP is ideal for AI research, offering services for developing, training, and deploying models on cloud infrastructure.


---

## Scenario 4 – Global E-Commerce Company

### Client Scenario
A global e-commerce company needs a cloud platform that can support customers from different countries. The company expects high traffic during sales and special events and needs scalable and highly available infrastructure.

### Recommended Platform: Amazon Web Services (AWS)
AWS offers scalable, highly available infrastructure for deploying applications globally, with services that automatically adjust resources based on traffic fluctuations.

### Recommended Services

| Service | Purpose |
|---|---|
| Amazon EC2 | Runs web and application servers |
| Amazon S3 | Stores product images, files, and other data |
| Amazon RDS | Manages the e-commerce database |

### Recommendation
AWS is ideal for global e-commerce due to its scalability, availability, and performance, managing regular traffic and spikes during promotions.



---

# Multi-Cloud Decision Matrix

The following decision matrix compares the recommended cloud provider based on different business requirements.

| Business Requirement | Recommended Platform | Justification |
|---|---|---|
| Startup Company | Amazon Web Services (AWS) | AWS provides a wide range of scalable services that allow startups to begin with smaller resources and expand as the business grows. |
| Enterprise Organization | Amazon Web Services (AWS) | AWS offers a large selection of enterprise services, scalable infrastructure, and global availability suitable for large organizations. |
| Microsoft Environment | Microsoft Azure | Azure provides strong integration with Microsoft technologies such as Windows Server, Microsoft 365, and Microsoft Entra ID. |
| AI / Machine Learning | Google Cloud Platform (GCP) | GCP provides strong AI, machine learning, and data processing services that are useful for AI-focused organizations. |
| Kubernetes Deployment | Google Cloud Platform (GCP) | GCP provides Google Kubernetes Engine (GKE), which is designed for deploying and managing containerized applications using Kubernetes. |
| Global Web Application | Amazon Web Services (AWS) | AWS provides global infrastructure, scalable computing, content delivery, and load balancing services that can support applications serving users worldwide. |

## Decision Matrix Summary

Based on the decision matrix, AWS is a strong choice for startups, enterprise organizations, and global web applications. Microsoft Azure is recommended when a company already depends heavily on Microsoft technologies. Google Cloud Platform is particularly suitable for AI and Machine Learning workloads and Kubernetes-based deployments.
