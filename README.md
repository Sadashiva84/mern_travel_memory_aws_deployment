
# MERN Stack Deployment on AWS with Terraform and Ansible

## Introduction

This project demonstrates deploying a MERN (MongoDB, Express.js, React, Node.js) stack application on AWS using Terraform for infrastructure setup and Ansible for application deployment and configuration. We will deploy [TravelMemory](https://github.com/UnpredictablePrashant/TravelMemory), a simple app for storing memorable travel destinations.

## Part 1: Infrastructure Setup with Terraform

### AWS Setup and Terraform Initialization

1. **Configure AWS CLI**: Install and configure the AWS CLI tool with your AWS account credentials using `aws configure`.
2. **Terraform Initialization**: Initialize a new Terraform project with `terraform init` targeting AWS.

### VPC and Network Configuration

1. **Create AWS VPC**: Set up a VPC with two subnets (public and private) in your `main.tf` file.
2. **Internet and NAT Gateways**: Configure an Internet Gateway for the public subnet and a NAT Gateway for the private subnet.
3. **Route Tables**: Set up appropriate route tables for both subnets.

### EC2 Instance Provisioning

1. **Launch EC2 Instances**: Use Terraform to launch two EC2 instances, specifying the public subnet for the web server and the private subnet for the database server.
2. **SSH Access**: Ensure SSH access is configured correctly, with the public instance only accessible from your IP.

### Security Groups and IAM Roles

1. **Security Groups**: Define security groups for both web and database servers in Terraform scripts.
2. **IAM Roles**: Create and assign IAM roles to EC2 instances for necessary AWS resource access.

### Resource Output

- Output the public IP of the web server EC2 instance using Terraform's output feature.

## Part 2: Configuration and Deployment with Ansible

### Ansible Configuration

1. **Configure Ansible**: Ensure Ansible can communicate with AWS EC2 instances, possibly using dynamic inventories.

### Web Server Setup

1. **Node.js and NPM**: Write an Ansible playbook to install Node.js and NPM on the web server.
2. **Clone Repository**: Clone the TravelMemory repository and install dependencies.

### Database Server Setup

1. **MongoDB Installation**: Use Ansible to install and configure MongoDB on the database server.
2. **Secure MongoDB**: Configure security settings, including user and database creation.

### Application Deployment

1. **Configure Environment**: Set up necessary environment variables for the MERN application.
2. **Start Application**: Ensure the React frontend can communicate with the Express backend.

### Security Hardening

- Implement security best practices, including configuring firewalls, security groups, and SSH key pairs.

## Deliverables

- Terraform scripts for AWS infrastructure setup.
- Ansible playbooks for configuration and deployment.
- A detailed report documenting the process, interactions, and infrastructure.
- Screenshots or video demonstrating the working application.

## Steps to Run

1. **Terraform**: Navigate to the Terraform directory and run `terraform apply` to set up the AWS infrastructure.
2. **Ansible**: With the infrastructure in place, use Ansible to configure and deploy the MERN stack application by running the playbook.

## Conclusion

By following this guide, you will have a MERN stack application fully deployed and running on AWS, utilizing the power of Terraform for infrastructure automation and Ansible for configuration management.