# Momentum Strategy Backtest 📈
A Python backtest of a simple moving-average crossover (momentum) strategy applied to equity price data.


## Overview
This project implements a **10-day vs 50-day Simple Moving Average (SMA) crossover** strategy to test short-term momentum in equity prices.  
The notebook downloads data via `yfinance`, generates buy/sell signals, and evaluates key performance metrics such as **CAGR, Sharpe Ratio, Max Drawdown, and Exposure**.

## Methodology
- **Data Source:** Yahoo Finance (adjusted close prices)  
- **Instrument Tested:** AAPL (Apple Inc.)  
- **Backtest Period:** 2015 – 2025  
- **Indicators Used:** SMA(10) and SMA(50)  
- **Trading Logic:**  
  - Buy when SMA(10) > SMA(50)  
  - Sell when SMA(10) < SMA(50)  
- **Transaction Cost:** 5 bps per trade (round trip)

## Key Results (AAPL)
| Metric | Value |
|:-------------------------------|:---------:|
| Total Return | **386.3 %** |
| CAGR | **15.8 %** |
| Sharpe Ratio | **0.87** |
| Max Drawdown | **-25.9 %** |
| Average Exposure | **61.7 %** |
| Number of Round-Trip Trades | **35** |
| Win Rate | **51.4 %** |

## Results & Insights
- The SMA crossover **captured large upward trends** but lagged during prolonged bull phases due to whipsaws.  
- The strategy maintained **lower drawdowns** than buy-and-hold, showing improved downside protection.  
- Roughly **62 % market exposure** reduced risk while keeping reasonable returns.  
- A **Sharpe ratio near 0.9** indicates balanced risk-adjusted performance.  
- Results confirm that **momentum performs best in trending regimes**, but weakens in sideways markets.  
- Enhancements such as volatility filters, adaptive SMAs, or position-sizing rules could further improve stability.

## Files
| File | Description |
|------|--------------|
| `Momentum_Strategy_Backtest.ipynb` | Main Jupyter Notebook with full backtest and plots |
| `AAPL_momentum_results.csv` | Daily level backtest results |
| `AAPL_momentum_summary.csv` | Summary metrics of the strategy |
| `AAPL_trade_summary.csv` | Trade-by-trade P&L and holding period data |
| `requirements.txt` | Python dependencies for environment setup |

## Future Extensions
- Parameter optimization (grid search over SMA lengths)  
- Multi-asset portfolio backtesting  
- Regime-based momentum with volatility or RSI filters  
- Integration with position-sizing and risk-control models  



