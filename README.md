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

###  2. Single Sign-On (SSO) & Federation Handshake
* **What I Did:** I connected our customized `CFG Bank Portal` straight to my Okta cloud manager using the **SAML 2.0 federation engine**. 
* **How I Tested It:** I logged into the user dashboard as Keith and clicked the portal tile. It automatically compiled a secure cryptographic token and shot it across the internet straight to Salesforce's authentication firewall. 

![My Single Sign-On Handshake Proof](saturday_2_sso_handshake.png)


##  Phase 3 Architecture: Conditional Access Control & Geofencing
Completed: Sunday, September 27, 2026

###  1. Dynamic Network Perimeter Zoning
* **What I Did:** I created an enterprise-grade geolocation dynamic zone mapping explicit high-risk international perimeters (Russian Federation, Iran, North Korea).

![My Custom Dynamic Network Zones](sunday_1_networks_zone.png)

###  2. Conditional Access Policy Assignment
* **What I Did:** I architected an automated policy rule named `Block International Bank Intrusions` and dragged it to the top of the list at Priority 1 so it triggers first.
* **Why it's an Access Control:** It tracks incoming client IP properties. If a connection attempts to hit the portal from outside our authorized parameters, the system denies access immediately before they can even type a password.

![My Priority 1 Policy Rule Logic](sunday_2_policy_rule.png)

###  3. Intrusion Simulation Testing (Success Proof)
* **What I Did:** I routed a mock user session through an overseas VPN tunnel to simulate an unauthorized remote connection attempt.
* **The Result:** The Okta policy engine actively intercepted the handshake, immediately blocked the traffic, and threw a clean `403 Access Forbidden` denial wall.
![My Live Geofencing Firewall Success Proof](sunday_3_firewall_success.png)

# CFG Mock Bank - Enterprise Network Identity Infrastructure
**Current Progress Date:** October 2, 2026  
**Active Weekend Objective:** Deploy an on-premises enterprise Windows Server environment, promote it to a master Active Directory Domain Controller, and write an automated PowerShell script to programmatically ingest bulk user data, eliminating tedious manual object provisioning.
##  Phase 1 Architecture: Enterprise Windows Infrastructure & Active Directory
* **The Goal:** Deploy the industry-standard corporate operating system, plant a fresh network data forest, and promote the machine to command network identities.
* **Windows Server Provisioning:** Built a brand new virtual machine named `CFG-Bank-DC01` (4GB RAM, 2 CPUs, 50GB Hard Drive) and installed **Windows Server 2022**. Installed Guest Additions display drivers so the interface stretches to full screen resolution cleanly.



* **Active Directory Forest Promotion:** Installed the core **Active Directory Domain Services (AD DS)** framework role and promoted the server to a **Domain Controller**. This officially crowned our network domain as `cfgmockbank.local`.
* **The Identity Upgrade:** The database promotion upgraded our local administrator account into a master network domain profile, changing our login gate prefix to **`CFGMOCKBANK\Administrator`**.



---

##  Phase 4 Architecture: Programmatic Lifecycle Automation & PowerShell Orchestration
Completed: Saturday, October 3, 2026

###  1. Core Directory Hierarchies (Organizational Units)
* **What I Did:** Bypassed the default system junk drawer container (`Users`) and created a dedicated root container called `Bank_Staff`. Inside it, I built a nested sub-folder drawer specifically for `Tellers`.
* **Why it's Best Practice:** Separating human bank employees from hidden network system accounts keeps our environment audit-ready. Placing the `Tellers` container inside `Bank_Staff` establishes inheritance, allowing us to enforce high-level security rules across the entire bank footprint later with a single policy line.

###  2. Advanced Parameter Splatting Automation Loop
* **What I Did:** Leveraged an AI co-pilot workflow to model a custom data generation loop, building a localized user profile spreadsheet (`C:\TellersList.csv`) right on the server disk core storage footprint.
* **Overcoming Technical Hurdles:** Faced text data corruption blocks where VirtualBox's clipboard system dropped code characters and critical dollar-sign (`$`) syntax variables. Solved the roadblock by engineering the loop with an advanced enterprise optimization model called **Parameter Splatting**.

* ![My Automated PowerShell Logging Output Success](saturday_3_powershell_success.png)
* **The Identity Automation Result:** Instead of wasting hours clicking menus 50 times, the automated PowerShell script packages the settings array into a tightly wrapped Hash Table, imports the file data, and programmatically provisions all 50 distinct corporate identities into our `Tellers` folder in under three seconds. Every account is assigned its unique login attributes, secure tracking tokens, and a mandatory first-time password change flag.

![My Active Directory Users Verification Grid](saturday_4_ad_users_verified.png)



---

##  Phase 5 Architecture: Locking Down the System with Group Policies (GPOs)
**Completed:** Sunday, October 4, 2026

###  1. Why we use Group Policies (GPOs)
* **In Simple Words:** Now that we have 50 bank tellers in our system, we need to enforce safety rules. While folder structures (OUs) organize our users and Groups give them permissions, **Group Policies (GPOs)** are the master rules we set to lock down what users can and cannot do on their computers.

