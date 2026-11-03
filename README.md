# Homelab Template

This repository contains the configuration files, Docker Compose files and documentation for the services i run in my homelab.

## Repository Structure

```text
homelab/
├── arr-stack/                  # Media management and streaming
│   ├── data/                   
│   │   ├── books/
│   │   ├── downloads/
│   │   │   └── qbittorrent/
│   │   │       ├── completed/  # Completed downloads
│   │   │       ├── incomplete/ # In-progress downloads
│   │   │       └── torrents/   # Torrent files
│   │   ├── movies/
│   │   ├── shows/
│   │   └── youtube/
│   │
│   ├── docker/
│   │   ├── arr/                # ARR applications
│   │   │   ├── compose.yaml
│   │   │   └── .env
│   │   └── jellyfin/           # Jellyfin and Seerr
│   │       ├── compose.yaml 
│   │       └── .env
│   │
│   └── README.md               # ARR stack documentation
│
├── docmost/                    # Documentation
│   ├── compose.yaml
│   └── .env
│
├── glance/                     # Dashboard
│   ├── assets/
│   │   └── user.css
│   ├── compose.yaml
│   ├── .env
│   ├── config/
│   │   ├── glance.yaml
│   │   ├── home.yaml           # Homepage
│   │   └── service.yml         # Services status
│   └── README.md               # Glance documentation
│
├── nextcloud/                  # Cloud
│   ├── data/
│   ├── docker/
│   │   ├── compose.yaml
│   │   └── .env
│   └── README.md               # Nextcloud documentation
│
└── README.md                   # Main homelab documentation
```



## Services

| Service | Description | Documentation |
|---|---|---|
| **ARR Stack** | Stack for managing and streaming media libraries. | [README](./arr-stack/README.md) |
| **Docmost** | Documentation and knowledge application. | [README](./docmost/README.md) |
| **Glance** | Personal dashboard with services, resources and news feed. | [README](./glance/README.md) |
| **Nextcloud** | Self-hosted cloud application. | [README](./nextcloud/README.md) |

--- 
