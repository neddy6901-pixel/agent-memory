---
title: Raspberry Pi 5 Server
created: 2026-05-16
updated: 2026-05-16
type: entity
tags: [hardware, environment, service]
confidence: high
sources: [session-2026-05-16]
---

# Raspberry Pi 5 Server

James's home server. Runs agent services, Open WebUI, and the wiki sync.

## Hardware
- **Board**: Raspberry Pi 5
- **Cooling**: Argon THRML fan on 4-pin JST header
  - Stock heatsink removed (using Argon cooler instead)
  - Custom fan baseline: ~1,700 RPM at idle
- **Fan Control**: Custom systemd service `pi5-fan-baseline`
  - Script: `/usr/local/bin/pi5-fan-baseline.sh`
  - Lowers first thermal trip point from 50°C to 35°C
  - Fan runs at idle instead of staying at 0% until 50°C

## Network
- Two locations: home address and mom's address
- WiFi networks differ between locations
- Local IP addresses differ between locations
- This complicates local-network services
- API server runs on this Pi
  - Host: `0.0.0.0`
  - Port: `8642`
  - Key: `Jessicathr33`

## Services
- **Open WebUI** → port 8080 (accessed from iPad browser)
- **Hermes Agent** → runs here
- **Wiki sync** → Git auto-push to GitHub
- **API server** → port 8642

## Model Setup
- Cloud-only (local Ollama models don't work reliably)
- Main: `kimi-k2.6:cloud`
- Fallback: `qwen3:cloud`

## Related
- [[james]] — the user
- [[network-notes]] — network-specific gotchas
