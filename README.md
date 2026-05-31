# homeassistant-docs

This folder contains a small MkDocs site documenting the Home Assistant repository.

Build and serve locally using Podman (compatible with the existing Dockerfile):

```bash
podman build -t homeassistant-docs:latest -f homeassistant-docs/Dockerfile homeassistant-docs
podman run --rm -p 8000:8000 homeassistant-docs:latest
```

Then open http://localhost:8000 in your browser.
