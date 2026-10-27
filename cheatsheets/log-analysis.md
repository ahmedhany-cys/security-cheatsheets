# Log Analysis

## grep / awk / sort
```bash
grep "Failed password" /var/log/auth.log
grep -c "404" access.log                          # count matches
awk '{print $1}' access.log | sort | uniq -c | sort -rn | head   # top client IPs
awk '$9 == 500' access.log                        # HTTP 500s (combined log format)
grep -oE '[0-9]{1,3}(\.[0-9]{1,3}){3}' file.log | sort -u          # unique IPs
```

## Failed SSH logins by IP
```bash
grep "Failed password" /var/log/auth.log \
  | grep -oE 'from [0-9.]+' | sort | uniq -c | sort -rn
```

## journalctl
```bash
journalctl -u ssh --since "1 hour ago"
journalctl -p err -b                              # errors since boot
journalctl -f                                     # follow live
```

## Live tailing
```bash
tail -f /var/log/syslog | grep --line-buffered -i error
```

## What to look for
- Many failures followed by a success (brute force that worked)
- Logins at odd hours or from new countries
- New users, new services, new scheduled tasks
- Gaps in logs or cleared logs
