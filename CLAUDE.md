# David Kukovic - Central Knowledge Hub

This repo is the single source of truth for all AI sessions (Surface, RPi, Cloud, Phone).
Every Claude Code / AI session should read this repo first.

## Identity
- **Name:** David Kukovic
- **GitHub:** kukdav
- **Languages:** German (native), English (fluent)
- **Preferred communication:** German casual, technical terms in English

## Infrastructure
See `memory/infrastructure.md` for full details.
- **Surface Pro 8** — daily driver, Windows 11, Claude Code, openclaw
- **Raspberry Pi** — always-on server, RPInvest trading system, cron jobs, Tailscale SSH
- **Gaming PC** — GTX 1080 Ti (11GB VRAM), Ollama exposed on tailnet at `http://100.119.168.35:11434`, ONLINE
- **Cloud** — iPhone-accessible coding environment, limited (no Telegram, sandboxed)
- **Tailscale** — mesh VPN connecting all devices (RPi: 100.83.139.98, Gaming PC: 100.119.168.35)

## Key Projects
See `memory/projects.md` for full details.
- **RPInvest** — quantitative finance system (S&P 500), 3 environments (dev/beta/prod), 6 AI agent roles, daily signals
- **openclaw** — personal AI assistant with Telegram bot interface
- **Website domains** — owned but not yet deployed

## Rules
- **NEVER** enter API keys, passwords, or secrets in any chat
- **No-lookahead bias** in all backtesting — see `memory/finance-rules.md`
- Always identify which AI model is responding
- Prefer free/local LLM options (Groq, Gemini, Ollama) over paid API
- Central artifacts here — don't duplicate knowledge across sessions

## Memory Files
- `memory/identity.md` — personal info, accounts, preferences
- `memory/infrastructure.md` — all devices, networking, installed software
- `memory/projects.md` — RPInvest structure, roles, environments
- `memory/finance-rules.md` — trading rules, no-lookahead, backtesting conventions
