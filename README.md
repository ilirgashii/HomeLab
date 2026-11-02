# Home Lab

A self-hosted infrastructure lab built with repurposed hardware, featuring an OPNsense firewall, a managed VLAN-capable switch, an Ubuntu Server, and containerized applications. This project is a practical environment for networking, Linux administration, security, and infrastructure operations.

## Current Status

**Operational:** managed switch, OPNsense firewall, internal network, Ubuntu Server, and hosted application services are running.

## Network Architecture

```text
Internet
   |
Fritz!Box 7530 AX (upstream router)
   |
TP-Link Omada ES208G (managed switch / VLANs)
   |
OPNsense (dedicated Samsung laptop firewall)
   |
Internal LAN / Asus Wi-Fi access point
   |
   +-- Ubuntu Server (Docker services)
   +-- Client devices
   +-- Printer
```

The managed switch provides VLAN-aware connectivity for upstream and internal network paths. OPNsense protects the internal LAN, while the Asus device operates as an access point rather than a second routing layer.

## Hardware

| Role | Device | Details |
| --- | --- | --- |
| Compute server | Acer Predator PH317-51 | Intel Core i7-7700HQ, 16 GB RAM |
| Firewall | Samsung laptop | Dedicated OPNsense appliance |
| Managed switch | TP-Link Omada ES208G | VLAN-capable Ethernet switch |
| Upstream router | Fritz!Box 7530 AX | Internet connectivity |
| Internal Wi-Fi | Asus router in AP mode | LAN wireless access |
| Server storage | NVMe + SATA SSD | 1 TB system disk and separate 512 GB data disk |

## Software and Services

- **Ubuntu Server 26.04 LTS** as the host operating system.
- **OPNsense 26.7** for firewalling, routing, and internal network services.
- **Docker and Docker Compose** for containerized applications.
- **Portainer** for container visibility and management.
- **Nlocki**, a self-hosted application with an API, PostgreSQL database, and Caddy gateway deployed as containers.
- **SSH keys and Tailscale** for secure remote administration.
- **Persistent data storage** on a separate SSD mounted at `/mnt/data`.

## Network Configuration

- Configured VLAN-aware switch ports for WAN and LAN connections.
- Configured OPNsense LAN networking, DHCP, and DNS.
- Set a stable LAN address for the Ubuntu server with a DHCP host reservation.
- Configured the Asus router as an access point with DHCP disabled.
- Verified connectivity between LAN clients, the firewall, and the server.

## Server and Container Operations

- Installed Ubuntu Server on the NVMe drive and mounted a separate SSD for service data.
- Configured SSH-based administration.
- Deployed the Nlocki application stack with Docker Compose.
- Configured container restart policies for automatic recovery after host or Docker restarts.
- Verified the managed switch, firewall, server, and application stack are operational.

## Security Practices

- Dedicated firewall between the upstream network and the internal LAN.
- SSH key-based remote access.
- Private remote administration with Tailscale.
- Separation of system and service-data storage.
- Credentials and private configuration are not included in this public documentation.

## Skills Practiced

Networking and VLANs · Firewall administration · DHCP and DNS · Linux server administration · Docker Compose · PostgreSQL · Reverse proxies · SSH · Remote access · Infrastructure troubleshooting

## Next Steps

- Add monitoring and alerting.
- Implement and test automated backups.
- Document recovery procedures.
- Continue improving least-privilege access and service security.
