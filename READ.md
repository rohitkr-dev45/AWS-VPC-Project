# Project 3: Multi-Tier AWS Network

Rohit

## Objective
Design a custom VPC with a public subnet, enabling internet access for an EC2 instance using an Internet Gateway and Route Table configuration.

## AWS Services Used
- VPC (Virtual Private Cloud)
- Subnet
- Route Table
- Internet Gateway
- EC2 (Elastic Compute Cloud)

## Steps Performed

### 1. Created a Custom VPC
- VPC Name: `MyCustomVPC`
- CIDR Block: `10.0.0.0/16`

### 2. Created a Public Subnet
- Subnet Name: `PublicSubnet`
- CIDR Block: `10.0.1.0/24`
- Associated with `MyCustomVPC`

### 3. Created and Attached an Internet Gateway
- IGW Name: `MyIGW`
- Attached to `MyCustomVPC`

### 4. Created a Route Table
- Route Table Name: `PublicRouteTable`
- Added route: `0.0.0.0/0` → Target: `MyIGW`
- This allows internet-bound traffic to flow through the Internet Gateway

### 5. Associated Route Table with Public Subnet
- Associated `PublicRouteTable` with `PublicSubnet`
- This makes the subnet "public" by giving it internet access

### 6. Launched an EC2 Instance
- Instance Name: `MyPublicEC2`
- AMI: Amazon Linux 2023
- Instance Type: t2.micro (Free Tier)
- Deployed in `PublicSubnet` within `MyCustomVPC`
- Auto-assign Public IP: Enabled
- Security Group: Allowed SSH (port 22)

## Result
Successfully created a custom VPC architecture with a public subnet that has internet connectivity via an Internet Gateway and Route Table. The EC2 instance launched in this subnet received a public IP address, confirming successful internet access.

## Screenshots
All screenshots documenting each step (VPC creation, subnet creation, IGW attachment, route table configuration, subnet association, and EC2 instance running) are included in this repository.
