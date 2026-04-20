# 🏗️ Homelab Architecture

## Network Diagram
┌─────────────────────────────────────────┐
│     Internet (Makedonski Telekom Fiber)  │
└─────────────────┬───────────────────────┘
│
▼
┌─────────────────────────────────────────┐
│           Tenda N300 Router             │
│              192.168.1.1                │
└─────────────────┬───────────────────────┘
│
▼
┌─────────────────────────────────────────┐
│         Mercusys 1Gbps Switch           │
└──────────────┬──────────────┬───────────┘
│              │
▼              ▼
┌──────────────────┐  ┌──────────────────┐
│  Asus VivoBook   │  │ Toshiba Satellite │
│    X550LC        │  │     L50-C        │
│  192.168.1.x     │  │  192.168.1.x     │
│                  │  │                  │
│ 🐳 cherry stack  │  │🐳 coffeetime stack│
│                  │  │                  │
│ • Immich         │  │ • Nginx Proxy    │
│ • Grafana        │  │ • Pi-hole        │
│ • Prometheus     │  │ • Nextcloud      │
│ • Zabbix         │  │ • Netdata        │
│ • cAdvisor       │  │ • WireGuard      │
│ • Node Exporter  │  │ • Uptime Kuma    │
│ • Portainer      │  │ • Portainer      │
│ • Uptime Kuma    │  │                  │
│ • Minecraft      │  └──────────────────┘
│ • Cloudflared    │
└──────────────────┘
## Remote Access
Friends/Admin
│
├── Cloudflare Tunnel ──► Immich (photos)
│
└── Tailscale VPN ──► All machines (admin only)
## Monitoring Coverage
┌─────────────────────────────────────┐
│           Prometheus                │
│         (Asus VivoBook)             │
│                                     │
│  Scrapes:                           │
│  ├── Node Exporter (Asus)           │
│  ├── Node Exporter (Toshiba)        │
│  └── cAdvisor (Docker containers)   │
└──────────────┬──────────────────────┘
│
▼
┌─────────────────────────────────────┐
│            Grafana                  │
│    Dashboards & Visualization       │
└─────────────────────────────────────┘
┌─────────────────────────────────────┐
│             Zabbix                  │
│    Enterprise Monitoring            │
│                                     │
│  Monitors:                          │
│  ├── Asus-Cherry (agent)            │
│  └── Networklap (agent)             │
└─────────────────────────────────────┘
