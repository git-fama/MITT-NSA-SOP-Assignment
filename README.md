# SOP: How to setup a Linux Server for Web Testing

| Document Info | Details |
| :--- | :--- |
| **Company** | MITT Student Project |
| **Version** | 1.0 |
| **Author** | Dongjun Li |
| **Date** | 2026-03-26 |

---

## 1. Approval Table
| Version | Date | Name | Job |
| :--- | :--- | :--- | :--- |
| 1.0 | 2026-03-26 | Dongjun Li | Student / Author |
| 1.1 | 2026-03-27 | Jibing Liang | Instructor |

---

## 2. Purpose
The goal of this document is to help people setup a Linux server to test web apps. I wrote this so we can do it the same way every time.

## 3. Scope
This is for students and IT staff at MITT who need a test server.

## 4. Who is responsible? (Accountability Matrix)
| Task | Who does it | Who checks it |
| :--- | :--- | :--- |
| Create VM | Dongjun Li | Jibing Liang |
| Setup OS | Dongjun Li | Jibing Liang |
| Install Software | Dongjun Li | Jibing Liang |

---

## 5. Steps to do

### Step 1: Create the Virtual Machine (VM)
1. Open VMware.
2. Create a new VM with these settings:
   - **OS:** Ubuntu 22.04 LTS
   - **CPU:** 2 Cores
   - **RAM:** 4 GB
   - **Hard Drive:** 40 GB

### Step 2: Install Ubuntu
1. Put the Ubuntu ISO in the VM and start it.
2. Choose **English**.
3. Set the hostname to: `git-fama`.
4. Create a user: `admin-dongjun` and pick a password.
5. Finish the install and restart the VM.

### Step 3: Basic Security and Update
1. Log in and update the system:
   `sudo apt update && sudo apt upgrade -y`
2. Setup the firewall (UFW):
   - `sudo ufw allow ssh`
   - `sudo ufw allow 80`
   - `sudo ufw enable`

### Step 4: Install Web Software (LAMP)
We need these tools to run a web app:
1. **Web Server:** `sudo apt install apache2 -y`
2. **Database:** `sudo apt install mysql-server -y`
3. **PHP:** `sudo apt install php libapache2-mod-php php-mysql -y`
4. **Git:** `sudo apt install git -y` (to get the code)

### Step 5: Check if it works
1. Open the browser and type the server's IP. 
2. If you see the "Apache2 Ubuntu Default Page", it is working.
3. Type `php -v` in the terminal to see if PHP is there.

---

## 6. History
| Version | Date | Who | What changed |
| :--- | :--- | :--- | :--- |
| 1.0 | 2026-03-26 | Dongjun Li | First version of the SOP. |
---

## 7. Reference or Related Documents
- **Official Ubuntu Documentation:** https://ubuntu.com/server/docs
- **Class Video:** IT Career Questions (2020). *Documentation and managing tickets - Learn help desk series*. YouTube.
- **MITT Lecture Notes:** Lesson 2 - SOP Documentation in Github.
