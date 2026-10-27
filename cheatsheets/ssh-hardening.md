# SSH Hardening

## Keys
```bash
ssh-keygen -t ed25519 -C "you@example.com"
ssh-copy-id user@server
chmod 700 ~/.ssh && chmod 600 ~/.ssh/authorized_keys
```

## `/etc/ssh/sshd_config`
```
PermitRootLogin no
PasswordAuthentication no
KbdInteractiveAuthentication no
PubkeyAuthentication yes
MaxAuthTries 3
AllowUsers alice bob
X11Forwarding no
ClientAliveInterval 300
ClientAliveCountMax 2
```

Check the config before restarting so you don't lock yourself out:
```bash
sudo sshd -t && sudo systemctl restart ssh
```

## Extra layers
- `fail2ban` to ban IPs after repeated failures
- Firewall: allow port 22 only from trusted ranges
- Keep an existing session open while testing changes
- Review logins: `journalctl -u ssh` or `/var/log/auth.log`
