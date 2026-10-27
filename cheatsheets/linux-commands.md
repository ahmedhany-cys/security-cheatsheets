# Linux Commands for Security

## Users and privileges
```bash
whoami; id                  # current user and groups
sudo -l                     # what you may run with sudo
cat /etc/passwd             # local accounts
last; lastb                 # successful / failed logins
```

## Files and permissions
```bash
ls -la                      # permissions, owner, hidden files
chmod 600 key.pem           # owner read/write only
find / -perm -4000 -type f 2>/dev/null   # SUID binaries
find / -mmin -60 -type f 2>/dev/null     # modified in last hour
```

## Processes and services
```bash
ps auxf                     # process tree
top / htop                  # live usage
systemctl list-units --type=service --state=running
crontab -l; ls /etc/cron.*  # scheduled jobs
```

## Network
```bash
ip a                        # interfaces and addresses
ss -tulpn                   # listening ports + owning process
ip route                    # routing table
cat /etc/resolv.conf        # DNS servers
```
