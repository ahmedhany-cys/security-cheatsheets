# Hash Identification

| Looks like | Likely type |
|---|---|
| 32 hex chars | MD5 (or NTLM) |
| 40 hex chars | SHA-1 |
| 64 hex chars | SHA-256 |
| 128 hex chars | SHA-512 |
| `$1$...` | MD5-crypt |
| `$5$...` | SHA-256-crypt |
| `$6$...` | SHA-512-crypt (common in `/etc/shadow`) |
| `$2a$` / `$2b$` / `$2y$` | bcrypt |
| `$argon2id$...` | Argon2id |
| `$y$...` | yescrypt (newer Linux distros) |

Length alone is a guess: MD5 and NTLM are both 32 hex characters.

## Generate hashes
```bash
echo -n "hello" | md5sum
echo -n "hello" | sha256sum
shasum -a 256 file.iso          # macOS
```

## Tools
- `hashid <hash>` or `name-that-hash -t <hash>` to identify
- Verify downloads by comparing against the publisher's SHA-256

## For storing passwords
Use **Argon2id**, **bcrypt**, or **scrypt** — never plain MD5/SHA-x.
