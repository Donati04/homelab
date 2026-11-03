# Glance
Dashboard for monitoring and accessing services.

## Data 

| File / Directory | Description |
|---|---|
| `assets/user.css` | Custom CSS (EMPTY). |
| `config/glance.yaml` | Main configuration file. Defines the theme and the pages. |
| `config/home.yaml` | Home dashboard. |
| `config/servizi.yml` | Services dashboard. |

### Dashboard Pages

The main configuration file, `glance.yaml`, loads the dashboard these pages:

- `home.yaml`: General dashboard with calendar, RSS feeds, Hacker News, YouTube videos, Reddit, ecc...
- `servizi.yml`: Homelab monitoring dashboard with HTTP service monitoring and Docker container status.

**IMPORTANT:** mount inside the container the docker socket for homelab monitoring.
```yaml
volumes:
- /var/run/docker.sock:/var/run/docker.sock:ro
```
