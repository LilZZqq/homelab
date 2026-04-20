# 🌐 Network Infrastructure

## Physical Network 
Internet (Fiber - Makedonski Telekom)
│
▼
ISP ONT/Modem
│
▼
Tenda N300 Router (192.168.1.1)
│
▼
Mercusys 1Gbps Switch
│
├── Asus VivoBook X550LC
└── Toshiba Satellite L50-C
## Network Devices

| Device | Model | Role |
|---|---|---|
| Router | Tenda N300 | NAT, DHCP, WiFi |
| Switch | Mercusys 1Gbps | Wired LAN switching |
| Node 1 | Asus VivoBook X550LC | Main services |
| Node 2 | Toshiba Satellite L50-C | Network services |

## Known Issues & Workarounds

| Issue | Workaround | Permanent Fix |
|---|---|---|
| Double NAT | Tailscale + Cloudflare Tunnel | OPNsense replacing Tenda |
| No VLANs | Flat network | Planned with OPNsense |

## Remote Access

| Method | Use Case |
|---|---|
| Tailscale | Admin access to all machines |
| Cloudflare Tunnel | Public Immich access for friends |
| Pi-hole DNS | Local .lab domain resolution |
