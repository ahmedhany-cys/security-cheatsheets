# OWASP Top 10 (2021)

| # | Risk | Example | Key defense |
|---|---|---|---|
| A01 | Broken Access Control | Changing `?id=123` to see another user's data | Deny by default, check authorization server-side |
| A02 | Cryptographic Failures | Passwords stored in plain text or MD5 | TLS everywhere, strong hashing (bcrypt/argon2) |
| A03 | Injection | SQL injection, command injection, XSS | Parameterized queries, output encoding |
| A04 | Insecure Design | No rate limit on password reset | Threat modeling, secure design patterns |
| A05 | Security Misconfiguration | Default creds, verbose errors, open S3 bucket | Hardened baselines, remove defaults |
| A06 | Vulnerable and Outdated Components | Old library with a known CVE | Dependency scanning, patching |
| A07 | Identification and Authentication Failures | Credential stuffing, weak sessions | MFA, lockouts, secure session handling |
| A08 | Software and Data Integrity Failures | Unsigned updates, insecure deserialization | Signatures, trusted pipelines |
| A09 | Security Logging and Monitoring Failures | Breach goes unnoticed for months | Centralized logs, alerting |
| A10 | Server-Side Request Forgery (SSRF) | App fetches `http://169.254.169.254/` | Allowlist outbound URLs, block metadata IPs |

Source: <https://owasp.org/Top10/>
