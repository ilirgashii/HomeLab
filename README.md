# Home Lab

A self-hosted home lab built from repurposed laptops: an Ubuntu Server running Docker services, protected by a dedicated OPNsense firewall, with secure remote access over SSH keys and Tailscale.

## Architecture

```
Internet
   │
[Router 1]  (ISP / main router)
   │
[OPNsense Firewall]  (Samsung laptop)
   │
[Router 2]  (internal LAN)
   ├── SRV (Ubuntu Server, Docker)
   └── Printer
```

> Status: SRV, OPNsense and the services are running. Final router/LAN configuration is in progress.

## Hardware

| Role | Device | Specs |
|------|--------|-------|
| Server (SRV) | Acer Predator PH317-51 | i7-7700HQ, 16 GB DDR4, 1 TB NVMe, 512 GB SSD for data |
| Firewall | Samsung 370R-series laptop | i5-3210M, 8 GB DDR3 |
| Network | 2 routers | Router 1 (WAN side), Router 2 (LAN side) |

## Software and Services

- **OS:** Ubuntu Server 26.04 on the server, OPNsense on the firewall
- **Containers:** Docker (application, game server, and further services)
- **Virtualization:** KVM / libvirt, VM storage on a separate data disk (`/mnt/data`)
- **Remote access:** SSH (key-only), Tailscale, SSH from phone via Termius
- **Hosted:** own web application in Docker, game server in Docker
- **Domain and email:** personal domain with private email

## Security

- OPNsense firewall between the internet and the internal network
- UFW enabled on the server
- SSH key authentication only, password login disabled
- Automatic security updates
- Tailscale for remote access instead of exposing SSH to the internet
- Public services are only exposed after the firewall is in place

## What I Learned

- Planning and segmenting a home network (WAN / firewall / LAN)
- Installing and hardening a Linux server
- Running and managing services with Docker
- Firewall configuration with OPNsense
- Secure remote administration

## Planned

- Portainer for container management
- Application hosted in a separate VM
- Monitoring and backups
