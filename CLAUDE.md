# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## ⚠️ CRITICAL: Pine Script Documentation Validation

**ALWAYS use Context7 MCP to validate Pine Script information.** Pine Script has frequent version changes and syntax updates that may not be in your training data.

Before writing or modifying Pine Script code:
1. Use `mcp__context7__resolve-library-id` with `libraryName: "pinescript"` or `libraryName: "tradingview pine script"`
2. Use `mcp__context7__query-docs` to verify function signatures, parameters, and syntax
3. Never assume Pine Script syntax - always verify against current documentation

This is mandatory when:
- You are unsure about a function's parameters or return type
- Working with newer Pine Script v6 features
- The user reports a compilation error
- Implementing built-in functions you haven't recently verified

## Repository Overview

This is a collection of TradingView Pine Script indicators focused on ICT (Inner Circle Trader) and SMC (Smart Money Concepts) trading methodologies. All indicators are written in Pine Script v6 and designed to work together as a complementary suite.

## Key Indicators

- **ICT Order Block Pro** (`ict-order-block-pro-paganie.pine`) - The flagship indicator. Institutional order block detection with liquidity sweeps, volume profile enhancement, and Power Row for real-time buy/sell pressure. Most complex indicator (~114KB).
- **Pagani Breakout Quality Engine** (`pagani-breakout-quality-engine.pine`) - Breakout scoring system using compression detection, key level analysis (PDH/PDL, PWH/PWL, H1 pivots), and acceptance/retest confirmation.
- **BTC Volume Analysis** (`btc-volume-analysis-paganie.pine`) - Multi-timeframe volume sentiment with intrabar buy/sell pressure analysis.
- **Parabolic Exhaustion** indicators - Multiple variants for detecting exhaustion patterns and potential reversals.
- **Regime-Aware Institutional VWAP** (`regime-aware-institutional-vwap.pine`) - VWAP with market regime awareness.

## Pine Script Development Notes

### Version and Constraints
- All indicators use Pine Script v6 (`//@version=6`)
- TradingView object limits: 500 boxes, 500 lines, 500 labels max
- Use `max_bars_back()` for targeted history buffers instead of `indicator(max_bars_back=...)`

### Common Patterns in This Codebase

**Settings Organization**: Settings are grouped logically with emojis for visual hierarchy:
```pinescript
group = "⚙️ Mode"
group = "🔥 Premium Features"
group = "Liquidity Sweeps"
```

**Signal Timing**: Most indicators support both realtime (intrabar) and confirmed (bar close) modes via `signalTiming` input.

**Auto Mode**: The ICT Order Block Pro uses a Settings Mode (Auto/Manual) pattern where Auto optimizes all settings based on timeframe.

**Strength Scoring**: Quality ratings use a consistent system: ★ Elite (4), ◆ Strong (3), ◇ Mid (2), ○ Weak (1).

**Volume Classification**: Two methods used across indicators:
- Pressure method: `(close-low)/(high-low)` ratio for proportional buy/sell assignment
- Polarity method: Binary classification based on candle color

### Performance Considerations
- VP (Volume Profile) analysis uses nested loops - auto-scale lookback on lower timeframes
- Use `renderMode` options (Gradient/Simple fill/Borders only) to reduce object count
- Conditional pre-computation for scalper mode to skip unused calculations

## Documentation Files

- `CHANGELOG.md` - Version history for ICT Order Block Pro with feature explanations
- `ICT_Order_Block_Pro_Pagani_Quick_Start_v3.1.md` - Detailed user guide including settings, troubleshooting, and trading strategies

## Testing Pine Script Changes

Pine Script is tested directly in TradingView:
1. Copy the `.pine` file contents
2. Paste into TradingView Pine Editor
3. Add to chart to verify compilation and visual output
4. Test across multiple timeframes and symbols

There are no automated tests or build systems for Pine Script.
