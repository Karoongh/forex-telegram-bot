# TRADING-SCREEN-RULES — FX-TRADER-01

> Operational rules for every monitor or phone screen that appears in images of FX-TRADER-01.
> This document works together with:
> - CHARACTER-LOCK.md (identity)
> - the character-identity-lock skill
> - the trading-screen-accuracy skill

## Status

**ACTIVE — 2026-10-02**

Every visible trading screen must pass these rules before the image can be approved.

## Core Principles

1. Screens are never decorative. Every chart must show a real-looking trade.
2. Preferred pair: **XAUUSD** on **M30** timeframe.
3. Allowed pairs (priority order): XAUUSD, EURUSD, GBPUSD, USDJPY, US30, NAS100.
4. Trade must usually be in profit.
5. Lot size and leverage must be realistic and not reckless.
6. Take Profit must be visible. Stop Loss should be visible when possible.
7. Risk-Reward target: approximately 1:3 or 1:4.
8. Candles, prices and indicators must look accurate.
9. UI must resemble real MetaTrader 5 (desktop or iPhone) or TradingView.
10. If any screen rule fails → fix **only** that problem. Do not redesign identity or the whole scene.

## Required Checklist (every screen)

### A. Platform & Timeframe
- [ ] Platform is clearly MT5 desktop, MT5 iPhone, or TradingView
- [ ] Timeframe is M30 (preferred) or clearly stated
- [ ] Pair is one of the allowed pairs (XAUUSD preferred)

### B. Trade Reality
- [ ] Candles look realistic (proper body/wick ratios)
- [ ] Current price is consistent with recent candles
- [ ] Trade is in profit (or very close and still valid)
- [ ] Entry, Take Profit and preferably Stop Loss are visible
- [ ] Risk-Reward is approximately 1:3 or 1:4

### C. Risk Management
- [ ] Lot size is logical (typical 0.20 – 0.50 for gold; never extreme)
- [ ] Leverage is reasonable (not 1:500 or 1:1000 shown as normal)
- [ ] Not multiple oversized positions open at once
- [ ] No gambling / all-in appearance

### D. Indicators
- [ ] Maximum one or two well-known indicators
- [ ] Preferred: 50 EMA + RSI, or 20 & 50 EMA, or Bollinger + RSI, or MACD
- [ ] Indicators do not clutter the chart

### E. UI Fidelity
- [ ] Looks like real MT5 (desktop or iPhone) or TradingView
- [ ] No obviously fake or generic AI chart appearance

## Risk Limits (Quick Reference)

| Parameter       | Allowed                          | Forbidden                  |
|-----------------|----------------------------------|----------------------------|
| Lot size (Gold) | 0.10 – 1.00 (typical 0.20–0.50) | 5+ lots, all-in            |
| Leverage        | 1:50 – 1:200                     | 1:500+, 1:1000+            |
| Open positions  | 1 main position preferred        | Many large simultaneous lots |

## Fix Policy (Critical)

1. Identify the exact failing item.
2. Fix **only** that item (or the screen content).
3. Do not change character identity, body, clothing or overall composition unless they also fail.
4. Re-check the fixed item and the full screen checklist.
5. Only after the screen passes → continue to Physical Realism & Scene Logic.

## Preferred Default Trade (for prompts)

- Symbol: XAUUSD
- Timeframe: M30
- Direction: Buy or Sell (in profit)
- Lot size: 0.20 – 0.50
- Risk-Reward: ≈ 1:3 or 1:4
- Visible Take Profit line
- Visible Stop Loss line (preferred)
- One or two indicators: e.g. 50 EMA + RSI
- Platform: MetaTrader 5 desktop / iPhone or TradingView

## Order of Checks for Every Image

1. Identity Lock (CHARACTER-LOCK.md)
2. Trading Screen Accuracy (this file)
3. Physical Realism & Scene Logic (hands, gaze, props, shadows)

Fail any layer → reject or fix only that layer.
