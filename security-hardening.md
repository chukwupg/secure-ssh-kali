# 🔒 Security Hardening

This section explains *why* each configuration matters, the reasoning behind every security layer.

---

## Changing the Default Port
- Default SSH port 22 is constantly scanned by threat actors and bots.  
- Moving to a custom port (e.g., 2222) reduces automated attacks.  
> It’s not foolproof, but it’s an important first layer of defense.

---

## Disabling Root Login
- Root accounts have unrestricted access.  
- Disabling direct root SSH login prevents brute-force access to the most powerful account.

Instead, log in as a normal user and use:
```
sudo -i
```
For root priviledge

## Using UFW Firewall
- UFW ensures only necessary traffic reaches your system.
- Limiting open ports means attackers have fewer entry points.
- You can verify rules with:
```
sudo ufw status
```

## Enabling Fail2Ban
Fail2Ban monitors authentication logs and bans IPs after repeated failures.
```
Default jail: [sshd]
Custom port: 2222
Log location: /var/log/fail2ban.log
```
This helps stop brute-force attempts before they succeed.

## Layered Security Concept

Each step strengthens the previous one:

- SSH Configuration → reduce exposure
- UFW → restrict access
- Fail2Ban → respond to attacks

Together, they form a layered defense.
