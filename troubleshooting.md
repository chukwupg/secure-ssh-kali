# 🧩 Troubleshooting

Common problems and fixes when configuring SSH on Kali Linux.

---

### ❌ SSH Connection Refused
**Cause:** SSH service not running.  
**Fix:**
```
sudo systemctl start ssh
sudo systemctl enable ssh
```

## ⚠️ Permission Denied (Publickey/Password)
**Cause: Wrong credentials or SSH configuration.
**Fix:**
Check /etc/ssh/sshd_config for:
```
PasswordAuthentication yes
```
Restart SSH:
```
sudo systemctl restart ssh
```

## 🚫 Fail2Ban Not Banning IPs

**Fix:**
```
sudo systemctl status fail2ban
sudo fail2ban-client status sshd
```
Ensure enabled = true and correct port is set in jail.local.

## 🔥 UFW Blocking SSH

If locked out:

Boot into recovery mode or access console directly.

Disable UFW:
```
sudo ufw disable
```

Recheck allowed ports:
sudo ufw allow 2222/tcp
