# IT Pre-Onboarding Runbook 📘  

## 📌 **Overview**  
This runbook was developed as part of a career simulation exercise in IT system administration. It documents the **step-by-step process** for preparing a new hire’s workstation at **StackFull Software**, a fictional company.  

The goal is to **standardize onboarding procedures**, ensure security compliance, and streamline IT operations using **Windows Server, Active Directory, Group Policy, and PowerShell automation**.  

---

## 🎯 **Learning Objectives**  
This runbook demonstrates proficiency in the following key areas:  

### 🔹 **Asset & Inventory Management**  
✔ Find, create, move, and delete files and directories.  
✔ Perform software asset inventory functions on Windows systems.  

### 🔹 **System Administration**  
✔ Manage Windows security settings via **Group Policies (GPOs)**.  
✔ Control access through **Active Directory (AD) security groups**.  
✔ Configure **domain user accounts and passwords**.  

### 🔹 **Computer Languages & Automation**  
✔ Generate system reports using **PowerShell scripts**.  

### 🔹 **Security & Problem-Solving**  
✔ Apply a **security-first mindset** when onboarding new users.  
✔ Identify and **harden system vulnerabilities**.  

### 🔹 **Documentation & Technical Writing**  
✔ Write clear, concise, and structured IT documentation.  
✔ Use screenshots to illustrate **step-by-step procedures**.  

---

## 🖥️ **Scenario (Career Simulation Context)**  
As a new IT administrator at **StackFull Software**, I was assigned to work with Damen, the IT Security Manager, to document the **IT pre-onboarding process**.  

This playbook follows a structured approach to setting up a new hire’s machine, covering:  
✔ **Domain Integration** – Joining machines to `contoso.com`.  
✔ **User & Group Management** – Creating **Active Directory accounts** and **security groups**.  
✔ **File Share & Permissions** – Implementing **role-based access control**.  
✔ **Security Policies** – Enforcing **Group Policies (GPOs)** to secure workstations.  
✔ **PowerShell Scripting** – Automating **system monitoring & audits**.  

---

## 🛠️ **Steps Covered in the Runbook**  
### ✅ **Step 1:** Join the Computer to the Domain (`contoso.com`)  
### ✅ **Step 2:** Create a New User in Active Directory  
### ✅ **Step 3:** Assign the User to a Department Security Group  
### ✅ **Step 4:** Create a Department File Share (with Controlled Access)  
### ✅ **Step 5:** Create an Organizational Unit (OU) & Attach a GPO  
### ✅ **Step 6:** Configure Group Policy for Security & Access Control  
### ✅ **Step 7:** Check Last Successful Login via Event Viewer  
### ✅ **Step 8:** Use PowerShell to Audit Installed Programs  
### ✅ **Step 9:** Write a PowerShell Script to List Running Services  

📄 **Runbook Files:**
- 📝 [Markdown Version](./Pre-onboarding_Run_Book.md) (Easier to read & edit)
- 📂 [PDF Version](./Pre-onboarding_Run_Book.pdf) (Official document)
  
---

## 🔥 **Why This Matters?**  
This runbook provides a **repeatable, secure, and efficient** onboarding workflow for IT teams managing **Windows environments**. By following these steps, administrators can:  
✔ Ensure **consistent IT setups** for new hires.  
✔ Enforce **security best practices** via **Active Directory & GPOs**.  
✔ Use **PowerShell automation** to streamline auditing & monitoring.  

---

## 📂 **How to Use This Repository?**  
1️⃣ **Read the Runbook PDF** to understand the step-by-step IT onboarding process.  
2️⃣ **Use the PowerShell Scripts** provided to automate routine tasks.  
3️⃣ **Fork this repo** and modify it for your organization's needs.  

---

## 🤝 **Contributing & Feedback**  
Have suggestions or improvements? Open a **Pull Request (PR)** or start a **Discussion**! 🚀  

---

## 🏆 **Acknowledgment**  
This project was completed as part of a **Cyber Security bootcamp**, focused on practical hands-on IT security, Active Directory management, and automation with PowerShell.  

🚀 **Built with a hacker mindset, IT precision, and a security-first approach.** 🔥  
