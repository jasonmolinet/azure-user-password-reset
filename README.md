<p align="center">
<img src="https://i.imgur.com/jP924On.jpg" alt="Reset Password"/>
</p>

<h1>User Password Reset in the Cloud (Azure)</h1>
This tutorial outlines the implementation of using Active Directory within Azure Virtual Machines to reset a password and enable/disable an account in a network.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 Pro

<h2>Prerequisite</h2>

- How to setup active directory in azure VM found here: https://github.com/jasonmolinet/configure-ad 

<h2>Deployment and Configuration Steps</h2>

Step 1:

![image](https://i.imgur.com/PBjwLL0.jpg)

User Password Reset
- Login as jane_admin or the adminstrative account created in DC-1 (Domain Controller)
- In DC-1 VM, navigate to "Active Directory Users and Computers"
- Click the _EMPLOYEES folder
- Select a random user and right click then reset password
- Assign a new password, you can also unlock the user's account in this window

Step 2:

![image](https://i.imgur.com/OSUMhBE.jpg)

Testing the New Password
- Login as the user that the password was changed into the client-1 VM
- Once successfully logged in, navigate to the search bar then type CMD
- In the command prompt, type "whoami"
- It will populate the user using the computer
- Sign out of client-1 VM

Step 3:

![image](https://i.imgur.com/1TbwqKQ.jpg) 

Disable/Enable an Account
- Navigate back to DC-1 VM
- Right click on the user used for the password change above
- You can also right click on the domain folder and search for the user by the "find" option
- Select disable account, this will stop the user from accessing the VM
- Connect and attempt to access to client-1 VM with this user
- A pop-up message will populate when attempting to log in
- Go back to DC-1 VM
- Right click the user and enable account
