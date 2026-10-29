# Algorithmic Trading Strategy

A multi-factor trend-following strategy, with an objective to beat the benchmark, evaluated on historical 1-hour Ethereum (`ETH-USDT`) data.

##  Technical Indicators & Strategy Logic

The strategy combines moving average crossovers, momentum filters, trend strength, and volume confirmation to determine entry and exit points:

* **Trend Filter (Moving Averages)**: Uses a Fast Exponential Moving Average (`EMA` span = 20) and a Slow Exponential Moving Average (`EMA` span = 50).
* **Trend Strength (`ADX`)**: Average Directional Index (period = 14) ensures positions are taken only when trend strength is sufficient (`ADX > 15`).
* **Momentum Filter (`RSI`)**: Relative Strength Index (period = 14) filters out overbought conditions (`RSI < 75` for entries).
* **Volume Confirmation**: Requires current candle volume to exceed the 15-period volume moving average (`Volume > Volume_MA`).

### Entry & Exit Rules
* **LONG Entry**: Triggered when the Fast EMA crosses above the Slow EMA, supported by an ADX > 15, RSI < 75, and volume above its 15-period moving average.
* **LONG Exit**: Triggered on the reverse crossover (Fast EMA crosses below the Slow EMA).

---

##  Backtest Summary

* **Net Profit**: 21,580.99 USDT (215.81% total return)
* **Sharpe Ratio**: 1.67
* **Sortino Ratio**: 1.02
* **Max Drawdown**: -21.88%
* **Win Rate**: 42.50% (80 trades total)
* **CAGR**: 46.60%
* **Transaction Fees**: 2,848.17 USDT
