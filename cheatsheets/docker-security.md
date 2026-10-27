# Docker Security

## Dockerfile
```dockerfile
FROM python:3.12-slim            # small, pinned base image
RUN useradd -m app
WORKDIR /app
COPY --chown=app:app . .
USER app                         # don't run as root
```
- Pin versions (or digests), not `latest`
- Use multi-stage builds so build tools don't ship
- Never bake secrets into images; use runtime secrets
- Add a `.dockerignore` (`.git`, `.env`, keys)

## Running containers
```bash
docker run --read-only --cap-drop ALL --security-opt no-new-privileges \
  --memory 512m --pids-limit 100 -u 1000:1000 myimage
```
- Avoid `--privileged` and mounting `/var/run/docker.sock`
- Don't publish ports you don't need

## Scanning and auditing
```bash
docker scout cves myimage        # or: trivy image myimage
docker image history myimage     # see what each layer added
docker inspect <container>
```

## Remember
Anyone in the `docker` group effectively has root on the host.
