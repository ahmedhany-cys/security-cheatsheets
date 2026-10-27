# OpenSSL and TLS

## Inspect a live site
```bash
openssl s_client -connect example.com:443 -servername example.com </dev/null
openssl s_client -connect example.com:443 </dev/null 2>/dev/null \
  | openssl x509 -noout -subject -issuer -dates
```

## Certificates
```bash
openssl x509 -in cert.pem -noout -text          # full details
openssl x509 -in cert.pem -noout -fingerprint -sha256
openssl verify -CAfile ca.pem cert.pem
```

## Keys and CSRs
```bash
openssl genpkey -algorithm RSA -pkeyopt rsa_keygen_bits:3072 -out key.pem
openssl req -new -key key.pem -out req.csr
openssl req -x509 -newkey rsa:3072 -nodes -keyout key.pem -out cert.pem -days 365   # self-signed
```

## Hashing and encoding
```bash
openssl dgst -sha256 file.iso
openssl base64 -in file.bin
openssl rand -hex 32                             # random secret
```

## Good TLS settings
- TLS 1.2 minimum, prefer TLS 1.3
- Disable SSLv3, TLS 1.0/1.1, RC4, 3DES
- Test with `testssl.sh example.com`
