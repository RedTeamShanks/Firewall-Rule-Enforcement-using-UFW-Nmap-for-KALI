# Firewall-Rule-Enforcement-using-UFW-Nmap-for-KALI

## 📘 Overview

This project demonstrates how to use `ufw` (Uncomplicated Firewall) on a Linux machine (IP: `192.168.239.135`) to control access to network services such as FTP, SSH, SMTP, and HTTP. The testing involves scanning open ports using `nmap` from a  machine on a different subnet and verifying whether the firewall is correctly allowing or denying access.

---

## 🖥️ Lab Setup

| Component         | Details                     |
|------------------|-----------------------------|
| 🔒 Firewall Tool  | UFW (on Linux)              |
| 📡 Verification Tool | Telnet (on Windows machine) |

---

## ⚙️ Machine Configuration

| Component         | Details                     |
|------------------|-----------------------------|
| 💻 Linux IP       | `192.168.239.135`           |
| 💻 Windows        | `192.168.239.134 `          |

---

## Service Found 

| 📁 Services       | Ports|
|--------------------|--------------------------|
|FTP |(Port 21, File Transfer Protocol)  |
|SSH |(Port 22, Secure Shell)  |
|SMTP |(Port 25, Simple Mail Transfer Protocol)  |
|HTTP| (Port 80, HyperText Transfer Protocol) |

---
## 🔍 Port Scan Results

### 🧪 Test 1: Before Applying UFW Rule

``` nmap -sS 192.168.239.135```


📌 Results:

- Port 21/tcp open (FTP)
- Port 22/tcp open (SSH)
- Port 25/tcp open (SMTP)
- Port 80/tcp open (HTTP)
---
<img width="1632" height="888" alt="Screenshot 2025-08-08 134041" src="https://github.com/user-attachments/assets/6deab96b-7279-43df-942e-c2c9ea3bd006" />

---

### 🔒 Test 2: After Applying UFW Rule

📌 Results:

- Port 21/tcp → filtered/closed
- Port 22/tcp → filtered
- Port 25/tcp → open
- Port 80/tcp → open
---
<img width="982" height="516" alt="Screenshot 2025-08-08 160122" src="https://github.com/user-attachments/assets/b36d2122-ebe3-47e0-9652-cea627f7ae3f" />

---
<img width="980" height="514" alt="Screenshot 2025-08-08 145326" src="https://github.com/user-attachments/assets/1d459d5b-5d31-439c-8d10-a234606b5fe7" />

---
<img width="1631" height="918" alt="Screenshot 2025-08-08 145517" src="https://github.com/user-attachments/assets/f80c9f47-d28b-40e5-9f80-ebcec13ae865" />

---

## UFW VERBOSE STATUS 
<img width="578" height="286" alt="Screenshot 2025-08-08 145641" src="https://github.com/user-attachments/assets/21470d4e-57a6-469c-bb8f-202a39d5f242" />



## ✅ Outcome
- UFW effectively blocked access to the FTP port (21) when the rule was set to DENY.
- Services such as SMTP and HTTP remained accessible as per the firewall configuration.
- SSH access was rate-limited and filtered as expected from a different subnet.

## 🏁 Conclusion
Firewall rules using ufw were successfully applied and validated with nmap. This hands-on exercise showcased how to properly manage access to critical services in a networked environment.

