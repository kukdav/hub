# Infrastructure

## Surface Pro 8 (daily driver)
- **OS:** Windows 11
- **Storage:** C: ~76 GB free (after cleanup 2026-05-18)
- **External:** E: Seagate 4.6 TB (backups at E:\BackupVonC-2026-05-18\)
- **Software:** Claude Code, Node.js, Python 3.10, Git, openclaw, Tailscale
- **SSH config:** C:\Users\david\.ssh\config
- **PowerShell:** 5.1 (ExecutionPolicy: RemoteSigned for CurrentUser)

## Raspberry Pi (always-on server)
- **LAN IP:** 192.168.0.185 (raspberrypi.local)
- **Tailscale IP:** 100.83.139.98
- **SSH:** `ssh rpi` (Tailscale) or `ssh rpi-local` (LAN)
- **Key:** `~/.ssh/rpi_ed25519_new` (Gaming PC) — no passphrase, authorized on Pi
- **User:** david
- **Software:** Python, Claude Code, gh CLI, Tailscale SSH, cron
- **Key paths:**
  - `~/Desktop/fin/` — RPInvest main directory
  - `~/Desktop/fin/ai/AGENT_README.md` — AI agent roles documentation
  - `~/Desktop/fin/rpinvest/LIVE_INFRASTRUCTURE.md` — live system docs
  - `~/Desktop/fin/claude_rpinvest/` — git repo with .env, run.py, sp500_downloader
  - `~/Desktop/ai_chats/ai_chatlog.md` — AI-Sync protocol (29KB)
  - `~/hub/` — this central knowledge hub repo (git initialized)
- **Cron:** Daily RPInvest runner, IBKR Gateway health check timer

## Gaming PC (1080)
- **Hostname:** desktop-csn80jb
- **GPU:** NVIDIA GTX 1080 Ti (11 GB VRAM), CUDA 12.9, Driver 576.28
- **RAM:** 32 GB
- **Tailscale IP:** 100.119.168.35 ✓ ONLINE
- **Status:** ACTIVE as of 2026-05-24
- **OS:** Windows 11 Pro
- **Software:** Ollama 0.24.0 (5 models), OpenClaw, Claude Code, Python 3.11, Node.js 24
- **Ollama models:** mistral:7b, gemma2:9b, qwen2.5:7b, llama3.1:8b, qwen2.5:14b
- **Ollama endpoint:** http://100.119.168.35:11434 — live, bound to 0.0.0.0, reachable from all tailnet devices
- **Storage:**
  - C: 512GB SSD (OS, apps) — 41 GB free (critical, watch)
  - D: 4TB HDD — encrypted backups only
  - E: 120GB portable — raw storage
  - F: 4.5TB USB HDD — incoming data from network devices
- **Roles:** Compute on demand, Ollama LLM backend, Storage, Researcher, Live-Trader support, Smart Home Controller
- **Local repos:** `~/hub/`, `~/second-brain/`
- **SSH client:** configured — `~/.ssh/config` with `rpi` (Tailscale 100.83.139.98) + `rpi-local` (LAN 192.168.0.185); key `~/.ssh/rpi_ed25519_new` (no passphrase)
- **SSH server:** OpenSSH Server running with autostart
- **OpenClaw:** gateway Scheduled Task installed, Telegram bot active (@cUjAL_bot), Ollama works without cloud API keys
- **CLAUDE_USB:** G: drive (57GB SanDisk exFAT) — labeled CLAUDE_USB, folders: hub/ inbox/ keys/ archive/, CLAUDE.md present
- **file-agent.py:** `--dry-run` flag added (C:\Users\Gaming-PC\Scripts\file-agent.py)

## Cloud Environment
- Accessible from iPhone
- Sandboxed — cannot send Telegram messages or access local infra
- Good for coding on the go, limited for system integration

## Networking
- **Tailscale:** Mesh VPN across all devices, zero-config, works from any network
- **LAN:** 192.168.0.x subnet, router at .1
- **Key devices on LAN:** RPi (.185), Surface (.154), LG TV (.151)

## openclaw
- **Config:** C:\Users\Gaming-PC\.openclaw\
- **Gateway:** Scheduled Task installed on Gaming PC
- **Status:** Telegram bot active (@cUjAL_bot); Ollama usable locally without cloud API keys
- **Pending:** Optional API keys only when explicitly approved
