# MonoQ Bot (Private Instance)

**Owner/Operator:** Wazuki Musashi
**Status:** Development / Experimental
**Focus:** Automated Quantitative Trading & Market Analysis

---

## Architecture Overview

This is a personal algorithmic trading stack using a multi-agent system to analyze, backtest, and execute trades on the Solana network.

### Core Agents
- **`rbi_agent.py`**: Research-Backtest-Implement. Converts external strategy ideas (video/text) into executable code.
- **`trading_agent.py`**: Executor. Makes buy/sell decisions based on generated signals.
- **`risk_agent.py`**: Guardian. Enforces max drawdown, position sizing, and stop-loss rules.
- **`strategy_agent.py`**: Validator. Verifies signals before execution.

### Market Scanners
- **`whale_agent.py`**: Monitors large capital movements and anomalies.
- **`liquidation_agent.py`**: Tracks liquidation events for potential reversal setups.
- **`funding_agent.py`**: Identifies high funding rate arbitrage opportunities.
- **`listingarb_agent.py`**: Scans for new tokens prior to major exchange listings.
- **`sentiment_agent.py`**: Analyzes social media sentiment (Twitter).

---

## Daily Workflow

1.  **Idea Generation**
    - Source strategies (YouTube, papers, social media).
    - Use `rbi_agent.py` to generate backtest code.
    - Validate results in `src/data/rbi/backtests_final/`.

2.  **Live Monitoring**
    - Execute `main.py` to initialize agents.
    - Use `focus_agent.py` for productivity monitoring.
    - Monitor alerts from specialized agents.

3.  **Execution**
    - Load strategies into `src/strategies/custom/`.
    - Use `ezbot.py` for manual overrides if necessary.

---

## Key Directories

- `src/agents/`: Agent logic and implementation.
- `src/strategies/`: Strategy definitions and alpha generation.
- `src/data/`: Logs, charts, and backtest results.
- `src/nice_funcs.py`: Utilities for Solana interactions and data fetching.

---

## Personal Todo List

- [ ] Refine RBI agent prompt for edge cases.
- [ ] Add sources to Sentiment Agent.
- [ ] Backtest "Vengeance" strategy variations.
- [ ] Integrate real-time PnL dashboard.

---

## Operational Notes

- Secure `.env` file credentials.
- Verify `risk_agent` settings before deployment.
- Manually verify backtest results.
- Process control: Terminate `main.py` to stop all operations.

---

*Built by Wazuki Musashi*
