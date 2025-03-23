<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/8/89/John_bryce_logo.jpg" alt="Logo" width="259" height="107">
</p>  

| Last update | 25/03/2025  |
|-------------|-------------|

# Lab 03 - Getting Started with AWS VPC  
Amazon VPC (Virtual Private Cloud) is a foundational networking service in AWS that allows you to create isolated virtual networks in the cloud.
It enables you to control your networking environment, including IP ranges, subnets, route tables, and gateways.  
In this lab, you will learn how to create a VPC from scratch, define public and private subnets, and configure basic routing and internet access.

### Estimated time: 60 minutes

## Overview
**Task 1:** Create a custom VPC with CIDR block 10.0.0.0/16  
**Task 2:** Create a public subnet and a private subnet  
**Task 3:** Create and attach an Internet Gateway  
**Task 4:** Configure route tables for public and private subnets  
**Task 5:** Launch an EC2 instance in the public subnet to test internet connectivity  

---

## Task 1: Create a Custom VPC

### In this task, you will create a custom VPC with your own IP address range.

1. Go to the [AWS Management Console](https://console.aws.amazon.com/), log in, and search for **VPC** in the search bar.
2. In the left menu, click **Your VPCs**.
3. Click **Create VPC**.
4. Choose **VPC only** option.
5. Enter the following:
   - **Name tag**: `LabVPC`
   - **IPv4 CIDR block**: `10.0.0.0/16`
   - Leave IPv6 CIDR and other settings as default.
6. Click **Create VPC**.

---

## Task 2: Create Public and Private Subnets

### Subnets divide your VPC into smaller IP ranges. Here you'll create one public and one private subnet.

1. In the VPC Dashboard, click **Subnets > Create subnet**.
2. Select the VPC you created: `LabVPC`.
3. Create two subnets:
   - **Public Subnet**:
     - Name: `PublicSubnet`
     - Availability Zone: choose one (e.g. us-east-1a)
     - CIDR block: `10.0.1.0/24`
   - **Private Subnet**:
     - Name: `PrivateSubnet`
     - Availability Zone: choose one (e.g. us-east-1b)
     - CIDR block: `10.0.2.0/24`
4. Click **Create subnet**.

---

## Task 3: Create and Attach an Internet Gateway

### An Internet Gateway enables instances in your VPC to connect to the internet.

1. In the VPC Dashboard, click **Internet Gateways**.
2. Click **Create internet gateway**.
3. Name it: `LabIGW`, then click **Create**.
4. Select it, then click **Actions > Attach to VPC**.
5. Choose your `LabVPC` and click **Attach internet gateway**.

---

## Task 4: Configure Route Tables

### You will now configure routing so only the public subnet has access to the internet.

1. In the VPC Dashboard, click **Route Tables**.
2. You’ll see a route table automatically created with your VPC. Rename it to `PublicRouteTable`.
3. Select it and go to the **Routes** tab.
4. Click **Edit routes > Add route**:
   - Destination: `0.0.0.0/0`
   - Target: your Internet Gateway (e.g., `igw-xxxxx`)
5. Click **Save routes**.
6. Now go to the **Subnet associations** tab > **Edit subnet associations**.
7. Select only the `PublicSubnet` and save.

The private subnet will remain without internet access for now.

---

## Task 5: Launch EC2 Instance in Public Subnet

### Finally, you'll launch a test EC2 instance in the public subnet to verify connectivity.

1. Go to the **EC2** service in the AWS Console.
2. Click **Launch instance**.
3. Use the following settings:
   - Name: `VPC-Test-Instance`
   - AMI: `Amazon Linux 2023` (or any available Amazon Linux)
   - Instance type: `t2.micro`
   - Key pair: choose or create one
   - Network: choose `LabVPC`
   - Subnet: choose `PublicSubnet`
   - Auto-assign public IP: **Enable**
   - Security group: create one that allows SSH from your IP
4. Launch the instance.
5. After it runs, connect via SSH and run:
   ```bash
   ping google.com
   ```
   If you get replies, your setup is correct!

---

## ✅ End of Lab

🎉 Congratulations! You’ve successfully created your first custom VPC with subnets, routing, and internet access. 

You now understand the basics of networking in AWS and how to isolate resources using subnets and route tables.
