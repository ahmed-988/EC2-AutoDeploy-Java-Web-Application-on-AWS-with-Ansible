[Untitled Diagram.drawio](https://github.com/user-attachments/files/26736371/Untitled.Diagram.drawio)![automated](https://github.com/user-attachments/assets/32eabdc2-4da2-4a92-bed5-c64271120906)# 🚀 Multi-Tier Java Application Deployment on AWS using Ansible

## 📌 Project Overview[Untitled Diagram.drawio](https://github.com/user-attachments/files/26736309/Untitled.Diagram.drawio)


This project demonstrates deploying a **multi-tier Java web application** on AWS using manual infrastructure (AWS Console) setup and Ansible automation.

The architecture follows a real-world production-like design with separate layers for application, database, caching, messaging, and load balancing.

---

## 🏗️ Architecture Diagram



---

## ☁️ AWS Infrastructure

### 🔹 VPC

* CIDR: `10.0.0.0/16`

### 🔹 Subnets

| Layer        | CIDR        |
| ------------ | ----------- |
| App          | 10.0.1.0/24 |
| DB           | 10.0.2.0/24 |
| Memcache     | 10.0.3.0/24 |
| RabbitMQ     | 10.0.4.0/24 |
| LoadBalancer | 10.0.5.0/24 |

### 🔹 Networking

* Internet Gateway attached to VPC
* Route Table:

  * Public Subnets: App, LoadBalancer
  * Private Subnets: DB, Memcache, RabbitMQ

---

## 🔐 Security Groups

| Security Group | Rules                           |
| -------------- | ------------------------------- |
| app-sg         | 8080 from lb-sg, SSH from my IP |
| db-sg          | 3306 from app-sg                |
| memcache-sg    | 11211 from app-sg               |
| rabbit-sg      | 5672 from app-sg                |
| lb-sg          | 80 from anywhere                |

---

## 🖥️ EC2 Instances

| Role         | Private IP |
| ------------ | ---------- |
| App          | 10.0.1.10  |
| DB           | 10.0.2.10  |
| Memcache     | 10.0.3.10  |
| RabbitMQ     | 10.0.4.10  |
| LoadBalancer | 10.0.5.10  |
| Control Node | 10.0.1.100 |

## 📌 Project Overview

* **Terraform**: Used to provision AWS infrastructure, including creating EC2 instances and handling initial setup such as copying required application files to the server.

* **Ansible**: Used for configuration management and application deployment. It installs Web App on the EC2 instance , and runs the application.




## 🎯 Key Learnings

* AWS Networking (VPC, Subnets, IGW)
* Security Groups Design
* Multi-Tier Architecture
* Infrastructure Automation using Ansible
* Deploying Java Applications


