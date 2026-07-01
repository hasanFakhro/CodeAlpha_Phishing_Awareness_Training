# CodeAlpha_Phishing_Awareness_Training
# Phishing Simulation & Defense Project

## Project Overview
This project was completed as part of my **Cyber Security Internship at CodeAlpha**.
I built a realistic phishing simulation using **GoPhish** on **Kali Linux** to understand social engineering tactics and credential harvesting.

---

## Technical Setup

### Tools Used:
- **GoPhish** – Phishing framework
- **Kali Linux** – Operating system
- **Postfix** – Mail Transfer Agent (SMTP server)

### Why Postfix?
Postfix is a mail transfer agent (MTA) that handles sending and receiving emails. In this project, GoPhish uses Postfix as the SMTP server to deliver phishing emails to victims. It acts as the bridge between GoPhish and the victim's inbox.

---

## Commands Used

### 1. Update System
```bash
sudo apt update
```

### 2. Install Postfix (Mail Server)
```bash
sudo apt install postfix -y
```
- During installation, select **"Internet Site"**
- Enter system mail name (e.g., `kali.local`)

### 3. Start Postfix Service
```bash
sudo systemctl start postfix
sudo systemctl enable postfix
sudo systemctl status postfix
```
### 4. launch postfix 

```bash
sudo gophish
```
## Steps Performed

### 1. Installed & Launched GoPhish
- Accessed dashboard at `https://127.0.0.1:3333`
- Logged in with default credentials and changed password

### 2. Created Fake Landing Page
- Cloned Instagram login page
- Enabled *"Capture Submitted Data"* and *"Capture Passwords"*
- Set redirect URL to real Instagram

### 3. Crafted Phishing Email
- Spoofed sender: `security@insta.com`
- Subject: *"Action Required: Unusual Login Activity Detected"*
- HTML template with Instagram logo
- Used `{{.URL}}` as malicious link placeholder

### 4. Configured Sending Profile (SMTP)
- Host: `127.0.0.1:25` (Postfix)
- From: `security@insta.com`
- Test email sent & confirmed

### 5. Targeted Victims
- Created group: *"Test Alert"*
- Added test email addresses using **TempMail** in Kali Linux for safe testing

### 6. Launched Campaign
- Selected template, landing page, profile, and group
- Entered local IP and clicked *Launch*

### 7. Captured Credentials
- Victims clicked link → entered username/password
- Credentials appeared in plain text in **Submitted Data** tab

---

## Key Learnings

- Attackers use **urgency** and **fear** in subject lines
- **Spoofed sender** emails can look convincing
- **Redirect** to real site keeps victims unaware
- **MFA** is the most critical defense

---

## STEP DEFENSE PLAN

- **Verify Sender**: Hover over the display name to check the real email address.

- **Hover Links**: Hover before clicking any link to see the true destination URL.

- **Go Direct**: Instead of using email links, type the website URL manually in your browser.

- **Enable MFA**: Even if your password is stolen, multi-factor authentication stops attackers from logging in.

- **Use a Password Manager**: It won't autofill your credentials on fake websites, acting as a built-in red flag.

---

## Screenshots

### 1. Setting Postfix + Launch GoPhish
![Postfix Setup](screenshots/Setting%20postfix%20%2B%20launch.png)

### 2. Default Credentials – Admin Login
![Default Credentials](screenshots/default%20credential%20admin%20gophish.png)

### 3. HTML Code Used to Generate Instagram Page
![HTML Code](screenshots/used%20HTML%20code%20to%20generate%20this%20instagram%20page.png)

### 4. Phishing Email – "Unusual Login Activity"
![Phishing Email](screenshots/Phishing%20Email.png)

### 5. SMTP Configuration – Postfix
![SMTP](screenshots/SMTP%20Configuration.png)

### 6. Generate Email Template
![Generate Email](screenshots/Generate%20Email.png)

### 7. Target User + Group
![Targets](screenshots/Target%20User%2BGrp.png)

### 8. Launch Campaign
![Launch Campaign](screenshots/launch-campain.png)

### 9. Email Received – Inbox
![Email Received](screenshots/Email-Received.png)

### 10. Inside the Email – Malicious Button
![Inside Email](screenshots/Inside%20Email.png)

### 11. Click Phishing Button
![Click Button](screenshots/Click%20Phishing%20Button.png)

### 12. Credential Harvesting – Captured Data
![Credential Harvesting](screenshots/Screenshot%20Credential.png)

### 13. Redirect to Original Page – Victim Unaware
![Redirect](screenshots/Redirect%20to%20original%20Page.png)

### 14. Launch + User Clicked
![Launch](screenshots/launch%20%2B%20User%20Clicked.png)

### 15. Credential Captured – Submitted Data
![Credential Captured](screenshots/credential-captured.png)

## Author

**Hassan Fakhereldine**  
Cyber Security Intern @ CodeAlpha  

