# Securing Remote SSH Access on Kali Linux VM

## 📘 Overview
This project walks through setting up and securing remote SSH access on a Kali Linux virtual machine.  
With detailing on best practices for SSH configuration, firewall setup, and brute-force protection using Fail2Ban.
It provides a solid foundation in Linux system hardening.

---

## 🧩 Project Background
I built this project as part of my cybersecurity learning journey to gain hands-on experience in securing remote connections.  
It was an opportunity to understand how real-world SSH security works, from configuration to active defense, and log monitoring.

---

## 🎯 What I Learnt
- Setting up SSH on Kali Linux  
- Connecting securely from your host machine  
- Configuring firewall and custom SSH ports  
- Protecting SSH from brute-force attacks using Fail2Ban  
- Analyzing logs to verify security layers  

---

## ⚙️ Requirements
1. Windows 10 (or later) system  
2. Kali Linux Virtual Machine (VirtualBox, VMware, or Hyper-V)  
3. SSH client on Windows (PowerShell)  
4. Internet connection 
5. Basic Linux terminal knowledge  

---

## 📖 Documentation Navigation
| File | Description |
|------|--------------|
| [setup-guide.md](setup-guide.md) | Step-by-step SSH setup instructions |
| [security-hardening.md](security-hardening.md) | Explanation of security layers |
| [testing-and-validation.md](testing-and-validation.md) | How to test and verify your setup |
| [troubleshooting.md](troubleshooting.md) | Fixing common SSH setup issues |
| [concepts-explained.md](concepts-explained.md) | Background theory and cybersecurity concepts |
| [resources.md](resources.md) | Tools, links, and references |

---

## 🧠 Skills Practiced
| Skill Area | Description |
|-------------|-------------|
| **Linux Administration** | Installed & configured OpenSSH |
| **Firewall Management** | Used UFW to restrict access |
| **Identity Access Management** | Specified users who can connect through SSH |
| **Security Hardening** | Changed SSH port, disabled root login, enabled Password authentication |
| **Intrusion Prevention** | Configured Fail2Ban |
| **Log Analysis** | Reviewed `/var/log/auth.log` & `fail2ban.log` |

---

## 💡 Key Takeaway
Security cannot be achieved with a single defense, it needs to be in-depth through layers.  
Combining:
- Authentication and Authorization
- Secure configurations  
- Firewalls  
- Intrusion prevention tools  

…creates a strong and resilient environment against real-world attacks.

---

## 🙏 Acknowledgment
Special thanks to **[Ezechi Jeremiah](https://x.com/cyberjeremiah)** for the opportunity to do this project.

---

➡️ **Next:** [Setup Guide →](setup-guide.md)
