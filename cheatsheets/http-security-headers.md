# HTTP Security Headers

| Header | Example | Protects against |
|---|---|---|
| `Strict-Transport-Security` | `max-age=31536000; includeSubDomains` | Downgrade to HTTP |
| `Content-Security-Policy` | `default-src 'self'` | XSS, data injection |
| `X-Content-Type-Options` | `nosniff` | MIME-type sniffing |
| `X-Frame-Options` | `DENY` | Clickjacking (legacy; CSP `frame-ancestors` is newer) |
| `Referrer-Policy` | `strict-origin-when-cross-origin` | Leaking URLs to other sites |
| `Permissions-Policy` | `camera=(), microphone=()` | Unwanted browser features |
| `Cross-Origin-Opener-Policy` | `same-origin` | Cross-window attacks |

## Cookies
```
Set-Cookie: session=abc; Secure; HttpOnly; SameSite=Lax; Path=/
```
- `Secure`: HTTPS only
- `HttpOnly`: not readable from JavaScript
- `SameSite`: limits cross-site sending (CSRF)

## Check a site
```bash
curl -sI https://example.com
```
Or use <https://securityheaders.com>.
