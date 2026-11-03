# ARR Stack

A self-hosted media management and streaming.
Two Docker Compose files:

- **ARR Stack:** Automation, indexers, and download. [HERE](./docker/arr/)
- **Jellyfin Stack:** Streaming, request, and analytics. [HERE](./docker/arr/)

### Services
| Application | Description |
|---|---|
| **Gluetun** | VPN gateway for some containers. |
| **qBittorrent** | Download client. |
| **Prowlarr** | Centralized indexer management. |
| **FlareSolverr** | Proxy service for anti-bot challenges. |
| **Sonarr** | Automated shows management. |
| **Radarr** | Automated movies management. |
| **Lidarr** | Automated music collection management. [NOT USED]|
| **Bazarr** | Automated subtitle management. |
| **Jellyfin** | Media streaming server. |
| **Seerr** | Media request. |
| **Jellystat** | Satistics and analytics. |
| **PostgreSQL** | Database backend for Jellystat. |

## ARR Stack Network
Docker network called `servarrnetwork`. <br>
Gluetun is the gateway for these containers:
- qBittorrent
- Prowlarr
- FlareSolverr

For each container:
```yaml
network_mode: service:gluetun
```

### VPN
VPN configuration with Wiregurad and ProtonVPN. <br>
For other VPNs providers follow: [HERE](https://github.com/qdm12/gluetun-wiki/tree/main/setup) and [HERE](https://www.reddit.com/r/gluetun/comments/1kpbfs2/the_definitive_howto_for_setting_up_protonvpn/?tl=it) <br>

#### Checking VPN Connection
```bash
docker exec -it container_name bash
wget -qO- https://ipinfo.io
```
Or
```bash
docker exec -it container_name bash
curl https://ipinfo.io
```


## Media Directories

| Directory | Description |
|---|---|
| `data/books/` | Book library. |
| `data/downloads/` | Download storage. |
| `data/downloads/qbittorrent/` | qBittorrent download directory. |
| `data/downloads/qbittorrent/completed/` | Completed downloads. |
| `data/downloads/qbittorrent/incomplete/` | In-progress downloads. |
| `data/downloads/qbittorrent/torrents/` | Torrent files. |
| `data/movies/` | Movie library. |
| `data/shows/` | TV show library. |
| `data/youtube/` | YouTube media library. |

## Hardware
The host devices are passed to Jellyfin container with:
```yaml
devices:
  - /dev/dri/renderD128:/dev/dri/renderD128
```
This enable Intel QuickSync.

**Note:** ${JWT_SECRET} can be generated with `openssl`.
```bash
openssl rand -hex 32
```

---
```
