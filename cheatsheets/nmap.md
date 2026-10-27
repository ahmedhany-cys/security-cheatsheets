# Nmap

Only scan hosts you own or are authorized to test.

| Goal | Command |
|---|---|
| Ping sweep (host discovery only) | `nmap -sn 192.168.1.0/24` |
| Top 1000 TCP ports | `nmap 10.0.0.5` |
| All TCP ports | `nmap -p- 10.0.0.5` |
| SYN scan (needs root) | `sudo nmap -sS 10.0.0.5` |
| Service + version detection | `nmap -sV 10.0.0.5` |
| OS detection | `sudo nmap -O 10.0.0.5` |
| Default scripts + versions | `nmap -sC -sV 10.0.0.5` |
| UDP top 100 | `sudo nmap -sU --top-ports 100 10.0.0.5` |
| Skip ping (host blocks ICMP) | `nmap -Pn 10.0.0.5` |
| Faster timing | `nmap -T4 10.0.0.5` |
| Save all output formats | `nmap -oA scan 10.0.0.5` |
| Run a script category | `nmap --script vuln 10.0.0.5` |

## Port states
- **open**: a service is accepting connections
- **closed**: reachable, nothing listening
- **filtered**: a firewall is dropping probes
