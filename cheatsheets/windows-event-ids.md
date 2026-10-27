# Windows Security Event IDs

| ID | Event | Why it matters |
|---|---|---|
| 4624 | Successful logon | Check logon type (2 interactive, 3 network, 10 RDP) |
| 4625 | Failed logon | Brute force / password spraying |
| 4634 / 4647 | Logoff | Session length |
| 4648 | Logon with explicit credentials | `runas`, lateral movement |
| 4672 | Special privileges assigned | Admin-level logon |
| 4688 | New process created | Enable command-line logging too |
| 4697 / 7045 | Service installed | Common persistence |
| 4698 | Scheduled task created | Common persistence |
| 4720 | User account created | |
| 4722 / 4725 | Account enabled / disabled | |
| 4724 | Password reset attempt | |
| 4728 / 4732 / 4756 | Member added to security group | Watch for admin groups |
| 4740 | Account locked out | |
| 4768 / 4769 | Kerberos TGT / service ticket | Kerberoasting shows up in 4769 |
| 4776 | NTLM credential validation | |
| 1102 | Security log cleared | Red flag |

## Query from PowerShell
```powershell
Get-WinEvent -FilterHashtable @{LogName='Security'; Id=4625} -MaxEvents 20
Get-WinEvent -FilterHashtable @{LogName='Security'; Id=4624; StartTime=(Get-Date).AddHours(-1)}
```

Sysmon adds richer events (process hashes, network connections, DNS).
