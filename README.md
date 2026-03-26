# SOP: How to setup a Linux Server for Web Testing

| Document Info | Details |
| :--- | :--- |
| **Company** | MITT - NSA Student Project |
| **Version** | 1.0 |
| **Author** | Dongjun Li |
| **Date** | March 26, 2026 |

---

## 1. Approval Table
| Version | Date | Name | Job Title |
| :--- | :--- | :--- | :--- |
| 1.0 | 2026-03-26 | Dongjun Li | Author / Student |
| 1.1 | 2026-03-26 | Jibing Liang | Instructor / Reviewer |

---

## 2. Purpose
The goal of this document is to show how to setup a Linux server for testing web applications. I wrote this so everyone can follow the same steps.

## 3. Scope
This SOP is for students and IT staff at MITT who need to create a test server environment.

## 4. Accountability Matrix (Who is responsible?)
| Task / Steps | Who does it | Who checks it |
| :--- | :--- | :--- |
| Create VM | Dongjun Li | Jibing Liang |
| Setup OS | Dongjun Li | Jibing Liang |
| Install Software | Dongjun Li | Jibing Liang |

---

## 5. Definitions
- **SOP:** Standard Operating Procedure (This document).
- **VM:** Virtual Machine (The computer inside VMware).
- **LAMP:** Linux, Apache, MySQL, PHP (The software tools we need).
- **IP:** Internet Protocol (The address of the server).
- **UFW:** Uncomplicated Firewall (The tool to protect the server).

---

## 6. Procedure Steps

### Step 1: Create the Virtual Machine (VM)
1. Open VMware Workstation or vSphere.
2. Create a new VM with these simple settings:
   - **OS:** Ubuntu 22.04 LTS (64-bit)
   - **CPU:** 2 Cores
   - **RAM:** 4 GB
   - **Hard Drive:** 40 GB (Thin Provision)

### Step 2: Install Ubuntu Server
1. Put the Ubuntu ISO in the VM and start it.
2. Choose **English** as the language.
3. Set the hostname to: `git-fama`.
4. Create a user: `admin-dongjun` and set a strong password.
5. Finish the install and restart the machine.

### Step 3: Security and Updates
1. Log in and update the system first:
   `sudo apt update && sudo apt upgrade -y`
2. Setup the firewall (UFW) to be safe:
   - Allow SSH: `sudo ufw allow ssh`
   - Allow Web: `sudo ufw allow 80`
   - Start firewall: `sudo ufw enable`

### Step 4: Install Web Tools (LAMP Stack)
We need these software packages for web application testing:
1. **Web Server:** `sudo apt install apache2 -y`
2. **Database:** `sudo apt install mysql-server -y`
3. **PHP:** `sudo apt install php libapache2-mod-php php-mysql -y`
4. **Git:** `sudo apt install git -y` (To get the test code from GitHub)

### Step 5: Check if everything is working
1. Open a web browser and type the server's IP.
2. If you see the **"Apache2 Ubuntu Default Page"**, it is successful.
3. Type `php -v` in the terminal to check if PHP is installed.
4. Type `mysql --version` to check the database.

---

## 7. Revision History
| Version | Date | Who | What was changed |
| :--- | :--- | :--- | :--- |
| 1.0 | 2026-03-26 | Dongjun Li | Initial version for the assignment. |

---

## 8. Reference or Related Documents
- **Official Ubuntu Documentation:** https://ubuntu.com/server/docs
- **Class Video:** IT Career Questions (2020). *Documentation and managing tickets - Learn help desk series*. YouTube.
- **MITT Lecture Notes:** Lesson 2 - SOP Documentation in Github.
