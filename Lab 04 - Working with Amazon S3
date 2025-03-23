<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/8/89/John_bryce_logo.jpg" alt="Logo" width="259" height="107">
</p>  

| Last update | 25/03/2025  |
|-------------|-------------|

# Lab 04 - Getting Started with Amazon S3  
Amazon S3 (Simple Storage Service) is a foundational object storage service in AWS that allows you to store and retrieve any amount of data, at any time, from anywhere on the web.
It is designed for durability, availability, and scalability, and is commonly used for backup, data archiving, hosting static websites, and more.  
In this lab, you will learn how to create and configure an S3 bucket, upload and manage files, set permissions, and enable static website hosting.

### Estimated time: 45 minutes

## Overview
**Task 1:** Create an S3 bucket  
**Task 2:** Upload and manage files  
**Task 3:** Set permissions and test access  
**Task 4:** Enable static website hosting  

---

## Task 1: Create an S3 Bucket

### In this task, you’ll create a new S3 bucket to store files.

1. Go to the [AWS Management Console](https://console.aws.amazon.com/) and log in.
2. In the search bar at the top, type `S3` and click on **S3**.
3. Click the **Create bucket** button.
4. Use the following settings:
   - **Bucket name**: must be globally unique, e.g., `jb-lab-s3-demo-[yourname]`
   - **Region**: choose your closest AWS region (e.g., us-east-1)
   - Leave **Block all public access** checked for now
5. Scroll down and click **Create bucket**.

✅ Your new bucket is now ready to use.

---

## Task 2: Upload and Manage Files

### Now you’ll upload a file to your bucket and view it.

1. Click on your new bucket’s name in the S3 Dashboard.
2. Click the **Upload** button.
3. Drag and drop a file (e.g., image, text, PDF) or use **Add files** to choose one.
4. Click **Upload** at the bottom of the page.
5. After the upload finishes, click on the file name to view details.

✅ You can now see file metadata and access options.

---

## Task 3: Set Permissions and Test Access

### You will now make the file publicly accessible.

1. While viewing the file in your bucket, go to the **Permissions** tab.
2. Scroll down to **Object Ownership** and ensure it’s set to **ACLs enabled** (if needed, adjust bucket settings).
3. Click **Edit** under **Access control list (ACL)**.
4. Under **Everyone (public access)**, check **Read**.
5. Save changes.
6. Go back to the **Properties** tab and copy the **Object URL**.
7. Paste the URL into a new browser tab to verify public access.

✅ If the file loads in the browser, permissions are working correctly.

---

## Task 4: Enable Static Website Hosting

### S3 can host static websites (HTML/CSS/JS) without a web server.

1. Go to the **Properties** tab of your bucket.
2. Scroll to **Static website hosting** and click **Edit**.
3. Enable it and set:
   - **Index document**: `index.html`
   - (Optional) **Error document**: `error.html`
4. Save changes.
5. Upload `index.html` (and optionally `error.html`) to the root of your bucket.
6. Make both files public using the same method as in Task 3.
7. Copy the **Bucket website endpoint** and open it in a browser.

✅ Your static site is now live on S3!

---

## ✅ End of Lab

🎉 Congratulations! You’ve completed the Amazon S3 Lab.

You now know how to:
- Create and configure S3 buckets
- Upload and manage objects
- Set permissions for public access
- Use S3 to host static websites

Amazon S3 is one of the most versatile and widely-used services in AWS. Great job!
