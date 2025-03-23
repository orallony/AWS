<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/8/89/John_bryce_logo.jpg" alt="Logo" width="259" height="107">
</p>  

| Last update | 25/03/2025  |
|-------------|-------------|

# Lab 02 - Getting Started with AWS IAM  
AWS IAM (Identity and Access Management) is a foundational service in AWS that allows you to manage users, groups, and permissions for secure access control.
It helps ensure that only the right people have the right access to the right resources.     
In this lab, you will learn how to create, configure, and manage IAM users and groups using the AWS Management Console.
###  Estimated time: 50 minutes
## Overview
**Task 1:** Create an IAM user with limited permissions
  
**Task 2:** Create a group and assign permissions to it
  
**Task 3:** Add the user to the group
 
**Task 4:** Sign in as the IAM user 
 
**Task 5:** Observe permission restrictions in action  

## Task 1: Create an IAM User

### In this task, you’ll create a new IAM user in your AWS account. IAM users are identities that represent people (like you or your teammates) who need to access AWS.

1. Open your browser and go to the [AWS Management Console](https://console.aws.amazon.com/).

2. Log in using your root user email and password (this is the main account owner).

3. In the top search bar, type `IAM` and click on **IAM**.

4. You’ll be taken to the IAM Dashboard. On the left menu, click **Users**.

5. Click the **Add users** button.

6. Under **User name**, type: `lab-student`. This is the name of the new user.

7. Under **Select AWS access type**, check the box for **AWS Management Console access**. This allows the user to sign in to the web interface.

8. For **Console password**, select **Custom password** and enter: `LabStudent123!` (or choose another strong password).

9. Uncheck the option **Require password reset** (so the user can log in immediately).

10. Click **Next** to move to the permissions step (we’ll assign those later).

11. On the permissions page, click **Next** again to skip adding permissions for now.

12. On the tags page, click **Next**.

13. On the review screen, confirm the details, then click **Create user**.


## Task 2: Create a Group and Attach Permissions  

### IAM groups let you manage permissions for multiple users at once. Instead of assigning policies to each user individually, you can assign them to a group, and then add users to that group.

1. From the IAM Dashboard, click **User groups** on the left menu.

2. Click the orange **Create group** button.

3. For the **Group name**, type: `ReadOnlyGroup`. This group will have read-only access to AWS services.

4. On the **Attach permissions policies** screen, use the search bar to find `ReadOnlyAccess`.

5. Check the box next to **ReadOnlyAccess** — this policy allows users to view AWS resources, but not change or delete anything.

6. Click **Next** (skip tags).

7. Click **Create group**.

## Task 3: Add the User to the Group  

### Now you’ll add the user `lab-student` to the `ReadOnlyGroup`. This means the user will automatically inherit all permissions attached to the group.  

1. Go to the **Users** section from the left menu.

2. Click on the username `lab-student`.

3. On the user's summary page, go to the **Groups** tab.

4. Click the **Add user to groups** button.

5. Check the box next to `ReadOnlyGroup`.

6. Click **Add to groups**.

## Task 4: Sign In as the IAM User

### In this step, you’ll sign in to the AWS Console as the IAM user you created and see what it looks like.

1. Return to the **IAM Dashboard** as the root user.

2. On the home screen, look for **IAM users sign-in link**.

3. Click the **Copy link** button and paste the URL into a new browser tab or window.

>**Note:** This URL is unique to your AWS account. It takes you to the IAM login screen.

4. Sign in using the credentials:
   - **Username**: `lab-student`
   - **Password**: `LabStudent123!`

5. You will now be logged in as the IAM user.

## Task 5: Test Permission Restrictions

### Now we will see how the IAM policy actually works. Since `lab-student` has **read-only** permissions, they can see services but **not make any changes**.

1. While logged in as `lab-student`, open the AWS Console and search for **EC2**.

2. Click on the **EC2** service to open the dashboard.

3. Try clicking the **Launch Instance** button.

4. You should receive an error message saying you are not authorized.

5. Go to the **S3** service (use the search bar again).

6. You might be able to see a list of S3 buckets, but you won’t be able to create a new bucket or delete anything.

## ✅ End of Lab

🎉 Congratulations! You’ve completed the AWS IAM Lab.

You now know how to:
- Create IAM users and set passwords
- Create groups and attach permission policies
- Add users to groups
- Use the IAM sign-in portal
- Test real-world access control scenarios

IAM is one of the most critical parts of AWS for managing access securely. Great job!
