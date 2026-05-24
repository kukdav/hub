---
name: devices-and-storage
description: All devices, drives, speeds, roles, backup status, USB stick scheme, cold vault plan
metadata:
  type: project
---

# Devices & Storage

## Compute Devices
| Device | Role | Tailscale IP | Status |
|---|---|---|---|
| Gaming PC (1080) | Compute, AI, storage, network specialist | 100.119.168.35 | Online, SSH, OpenClaw, Ollama |
| RPi 4B | Orchestrator, always-on, RPInvest | 100.122.247.36 | Online LAN, Tailscale status unclear |
| Surface Pro 8 | Human interface, banking, docs, dev | 100.112.191.59 | Pending factory reset |
| iPhone Firma | Always-with, voice, Telegram | on tailnet | Active |
| Pixel 6 Graphene | Privacy SSH client, sensitive tasks | — | Available |

## Storage — Gaming PC
| Drive | Size | Type | Purpose | Free |
|---|---|---|---|---|
| C: | 512 GB | SSD | OS + apps | ~41 GB (watch) |
| D: | 4 TB | HDD | Main storage, receiving F: data | ~987 GB |
| E: | 120 GB | — | Portable staging | ~112 GB |
| F: | 4.5 TB | USB HDD | INCOMING — move to D: then secure wipe | 333 GB data |

> TODO: Run `winsat disk` to get actual speed numbers for C: and D:

## F: → D: Migration Status (2026-05-24)
- File pipeline ran: 333 GB copied to D:\Sorted\ (22K code, 393 docs, 1142 media, 107 GB review)
- Completeness check: PENDING (background task failed, needs re-run)
- **Do NOT wipe F: until completeness verified**
- Secure wipe estimate: 37–75 hours (5× random + zeros on 4.5 TB)
- Tool needed: Linux `shred` or boot USB with nwipe

## Cold Storage Vault Plan (F: after wipe)
- Full encrypted VeraCrypt container on F: drive
- Contents: all repos, second-brain, hub, documents, iCloud export, IBKR config
- Add plausible decoy partition (deniable encryption)
- Store in Faraday bag, off-site from PC
- Encryption: AES-256-XTS + Whirlpool, 30+ char passphrase

## USB Stick — DataTraveler 2000
- Hardware AES-256, physical keypad PIN
- Rename label to: CLAUDE_USB
- Cross-device folder structure:
```
CLAUDE_USB/
├── CLAUDE.md       ← instructions
├── Gaming-PC/
├── Surface/
├── Pi/
├── inbox/
└── _context/current.md   ← cross-session state snapshot
```
- Rule: read _context/current.md first, process inbox, update before ejecting

## Backup Status
| Device | Backed up? | Location |
|---|---|---|
| Surface C: | YES (2026-05-18) | F:\Backups\2026-05-21\ — VeraCrypt + 7z |
| Pi | YES (2026-05-22) | F:\Backups\raspberry_pi\ |
| Gaming PC | NO | — |
| iCloud photos | Unknown | — |
| Repos | Partial | GitHub: hub, DigiBar |

## Surface Factory Reset Plan
- Battery 87% health — do not drop below 80%
- Bad power optimizer script from previous Claude session — factory reset clears it
- Post-reset role: secure/clean device (banking, docs, dev testing)
- Keep: small encrypted backups, large scratch space for dev/sandbox (WSL2 or VM)
- Enable Windows Hello biometrics on all sensitive access
- No large files — stays lean

## Pi Tailscale Status
- SSH key found: D:\Sorted\Review\rpi_ed25519
- SSH config needed on Gaming PC: ~/.ssh/config with Host rpi → 100.122.247.36
- Pi Tailscale: reportedly not working — needs check next session
- Connection to verify: Gaming PC → Pi via Tailscale SSH
