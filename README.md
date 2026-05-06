# Advanced Donchian Channel Strategy (Multi-Mode & Dynamic)

This repository contains a professional-grade trading strategy based on the **Donchian Channel** indicator. Unlike standard breakout systems, this version incorporates advanced volatility filters, percentage-based logic, and a Mean Reversion toggle to adapt to different market regimes.

## 📌 Strategy Overview

The core of the strategy utilizes the highest high and lowest low over a specific period to create dynamic support and resistance zones. It is designed to be versatile, allowing traders to switch between aggressive trend-following and conservative mean-reversion tactics.

### Key Features:
- **Dual Mode Execution**: Switch between `Trend Following (Breakout)` and `Mean Reversion (Mean Rev)`.
- **Volatility Filtering**: Integrated Channel Width filter to avoid trading in "choppy" or "overextended" markets.
- **Percentage-Based Logic**: All calculations (buffers, widths, and exits) are percentage-based, making the strategy asset-agnostic (works on BTC, Forex, or Equities without recalibration).
- **Dynamic Risk Management**: Built-in Stop Loss and Take Profit settings.

---

## 🛠 Strategic Logic

### 1. Trend Following (Breakout Mode)
In this mode, the strategy follows the momentum. 
- **Long Entry**: Triggered when the price closes above the Upper Band plus a user-defined percentage buffer.
- **Short Entry**: Triggered when the price closes below the Lower Band minus a user-defined percentage buffer.
- *Goal*: Catching major trend expansions.

### 2. Mean Reversion Mode
Designed for ranging markets where price tends to return to the average.
- **Long Entry**: Triggered when the price touches or drops below the Lower Band (oversold condition).
- **Short Entry**: Triggered when the price touches or exceeds the Upper Band (overbought condition).
- *Goal*: Scalping reversals at the edges of the channel.

### 3. Channel Width Filter (Kanal Genişliği)
To increase the quality of signals, the strategy calculates the distance between the bands:
- **Min Width %**: Prevents entering trades during low-volatility periods where "fake-outs" are common.
- **Max Width %**: Prevents entering "late" into a trend after the move has already become overextended.

---

## ⚙️ Input Parameters

| Input | Type | Description |
| :--- | :--- | :--- |
| **Strategy Mode** | Dropdown | Choose between `Breakout` or `Mean Reversion`. |
| **Donchian Period** | Integer | The lookback period (e.g., 20) for calculating bands. |
| **Breakout Buffer (%)** | Float | Extra % distance required above/below bands to confirm a breakout. |
| **Min Channel Width %** | Float | Minimum required % difference between bands to allow a trade. |
| **Max Channel Width %** | Float | Maximum allowed % difference between bands to prevent overextension. |
| **Stop Loss (%)** | Float | Percentage-based hard stop from the entry price. |
| **Take Profit (%)** | Float | Percentage-based target for closing positions. |

---

## 📈 Usage Instructions

1.  **Installation**: Copy the script into your Pine Editor (TradingView) or Python environment.
2.  **Backtesting**: Use the Strategy Tester to find the optimal `Channel Width` for your specific timeframe.
3.  **Optimization**: 
    - For **Scalping**: Use lower timeframes (5m, 15m) with Mean Reversion mode.
    - For **Swing Trading**: Use higher timeframes (4H, Daily) with Breakout mode.

## 📜 Disclaimer
This software is for educational purposes only. Trading involves significant risk. Always perform your own due diligence and backtest thoroughly before using real capital.

---
**Author:** [Senin Adın/Kullanıcı Adın]  
**License:** MIT
