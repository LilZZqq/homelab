# 🗺️ Homelab Journey

## Why I Started

As a second-year IT student in Skopje, I wanted more than just theory. I had spare laptops sitting around and decided to build a real infrastructure from scratch — learning by doing rather than just reading about it.

The goal was simple: build something that actually works, for real users, solving real problems. Not just a classroom exercise.

---

## Phase 1 — First Steps (Early 2025)

Started with a single Asus VivoBook running Ubuntu. No prior Linux experience beyond what university taught.

**First challenge:** Getting Docker installed and understanding how containers work. Spent days debugging YAML errors in docker-compose files.

**First win:** Getting Portainer running and seeing all containers managed from a web UI. That moment made everything click.

**What I deployed first:**
- Portainer (container management)
- Uptime Kuma (monitoring)
- Pi-hole (DNS filtering)

**What I learned:** Linux CLI basics, Docker networking, how DNS works in practice.

---

## Phase 2 — Expanding the Stack

Once the basics worked, I kept adding services. Each one taught me something new.

**Immich** — Self-hosted Google Photos alternative. Learned about PostgreSQL, Redis, and how complex multi-container applications are structured.

**Nginx Proxy Manager** — Learned about reverse proxies, virtual hosts, and how web traffic routing works.

**WireGuard VPN** — First attempt at VPN setup. Hit double-NAT issues with my ISP router. Learned what NAT is the hard way.

**The double NAT problem:** My ISP router + home router created two layers of NAT. Port forwarding wouldn't work properly. Spent days troubleshooting before switching to Tailscale which bypasses NAT entirely.

---

## Phase 3 — Networking Challenges

**Tailscale setup:** Replaced WireGuard with Tailscale for simpler VPN mesh networking. Learned about MagicDNS, ACLs, and mesh networking concepts.

**Pi-hole + Tailscale:** Configured Pi-hole as custom DNS for Tailscale so `.lab` domain resolved across all devices. Learned how DNS resolution order works.

**Real users:** Set up Immich for 10 friends with 50GB storage quotas each. First time managing a service for real users — learned about user management, storage quotas, and the importance of uptime.

**Cloudflare Tunnel:** When friends couldn't connect via Tailscale (shared user limitations), switched to Cloudflare Tunnel for public access. No port forwarding, no domain needed, works through any NAT.

---

## Phase 4 — Monitoring Stack

This is where things got serious. Deployed a full enterprise-grade monitoring stack:

**Prometheus + Grafana:**
- Prometheus scrapes metrics from both machines every 15 seconds
- Node Exporter on both laptops for host metrics
- cAdvisor for Docker container metrics
- Grafana dashboards showing CPU, RAM, disk, network in real time

**Zabbix:**
- Deployed alongside Prometheus to learn enterprise monitoring
- Agent-based monitoring on both machines
- Zabbix uses PostgreSQL backend
- Hit MySQL trigger creation bug (binary logging issue) — solved by switching to PostgreSQL
- Both machines monitored from single Zabbix instance via Tailscale

**Key lesson:** Running both Prometheus/Grafana (modern DevOps approach) and Zabbix (enterprise approach) gives a complete picture of how different organizations monitor infrastructure.

---

## Phase 5 — Documentation & Portfolio

Realized that building things without documenting them means losing the learning. Started:
- GitHub repository documenting the entire homelab
- Clean docker-compose files with comments
- Network diagrams and architecture documentation
- Roadmap for future improvements

**Cisco Packet Tracer:** Parallel to the homelab, started building network simulations to reinforce theoretical networking knowledge. Progressed from simple static LAN to multi-building enterprise topology with ISP connectivity.

---

## Biggest Challenges & How I Solved Them

| Problem | What I tried | Solution |
|---|---|---|
| Double NAT blocking VPN | Port forwarding, DMZ | Switched to Tailscale then Cloudflare Tunnel |
| Zabbix schema import failing | MySQL restarts, config changes | Switched from MySQL to PostgreSQL |
| Friends couldn't access Immich via Tailscale | ACL changes, machine sharing | Cloudflare Tunnel — no Tailscale needed |
| Grafana admin user lost after power cut | Password reset commands | Wiped volume, redeployed fresh |
| Docker containers not in compose file | Manual inspection | Reconstructed full compose from docker inspect |
| Tailscale free plan user limit | Tried member invites | Machine sharing for guests |

---

## What I'd Do Differently

1. **Start with proper compose files** — orphan containers caused headaches
2. **Document as I go** — reconstructing configs from memory is painful
3. **Plan networking first** — adding VLANs after the fact is harder than designing upfront
4. **Use PostgreSQL from the start** — MySQL caused multiple issues

---

## What's Next

See [FUTURE.md](FUTURE.md) for the full roadmap. Key priorities:

1. Windows Server 2022 — Active Directory, DHCP, DNS, GPO
2. OPNsense on networklap — eliminate double NAT, add VLANs
3. TrueNAS on Dell laptop — proper NAS with ZFS
4. Jellyfin with GPU transcoding on Asus
5. K3s Kubernetes cluster
6. CompTIA Network+ certification

---

## Tools That Helped Me Learn

- **Claude AI** — Debugging, architecture advice, documentation
- **ChatGPT** — Cisco Packet Tracer guidance
- **YouTube** — TechWorld with Nana (Kubernetes), NetworkChuck (networking)
- **Reddit** — r/homelab, r/selfhosted communities
- **Official docs** — Docker, Tailscale, Zabbix, Prometheus documentation

*Note: I used AI tools throughout this journey as learning aids, not shortcuts. Every configuration was deployed, tested, broken, and fixed by me.*
