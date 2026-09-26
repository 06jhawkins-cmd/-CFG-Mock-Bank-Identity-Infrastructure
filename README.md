# CFG Mock Bank - My Identity & Access Management (IAM) Lab
This is my hands-on project where I am practicing how corporate networks and cloud security tools manage employee access to sensitive data. 

---

#  THE MAIN EVENT: WHAT I AM BUILDING THIS WEEKEND
My primary objective for Saturday and Sunday is to build an enterprise authentication hub focused on two high-yield industry standards:

* ** SETTING UP SINGLE SIGN-ON (SSO):** I will be connecting mock cloud applications straight to my Okta security hub. The goal is to make it so a bank employee only has to log in ONCE to securely unlock all of their corporate work portals without re-typing credentials.
* ** CREATING GROUP ACCESS CONTROLS:** I will be organizing my users into operational teams (like Bank Tellers vs. Loan Officers) to practice the Principle of Least Privilege—ensuring users can only open the specific banking apps required for their job description.

---


##  The Foundation (What I Completed on Friday)

### 1. Set Up My Local Server Environment
* **Installed VirtualBox:** I set up a virtual machine on my laptop so I have a separate, isolated mini-computer to act as my local bank server.
* **Installed Ubuntu Linux:** I deployed a lightweight Linux operating system onto that virtual machine to act as the bank's core basement database.
* **Configured Network Basics:** I made sure the server can connect to the internet safely so it's ready to handle user accounts.

• 
• ![My Local VirtualBox Server Setup](friday_1_virtualbox_setup.png)


### 2. Set Up My Cloud Security Manager
* **Created a Free Okta Developer Account:** I set up an enterprise-grade Okta cloud security portal to manage user access profiles.
* **Created My First Users:** I practiced the onboarding process by manually adding user accounts (like myself and a test account for Othenial) into the cloud directory.
* **Verified Password Security Policies:** Checked my user list to ensure our corporate password rules are actively forcing safety checks on new accounts.

![My Initial Okta User Registry](friday_2_okta_users.png)

##  Phase 2 Architecture: Access Control & Federated SSO
Completed: Saturday, September 26, 2026

###  1. Role-Based Access Control (RBAC) 
* **What I Did:** I created a centralized security group called `SG-Branch-Operations`. This group represents a specific job "Role" at my bank (Retail Tellers). I dropped my mock users (like Keith and Othenial) into it.
* **Why it's an Access Control:** Instead of manually assigning apps to users one by one, I attached our custom banking portal app straight to the group. The users inherited access automatically **just because of their role in the company.**

![My Okta Group Mapping](saturday_1_rbac_groups.png)

### 🌐 2. Single Sign-On (SSO) & Federation Handshake
* **What I Did:** I connected our customized `CFG Bank Portal` straight to my Okta cloud manager using the **SAML 2.0 federation engine**. 
* **How I Tested It:** I logged into the user dashboard as Keith and clicked the portal tile. It automatically compiled a secure cryptographic token and shot it across the internet straight to Salesforce's authentication firewall. 

![My Single Sign-On Handshake Proof](saturday_2_sso_handshake.png)