###  2. The 2 Safety Rules I Configured
* **The 3-Strike Lockout Rule (Brute-Force Defense):** I set a rule that says if anyone tries to guess a teller's password incorrectly **3 times in a row**, Active Directory will instantly freeze that account for **30 minutes**. This stops hackers from trying to guess passwords forever.
* **The 10-Minute Screen Lock (The Coffee Break Rule):** I set a rule that tracks if a computer is sitting empty. If a bank teller walks away from their desk and forgets to lock their screen, the server automatically locks the monitor after **600 seconds (10 minutes)** so random people can't look at customer bank data.

###  3. Forcing the System to Update
* **What I Did:** Group policies usually take a long time to turn on by themselves, so I opened up the Command Prompt terminal and ran a quick refresh command (`gpupdate /force`) to force the server to activate my new security rules instantly.

![My Group Policy Account Lockout Rules](sunday_5_lockout_configured.png)
![My Group Policy 10-Minute Idle Timeout Rule](sunday_6_timeout_configured.png)






---

#  WEEKEND MILESTONE: ENTERPRISE LIFECYCLE AUTOMATION AT SCALE
**Current Milestone Date:** Friday, October 9, 2026  
**Active Weekend Objective:** Move out of the small-scale lab phase and prepare our network directory database to programmatically ingest, filter, and sort 3,000 active employee records across multiple banking role containers using automated scripts.

---

## Phase 6 Architecture: Enterprise Data Scale, Staging, & Infrastructure Auditing

###  1. Self-Built Corporate Department Hierarchies (OUs)
* **What I Did:** Navigated the Active Directory tree console entirely on my own to expand our mock bank infrastructure. I built three brand new custom folder drawers (**Organizational Units**) under the main staff container: `Managers`, `Accounting`, and `HR`.
* **Why it's Crucial for Scaling:** To scale our database to 3,000 users, our upcoming automated script needs realistic corporate compartments to file accounts into. These folders give our script engine clean target paths to route employees based on their exact jobs.

![My Custom Corporate Banking OU Directory Tree](friday_6_ou_structure_active.png)

###  2. Enterprise Domain Controller Health Audit (DCDIAG)
* **What I Did:** Before dumping thousands of user records onto a server, a Systems Administrator must run a structural health check. I opened the administrative terminal and executed Microsoft's official health check engine: `dcdiag /v`. 
* **The Result:** I audited the live terminal logs to verify that our core infrastructure lifelines—including internal DNS routing paths, file system partitions, and Kerberos security token components—all returned successful `passed test` validation stamps. This proves our domain backbone is stable and fully prepped for heavy data migration stress tests tomorrow.

![My Successful Domain Controller Health Diagnostics](friday_7_dcdiag_audit_passed.png)


---

##  Phase 7 Architecture: Programmatic Lifecycle Automation & Multi-Department Ingestion
**Current Milestone Date:** Saturday, October 10, 2026  
**Active Weekend Objective:** Leverage script automation to ingest a high-velocity data spreadsheet and programmatically sort thousands of corporate profiles into their correct department containers instantly.

###  1. High-Velocity Mass Data Generation
* **What I Did:** Used an automated math array command to build a massive data spreadsheet (`C:\EnterpriseStaff.csv`) holding exactly 3,000 distinct employee entries. The command used mathematical remainder formulas to automatically distribute the names across four distinct banking departments.

* ###  2. Dynamic Department-Sorting Ingestion Loop (AI Co-Pilot Assisted)
* **What I Did:** Assumed the role of a modern IAM Engineer by leveraging an AI co-pilot workflow to generate our core automation script framework. I read through, modified, and supervised the execution of the script inside PowerShell ISE as an Administrator.
* **The Identity Automation Result:** This workflow allows me to learn foundational PowerShell scripting logic piece-by-piece without getting bogged down by tedious manual typing or clipboard corruption. The script programmatically loops through all 3,000 lines, evaluates each employee's department column, dynamically calculates their target folder path (`OUs`), and provisions their live user accounts into the database in under 3 minutes. Every account is assigned its unique login attributes, secure tracking tokens, and a mandatory first-time password reset flag.


![My Automated 3000-User Ingestion Logging Success](saturday_3_powershell_success.png)

###  3. Live Directory Database Verification
* **What I Did:** Opened the Active Directory Users and Computers console to audit the database results. I verified that all 3,000 automated accounts were perfectly sorted into their custom department drawers with zero errors.

![Automated User Accounts Populating Accounting OU](saturday_4_accounting_verification.png)
![Automated User Accounts Populating HR OU](saturday_5_hr_verification.png)
![Automated User Accounts Populating Managers OU](saturday_6_managers_verification.png)




---

##  Phase 8 Architecture: Role-Based Access Control (RBAC) & Folder Security Hardening
**Current Milestone Date:** Sunday, October 11, 2026  
**Active Weekend Objective:** Implement traditional Role-Based Access Control (RBAC) boundaries inside our corporate directory database to enforce the Principle of Least Privilege over local server storage file assets.

