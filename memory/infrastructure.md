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
- **Tailscale IP:** 100.122.247.36
- **SSH:** `ssh rpi` (Tailscale) or `ssh rpi-local` (LAN)
- **Key:** C:\Users\david\.ssh\rpi_ed25519
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

## Gaming PC
- **GPU:** NVIDIA GTX 1080 Ti (11 GB VRAM)
- **Status:** Currently offline / not on network
- **Planned:** Ollama for local LLM inference, Tailscale, openclaw provider
- **LAN:** Not yet discovered (was not online during network scan)

## Cloud Environment
- Accessible from iPhone
- Sandboxed — cannot send Telegram messages or access local infra
- Good for coding on the go, limited for system integration

## Networking
- **Tailscale:** Mesh VPN across all devices, zero-config, works from any network
- **LAN:** 192.168.0.x subnet, router at .1
- **Key devices on LAN:** RPi (.185), Surface (.154), LG TV (.151)

## openclaw
- **Config:** C:\Users\david\.openclaw\openclaw.json
- **Gateway:** local mode, token auth
- **Token:** configured in openclaw.json
- **Status:** Gateway runs, no LLM provider configured (no API keys)
- **Pending:** Telegram bot channel, free LLM provider (Groq/Gemini/Ollama)
