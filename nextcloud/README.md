# Nextcloud
Self-hosted cloud using Nextcloud All-in-One (AIO).

## Services

| Application | Description |
|---|---|
| **Nextcloud AIO** | All-in-One deployment for the Nextcloud installation and its containers. |
| **Nginx Proxy Manager** | Reverse proxy and SSL certificate management. |

## Hardware
The host devices are passed to the container with:
```yaml
devices:
  - /dev/dri:/dev/dri
```

**Important:** Set the data directory before the first installation. Changing it afterwards is not supported. 

## Subomains
Each application can be accessed through its own subdomain:
```text
https://[app-name].domain.com
