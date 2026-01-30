# Regime Aware Systematic Momentum Framework

## Abstract
Regime-aware swing trading framework operating exclusively in Stage-2 market cycle. 

**Systematic 4 Layers architecture:**
** 1. Regime Filter**
** 2. Setup Classification**
** 3. Execution**
** 4. Multi-Phase Exits**

### Layer 1: Universal Trading Regime Filter
Stage-2 Uptrend Identification:
Timeframe: Daily
- Structure: EMA(50) > EMA(200) + SMA(200) slope > 0
Timeframe: Weekly
- Momentum: RSI(14) > 40 
  → bearish filter on higher timeframe

### Layer 2: Setup Classification
Timeframe: Daily

**Lane A - Conservative Pullback**
- Structure: Price < EMA(50)
- Volume dry-up: Volume < [70% of max bullish volume in last 20 bars]

**Lane B - Aggressive Pullback**
- Structure: Price < EMA(20) and EMA(20) > EMA(50)
- Momentum: 40< RSI(14) < 70
- Volume stabilization, no accelaration: Volume < [80%; 120%] of ADV(20) 
  → ensures pullback participation without distributional pressure
- Structural Trend Strenght: ROC(20) custom > 0 

  → ROC(20) custom = (Current Close - Lowest Close(20)) / (Lowest Close(20)) * 100

For both lanes, the setup is only valid for the crossoving bars where the price crosses below the EMA(50) or EMA(20) respectively + buffer of 2 bars after the crossover.

### Layer 3: Specific Entry Point
Timeframe: 4-Hour
- First Trigger: 0.0998 VWAP > Current Price > (VWAP - 1.5 * VWAP Standard Deviation(20))
- Second Trigger: Price crosses above EMA(9) OR
                  Price crosses above VWAP +  VWAP Slope > 0
- Volume Confirmation: Volume > 70th Percentile of Volume in last 20 bars

VWAP Setting: Session-based VWAP starting from NY Open. 

### Layer 4: Exit Conditions
**Phase 1 - Initial Stop Loss:**
Timeframe: 4-Hour
- During entry bar, set stop loss at: VWAP - 2.5 * VWAP Standard Deviation(20) - buffer of 1.5%

**Phase 2 - Time Stop:**
Timeframe: Daily
- Exit position if after 10 days from the entry, no volatility expansion is observed

**Phase 3 - Dynamic Trailing Stop:**
Timeframe: Daily
- SL_trail = New_High - ATR(14_Daily) × 2.5
  Update at daily close only if New_High > Previous_High

**Phase 4 - Emergency Exit:**
-  Layer 1 conditions are no longer met on Daily or Weekly timeframe.

**Phase 5 - Profit Target:**
- **TP1 fixed 50% of the position liquidated:**
  Lane A Setup: 3.5:1 RR
  Lane B Setup: 2.5:1 RR

- **TP2 remaining position:**
  Timeframe: daily
  First condition, swing Higher High: Close > max(high last 50 bars)
  Timeframe: 4-Hour
  - MACD bearish divergence on histogram: price_new_high > price_prev_high AND macd_new < macd_prev
  - RSI Overbought condition: RSI(14)t-2 > 70
  - MACD Bearish Crossover: MACD_line(t) < MACD_signal(t) AND MACD_line(t-1) ≥ MACD_signal(t-1)

  Exit when any of the above three conditions are met.