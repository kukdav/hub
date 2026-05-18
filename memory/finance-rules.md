# Finance & Trading Rules

## No-Lookahead Bias — ABSOLUTE RULE
**Every AI agent working on RPInvest MUST follow these rules.**

### Core Principle
At any point in time t, the system may ONLY use information that was available at or before time t.
No future data may leak into decisions, signals, or model training.

### Specific Rules
1. **Feature calculation:** Only use data available at the time of the trading decision
2. **Train/test splits:** Training data must strictly precede test data chronologically
3. **Parameter tuning:** No optimization on future data — use walk-forward or expanding window
4. **Signal generation:** Signals for day t use only data up to market close on day t-1
5. **Survivorship bias:** Use point-in-time S&P 500 constituents, not current list
6. **Transaction costs:** Always include realistic slippage and commission estimates

### Code Review Checklist (Hardlogic Agent)
- [ ] No `.shift(-1)` or negative shifts on target variables
- [ ] No `.rolling()` windows that include current or future data
- [ ] No joins that leak future information
- [ ] Train/test split is temporal, not random
- [ ] No features derived from future price movements
- [ ] Index alignment is correct after merges

## Backtesting Conventions
- **Benchmark:** S&P 500 (SPY)
- **Metrics:** Sharpe ratio, max drawdown, annual return, win rate
- **Minimum test period:** 2 years out-of-sample
- **Walk-forward:** Preferred over single train/test split
- **Results reporting:** Always include drawdown and transaction costs

## IBKR Integration
- Gateway runs on RPi with health check timer
- Paper trading in beta environment
- Live trading only on main/prod branch
- All orders must be logged and reconciled
