# 🧠 Concepts Explained

This section explains the key cybersecurity principles behind the project.

---

## What is SSH?
SSH (Secure Shell) is a protocol used to securely connect to remote systems using encryption.

---

## Why Change the Default Port?
Attackers use port scanners to find SSH on port 22.  
Changing it adds a layer of obscurity and reduces random attack attempts.

---

## What is a Firewall?
A firewall filters incoming and outgoing traffic.  
Using UFW, I allowed only the service I needed (SSH), thereby, reducing the attack surface.

---

## What is Fail2Ban?
Fail2Ban monitors logs for repeated authentication failures and bans offending IPs temporarily or permanently.

---

## Brute-force vs Dictionary Attack
- **Brute-force:** tries all possible passwords.  
- **Dictionary attack:** tries words from a predefined list.  
Fail2Ban helps mitigate both.

---

## Layered Security
No single measure guarantees safety, a defense in-depth approach should always be adopted. 
Multiple layers (configuration, firewall, monitoring) create real resilience.

---
