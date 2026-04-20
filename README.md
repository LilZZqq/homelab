# 🏠 Homelab

A self-hosted homelab running across multiple machines, built from scratch as a personal learning environment for Linux administration, networking, containerization, and infrastructure monitoring.

## 🖥️ Hardware

| Machine | Model | CPU | RAM | OS | Role |
|---|---|---|---|---|---|
| Asus VivoBook | X550LC | Intel i7-4500U (4c) @ 3.0GHz | 4GB | Ubuntu 24.04 LTS | Main services node |
| Networklap | Toshiba Satellite L50-C | Intel i5-5200U (4c) @ 2.7GHz | 4GB | Ubuntu 24.04 LTS | Network services node |

## 🗺️ Architecture
Internet (Fiber - Makedonski Telekom)
│
▼
Tenda N300 Router (192.168.1.1)
│
▼
Mercusys 1Gbps Switch
│
├── Asus VivoBook X550LC ─── Main Services
│     ├── Immich
│     ├── Prometheus + Grafana
│     ├── Zabbix
│     ├── Portainer
│     ├── Uptime Kuma
│     ├── Minecraft Server
│     └── Cloudflare Tunnel
│
└── Toshiba Satellite L50-C ─── Network Services
├── Nginx Proxy Manager
├── Pi-hole (DNS)
├── Nextcloud
├── Netdata
├── WireGuard VPN
└── Uptime Kuma
## 🐳 Services

### Asus VivoBook — cherry stack
| Service | Purpose | Port |
|---|---|---|
| Immich | Self-hosted photo & video backup | 2283 |
| Grafana | Metrics visualization | 3000 |
| Prometheus | Metrics collection | 9090 |
| Zabbix | Enterprise infrastructure monitoring | 8090 |
| cAdvisor | Docker container metrics | 8080 |
| Node Exporter | Host system metrics | 9100 |
| Portainer | Container management UI | 9000 |
| Uptime Kuma | Service uptime monitoring | 3001 |
| Minecraft | Java Edition game server | 25565 |
| Cloudflared | Cloudflare Tunnel for remote access | - |

### Toshiba Networklap — coffeetime stack
| Service | Purpose | Port |
|---|---|---|
| Nginx Proxy Manager | Reverse proxy | 80 |
| Pi-hole | Network-wide DNS & ad blocking | 8082 |
| Nextcloud | Self-hosted cloud storage | - |
| Netdata | Real-time performance monitoring | 19999 |
| Portainer | Container management UI | 9000 |
| Uptime Kuma | Service uptime monitoring | - |
| WireGuard | VPN server | 51820 |

## 🔧 Tech Stack

- **OS:** Ubuntu 24.04 LTS
- **Containerization:** Docker, Docker Compose, Portainer
- **Monitoring:** Prometheus, Grafana, Zabbix, cAdvisor, Node Exporter, Netdata
- **Networking:** Tailscale, Cloudflare Tunnel, Pi-hole, WireGuard, Nginx Proxy Manager
- **Remote Access:** Tailscale VPN, Cloudflare Tunnel

## 📡 Remote Access

- Immich accessible remotely via Cloudflare Tunnel
- Admin access to all machines via Tailscale VPN
- Local services accessible via Pi-hole DNS with `.lab` domain
- 10 users hosted on Immich with 50GB storage quota each

## 🗺️ Roadmap

See [docs/FUTURE.md](docs/FUTURE.md) for planned upgrades.
