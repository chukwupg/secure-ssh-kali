# ⚙️ Setup Guide: Securing SSH on Kali Linux

This guide provides the full process of setting up and securing SSH access on a Kali Linux VM.

---

## Step 1: Update the System
Keeping your system up to date ensures all security patches are applied.
```bash
sudo apt update && sudo apt upgrade -y
```
Always start with a clean, updated base before configuring security services.

## Step 2: Install and Configure SSH

Install OpenSSH:
```
sudo apt install openssh-server -y
```

Enable and start the SSH service:
```
sudo systemctl enable ssh
sudo systemctl start ssh
```

Edit the SSH configuration:
```
sudo nano /etc/ssh/sshd_config
```

Make the following changes:

Comment/uncomment the following lines;
```
[SSHD]
Port 2222
PermitRootLogin no
PasswordAuthentication yes
AllowUsers <username>
```

Restart SSH to apply changes:
```
sudo systemctl restart ssh
```

## Step 3: Configure Network Settings

Your VM must be reachable from your host system.

- In VirtualBox, open Settings → Network
- Choose Bridged Adapter (recommended) Or use NAT with Port Forwarding

Check VM’s IP address:
```
ip address
or
ifconfig
```
Take note of your IP

Will be used for SSH access.

## Step 4: Configure Firewall (UFW)

UFW (Uncomplicated Firewall) helps control which connections are allowed.

Install and enable UFW:
```
sudo apt install ufw -y
sudo ufw enable
```

Allow custom SSH port:
```
sudo ufw allow 2222/tcp
sudo ufw status
```

## Step 5: Install and Configure Fail2Ban

Fail2Ban protects SSH by blocking IPs after multiple failed login attempts.

Install Fail2Ban:
```
sudo apt install fail2ban -y
```

Copy and edit configuration:
```
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local
sudo nano /etc/fail2ban/jail.local
```

Locate the [sshd] section and set:
```
enabled = true
port = 2222
```

Restart the service:
```
sudo systemctl restart fail2ban
```

## Step 6: Test SSH Access

From Windows PowerShell or Terminal:
```
ssh username@<VM_IP_address> -p 2222
```
Replace username and <VM_IP_address> with actual details.

A successfull connection ✅ means SSH setup works!
