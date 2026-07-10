# AWS VPC with Public and Private Subnets

This project demonstrates how to create a Virtual Private Cloud (VPC) using the AWS VPC Wizard. Inside the VPC, one Public Subnet and one Private Subnet are created. A Windows EC2 instance is launched in the Public Subnet, while an Amazon Linux EC2 instance is launched in the Private Subnet. Finally, network connectivity between both instances is verified using ICMP (Ping).

---

# Architecture Diagram

![Architecture Diagram](images/architecture-diagram.png)

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

# Step 1: Create VPC

A  VPC was created using the AWS VPC Wizard. The wizard automatically created the required networking resources such as Internet Gateway, Route Tables, and Subnets.

### Configuration

- VPC Name : My-VPC
- IPv4 CIDR : 10.0.0.0/16

### Resources Created

- One Public Subnet
- One Private Subnet
- Internet Gateway
- Public Route Table
- Private Route Table

### Screenshot

![VPC](images/vpc-created.png)

---

# Step 2: Verify Subnets

The VPC contains two subnets.

### Public Subnet

- Used for internet-facing resources.
- Windows EC2 instance is deployed here.
- Connected to the Internet Gateway through the Public Route Table.

### Private Subnet

- Used for internal resources.
- Amazon Linux EC2 instance is deployed here.
- Does not have a public IP address.

### Screenshot

![Subnets](images/subnets.png)

---

# Step 3: Launch Windows EC2 Instance

A Windows Server instance was launched inside the Public Subnet.

### Configuration

- Operating System : Windows Server 2022
- Public IP : Enabled
- Private IP : Automatically Assigned

### Security Group Rules

| Type | Port | Source |
|------|------|--------|
| RDP | 3389 | My IP |
| ICMP | All | Linux Security Group |

### Purpose

The Windows instance acts as the public machine that can be accessed over the internet using Remote Desktop (RDP).

### Screenshot
[Windows Instance](images/windows-instance.png)

---

