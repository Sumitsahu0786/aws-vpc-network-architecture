# aws-vpc-network-architecture
AWS VPC network architecture with 8 subnets across 2 Availability Zones, including Public, Private Application, Database, and Middleware subnets, Internet Gateway, NAT Gateways, Route Tables, and infrastructure diagram.
# AWS VPC Network Architecture – Multi-AZ Infrastructure

## Project Overview

This project demonstrates the design and implementation of a scalable AWS VPC network architecture with a CIDR block of `10.0.0.0/17`, supporting more than 20,000 IP addresses.

The VPC is divided into 8 subnets across 2 Availability Zones to provide network segmentation, isolation, and high availability.

## AWS Architecture Diagram

![AWS VPC Infrastructure Architecture](diagrams/aws-vpc-architecture.png)

## Project Requirements

- AWS VPC with CIDR `10.0.0.0/17`
- 2 Availability Zones
- 2 Public Subnets
- 2 Private Application Subnets
- 2 Private Database Subnets
- 2 Private Middleware Subnets

## Subnet Configuration

| Subnet Type | Availability Zone | CIDR Block |
|---|---|---|
| Public | AZ-1 | 10.0.0.0/25 |
| Public | AZ-2 | 10.0.0.128/25 |
| Application | AZ-1 | 10.0.8.0/21 |
| Application | AZ-2 | 10.0.16.0/21 |
| Database | AZ-1 | 10.0.24.0/23 |
| Database | AZ-2 | 10.0.26.0/23 |
| Middleware | AZ-1 | 10.0.28.0/22 |
| Middleware | AZ-2 | 10.0.32.0/22 |

## AWS Services Used

- Amazon VPC
- Public and Private Subnets
- Availability Zones
- Internet Gateway (IGW)
- NAT Gateways
- Route Tables
- Elastic IP Addresses
- VPC DNS Settings
- AWS Resource Tags

## Network Architecture

### 1. Public Subnets
Configured two public subnets with Internet Gateway connectivity through the public route table.

### 2. Private Application Subnets
Configured two private application subnets with NAT Gateway-based outbound internet connectivity.

### 3. Private Database Subnets
Configured two isolated database subnets with local VPC routing only.

### 4. Private Middleware Subnets
Configured two isolated middleware subnets with local VPC routing only.

## Subnet Tags

| Tag Key | Tag Value |
|---|---|
| type | public |
| type | application |
| type | database |
| type | middleware |

## Key Learnings

- AWS VPC creation and configuration
- CIDR calculation and subnet planning
- IP address management
- Multi-AZ network architecture
- Public and private subnet configuration
- Internet Gateway and NAT Gateway
- Route table configuration and subnet association
- Network segmentation and isolation

## Project Implementation

The infrastructure was created and configured using the AWS Management Console.

Refer to the `screenshots/` and `documentation/` directories for implementation evidence and configuration details.

## Future Improvements

- Deploy EC2 instances in application subnets.
- Configure security groups and network ACLs.
- Deploy an Application Load Balancer.
- Configure RDS in private database subnets.
- Implement infrastructure as code using Terraform.

## Author

Cloud & DevOps Engineering Learner

## Disclaimer

This project is created for educational and hands-on AWS networking practice.
