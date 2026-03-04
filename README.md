# Terraform AWS High Availability Architecture

Production-ready AWS infrastructure built using Terraform.  
Implements a Multi-AZ architecture with Application Load Balancer, Auto Scaling Group, and private EC2 instances following AWS best practices.

---

## 🏗 Architecture Overview

This project provisions:

- VPC
- 2 Public Subnets (Multi-AZ)
- 2 Private Subnets (Multi-AZ)
- Internet Gateway
- NAT Gateway (optional)
- Application Load Balancer (Public)
- Auto Scaling Group
- Private EC2 Instances

### Architecture Flow

Internet  
↓  
Application Load Balancer (Multi-AZ)  
↓  
Target Group  
↓  
Auto Scaling Group  
↓  
EC2 Instances (Private Subnets)

---

## 📦 Project Structure

```
terraform-aws-ha-architecture/
│
├── environments/
│   ├── dev/
│   └── prod/
│
├── global/
│
└── modules/
    ├── vpc/
    ├── alb/
    ├── autoscaling/
    └── ec2/
```

---

## 🚀 Features

- Multi-AZ High Availability
- Load Balancing using Application Load Balancer
- Automatic scaling based on demand
- Secure architecture (no public EC2)
- Modular Terraform design
- Environment separation (dev & prod ready)

---

## 🔐 Security Best Practices

- EC2 instances are deployed in private subnets
- Only ALB is publicly accessible
- Security Groups restrict inbound traffic
- Optional NAT Gateway for outbound internet access

---

## 🛠 Requirements

- Terraform >= 1.5
- AWS CLI configured
- AWS Account

---

## ⚙️ Usage

### 1. Clone Repository

```bash
git clone https://github.com/yourusername/terraform-aws-ha-architecture.git
cd terraform-aws-ha-architecture
```

### 2. Initialize Terraform

```bash
cd environments/dev
terraform init
```

### 3. Plan Infrastructure

```bash
terraform plan
```

### 4. Apply Infrastructure

```bash
terraform apply
```

---

## 🌍 Environments

- `dev` — Development environment
- `prod` — Production environment

Each environment has its own:
- backend configuration
- variables
- state management

---

## 📈 Future Improvements

- Add RDS Multi-AZ
- Add CloudWatch monitoring
- Add WAF
- Implement CI/CD pipeline
- Add ECS or EKS deployment

---

## 🧠 Author

Built for learning and production-grade AWS architecture practice.