# docker-images
Repository of docker images for misc use-cases.

## Images

### debian-bookworm-packager

Debian Bookworm Slim for building debian packages (manually and CI).

```bash
# Login
docker login

# Build And Push
docker buildx build --platform linux/amd64,linux/arm64/v8 -t <YOUR_NAME>/<IMAGE_NAME>:<TAG> --push .
```


