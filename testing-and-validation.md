# 🧪 Testing and Validation

Once configuration is complete, this guide will help you confirm that your setup works, and that your security layers are effective.

---

## Test SSH Connection
From PowerShell (Windows):
```
ssh username@<your_VM_IP> -p 2222
```
If login succeeds — SSH is working correctly.

## Test Fail2Ban

Try logging in with a wrong password several times, then check:
```
sudo cat /var/log/fail2ban.log
```
You should see entries showing banned IPs.

Example:

Ban 192.168.0.102
Unban 192.168.0.102

## Check Firewall Status
```
sudo ufw status verbose
```
Ensure only port 2222/tcp and essential services are open.

## Log Review

Use:
```
sudo tail -f /var/log/auth.log
```
to watch login attempts in real time.
