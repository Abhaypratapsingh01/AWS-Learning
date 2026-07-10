# AWS VPC with Public and Private Subnets

This project demonstrates how to create a Virtual Private Cloud (VPC) using the AWS VPC Wizard. Inside the VPC, one Public Subnet and one Private Subnet are created. A Windows EC2 instance is launched in the Public Subnet, while an Amazon Linux EC2 instance is launched in the Private Subnet. Finally, network connectivity between both instances is verified using ICMP (Ping).

---

# Architecture Diagram

![Architecture Diagram](images/architecture diagram.png)

---

# Project Objective

The objective of this project is to understand how networking works in AWS by creating a custom VPC, deploying EC2 instances in different subnets, and verifying communication using private IP addresses.

---

# AWS Services Used

- Amazon VPC
- Amazon EC2
- Internet Gateway
- Route Tables
- Security Groups
- Remote Desktop Protocol (RDP)
- Secure Shell (SSH)

---

# Architecture Overview

| Resource | Details |
|----------|---------|
| VPC | 10.0.0.0/16 |
| Public Subnet | Windows EC2 Instance |
| Private Subnet | Amazon Linux EC2 Instance |
| Internet Gateway | Internet access for Public Subnet |
| Route Tables | Public and Private Routing |
| Security Groups | Control inbound and outbound traffic |

---

