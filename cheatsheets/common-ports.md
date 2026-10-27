# Common Ports

| Port | Protocol | Service | Notes |
|---|---|---|---|
| 20/21 | TCP | FTP | Cleartext; prefer SFTP |
| 22 | TCP | SSH / SFTP | |
| 23 | TCP | Telnet | Cleartext; disable |
| 25 | TCP | SMTP | |
| 53 | TCP/UDP | DNS | |
| 67/68 | UDP | DHCP | |
| 80 | TCP | HTTP | |
| 88 | TCP/UDP | Kerberos | Active Directory |
| 110 | TCP | POP3 | |
| 123 | UDP | NTP | |
| 135 | TCP | MS RPC | |
| 139/445 | TCP | SMB | Never expose to the internet |
| 143 | TCP | IMAP | |
| 161/162 | UDP | SNMP | Change default communities |
| 389 / 636 | TCP | LDAP / LDAPS | |
| 443 | TCP | HTTPS | |
| 465 / 587 | TCP | SMTP (TLS / submission) | |
| 993 / 995 | TCP | IMAPS / POP3S | |
| 1433 | TCP | MS SQL Server | |
| 3306 | TCP | MySQL / MariaDB | |
| 3389 | TCP | RDP | Put behind VPN |
| 5432 | TCP | PostgreSQL | |
| 5900 | TCP | VNC | |
| 6379 | TCP | Redis | No auth by default |
| 8080 / 8443 | TCP | Alt HTTP / HTTPS | |
| 9200 | TCP | Elasticsearch | |
| 27017 | TCP | MongoDB | |
