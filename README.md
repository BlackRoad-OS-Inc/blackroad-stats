<div align="center">
<img src="https://images.blackroad.io/pixel-art/road-logo.png" alt="BlackRoad OS" width="80" />

# BlackRoad Stats

**Live fleet metrics API. KV-backed telemetry from all 5 Raspberry Pi nodes.**

[![BlackRoad OS](https://img.shields.io/badge/BlackRoad_OS-Pave_Tomorrow-FF2255?style=for-the-badge&labelColor=000000)](https://blackroad.io)
</div>

---

## Live

**[stats-blackroad.amundsonalexa.workers.dev](https://stats-blackroad.amundsonalexa.workers.dev/fleet)**

## Endpoints

```bash
# Full fleet status (all 5 nodes)
curl https://stats-blackroad.amundsonalexa.workers.dev/fleet

# Response includes per-node:
# name, host, status, uptime, cpu_temp, cpu_pct, mem_total/used,
# disk_pct, ollama_models, docker_containers, tcp_ports, services
```

## Current Fleet

| Node | IP | Role | Hardware |
|------|----|------|----------|
| Alice | .49 | Gateway, DNS, DB | Pi 400 |
| Cecilia | .96 | AI Inference | Pi 5 + Hailo-8 |
| Octavia | .101 | Git, Docker | Pi 5 + Hailo-8 |
| Aria | .98 | Monitoring | Pi 5 |
| Lucidia | .38 | Apps, CI | Pi 5 |

## Stack

- Cloudflare Workers + KV
- SSH-based collectors on each Pi (cron */5)
- JSON telemetry pushed to KV

---

*Copyright (c) 2024-2026 BlackRoad OS, Inc. All rights reserved.*
