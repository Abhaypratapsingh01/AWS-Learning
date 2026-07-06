# AWS Secure Web Application Deployment

## Project Overview

This project demonstrates how to securely deploy a web application on AWS using a Bastion Host, Public and Private Subnets.

The infrastructure is designed to meet the following requirements:

- Internet users can access the web application.
- Database server is deployed in a private subnet.
- Administrator can access private instances only through a Bastion Host.
- Private instances can access the internet using a NAT Gateway for software updates.

## AWS Services Used

- Amazon VPC
- Public & Private Subnets
- Internet Gateway
- NAT Gateway
- Route Tables
- Security Groups
- Amazon EC2
- Elastic IP

- ## Architecture Diagram

The following architecture shows the complete network design of the project. The web server is deployed in the public subnet, while the database server is deployed in the private subnet. Administrative access is provided through a Bastion Host, and private instances access the internet through a NAT Gateway.

[Architecture Diagram](images/architecture.png)

# Step 1: Create a Virtual Private Cloud (VPC)

The first step was to create a Virtual Private Cloud (VPC) with the CIDR block **10.0.0.0/16**. The VPC provides an isolated networking environment where all AWS resources are deployed securely.

**Purpose:**
- Provides network isolation.
- Allows creation of public and private subnets.
- Enables secure communication between AWS resources.

  [VPC](images/VPC.png)

  ---

# Step 2: Create Public and Private Subnets

After creating the VPC, two subnets were created to separate public-facing resources from internal resources.

### Public Subnet
- CIDR Block: **10.0.1.0/24**
- Used for:
  - Bastion Host
  - Web Server
  - NAT Gateway

### Private Subnet
- CIDR Block: **10.0.2.0/25**
- Used for:
  - Database Server

This design improves security by ensuring that sensitive resources remain inaccessible from the public internet.

![Subnets](images/subnet.png)

---

# Step 3: Attach an Internet Gateway

An Internet Gateway (IGW) was attached to the VPC to provide internet connectivity for resources deployed in the public subnet.

Without an Internet Gateway, the web server cannot receive requests from internet users.

### Result
- Public Subnet can communicate with the Internet.
- Web Server becomes accessible through its Public IP.

![Internet Gateway](images/internet-gateway.png)
