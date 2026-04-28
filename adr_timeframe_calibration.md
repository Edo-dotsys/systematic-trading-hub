# ADR Timeframe Calibration

**50% ADR target per trade — FX G10, Indices and Gold**

---

## Duration of 15 Candles per Timeframe

| Timeframe | Duration | Notes |
|-----------|----------|-------|
| M5 | 75 min (~1h 15) | |
| M15 | 225 min (~3h 45) | |
| M30 | 450 min (~7h 30) | Almost the entire trading session |

---

## FX G10 — Timeframe Calibration

| Pair | ADR (pips) | 50% Target | Recommended TF | Best for ABC |
|------|-----------|------------|----------------|--------------|
| EUR/USD | 80–90 | 40–45 pips | M5, M15 | M15 — cleaner ABC |
| GBP/USD | 90–120 | 45–60 pips | M5, M15 | M15 |
| USD/JPY | 60–80 | 30–40 pips | M5, M15 | M5 |
| USD/CHF | 60–75 | 30–37 pips | M5 | M5 |
| AUD/USD | 65–80 | 32–40 pips | M5, M15 | M5 |
| NZD/USD | 65–75 | 32–37 pips | M5 | M5 |
| USD/CAD | 65–90 | 32–45 pips | M5, M15 | M15 |
| EUR/GBP | 50–65 | 25–32 pips | M5 | M5 — low ADR |
| **EUR/JPY** | **100–130** | **50–65 pips** | **M15, M30** | **M15–M30** |
| **GBP/JPY** | **120–150** | **60–75 pips** | **M15, M30** | **M30 — wide structure** |

---

## Indices and Gold

| Instrument | Avg ADR | 50% Target | Recommended TF | Best for ABC |
|------------|---------|------------|----------------|--------------|
| **NAS100** | **300–450 pt** | **150–225 pt** | **M15, M30** | **M15–M30** |
| SP500 | 50–80 pt | 25–40 pt | M5, M15 | M5–M15 |
| DAX | 180–280 pt | 90–140 pt | M15, M30 | M15 |
| CAC40 | 80–130 pt | 40–65 pt | M5, M15 | M15 |
| **Gold XAU/USD** | **60–80 $** | **30–40 $** | **M5, M15** | **M15** |

---

## ⚠️ M30 Warning

15 candles on M30 = 7h30, nearly the full London + New York session.

Only suitable for high-ADR instruments like **GBP/JPY**, **EUR/JPY** and **NAS100**. On low-ADR instruments you risk exhausting the daily range within the 15-candle window.

> **Remember:** 10–15 candles is a maximum time-based invalidation limit, not a fixed target — if the ABC structure completes in 8 candles, the trade is done.
