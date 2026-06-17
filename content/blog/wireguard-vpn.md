+++
title = "Self-Hosted WireGuard VPN"
description = "Running a WireGuard VPN server in Docker on a VPS for personal use."
date = 2026-06-18

[taxonomies]
tags = ["wireguard", "vpn", "docker", "privacy"]
+++

I run a WireGuard VPN server in a Docker container on a Hetzner VPS. I use it to route traffic from my laptop and phone when I'm on untrusted networks.

The setup uses the `linuxserver/wireguard` Docker image. Configuration is straightforward:

```yaml
services:
  wireguard:
    image: lscr.io/linuxserver/wireguard:latest
    cap_add: [NET_ADMIN, SYS_MODULE]
    environment:
      - SERVERURL=<vps-ip>
      - SERVERPORT=51820
      - PEERS=laptop,phone
      - PEERDNS=1.1.1.1
      - ALLOWEDIPS=0.0.0.0/0
    ports:
      - 51820:51820/udp
    volumes:
      - ./config:/config
      - /lib/modules:/lib/modules
```

The container generates keys and configuration for each peer automatically, saved to `./config/peer_<name>/`. For mobile clients it also outputs a QR code PNG. I imported the laptop config as a file and scanned the QR code from my phone.

A full-tunnel setup routes all traffic through the VPS. Latency is about 2ms above baseline. Bandwidth is limited by the VPS link. No logs unless I turn them on. No maintenance since the initial deploy.
