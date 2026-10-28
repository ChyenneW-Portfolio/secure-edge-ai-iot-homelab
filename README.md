# Secure Edge AI & IoT Infrastructure Homelab

> **Status:** Planning | **Type:** Personal networking, Linux, security, and edge-AI learning project

## Overview
Build and document a self-hosted network video recorder using a Raspberry Pi 4, Docker, and Frigate. Start with one compatible IP camera and expand toward an isolated camera network with VLANs, firewall policies, monitoring, and up to three cameras.

**Why:** Practice networking, Linux administration, container deployment, secure IoT design, troubleshooting, and local AI inference. This is a learning lab, not a production security system.

## Goals
- Deploy a Linux host and containerized Frigate service.
- Integrate one local-stream camera (RTSP preferred; ONVIF desirable).
- Configure camera access without mandatory cloud recording.
- Evaluate CPU, memory, storage, decoding, and AI inference performance on Pi 4 before scaling.
- Isolate cameras with VLANs and firewall rules **when compatible router, switch, and/or access point hardware is available**.
- Validate allowed and denied traffic and document evidence.

## Planned architecture

```text
T-Mobile Home Internet gateway
        |
   [Lab router/firewall — TBD]
        |
 [Managed switch/AP — TBD]
      /          \
 Pi 4 + Frigate   IP camera (initially 1)
  (server zone)   (camera zone)
```

**Important:** The diagram is a *target design*, not a completed configuration. A VLAN-capable access point is needed to place a Wi-Fi camera on a dedicated wireless VLAN. A managed switch alone does not provide inter-VLAN firewall enforcement.

## Progress
| Phase | Deliverable | Status |
|---|---|---|
| 1 | Plan, inventory, topology, requirements | In progress |
| 2 | Raspberry Pi OS, SSH, updates, storage | Not started |
| 3 | Docker and Frigate baseline | Not started |
| 4 | Camera streaming and local AI detection | Not started |
| 5 | VLANs, DHCP, routing, firewall rules | Not started |
| 6 | Monitoring, validation, troubleshooting, portfolio write-up | Not started |

## Hardware (planned / to verify)
- Raspberry Pi 4 (RAM capacity to confirm)
- T-Mobile Home Internet gateway (model to confirm)
- Older Netgear device (model to confirm; C3700-NAR only a possibility)
- One RTSP-capable indoor/outdoor camera (not yet selected)
- External SSD (optional, recommended for recordings)
- Managed switch / VLAN-capable router / access point (not yet selected)
- Supported AI accelerator (optional; evaluate feasibility first)

## Documentation
- [Roadmap](docs/project-roadmap.md)
- [Inventory](docs/hardware-inventory.md)
- [Architecture](docs/network-architecture.md)
- [IP plan](docs/ip-addressing.md)
- [Security policies](docs/security-policies.md)
- [Troubleshooting log](docs/troubleshooting-log.md)
- [Test plan](testing/connectivity-tests.md)

## Security and privacy
Never commit credentials, `.env` files, tokens, real camera URLs with passwords, private IP-to-location mappings, sensitive network details, or recordings. Use redacted screenshots and example configurations. Keep Frigate private; do not expose it directly to the internet.

## Skills demonstrated (as completed)
TCP/IP · VLANs · DHCP · Routing · Firewall policy · Linux · Docker · RTSP · Local AI inference · Packet analysis · Monitoring · Technical documentation

## References
- Frigate documentation: https://docs.frigate.video/
- Docker documentation: https://docs.docker.com/
- Raspberry Pi documentation: https://www.raspberrypi.com/documentation/

## License
See [LICENSE](LICENSE). This repository documents a personal learning project and is not affiliated with Frigate or hardware vendors.
