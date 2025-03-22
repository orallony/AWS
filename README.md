<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/8/89/John_bryce_logo.jpg" alt="Logo" width="259" height="107">
</p>

# Lab 01 - Launching Amazon EC2 instance
## Lab introduction
This hands-on lab introduces you to Amazon EC2 (Elastic Compute Cloud), one of the core services in AWS. You will learn how to launch, configure, connect to, and monitor a Windows-based EC2 instance using essential AWS tools and best practices.
## Estimated time: 50 minutes
## Overview
Task 1: Launching a Windows EC2 instance  
Task 2: Connecting to the instance via Remote Desktop (RDP)  
Task 3: Configuring Security Group rules  
Task 4: Allocating and assigning an Elastic IP  
Task 5: Monitoring the instance using Amazon CloudWatch

## Task 1: Launching a Windows EC2 instance  
In this task, you will launch a new Windows-based virtual machine (EC2 instance) in AWS. This is the foundation for all following tasks.  
1. Log in to the AWS Management Console - `https://eu-north-1.signin.aws.amazon.com/` using your AWS credentials:
 
| Username   | Password   |
|------------|------------|
| `username` | `password` |

2. From the AWS Console homepage, navigate to *EC2* by typing "EC2" in the search bar. 
4. Navigate to EC2 > Instances > Click Launch instance.

Name and tags: Enter a name for your instance (e.g., MyWindowsInstance).

Application and OS Images (AMI):

Choose an AMI: Select Microsoft Windows Server 2019 Base or any Windows version you prefer.

Instance type:

Choose t2.micro (Free Tier eligible).

Key pair (login):

Choose an existing key pair or create a new one. Download the .pem file if creating a new key.

Network settings:

Select the default VPC and subnet.

Enable Auto-assign public IP.

Create or select a Security Group (details in Task 3).

Storage:

Default settings are fine (e.g., 30 GiB gp2).

Click Launch Instance.

select `orallony`
| Option           | Value                                 |
|------------------|----------------------------------------|
| Resource Group   | `az104-rg4` (if necessary, create new) |
| Name             | `CoreServicesVnet`                     |
| Region           | (US) **East US**                       |
```powershell
# Sign in to Azure
Connect-AzAccount
