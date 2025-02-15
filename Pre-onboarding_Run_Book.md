# IT Pre-Onboarding Runbook

📅 Date: February 2025
🛠 Version: 1.0
👨‍💻 Prepared by: Carlos R.

### 📌 Executive Summary

This IT Pre-Onboarding Runbook outlines the step-by-step process for setting up a new hire’s workstation at StackFull Software. It ensures proper:

✔ Domain Integration – Joining the workstation to the contoso.com domain.
✔ User & Group Creation – Creating an Active Directory user account and assigning permissions.
✔ File Share & Access Control – Configuring role-based access to shared folders.
✔ Security Policies & Restrictions – Applying Group Policy Objects (GPOs) to enforce security.
✔ System Auditing – Using Event Viewer & PowerShell to verify system activity.
✔ Automation & Monitoring – Implementing PowerShell scripts to track running services.

By following this guide, IT administrators can ensure a secure, standardized, and efficient onboarding process.


🛠 New Hire Information

Name: New Hire

Role: Staff

Department: Human Resources


# 🔹 Steps to Follow

## 🖥 Step 1: Join the Computer to the Domain

1️⃣ Log into the workstation as a local administrator.

2️⃣ Open System Properties:
	•	Press Win + R, type sysdm.cpl, and press Enter.

3️⃣ Click Change under the Computer Name tab.

4️⃣ Join the domain:
	•	Select Domain, enter: contoso.com
 	•	Click OK.


5️⃣ Enter domain administrator credentials:

Username: administrator  
Password: Pa$$w0rd 

6️⃣ Restart the computer to apply changes.

✅ Verification: Log in using domain credentials (contoso\newhire).

##👤 Step 2: Create a New User Account

1️⃣ Log into the server as a domain administrator.

2️⃣ Open Active Directory Users and Computers (dsa.msc).

3️⃣ Navigate to contoso.com > Users.

4️⃣ Right-click Users > New > User.

5️⃣ Fill in the new hire’s details:

Username: newhire  
Password: [Set Secure Password]  

	•	Ensure “User must change password at next logon” is checked.
6️⃣ Click Finish.

✅ Verification: The user should appear in Active Directory.

## 👥 Step 3: Create a Group and Assign the User

1️⃣ In Active Directory Users and Computers, navigate to contoso.com > Groups.

2️⃣ Right-click Groups > New > Group.

3️⃣ Name the group based on the department (e.g., HR Team).

4️⃣ Add the new hire to the group:
	•	Right-click the user > Properties > Member Of > Add > Select the department group.

✅ Verification: The user is now part of the correct department group.


## 📂 Step 4: Create a Department Share and Assign Permissions

1️⃣ On the server, open File Explorer.

2️⃣ Create a folder in C:\Shares\HR.

3️⃣ Inside the folder, create a text file: test.txt

4️⃣ Configure sharing settings:
	•	Right-click the folder > Properties > Sharing tab > Advanced Sharing.
	•	Check “Share this folder” > Click Permissions.
	•	Remove Everyone, then Add:
	•	The department group (HR Team).
	•	Set Read & Write permissions.

✅ Verification: Only department members can access the shared folder.

## 🏢 Step 5: Create an Organizational Unit (OU) and Apply Group Policy

1️⃣ Open Active Directory Users and Computers.

2️⃣ Right-click contoso.com > New > Organizational Unit (OU).

3️⃣ Name the OU based on the department (e.g., HR).

4️⃣ Move the user, group, and computer into the new OU.

✅ Verification: The new OU contains the correct user, group, and computer.


## 🔒 Step 6: Configure Group Policy (GPO) for Security & Access Control

1️⃣ Open Group Policy Management (gpmc.msc).

2️⃣ Right-click the new OU > Create a GPO in this domain and Link it here.

3️⃣ Name the GPO: Department Security Policy.

4️⃣ Edit the GPO and apply the following rules:

✅ Display a warning at login
	•	Navigate to:
 Computer Configuration > Windows Settings > Security Settings > Local Policies > Security Options  

	•	Set “Interactive logon: Message text for users attempting to log on”:
 Do not install unauthorized programs.

✅ Prevent CMD access

User Configuration > Policies > Administrative Templates > System  
	•	Enable “Prevent access to the command prompt”.

✅ Map network drive at login

User Configuration > Windows Settings > Scripts (Logon/Logoff) > Logon  

	•	Add a script:
 net use Z: \\server\HR


✅ Verification: Restart the machine and test policy enforcement.


## 🛠 Step 7: Check Last Successful Login in Event Viewer

1️⃣ Open Event Viewer (eventvwr.msc).

2️⃣ Navigate to: Windows Logs > Security

3️⃣ Filter events for Event ID 4624 (successful logins).

4️⃣ Locate the last successful login for the new hire.

✅ Verification: The login event is recorded in Event Viewer.

## 📊 Step 8: Check Recently Installed Programs via PowerShell

1️⃣ Open PowerShell as Administrator.

2️⃣ Run: Get-WmiObject -Class Win32_Product | Sort-Object InstallDate | Select-Object -Last 5 | Format-Table Name, InstallDate

3️⃣ Review the most recently installed programs.

✅ Verification: Confirm the latest installed program is logged.

## ⚡ Step 9: PowerShell Script to List Running Services

1️⃣ Open Notepad and paste: Get-Service | Where-Object {$_.Status -eq 'Running'} | Format-Table -AutoSize | Out-File -FilePath "C:\running_services.txt"

2️⃣ Save the file as: running_services.ps1

3️⃣ Open PowerShell as Administrator and run: .\running_services.ps1

4️⃣ The list of running services is saved to C:\running_services.txt.

✅ Verification: Open running_services.txt to view active services.

🎯 Final Thoughts

🚀 This runbook ensures a secure, efficient, and repeatable onboarding process for all new hires. IT teams can use these standardized steps to maintain security, enforce policies, and automate system monitoring.









 

 





