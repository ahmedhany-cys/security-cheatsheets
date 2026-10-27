# Regex for Security Work

## Basics
| Token | Meaning |
|---|---|
| `.` | any character |
| `\d` `\w` `\s` | digit, word char, whitespace |
| `*` `+` `?` | 0+, 1+, 0 or 1 |
| `{n,m}` | between n and m times |
| `^` `$` | start, end of line |
| `[abc]` `[^abc]` | one of, none of |
| `(a\|b)` | group / alternation |

## Handy patterns
| Find | Pattern |
|---|---|
| IPv4 (loose) | `\b(\d{1,3}\.){3}\d{1,3}\b` |
| Email | `[\w.+-]+@[\w-]+\.[\w.-]+` |
| URL | `https?://[^\s"'<>]+` |
| MD5 hash | `\b[a-fA-F0-9]{32}\b` |
| SHA-256 hash | `\b[a-fA-F0-9]{64}\b` |
| AWS access key ID | `\b(AKIA\|ASIA)[A-Z0-9]{16}\b` |
| Private key block | `-----BEGIN [A-Z ]*PRIVATE KEY-----` |
| JWT | `eyJ[\w-]+\.[\w-]+\.[\w-]+` |

## Using them
```bash
grep -E  'pattern' file      # extended regex
grep -oP '\d+'     file      # Perl regex (GNU grep), print only matches
rg 'pattern'                 # ripgrep, fast recursive search
```
