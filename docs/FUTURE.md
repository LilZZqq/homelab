# 🔮 Homelab Roadmap

## Phase 1 — Hardware Repurpose (Planned)

### Networklap → OPNsense Firewall/Router
- Replace Tenda N300 with OPNsense
- Eliminate double NAT
- Configure firewall rules and VLANs
- IDS/IPS with Suricata
- Separate homelab VLAN from home network

### Asus VivoBook → Media & Gaming Server
- Deploy Jellyfin with NVIDIA GPU hardware transcoding
- Remove Immich (moving to NAS)
- Keep Minecraft server

### Dell Laptop → TrueNAS NAS
- Install TrueNAS SCALE
- ZFS storage with optical bay HDD caddy (2TB total)
- Host Immich photo library
- Samba/NFS shares for network storage

## Phase 2 — Network Upgrade

- Replace Networklap with Raspberry Pi 4 running OPNsense
- Proper VLAN segmentation
- Subnet routing between VLANs

## Phase 3 — DevOps Learning

- Deploy K3s across machines
- Set up Gitea self-hosted Git
- CI/CD pipeline with Gitea Actions
- Automate container deployments

## 🎯 Certification Goals

- [ ] CompTIA Network+
- [ ] CompTIA Linux+
- [ ] AWS Cloud Practitioner
- [ ] CCNA
