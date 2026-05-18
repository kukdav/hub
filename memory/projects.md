# Projects

## RPInvest — Quantitative Finance System
**Location:** RPi `~/Desktop/fin/`

### Environments
| Env | Branch | Purpose |
|-----|--------|---------|
| dev | dev | Experimental strategies, backtesting |
| beta | beta | Paper trading validation |
| prod | main | Live trading via IBKR |

### AI Agent Roles (from AGENT_README.md)
1. **Live-Betrieb** — monitors live system, checks cron, validates signals
2. **Datenmanager** — data pipeline, S&P 500 download, database integrity
3. **Research** — strategy development, backtesting, statistical analysis
4. **Hardlogic** — enforces no-lookahead bias, code review for data leaks
5. **Andere** — general tasks, documentation, infrastructure
6. **IBKR Manager** — Interactive Brokers gateway, order execution, health checks

### Daily Flow
- Cron triggers daily runner
- Downloads latest market data
- Runs strategy signals
- IBKR Gateway executes trades (prod only)
- Health check timer monitors gateway status

### Key Files
- `ai/AGENT_README.md` — role definitions, coordination rules
- `rpinvest/LIVE_INFRASTRUCTURE.md` — system architecture
- `claude_rpinvest/run.py` — main runner
- `claude_rpinvest/sp500_downloader/` — data pipeline
- `claude_rpinvest/.env` — environment config

## openclaw — Personal AI Assistant
**Location:** Surface `C:\Users\david\.openclaw\`
- Telegram bot interface (token regenerated, not yet connected)
- Gateway with 45 provider plugins
- Needs: free LLM backend (Groq/Gemini or Ollama on Gaming PC)

## AI-Sync Protocol
**Location:** RPi `~/Desktop/ai_chats/ai_chatlog.md`
- Structured AI-to-AI communication format
- Task requests between CursorAI and StrategyAI threads
- 29KB of coordination history

## Central Hub (this repo)
**Location:** RPi `~/hub/` + GitHub kukdav/hub
- Single source of truth for all AI sessions
- Memory files for persistent context
- Cloned on all devices
