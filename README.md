🚀 Multi-Tier Java Application Deployment on AWS using Ansible

<img width="851" height="591" alt="Untitled Diagram drawio (2)" src="https://github.com/user-attachments/assets/b7e03368-a573-4b42-8454-4ba46e2a4ab8" />




### 🛠️ Project Overview

The main objective of this project is to deploy a **Multi-Tier Java Web Application on AWS** using **Ansible Roles**.

The infrastructure consists of multiple EC2 instances, where each server is responsible for a specific service. Ansible is used to automate the installation, configuration, and deployment of the application across all managed nodes. 

---

### ☁️ AWS Infrastructure

* **VPC:** `10.0.0.0/16`
* **App Subnet:** `10.0.1.0/24`
* **DB Subnet:** `10.0.2.0/24`
* **Memcache Subnet:** `10.0.3.0/24`
* **RabbitMQ Subnet:** `10.0.4.0/24`
* **Load Balancer Subnet:** `10.0.5.0/24`
* **Internet Gateway**
* **Route Table**
* **Security Groups**
* **6 EC2 Instances** including the Ansible Control Node.

## 🔐 Security Groups

The project uses separate Security Groups for each service:

| Server        |  Port | Purpose   |
| ------------- | ----: | --------- |
| App           |    22 | SSH       |
| App           |  8080 | Tomcat    |
| DB            |  3306 | MySQL     |
| Memcache      | 11211 | Memcached |
| RabbitMQ      |  5672 | RabbitMQ  |
| Load Balancer |    80 | HTTP      |

Service-to-service access is controlled through Security Groups, for example the DB, Memcached, and RabbitMQ ports allow traffic from the App Server Security Group. 


---

## 📋 Features

### 🔹 Ansible Automation

Ansible is used from the **Control Node** to configure all managed EC2 instances using **SSH key-based authentication**. 

### 🔹 Ansible Roles

The project is divided into five reusable roles:

```text
roles/
├── app/
├── db/
├── memcache/
├── rabbitmq/
└── loadbalancer/
```
Each role is responsible for configuring a specific server. 

### 🔹 Application Server
### 🔹 Database Server
### 🔹 Memcached Server
### 🔹 RabbitMQ Server
### 🔹 Nginx Load Balancer
---

## 🚀 How It Works

```text
User
  │
  ▼
Nginx Load Balancer :80
  │
  ▼
Tomcat App Server :8080
  │
  ├──► MySQL :3306
  │
  ├──► Memcached :11211
  │
  └──► RabbitMQ :5672
```

The deployment process is automated using:

```text
Control Node
     │
     ▼
   Ansible
     │
     ├──► App Role
     ├──► DB Role
     ├──► Memcache Role
     ├──► RabbitMQ Role
     └──► Load Balancer Role
```

The complete deployment is executed through the Ansible Playbook:

```bash
ansible-playbook -i inventory.ini site.yml
```


---

## 🧪 Testing

After deployment, connectivity between the application and backend services is tested.

---

## 🧠 Key Benefits

* **Automation** — Server configuration and application deployment are automated using Ansible.
* **Reusability** — Ansible Roles can be reused across different projects.
* **Modularity** — Each service has its own dedicated role.
* **Consistency** — The same configuration can be applied across multiple servers.
* **Multi-Tier Architecture** — Application, database, caching, messaging, and load-balancing layers are separated.
* **Centralized Management** — All managed nodes are controlled from the Ansible Control Node.

The project structure is organized into separate roles for each service. 

---

## 📊 Final Result

✅ AWS VPC and networking infrastructure created
✅ 5 service EC2 instances deployed
✅ Ansible Control Node configured
✅ Ansible SSH key-based authentication configured
✅ Five Ansible Roles created
✅ Java application built using Maven
✅ Application deployed on Tomcat
✅ MySQL database configured
✅ Memcached configured
✅ RabbitMQ configured
✅ Nginx configured as Load Balancer
✅ Connectivity between application and backend services tested

---

## 🛠️ Technologies

**AWS** • **EC2** • **VPC** • **Subnet** • **Internet Gateway** • **Route Table** • **Security Groups** • **Ansible** • **Ansible Roles** • **Nginx** • **Tomcat** • **Java** • **Maven** • **MySQL** • **Memcached** • **RabbitMQ** • **Git** • **Ubuntu** • **SSH**

---

## 👨‍💻 Author

**Ahmed Anany**


