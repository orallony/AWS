<img src="https://upload.wikimedia.org/wikipedia/commons/8/89/John_bryce_logo.jpg" alt="Logo" width="259" height="107">

![logo](https://upload.wikimedia.org/wikipedia/commons/8/89/John_bryce_logo.jpg)
# Lab 01 - Launching Amazon EC2 instance
## Lab introduction
This hands-on lab introduces you to Amazon EC2 (Elastic Compute Cloud), one of the core services in AWS. You will learn how to launch, configure, connect to, and monitor a Windows-based EC2 instance using essential AWS tools and best practices.
## Estimated time: 50 minutes
## Job skills
Task 1: Launching a Windows EC2 instance  
Task 2: Connecting to the instance via Remote Desktop (RDP)  
Task 3: Configuring Security Group rules  
Task 4: Allocating and assigning an Elastic IP  
Task 5: Monitoring the instance using Amazon CloudWatch  

select `orallony`
| Option           | Value                                 |
|------------------|----------------------------------------|
| Resource Group   | `az104-rg4` (if necessary, create new) |
| Name             | `CoreServicesVnet`                     |
| Region           | (US) **East US**                       |
```powershell
# Sign in to Azure
Connect-AzAccount
