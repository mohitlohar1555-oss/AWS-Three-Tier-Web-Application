
# 🚀 AWS Three-Tier Web Application Deployment

<p align="center">
  <b>☁️ Cloud & DevOps Project | AWS Hands-On Implementation</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Cloud-AWS-orange?logo=amazonaws" />
  <img src="https://img.shields.io/badge/Region-ap--southeast--2-blue" />
  <img src="https://img.shields.io/badge/Architecture-Three--Tier-green" />
  <img src="https://img.shields.io/badge/Status-Completed-success" />
</p>

## 📌 Project Overview

This project demonstrates the deployment of a **secure, highly available, and scalable Three-Tier Web Application on AWS**.

The architecture separates the application into three independent layers:

- 🌐 **Web Tier:** Nginx + React
- ⚙️ **Application Tier:** Node.js + PM2
- 🗄️ **Database Tier:** Amazon RDS for MySQL 8.4

The infrastructure is deployed inside a custom Amazon VPC in the **Asia Pacific (Sydney) Region (`ap-southeast-2`)**.

## 🏗️ Architecture

```text
                 🌍 Internet
                      |
                      ▼
          ⚖️ External Application
                Load Balancer
                      |
                      ▼
               🌐 Web Tier
              Nginx + React
                      |
                      ▼
          ⚖️ Internal Application
                Load Balancer
                      |
                      ▼
             ⚙️ Application Tier
                Node.js + PM2
                      |
                      ▼
              🗄️ Database Tier
              Amazon RDS MySQL
```

## 🛠️ AWS Services Used

| AWS Service | Purpose |
|---|---|
| 🌐 Amazon VPC | Network isolation |
| 🔀 Subnets | Public and private networking |
| 🚪 Internet Gateway | Internet connectivity |
| 🔒 NAT Gateway | Outbound internet access |
| 🖥️ Amazon EC2 | Web and application servers |
| 🗄️ Amazon RDS | MySQL database |
| ⚖️ Application Load Balancer | Traffic distribution |
| 📈 Auto Scaling | Automatic scaling |
| 🪣 Amazon S3 | Application source code storage |
| 🔐 AWS IAM | Identity and access management |
| 🛠️ Systems Manager | Secure server access |
| 📊 Security Groups | Network traffic control |

## 📐 Network Architecture

- AWS Region: `ap-southeast-2`
- VPC CIDR: `10.0.0.0/16`
- Total Subnets: 6
- Availability Zones: 3

### Subnet Configuration

| Tier | Subnet Type | CIDR |
|---|---|---|
| Web Tier | Public | `10.0.1.0/24` |
| App Tier | Private | `10.0.2.0/24` |
| DB Tier | Private | `10.0.3.0/24` |
| Web Tier | Public | `10.0.4.0/24` |
| App Tier | Private | `10.0.5.0/24` |
| DB Tier | Private | `10.0.6.0/24` |

## 🔐 Security Configuration

| Component | Port | Allowed Source |
|---|---:|---|
| External Load Balancer | 80 | Internet |
| Web Tier | 80 | External ALB |
| Internal Load Balancer | 80 | Web Tier |
| Application Tier | 4000 | Internal ALB |
| Database Tier | 3306 | Application Tier |

🔒 The database is deployed in private subnets and is not directly accessible from the internet.

## ⚙️ Technologies Used

- ☁️ Amazon Web Services (AWS)
- 🐧 Amazon Linux
- 🟢 Node.js
- ⚛️ React.js
- 🌐 Nginx
- 🔄 PM2
- 🗄️ MySQL 8.4
- 🛠️ AWS Systems Manager
- 🔀 Application Load Balancer
- 📈 EC2 Auto Scaling

## 🚀 Project Implementation Steps

1. 🌐 Create a custom VPC and six subnets.
2. 🚪 Configure Internet Gateway and NAT Gateways.
3. 🔀 Configure route tables and security groups.
4. 🗄️ Create Amazon RDS MySQL database.
5. 🔐 Create IAM roles and policies.
6. 🪣 Create an S3 bucket and upload application source code.
7. ⚙️ Configure the application tier.
8. 🖥️ Launch application and web EC2 instances.
9. 🌐 Configure Nginx and React web tier.
10. ⚖️ Create internal and external load balancers.
11. 🎯 Configure target groups and health checks.
12. 📸 Create AMIs and launch templates.
13. 📈 Configure Auto Scaling Groups.
14. 🌍 Access and test the deployed application.
15. 🧹 Clean up AWS resources.

## 🔄 Application Traffic Flow

1. A user accesses the application through the internet.
2. The External Application Load Balancer receives the request.
3. The Web Tier serves the React application using Nginx.
4. The Internal Application Load Balancer forwards application requests.
5. The Node.js application processes the request.
6. The application communicates with Amazon RDS MySQL.
7. The response is returned to the user.

## 🔑 Secure Server Access

AWS Systems Manager Session Manager is used to access private EC2 instances.

✅ No SSH key pair required for Session Manager access.  
✅ No bastion host required.  
✅ Private servers do not need public IP addresses.

## 📚 Learning Outcomes

Through this project, I gained practical experience in:

- AWS VPC and networking.
- Public and private subnet configuration.
- EC2 instance deployment.
- RDS MySQL database connectivity.
- Application Load Balancer configuration.
- Target groups and health checks.
- IAM roles and security groups.
- Nginx and Node.js configuration.
- PM2 process management.
- Auto Scaling and high availability.
- Secure access using AWS Systems Manager.

## 📸 Project Documentation

📄 Complete implementation guide:

**AWS Three-Tier Web Application Deployment – Mohit Gadilohar**

This documentation includes step-by-step instructions, AWS configurations, terminal commands, screenshots, troubleshooting, and resource cleanup.

## 👨‍💻 Author

**Mohit Gadilohar**

🎯 Aspiring Cloud & DevOps Engineer

🎓 BSc Computer Science Graduate

🔗 **LinkedIn:**  
https://www.linkedin.com/in/mohit-gadilohar-devops

🐙 **GitHub:**  
https://github.com/mohitlohar1555-oss

---

⭐ If you find this project useful, feel free to star the repository!

**#AWS #CloudComputing #DevOps #ThreeTierArchitecture #EC2 #VPC #RDS #LoadBalancer #AutoScaling #CloudEngineer**
