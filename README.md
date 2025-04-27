

# 🏜️ West Wild: 1 — VulnHub Walkthrough

## About
This is my walkthrough for **West Wild: 1** from VulnHub — a beginner-intermediate level box focused on enumeration, exploitation, and privilege escalation.

- **Difficulty**: Beginner/Intermediate
- **IP Address**: (Example: `192.168.235.108`) — _your IP might vary_

---

## 1. Scanning and Enumeration

**Netdiscover
'''bash
 netdiscover -r 192.168.235.108
 '''

**Basic Nmap Scan:**
```bash
nmap -sV -sC -Pn 192.168.193.74
```

**Findings:**
- **Port 22** → OpenSSH (SSH service)
- **Port 80** → Apache Web Server (Website)
- **port 139and445** → Tcp open smbd
---

## 2. Web Enumeration (HTTP)

**Check in Browser:**  
Go to `http://192.168.235.108`

- Found a basic website with some western-themed content.
- No login panel or upload feature directly visible.

 **use smbclient tool
 '''bash
  smbclient -L //192.168.193.74 
 '''
 
- you can find the wave file wavedoor try to open it in terminal
 '''bash
 smbclient //192.168.193.74/wave -U wave
  '''
  - we will get the flag1.txt file
  - use get command to download the flag1.txt file and message_from_avg.txt file
  - open the file by uding cat command u will get the encrypted format
  - now check what is inside the message_from_aveng.txt using cat command.
   

## 3. Finding Credentials

 - we need to find the username and password so, we got the encrypted format to decrypt it by using base64 
   '''bash
   echo '<code>' | base64 -d
   '''
- we got the flag1{welcome_**_***_-****-*****}, user and password to login
- After we got the username and password we need to open wave@westwild root shell.


✅ **Got login credentials**.
user : 
password :
---

## 5.SSH (Secure Shell)
 '''bash
 ssh wave@192.168.193.74

 - it will ask for password so give the passowrd to  get the accsess
 - Afetr the secure login in wave@westwild

 - Follow the commands
 - id
 - cat /usr/share/av/westsidesecret
 - cd /usr/share/av/westsidesecret
 - ls
 - cat ififorget.sh

** we will get one more username an d password **
 echo "*****"
 echo "*************"
 
 - To login got to root shell use sudo suto get final flag.

   
 After login:
- use commands

- su aveng
- sudo -l
- sudo su
- cd /root
- cat FLAG2.txt


## 6. Capture the Flag 🏴

```bash
cat FLAG2.txt
```
✅ **Flag captured successfully!**

Flag2{**************_**_******}
---



# Tools Used
- Nmap
- smbclient
- echo '<code>' |base64
- ssh user@192.168.*.*

---

# Disclaimer
_This activity was performed in a controlled environment for educational purposes only._

---

