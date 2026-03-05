# AWS-Infrastructure-Automation-using-Terraform

Project Overview

This project demonstrates how to automate AWS infrastructure provisioning using Terraform.

Using Terraform, the following AWS resources were automatically created:

VPC (Virtual Private Cloud)

EC2 Web Servers

Security Groups

Application Load Balancer

Target Groups

S3 Bucket

The infrastructure deploys two web servers behind a load balancer, allowing users to access the application using the Load Balancer DNS.



Technologies Used

AWS EC2

AWS VPC

AWS Application Load Balancer

AWS S3

Terraform

Linux

IAM

Project Architecture:-

                Internet
                    │
                    ▼
          Application Load Balancer
                    │
        ┌───────────┴───────────┐
        ▼                       ▼
    EC2 Web Server 1       EC2 Web Server 2
        │                       │
        └───────────VPC─────────┘


Step 1: Configure IAM User

An IAM user was created with required permissions for Terraform.

Policies attached:

AmazonEC2FullAccess

IAMFullAccess

AWSCloudFormationFullAccess

AmazonEKSClusterPolicy

AmazonEKSWorkerNodePolicy

This user allows Terraform to provision AWS resources.


Step 2: Create Terraform Project Structure

Project files used:

terraform-demo
│
├── main.tf
├── provider.tf
├── variables.tf
├── userdata.sh
├── userdata1.sh
└── aws-cli-v2.zip

These files define the infrastructure configuration.

Step 3: Initialize Terraform

Terraform was initialized to download provider plugins.

terraform init


Step 4: Terraform Execution Plan

Terraform shows the resources that will be created.

terraform plan

Step 5: Deploy Infrastructure

The infrastructure was deployed using:

terraform apply

Terraform asks for confirmation.

Enter a value: yes

After execution, AWS resources are created automatically.



Step 6: Resources Created

Terraform created the following resources:

AWS VPC

Subnets

Security Groups

EC2 Instance 1

EC2 Instance 2

Application Load Balancer

Target Groups

S3 Bucket



Step 7: Access Web Application

After deployment, Terraform generated a Load Balancer DNS.

Example:

myalb-941958402.us-east-1.elb.amazonaws.com

Opening the URL shows:

Hello from Web Server 1

The load balancer distributes traffic across the EC2 instances.















