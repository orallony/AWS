

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/8/89/John_bryce_logo.jpg" alt="Logo" width="259" height="107">
</p>  

| Last update | 26/03/2025  |
|-------------|-------------|

# Lab 01 - Launching Amazon EC2 instance  
This tutorial is designed for beginners with no prior experience using Amazon EC2. We'll guide you through the steps for creating—we call it launching—your very first EC2 instance using the EC2 console. An instance is essentially a web server in the AWS Cloud. After launching your instance, we'll show you how to find it in the console. Finally, to help you manage costs, we'll show you how to delete—we call it terminate—your instance.

## Estimated time: 50 minutes
## Overview
**Task 1:** Launch your instance

**Task 2:** Find your instance

**Task 3:** View your instance configuration

**Task 4:** Terminate your instance

## Task 1: Launching a Windows EC2 instance 

#### In this task, you'll take the quickest path to launching your instance by doing only the essentials. We'll use the EC2 launch instance wizard, a web-based form that provides all the fields for configuring and launching your instance. It simplifies the process by providing default values for the instance configuration fields.  
1. Log in to the AWS Management Console using your AWS credentials.

2. Open the EC2 launch instance wizard:

From the EC2 dashboard, choose **Launch instance**.

The Launch an instance web-based form opens. This is the EC2 launch instance wizard.

3. **Name your instance:**

Under **Name and tags**, for **Name**, enter a descriptive name like `My first EC2 instance`.

While naming your instance isn't required, it helps identify your instance later.

4. **Proceed without a key pair:**

Under **Key pair (login)**, for **Key pair name**, choose **Proceed without a key pair (Not recommended)**.

A key pair can be used for secure login. However, because we won't be logging into the instance in this tutorial, you don't need a key pair for now.

5. **Launch your instance:**

In the **Summary** panel on the right, choose **Launch instance**.

Amazon EC2 quickly launches your instance using the default settings. A **Success** banner confirms the launch.

## Task 2: Find your instance  

#### In this task, you'll locate the instance that you just launched in the EC2 console.

1. Open the **Instances page**:

If you're still on the success page, choose **Instances** in the breadcrumb at the top of the screen. You might need to choose the three ellipses first to access it.

If you've navigated away, choose Instances from the navigation pane.

2. **Locate your instance:**

In the **Name** column, find your instance by the name you gave it.

## Task 3: View your instance configuration  

#### In this task, you'll become familiar with viewing your instance's configuration details.

1. **Locate the instance ID:**  
   In the **Instance ID** column, take note of your instance's unique ID. It begins with **i-** followed by 17 alphanumeric characters, for example, **i-01aeed690c9fb5322**.  
   The instance ID is automatically assigned to your instance when it's launched.

2. **Open the instance details page:**  
   In the **Instance ID** column, choose the ID link to open the instance details page where you can review its configuration.

3. **Explore instance configuration details:**  
   Take a few minutes to explore the configuration details of your instance. In the next tutorial, we'll dive deeper into the configuration. For now, use this time to familiarize yourself with the instance details page.

   **Tip:** To quickly find a field, press Ctrl+F or command+F on your keyboard.

   a. **Instance type:** Can you find the instance type? It's either **t2.micro** or **t3.micro**.  
   b. **Public IPv4 address:** Can you find the public IPv4 address that was allocated to your instance? It's in a format similar to the following example: **34.242.148.128**.  
   c. **Instance owner:** Can you identify the owner of this instance? It's you! Your AWS account number is listed under the **Owner** field.  
   d. **Instance tags:** The name you gave your instance is actually a tag. Can you find your instance tags? Choose the **Tags** tab. The key is **Name**, and the value is the name you provided.  
   e. **Launch time:** Can you find when you launched your instance? Choose the **Details** tab and find the **Launch time** field.  
   f. **Instance state:** Can you verify the state of your instance? It should be **Running**.

Take a few more minutes to explore the other instance configuration fields. When you're ready, proceed to the next task.


## Task 4: Terminate your instance

#### In this task, you'll delete your instance to preserve your Free Tier benefits. In EC2, terminate is the term used for deleting an instance.

1. **Initiate termination:**  
   If you're still on the instance details page, choose the **Instance state** menu (top right), and then choose **Terminate (delete) instance**.  
   If you've navigated away, choose **Instances** from the navigation pane. Then, on the **Instances** page, select the checkbox next to the name of your instance, and then choose the **Instance state** menu (top right), and choose **Terminate (delete) instance**.

2. **Confirm termination:**  
   In the **Terminate (delete) instance** window that opens, choose the **Terminate (delete)** button to confirm that you want to terminate your instance.

3. **Monitor instance state:**  
   On the **Instances** page, check the **Instance state** column. The state of your instance changes to **Shutting-down**. If you don't see the full text, try widening the column.  
   Once the instance has shut down, Amazon EC2 deletes the instance, and it disappears from the **Instances** page.


## ✅ End of Lab  

#### 🎉 Congratulations! You’ve completed the AWS EC2 Lab.
