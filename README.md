<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/8/89/John_bryce_logo.jpg" alt="Logo" width="259" height="107">
</p>  

| Last update | 25/03/2025  |
|-------------|-------------|

# Lab 01 - Launching Amazon EC2 instance  
Amazon EC2 (Elastic Compute Cloud) is a foundational service in AWS that allows you to run virtual machines in the cloud.   
In this lab, you will learn how to create, configure, and manage a Windows-based EC2 instance using the AWS Management Console.

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

2. From the AWS Console homepage, navigate to **EC2** by typing `EC2` in the search bar.
3. Click **Launch instance** to begin the process of creating a virtual machine.  
4. In the **Name and tags** section, enter a name for your instance: `MyWindowsInstance`.
5. Under **Application and OS Images (AMI)**, select **Microsoft Windows Server 2019 Base** as the image.
6. For Instance type, select **t2.micro**. This instance type includes 1 vCPU and 1 GiB of memory.
7. Under **Key pair (login)**, click **Create new key pair**
     
| Setting                  | Value      |
|:-------------------------|:-----------|
| Name                     | `ec2lab-key` |
| Key pair type            | **RSA**        |
| Private key file format  | **.pem**       |
| Key pair type            | **RSA**        |

8. In **Network settings**, keep the default VPC and subnet.
   Make sure **Auto-assign public IP** is enabled so your instance can be reached from the internet.
9. Under **Firewall (security groups)**, click **Create security group**.
10. Under **Name** type `ec2lab-sg`.
11. Add one inbound rule: 🟢

    | Setting                  | Value      |
|:-------------------------|:-----------|
| Type                     | `RDP` |
| Port range            | **3389**        |
| Source  | **My IP**       |

12. Under **Storage**, leave:
    - 30 GiB
    - gp2 (General Purpose SSD)
    - Delete on termination: enabled
13. Click **Launch Instance**.

---

### 🟢 Task 2: Connect to the Windows EC2 Instance

This task will guide you through accessing your Windows EC2 instance remotely using Remote Desktop Protocol (RDP).

1. In the EC2 Dashboard, go to **Instances**.
2. Wait until the instance is **Running** and **2/2 checks passed**.
3. Select the instance and click **Connect**.
4. In the Connect tab, choose **RDP client**.
5. Click **Get Password**.
6. Upload your `.pem` file to decrypt the Administrator password.
7. Copy the public DNS/IP and the password.
8. Open **Remote Desktop Connection** (Windows: `mstsc`, macOS: Microsoft Remote Desktop).
9. Paste the IP and use the username `Administrator` with the decrypted password.
10. Click **Connect** and accept the certificate warning.

---

### 🟢 Task 3: Configure Security Group Rules

You will configure firewall rules (inbound access) for your EC2 instance using Security Groups.

1. In the EC2 Dashboard, go to **Security Groups**.
2. Select the security group `ec2lab-sg`.
3. Go to the **Inbound rules** tab.
4. Click **Edit inbound rules**.
5. Add the following rules:
   - RDP: TCP 3389 | Source: My IP
   - (Optional) HTTP: TCP 80 | Source: Anywhere (for web server access)
   - (Optional) HTTPS: TCP 443 | Source: Anywhere (for HTTPS access)
6. Click **Save rules**.

---

### 🟢 Task 4: Allocate and Associate an Elastic IP

In this task, you will assign a static public IP address to your EC2 instance.

1. In the EC2 Dashboard, go to **Elastic IPs** (left menu).
2. Click **Allocate Elastic IP address** > Leave default settings > Click **Allocate**.
3. Select the allocated IP > Click **Actions > Associate Elastic IP address**.
4. Choose your EC2 instance and private IP.
5. Click **Associate**.

💡 You now have a static public IP for your instance — useful for DNS, monitoring, and persistent remote access.

---

### 🟢 Task 5: Monitor EC2 Performance with CloudWatch

This task focuses on viewing and monitoring the instance's resource usage via CloudWatch.

1. From the AWS Console, go to **CloudWatch**.
2. Navigate to **Metrics > All metrics > EC2 > Per-Instance Metrics**.
3. Select your EC2 instance to view:
   - CPUUtilization
   - NetworkIn / NetworkOut
   - DiskReadBytes / DiskWriteBytes
4. To create an alert:
   - Go to **Alarms > Create Alarm**
   - Choose `CPUUtilization` > Set condition: greater than 80% for 5 minutes
   - Set up email notification using SNS
   - Review and create the alarm

This allows proactive monitoring and alerting when thresholds are exceeded.

---

### ✅ End of Lab

You have successfully completed a hands-on lab using EC2 in AWS. You launched, configured, secured, connected to, and monitored a Windows EC2 instance.

Click Launch Instance.
```powershell
# Sign in to Azure
Connect-AzAccount
