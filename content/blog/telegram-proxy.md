+++
title = "Telegram MTProto Proxy"
description = "Running an MTProto proxy on a VPS so I can connect when Telegram is blocked."
date = 2026-06-18

[taxonomies]
tags = ["telegram", "docker", "proxy", "infrastructure"]
+++

I run a Telegram MTProto proxy on one of my VPSes so I can connect from networks where Telegram is blocked.

It's a single Docker container using the official `telegrammessenger/proxy` image, mapped to port 8448 on the host. The setup is a one-liner:

```bash
docker run -d -p 8448:443 -e SECRET=<random-hex> telegrammessenger/proxy
```

The secret is a 16-byte hex string generated with `head -c 16 /dev/urandom | xxd -ps`. Clients authenticate with a `tg://proxy?server=<ip>&port=8448&secret=<secret>` link. I shared mine with a few people who also run into the same blocks.

No logging, no user tracking, no maintenance. It's been running for months without a single restart.
