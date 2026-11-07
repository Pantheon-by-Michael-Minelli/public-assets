# public-assets — Pantheon

Public asset hosting for the Pantheon stack. Served over
`raw.githubusercontent.com` — an OrbStack-allowlisted domain — so containers can
declare their own icons; local files and other domains are not supported.

## Icons

`icons/<service>.png` — one square **PNG, exactly 512×512**, named after the
compose service (`zeus.png`, `athena.png`, `hypnos.png`…).

Consumers add the three labels in their own `compose.yaml`:

```yaml
labels:
  - "dev.orbstack.icon=https://raw.githubusercontent.com/Pantheon-by-Michael-Minelli/public-assets/main/icons/<service>.png"
  - "org.opencontainers.image.logo=<same URL>"
  - "com.docker.extension.icon=<same URL>"
```

A service declares the labels only once its PNG exists here. The repo must stay
public — `raw.githubusercontent.com` requires a token for private repos.
