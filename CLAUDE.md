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
- **Pagani Breakout Quality Engine** (`pagani-breakout-quality-engine.pine`) - Breakout scoring system using key level analysis (PDH/PDL, PWH/PWL, H1 pivots), and acceptance/retest confirmation.
- **BTC Volume Analysis** (`btc-volume-analysis-paganie.pine`) - Multi-timeframe volume sentiment with intrabar buy/sell pressure analysis.
- **Pagani Dashboard Hub** (`pagani-dashboard-hub.pine`) - Unified dashboard consolidating data from BTC Volume Analysis, BQE, and ICT Order Block Pro. Use this to declutter by disabling individual indicator dashboards.
- **Crypto S&D Zones** (`crypto-sd-zones.pine`) - Supply/demand zone detection with crypto-specific filters (BTC.D, Open Interest, weekend penalty).
- **Parabolic Exhaustion** (`parabolic-exhaustion-paganie.pine`, `parabolic-exhaustion-reversal-pro.pine`) - Exhaustion pattern detection for potential reversals. The "Reversal Pro" variant has additional confirmation logic.
- **Regime-Aware Institutional VWAP** (`regime-aware-institutional-vwap.pine`) - VWAP with market regime awareness.

## Pine Script Development Notes

### Version and Constraints
- All indicators use Pine Script v6 (`//@version=6`)
- TradingView object limits: 500 boxes, 500 lines, 500 labels max
- Use `max_bars_back()` for targeted history buffers instead of `indicator(max_bars_back=...)`

### Common Patterns in This Codebase

**Settings Organization**: Settings are grouped with emoji prefixes and uppercase constants:
```pinescript
string GRP_MODE = "⚙️ Mode"
string GRP_MOD = "📊 Modules"
string GRP_VIS = "🎨 Visuals"
string GRP_ALERT = "🔔 Alerts"
string GRP_INT = "🛠️ Internal Tuning"
```

**Effective Settings Pattern**: Auto/Manual mode with derived effective values:
```pinescript
string tfBasedPreset = is_scalping ? "Scalping" : is_swing ? "Swing" : "Position"
string effectivePreset = (settingsMode == "Manual" and manualPreset != "Auto") ? manualPreset : tfBasedPreset
bool effectiveAutoMode = settingsMode == "Auto"
```

**Signal Timing**: Most indicators support both realtime (intrabar) and confirmed (bar close) modes via `signalTiming` input.

**Auto Mode**: The ICT Order Block Pro uses a Settings Mode (Auto/Manual) pattern where Auto optimizes all settings based on timeframe.

**Strength Scoring**: Quality ratings use a consistent system: ★ Elite (4), ◆ Strong (3), ◇ Mid (2), ○ Weak (1).

**Volume Classification**: Two methods used across indicators:
- Pressure method: `(close-low)/(high-low)` ratio for proportional buy/sell assignment
- Polarity method: Binary classification based on candle color

**Timeframe Auto-Detection**: Standard pattern across indicators:
```pinescript
tf_in_minutes = timeframe.in_seconds() / 60
is_scalping = tf_in_minutes <= 15
is_swing = tf_in_minutes > 15 and tf_in_minutes <= 240
is_position = tf_in_minutes > 240
```

**Direction Constants**: Avoid string comparisons with integer constants:
```pinescript
int DIR_BULL = 1
int DIR_BEAR = -1
```

**User-Defined Types**: Structured data uses `type` keyword (Pine Script v5+):
```pinescript
type Zone
    float   top
    float   bottom
    int     start_bar
```

**Helper Functions**: Common utilities across indicators:
```pinescript
round2(float x) => math.round(x * 100) / 100
round1(float x) => math.round(x * 10) / 10
safeDivide(float num, float denom) => na(num) or na(denom) or denom == 0 ? na : num / denom
formatVolume(float vol) => vol >= 1000000 ? str.tostring(round2(vol/1000000)) + "M" : vol >= 1000 ? str.tostring(round2(vol/1000)) + "K" : str.tostring(math.round(vol))
strengthSymbol(string s) => s == "Elite" ? "★" : s == "Strong" ? "◆" : s == "Mid" ? "◇" : "○"
```

### Performance Considerations
- VP (Volume Profile) analysis uses nested loops - auto-scale lookback on lower timeframes
- Use `renderMode` options (Gradient/Simple fill/Borders only) to reduce object count
- Conditional pre-computation for scalper mode to skip unused calculations
- Consolidate `request.security()` calls where possible (e.g., fetch OHLCV in one call via tuple return)
- Use `request.security_lower_tf()` for intrabar analysis instead of multiple single-bar requests
- Use targeted `max_bars_back()` on individual series instead of global `indicator(max_bars_back=...)`:
```pinescript
max_bars_back(open, 600)
max_bars_back(high, 600)
max_bars_back(close, 600)
max_bars_back(volume, 600)
```

### Alert Patterns
**Edge-Triggered Alerts** (anti-spam): Use state variables to fire once per event:
```pinescript
var bool wasInZone = false
bool isInZone = close >= zoneBottom and close <= zoneTop
bool justEntered = isInZone and not wasInZone
wasInZone := isInZone
// justEntered only fires on transition, not while staying in zone
```

### File Header Convention
Each indicator follows this version header pattern:
```pinescript
//@version=6
indicator("Name [Paganie] vX.Y.Z", overlay=true, max_boxes_count=500, max_lines_count=500, max_labels_count=500)

// ============================================================================
// INDICATOR NAME VX.Y.Z - BRIEF DESCRIPTION
// Longer description of purpose
//
// VX.Y.Z - Changelog Title:
// • Bullet point changes
// ============================================================================
```

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