###  1. Building Access Governance Roles (Security Groups)
* **What I Did:** Navigated the Active Directory console tree to explicitly separate our user pool by creating two distinct **Global Security Groups** under our main staff container: `SG-Teller-Team` and `SG-Accounting-Team`.
* **Why it Matters:** While Organizational Units (OUs) are strictly used for sorting and folder organization, Security Groups are what the Windows kernel reads to actually grant or deny user access tokens to network resources. I populated our test identity accounts into these designated roles to prepare for permission boundary testing.

![Accounting Global Security Group Object Active](sunday_4_accounting_group_active.png)
![Teller Global Security Group Object Active](sunday_5_teller_group_active.png)

###  2. Configuring the Strict Least Privilege Firewall
* **What I Did:** Built a secure local directory folder path on the server storage disk named `C:\CFG-Bank-Vault` and dropped a sensitive financial log file named `Master_Ledger.txt` inside it.
* **The Permission Logic:** Modified the Access Control Lists (ACLs) for the folder. I explicitly configured the system rules to grant full Read/Write permissions to our `SG-Accounting-Team` role while placing a flat **Deny** restriction over the entire `SG-Teller-Team` role, satisfying enterprise compliance standards.

![Enforcing Allowed Rights for the Accounting Role](sunday_6_vault_accounting_allowed.png)
![Enforcing Full Deny Blocks for the Teller Role](sunday_7_vault_teller_denied.png)

### 🧠 3. Advanced Engineering Insight: Why Local Console Sign-ins Are Blocked
* **The Strategic Hurdle:** When attempting to log directly into the server screen console or run terminal execution shortcuts as a standard teller user object, the server's underlying security subsystem intercepted the handshake and threw a flat security block: *"The sign-in method you're trying to use isn't allowed."*
* **The Enterprise Reason:** In a production workforce, standard domain users (like bank tellers or corporate accountants) are strictly forbidden from logging directly onto the physical screen console of a Domain Controller. This is an active Microsoft security mechanism built into the Windows NT kernel to prevent unauthorized physical system tampering or local data manipulation in the server room. 
* **The Architecture Takeaway:** In a real corporate banking infrastructure, employees never touch the server hardware. Instead, they consume their role-based permissions from isolated client workstations out on the bank floor, proving our domain controller's security settings behave exactly like a real enterprise environment.



---

#  WEEKEND MILESTONE: IDENTITY GOVERNANCE, AUDITING, & ACCESS CREEP REMEDIATION
**Current Milestone Date:** Friday, October 16, 2026  
**Active Weekend Objective:** Simulate a production network environment over a multi-year timeline to identify, audit, and programmatically remediate high-risk "Access Creep" vulnerability gaps across a 3,000-user database footprint.

---

##  Phase 9 Architecture: Programmatic Attack Surface Staging & Dependency Troubleshooting

###  1. Simulating Active Directory Access Creep (AI Co-Pilot Assisted)
* **What I Did:** Assumed the role of a modern IAM Engineer to stage an internal network threat test. I used an AI co-pilot workflow to generate a script designed to take 100 random user accounts out of our `Tellers` folder and programmatically inject them into an elevated administrative management group. This perfectly simulates five years of messy corporate history where employees changed roles but kept old access permissions.

### 2.  Troubleshooting Roadblock #1: The Missing Security Group
* **The Problem:** When I ran the script, it didn't work and returned a blank screen. I investigated the system architecture and found that the AI co-pilot wrote code targeting an elevated security group name (`SG-Branch-Managers`) that **did not exist yet** in our database cabinet. 
* **The Fix:** I took initiative, stepped into the Active Directory console, and manually built the missing `SG-Branch-Managers` global security group so the script robot finally had a valid target folder bucket to drop users into.

###  3. Troubleshooting Roadblock #2: The Empty Department Field
* **The Problem:** After fixing the group, the script still didn't add anyone. I ran a terminal diagnostic query (`Get-ADUser`) to inspect a teller's properties card and found that their **Department text fields were completely empty in the database**. 
* **Why it Happened:** When we used a script to create our 3,000 users last weekend, the code successfully put the users into the right folder paths, but we completely forgot to include the specific line telling the robot to write the actual words "Branch Operations" into their internal department profile fields. Because that field was blank, tonight's search filter couldn't find them.
* **The Fix:** To bypass this data mismatch, I changed the script filter to a wildcard star (`*`). This told the script engine: *"Turn off the strict filters. I don't care if the department box is blank right now—just grab the first 100 actual user accounts sitting inside that Tellers folder drawer."*

###  4. The Automation Victory
* **The Result:** With the script fixed to match our real database data, the loop fired perfectly. The conveyor belt instantly processed the 100 teller accounts and injected them straight into the high-privilege management vault. This successfully gave our network a realistic "Access Creep" vulnerability, which sets the stage perfectly for us to build automated auditing and clean-up scripts tomorrow night!

![My Automated Access Creep Staging Script Execution](friday_9_access_creep_staged.png)

