# ICT Order Block Pro [Pagani] - Quick Start Guide

> **📖 Full Documentation:** For the complete interactive guide with detailed instructions, please **download and open `ICT_Order_Block_Pro_Pagani_Quick_Start_v3.1.html` in Google Chrome** to read the full description on how to use this indicator.

## 📋 Quick Reference Card

**Order Block Quality (Focus on these!):**
- ★ Elite = Best (VP + 2-3 confirmations) - **Trade these!**
- ◆ Strong = Good (2-3 confirmations) - **Trade these!**
- ◇ Mid = Okay (1 confirmation) - Use caution
- ○ Weak = Avoid (no confirmations) - Skip

**Entry Checklist:**
1. ✅ Elite★ or Strong◆ block identified
2. ✅ Price retests the zone (see "ACTIVE" status)
3. ✅ Rejection wick forms (↗ BOUNCE or ↘ REJECT)
4. ✅ Volume confirms (check dashboard "Vol" column)
5. ✅ Aligned with trend (check higher timeframe)
6. ✅ Set stop loss beyond OB zone (5-10 pips)

---

## 🚀 What's New in v3.1.0

**ICT LIQUIDITY SWEEP DETECTION:** Track and trade liquidity sweeps like the pros!

✅ **Buy-Side Liquidity (BSL)** - Stops above swing highs (target for bearish sweeps)  
✅ **Sell-Side Liquidity (SSL)** - Stops below swing lows (target for bullish sweeps)  
✅ **Sweep vs Run Detection** - Distinguish reversals from continuations  
✅ **Equal Highs/Lows Detection** - Identify clustered liquidity zones (stronger targets)  
✅ **Quality Scoring** - Strong/Mid/Weak ratings based on wick size, volume, OB confluence  
✅ **Order Block Confluence** - Detects when sweeps occur near existing OB zones  
✅ **Visual Components** - Dashed liquidity lines, sweep event boxes with quality labels  
✅ **Dashboard Integration** - Shows nearest BSL/SSL with distance tracking  
✅ **Flexible Display** - Show levels, sweep events, or runs independently  
✅ **Alert System** - Sweep detection, run detection, and proximity alerts  
✅ **OFF BY DEFAULT** - Enable via "Show Liquidity Levels" or "Mark Sweep Events"  

**Configuration:**
- Configurable swing lookback (5-50 bars, default 20)
- Minimum wick requirements (ATR-based, default 0.5)
- Equal High/Low threshold (0-1%, default 0.1%)
- Volume spike requirement toggle
- Max levels per side (2-12, default 6)

---

## 🚀 What's New in v3.0.1

**PROXIMITY ALERT SYSTEM:** Advance warning before price reaches zones

✅ **Early Warning Alerts** - When price approaches nearest OB zones  
✅ **Configurable Distance** - 0.1-5.0% threshold (optimal: 0.5-2% by timeframe)  
✅ **Smart Quality Filters** - Alert only for Strong/Elite blocks or Fresh zones  
✅ **Directional Approach** - Only alerts when price moving toward zone (actionable)  
✅ **Anti-Spam Tracking** - One alert per approach, resets when price exits  
✅ **Perfect for Prep** - Get ready before price reaches reaction zones  
✅ **Separate Alerts** - "Approaching Bull OB" (LONG prep) and "Approaching Bear OB" (SHORT prep)

---

## 🚀 What's New in v3.0

**PERFORMANCE OPTIMIZATION:** 30-50% faster execution

✅ **Conditional Pre-computation** - Scalper mode skips unused calculations (5 calls/bar saved)  
✅ **VP Early Exit** - O(300) → O(20-50) average when samples collected  
✅ **Single-Pass Overlap** - O(N²) → O(N) with deferred batch deletion  
✅ **Conditional UI Updates** - Only on new bars or state changes  
✅ **Smart Sizing Fix (v2.4.2)** - ICT-aligned zone anchoring (bull=LOW, bear=HIGH)  

---

## 🚀 What's New in v2.4.1

**ADVANCED USER CONTROLS:** Complete customization of signal quality vs frequency

✅ **30+ Advanced Settings** - Fine-tune every aspect of detection and filtering  
✅ **Displacement Tuning** - Control ATR multipliers and body/range thresholds  
✅ **FVG Modes** - Classic, Strict (body gap), Loose (wick gap), or Off  
✅ **Mitigation Controls** - Adjustable penetration thresholds prevent premature deletion  
✅ **Zone Sizing** - Configurable Smart sizing for different volatility levels  
✅ **Strength Scoring** - Customize volume/body thresholds across assets  
✅ **Render Modes** - Gradient/Simple/Borders to avoid TradingView object limits  
✅ **Alert Granularity** - Separate toggles for New OB, Touch, and Rejection alerts  
✅ **MSB Control** - Choose preset or user override for structure lookback  
✅ **Performance Options** - Manual max blocks override for busy charts  
✅ **Non-Breaking** - All defaults match v2.4.0 behavior exactly  

**🔧 Bug Fixes:**
- Fixed displacement controls now work in both Scalper AND Institutional modes
- MSB lookback now actually user-controllable with new "User override" mode
- Fixed type mismatch in max blocks conversion

## 🚀 What's New in v2.4.0

**PERFORMANCE OPTIMIZATION:** Auto-scaling VP for faster execution

✅ **VP Auto-Scaling** - Automatically adjusts VP lookback based on timeframe  
✅ **Dramatically faster on low TF** - No more "script took too long" errors on 1m/3m/5m  
✅ **Smart defaults** - 1m→60 bars, 3m→80, 5m→100, 15m→150, 1h→200, 4h+→300  
✅ **User control preserved** - Your VP setting acts as maximum cap  
✅ **Manual override** - Turn off Auto-Adjust to use exact VP value  

## 🚀 What's New in v2.3.x

**CODE QUALITY & BUG FIXES:**

✅ **MSB refinement** - Added pivot fallback for minimum structure level  
✅ **FVG documentation** - Comprehensive candle mapping added  
✅ **Performance warnings** - Alerts for VP analysis and object limits  
✅ **Defensive coding** - Label guards to prevent crashes  
✅ **Optimized ATR** - Cached series for better performance  

## 🚀 What's New in v2.2

**CRITICAL BUG FIXES:** Historical detection now 100% accurate

✅ **Fixed ATR indexing** - Uses historical ATR instead of current (critical!)  
✅ **Fixed MSB logic** - Structure break detection now scans correct direction  
✅ **Improved FVG clarity** - Added comprehensive documentation  
✅ **Consistent signals** - No more false detections from volatility mismatch  
✅ **Reliable backtesting** - Historical performance is now accurate

---

## ⚠️ Important: Upgrade to v3.1.0

If you're using an older version, **update to v3.1.0** for:

🔴 **NEW FEATURE:** ICT Liquidity Sweep Detection - Track BSL/SSL levels and sweep events  
🟢 **Performance:** 30-50% faster execution (v3.0 optimization)  
🟢 **Proximity Alerts:** Advance warning system for approaching OB zones (v3.0.1)  
🟢 **Smart Sizing Fix:** ICT-aligned zone anchoring (v2.4.2)  
🟢 **Advanced Controls:** 30+ settings for complete customization (v2.4.1)  
🟢 **Critical Fixes:** Historical detection bugs (ATR, MSB) from v2.0-2.2  
🟢 **VP Auto-Scaling:** Prevents timeout errors on low timeframes (v2.4)  

**How to check your version:** Look at the indicator title in chart - should say "v3.1.0"

---

## ⚡ Quick Setup (60 Seconds)

### **For Crypto Scalping (1m-15m):**
```
1. Detection Method: Scalper
2. Scalper Lookback: 10
3. Auto-Adjust for Timeframe: ON
4. Volume Profile Enhancement: ON (if Premium)
5. Track Rejections: ON
6. [OPTIONAL] Show Liquidity Levels: ON (NEW in v3.1)
7. [OPTIONAL] Mark Sweep Events: ON (NEW in v3.1)
```

### **For Swing Trading (1H-4H):**
```
1. Detection Method: Institutional
2. Auto-Adjust for Timeframe: ON
3. Displacement Filter: ON
4. FVG Filter: ON
5. MSB Filter: ON
6. [OPTIONAL] Show Liquidity Levels: ON (NEW in v3.1)
7. [OPTIONAL] Mark Sweep Events: ON (NEW in v3.1)
```

---

## 🎯 How to Trade Order Blocks

### **1. Identify Order Block**
```
Bullish OB (Green):
🔴 ← Last bearish candle
  🟢🟢🟢 ← Strong move up
  
Bearish OB (Red):  
🟢 ← Last bullish candle
  🔴🔴🔴 ← Strong move down
```

### **2. Wait for Retest**
- Price must return to the order block zone
- Look for rejection signals (wicks, volume)
- Check dashboard for status: ACTIVE

### **3. Entry Confirmation**
- ★ **Elite blocks** = Highest probability (VP confirmed)
- ◆ **Strong blocks** = Good probability
- ◇ **Mid blocks** = Medium probability
- ○ **Weak blocks** = Lower probability (avoid if possible)

### **4. Position Setup**
```
LONG Entry (Bull OB):
Entry: When price touches OB zone + shows rejection
Stop Loss: Below OB zone (5-10 pips)
Take Profit: Previous high or next resistance

SHORT Entry (Bear OB):
Entry: When price touches OB zone + shows rejection
Stop Loss: Above OB zone (5-10 pips)
Take Profit: Previous low or next support
```

---

## 📊 Understanding the Dashboard

```
REZ Scalper - SCALPING [Scalper] 📊VP
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Type    Volume   Dist%   Strength  Tests  Status   Vol
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
BEAR ▼  1.2M    +0.5%   Elite★    2      TESTED   1.8x
BULL ▲  850K    -1.2%   Strong◆   1      ACTIVE   1.5x
```

### **Columns Explained:**

| Column | Meaning |
|--------|---------|
| **Type** | BULL ▲ (support) or BEAR ▼ (resistance) |
| **Volume** | Total volume on order block candle |
| **Dist%** | Distance from current price (+ above, - below) |
| **Strength** | Elite★ / Strong◆ / Mid◇ / Weak○ |
| **Tests** | Number of times price has retested |
| **Status** | FRESH/ACTIVE/TESTED/REJECT |
| **Vol** | Relative volume (vs average) |

### **Status Meanings:**

- **FRESH** ⚪ = Never tested, waiting for first touch
- **ACTIVE** 🟡 = Price currently in the zone
- **TESTED** 🟠 = Previously tested, waiting for next retest
- **REJECT** 🟢 = Price bounced (potential trade signal!)

---

## ⚙️ Settings Guide

### **💧 Liquidity Sweeps** (NEW in v3.1.0)

**Show Liquidity Levels**
- OFF by default
- Shows horizontal dashed lines at swing highs (BSL) and lows (SSL)
- Identifies where stop losses cluster (liquidity pools)

**Mark Sweep Events**
- ON by default when liquidity features enabled
- Highlights when price sweeps liquidity then reverses
- Shows quality rating (Strong/Mid/Weak) on sweep labels

**Mark Liquidity Runs**
- OFF by default
- Also marks when price takes liquidity and CONTINUES (trend confirmation)
- Distinguishes sweeps (reversals) from runs (continuations)

**Highlight Equal Highs/Lows**
- ON by default
- Marks clustered swing levels with stronger liquidity
- Equal levels = more stops = stronger magnet for price

**Swing Lookback** (5-50, default 20)
- Bars to identify swing highs/lows for liquidity pools
- Lower = more recent swings only
- Higher = includes older swings

**Equal High/Low Threshold %** (0.0-1.0%, default 0.1%)
- Price range to consider highs/lows as "equal"
- 0.1% works well for most markets
- Increase for more volatile assets

**Min Sweep Wick (ATR mult)** (0.1-2.0, default 0.5)
- Minimum wick beyond level to qualify as sweep
- Prevents false sweeps from minor wicks
- 0.5 ATR is standard ICT criteria

**Require Volume Spike**
- ON by default
- Sweep candle must have above-average volume
- Confirms institutional participation

**Max Levels per Side** (2-12, default 6)
- Maximum BSL and SSL levels to track
- Higher = more levels but can clutter chart
- 6 is optimal for most use cases

**Liquidity Alerts**
- **Alert on Sweep**: Notifies when liquidity sweep detected
- **Alert Approaching Liquidity**: Warns when price near BSL/SSL levels
- **Liquidity Proximity %**: Distance threshold for proximity alerts (0.1-3.0%, default 0.5%)

**🎯 Trading Liquidity Sweeps:**
1. Identify BSL (above price) or SSL (below price)
2. Watch for price to sweep the level (wick beyond, close back)
3. Look for Strong quality sweeps (best probability)
4. Check for OB confluence (sweep near existing order block = powerful)
5. Enter on reversal confirmation after sweep
6. Stop loss beyond the swept level

### **🔥 Premium Features** (Requires TradingView Premium)

**📊 Volume Profile Enhancement**
- Turn ON if you have Premium subscription
- Identifies institutional accumulation zones
- Boosts order blocks to "Elite" status
- **NEW in v2.4:** Auto-scales lookback based on timeframe

**VP Analysis Period** (20-500, default 100)
- **IMPORTANT:** With Auto-Adjust ON, this acts as a **maximum cap**
- Script automatically reduces on lower timeframes:
  - 1m chart → 60 bars (or your setting, whichever is lower)
  - 3m chart → 80 bars
  - 5m chart → 100 bars
  - 15m chart → 150 bars
  - 1h chart → 200 bars
  - 4h+ chart → 300 bars
- Turn Auto-Adjust OFF to use exact value (manual mode)
- **Why?** Prevents "script took too long" errors on fast timeframes

**VP Strength Multiplier** (1.0-3.0, default 1.5)
- Volume threshold for Elite status
- 1.2 = More Elite blocks (less strict)
- 2.0 = Fewer Elite blocks (more strict)

### **⚙️ Mode**

**Auto-Adjust for Timeframe**
- ON = Automatically optimizes for current chart timeframe
- OFF = Use manual preset

**Detection Method**
- **Institutional**: Pivot-based + strict filters (fewer, higher quality)
- **Scalper**: ICT/SMC displacement-based (more signals, faster)

**Scalper Lookback** (2-30, default 10)
- How far back to look for order blocks
- Lower = more recent blocks only
- Higher = includes older blocks

### **Detection**

**Swing Detection Period** (3-20, default 5)
- For Institutional mode only
- Pivot point sensitivity

**Block Sizing**
- **Smart**: ATR-adjusted (best for scalping)
- **Body Only**: Candle body only
- **Full Range**: Entire high-low range

### **Filters** (Institutional Mode)

**Displacement Filter**
- Requires strong body candles (>1.3x average)
- Indicates institutional participation

**Fair Value Gap Filter**
- Requires price imbalance (gap between candles)
- Shows aggressive buying/selling

**Structure Break Filter**
- Requires break of previous market structure
- Confirms trend change

**Volume Confirmation**
- Requires above-average volume
- Validates institutional activity

### **Mean Reversion**

**Track Rejections**
- Detects bounces off order blocks
- Shows "↗ BOUNCE" or "↘ REJECT" in labels
- Triggers rejection alerts

**Show Retest Count**
- Displays "2× TEST" in labels
- More retests = stronger level

**Alert Granularity** (v2.4.1+)
- **Alert on New OB**: Alert when order blocks are detected
- **Alert on Touch**: Alert when price enters zones
- **Alert on Rejection**: Alert when price rejects from zones
- Control each alert type independently

**Proximity Alerts** (NEW in v3.0.1)
- **Enable Proximity Alerts**: Get advance warning before price reaches OB zones
- **Proximity Distance %**: Alert when within this % of zone (0.1-5.0%, default 1.0%)
- **Proximity: Only Strong/Elite**: Filter to high-quality blocks only
- **Proximity: Only Fresh (Untested)**: Alert only for zones with no prior retests
- **Require Directional Approach**: Bull OB alerts only when price falling, Bear OB only when rising

---

## ⚙️ Advanced Settings (v2.4.1)

**NEW:** 30+ advanced parameters for complete control over signal quality vs frequency. All settings include tooltips explaining their impact.

### **🎯 Displacement / Impulse Tuning**

Fine-tune what qualifies as a displacement candle (affects both Scalper AND Institutional modes):

**Displacement ATR Body Mult** (0.5-2.0, default 0.8)
- Body size threshold: `body > atr × this multiplier`
- **Lower = more signals** (e.g., 0.6 for busy markets)
- **Higher = stricter quality** (e.g., 1.0 for cleaner signals)

**Displacement Body/Range Min** (0.4-0.9, default 0.6)
- Body dominance: `body/range > this threshold`
- **Lower = more signals** (e.g., 0.5 includes more candles)
- **Higher = cleaner candles** (e.g., 0.7 for strong momentum only)

### **🔍 Scalper OB Search Window**

**Scalper OB Scan Window** (1-6, default 3)
- Max bars to scan back from impulse for opposite candle
- **Wider = more signals** (finds OB further back)
- **Narrower = more recent OBs only**

### **📐 MSB (Market Structure Break) Controls**

**MSB Lookback Mode** (NEW in v2.4.1)
- **Auto (preset)**: Uses timeframe presets (5/10/15) - Default
- **User override**: Uses your MSB Lookback value below

**MSB Structure Lookback** (3-30, default 10)
- Bars to scan for structure confirmation
- **Higher = stricter** structure requirements
- Only applies when "User override" is selected

**MSB Use Pivot Fallback** (default ON)
- Include pivot point as minimum structure level
- Recommended: Keep ON for better structure detection

### **📊 FVG (Fair Value Gap) Controls**

**FVG Mode** (default "Classic 3-candle")
- **Classic 3-candle**: Standard wick gap detection
- **Strict (body gap)**: Requires body gap (more selective)
- **Loose (wick gap)**: Allows partial gaps (more permissive)
- **Off**: Disables FVG filter

**FVG Min Gap (ATR mult)** (0.0-1.0, default 0.0)
- Minimum gap size: `gapSize > atr × this`
- **0 = no minimum** (accept all gaps)
- **0.1-0.3 = filter micro-gaps** on low timeframes

### **📏 Zone Sizing Controls**

**Smart Size ATR Multiplier** (0.5-3.0, default 1.2)
- Zone height for Smart sizing: `atr × this multiplier`
- **Higher = wider zones** for volatile assets
- **Lower = narrower zones** for stable assets

**Smart Sizing Applies To** (default "Scalping only")
- **Scalping only**: Smart sizing on timeframes ≤15m
- **All timeframes**: Apply Smart sizing everywhere

### **🔄 Mitigation Controls**

When order blocks are deleted (prevents premature deletion on noisy pairs):

**Mitigation Mode** (default "Auto")
- **Auto**: Adapts to timeframe (Wick/Close/Mean)
- **Wick**: Requires wick penetration through zone
- **Close**: Requires close through zone
- **Mean**: Requires close past midpoint

**Min Penetration (Zone %)** (0.0-0.5, default 0.10)
- Minimum zone penetration to confirm deletion
- **Higher = prevents deletion on noise** (e.g., 0.15-0.20)

**Min Penetration (ATR %)** (0.0-0.3, default 0.05)
- Minimum ATR-based penetration threshold
- **Higher = more stable on volatile pairs**

**Mean Mitigation Level** (0.0-1.0, default 0.5)
- For Mean mode: 0 = top, 1 = bottom, 0.5 = midpoint

### **🔄 Retests + Rejections Controls**

**Touch Detection Mode** (default "Wick")
- **Wick**: Any wick into zone counts as touch
- **Close inside zone**: Only closes inside zone count

**Retest Counting** (default "Require exit before recount")
- **Require exit before recount**: Touch → exit → touch = 2 retests
- **Count each bar in zone**: Every bar in zone increments count

**Rejection Close Level** (default "Mid")
- **Mid**: Close must be beyond midpoint
- **Top/Bottom**: Close must be beyond zone edge
- **Percent into zone**: Custom percentage (see below)

**Rejection Close Percent** (0.0-1.0, default 0.5)
- For "Percent into zone" mode
- 0 = zone edge, 1 = opposite edge, 0.5 = midpoint

### **💪 Strength Scoring Thresholds**

Customize what qualifies as "strong":

**Volume Score Multiplier** (1.0-3.0, default 1.5)
- Volume threshold: `vol > avgVol × this`
- **Lower = more Strong/Elite ratings**
- **Higher = stricter requirements**

**Body Score Multiplier** (1.0-3.0, default 1.5)
- Body size threshold: `body > avgBody × this`
- **Adjust for different assets** (e.g., 1.3 for crypto)

**VP Score Boost** (0-2, default 1, Premium)
- Extra strength points when VP confirms
- **2 = VP has double influence** on rating

**Elite Requires VP** (default ON, Premium)
- ON: Elite rating requires VP confirmation
- OFF: Elite available without VP if score ≥3

### **⚡ Performance / Object Limits**

**Max Blocks** (default "Auto")
- **Auto**: Adapts to timeframe (5/6/8 blocks)
- **3, 5, 8, 10, 12, 15**: Manual override

**Render Mode** (default "Gradient")
- **Gradient**: Full gradient visuals (~12-15 objects per block)
- **Simple fill**: Single fill box (~3-5 objects per block)
- **Borders only**: Just border lines (~2-3 objects per block)
- **Use Simple/Borders if hitting TradingView's 500 box/line limits**

### **📌 When to Use Advanced Settings**

**For More Signals (Aggressive):**
```
- Lower dispAtrBodyMult to 0.6-0.7
- Lower dispBodyToRangeMin to 0.5
- Increase obScanWindow to 5-6
- Set fvgMode to "Loose" or "Off"
- Set msbLookbackMode to "User override" and lower msbLookback to 5-7
```

**For Higher Quality (Conservative):**
```
- Increase dispAtrBodyMult to 1.0-1.2
- Increase dispBodyToRangeMin to 0.7
- Set fvgMode to "Strict"
- Increase msbLookback to 15-20
- Increase volScoreMult and bodyScoreMult to 1.8-2.0
- Set fvgMinGapAtr to 0.2-0.3
```

**For Volatile/Noisy Assets:**
```
- Increase minPenZonePct to 0.15-0.20
- Increase minPenAtrPct to 0.08-0.10
- Increase smartSizeAtrMult to 1.5-2.0
- Set mitigationMode to "Close" or "Mean"
```

**For Performance (Busy Charts):**
```
- Set renderMode to "Simple fill" or "Borders only"
- Set maxBlocks to "5" or "8"
- Turn off showCornerAccents
```

---

## 🎨 Visual Indicators

### **Strength Symbols (Icons on Order Blocks):**

| Icon | Rating | Scoring | Best Use |
|------|--------|---------|----------|
| **★** | Elite | 3-4 points | **Highest probability** - VP confirmed + multiple validations |
| **◆** | Strong | 2-3 points | **High probability** - Multiple confirmations |
| **◇** | Mid | 1 point | **Medium probability** - Some confirmation |
| **○** | Weak | 0 points | **Low probability** - Basic detection only |

**Scoring System:**
- +1 point: Volume > 1.5× average
- +1 point: Body size > 1.5× average  
- +1 point: Trend aligned (price above/below SMA50)
- +1 point: Volume Profile concentration (Premium feature)

**Trading Tip:** Focus on ★ Elite and ◆ Strong blocks for best results!

### **Status Messages:**
- **● ACTIVE** = Price in zone now
- **↗ BOUNCE** = Bullish rejection detected (support held)
- **↘ REJECT** = Bearish rejection detected (resistance held)
- **N× TEST** = Retested N times (e.g., "2× TEST" = 2 retests)

### **Visual Elements:**
- **Corner boxes** = Only appear on Strong/Elite blocks for emphasis
- **Gradient fill** = Edge-to-center transparency shows strength
- **Dotted lines** = Top and bottom boundaries of order block

### **Colors:**
- 🟢 **Green (#00ff88)** = Bullish order blocks (support)
- 🔴 **Red (#ff3366)** = Bearish order blocks (resistance)
- 🟡 **Yellow** = Elite strength in dashboard
- 🟠 **Orange** = Mid strength
- ⚪ **White** = Fresh/untested

---

## 🚨 Alert Setup

### **Available Alerts:**

**Order Block Alerts:**
1. **New Bullish Order Block** - New support zone detected
2. **New Bearish Order Block** - New resistance zone detected
3. **Price in Bull Zone** - Price testing support
4. **Price in Bear Zone** - Price testing resistance
5. **Bull Zone Rejection** 🚀 - Potential LONG signal
6. **Bear Zone Rejection** 💥 - Potential SHORT signal

**Proximity Alerts** (NEW in v3.0.1):
7. **Approaching Bull OB** ⚠️ - Price nearing bullish zone (prepare LONG setup)
8. **Approaching Bear OB** ⚠️ - Price nearing bearish zone (prepare SHORT setup)

**Liquidity Sweep Alerts** (NEW in v3.1.0):
9. **Bullish Liquidity Sweep** - SSL taken, potential LONG (reversal)
10. **Bearish Liquidity Sweep** - BSL taken, potential SHORT (reversal)
11. **Bullish Liquidity Run** - SSL broken, trend continuation DOWN
12. **Bearish Liquidity Run** - BSL broken, trend continuation UP
13. **Approaching BSL** - Price nearing buy-side liquidity
14. **Approaching SSL** - Price nearing sell-side liquidity

### **How to Set Alerts:**

1. Click "Alert" button (top right of chart)
2. Condition: Select indicator name
3. Choose alert type (e.g., "Bull Zone Rejection")
4. Configure notification method
5. Create alert

---

## 💡 Pro Tips

### **Best Practices:**

✅ **Use v3.1.0 for best performance** (Liquidity sweeps + proximity alerts + all optimizations)  
✅ **Start with defaults** (proven settings, liquidity features OFF initially)  
✅ **Enable Auto-Adjust** (optimizes settings for your timeframe)  
✅ **Use higher timeframes** (4H, Daily) for more reliable signals  
✅ **Wait for Elite★ or Strong◆ blocks** for best probability  
✅ **Combine with market structure** (trend direction)  
✅ **Look for rejection confirmation** before entry  
✅ **Use proper risk management** (1-2% per trade)  
✅ **Enable Volume Profile** (Premium) for Elite★ blocks  
✅ **Trust the MSB filter** (correctly detects structure breaks since v2.2)  
✅ **Experiment with Advanced Settings** gradually (one at a time)  
✅ **NEW: Watch for liquidity sweeps** near order blocks (confluence = powerful)  
✅ **NEW: Use proximity alerts** to prepare trades before price arrives  

### **What to Avoid:**

❌ Trading every order block (be selective)  
❌ Ignoring volume (low volume = weaker)  
❌ Going against strong trends  
❌ Using only lower timeframes (1m-5m)  
❌ Not using stop losses  
❌ Overtrading weak○ blocks  

### **Optimal Timeframes:**

- **1m-5m**: Scalping (fast trades, lower probability)
- **15m-1H**: Day trading (balanced)
- **4H-Daily**: Swing trading (highest probability)
- **Weekly+**: Position trading (very high quality)

### **Best Markets:**

✅ **Crypto**: 24/7, high volatility, clear order blocks  
✅ **Forex Major Pairs**: High liquidity, clean price action  
✅ **Stock Indices**: ES, NQ, YM (futures)  
⚠️ **Low Volume Stocks**: Less reliable  

---

## 🔧 Troubleshooting

### **Liquidity levels not showing:**
- Enable "Show Liquidity Levels" in Liquidity Sweeps section
- Or enable "Mark Sweep Events" to see sweeps without levels
- Ensure chart has enough history (need swing highs/lows)
- Adjust "Swing Lookback" (try 15-30 bars)
- Lower "Equal High/Low Threshold" to 0.05% for more levels

### **Too many liquidity levels:**
- Increase "Swing Lookback" to 30-40 (fewer, stronger swings)
- Reduce "Max Levels per Side" to 3-4
- Increase "Equal High/Low Threshold" to 0.2-0.3%

### **Sweep events not marking:**
- Enable "Mark Sweep Events" in Liquidity Sweeps section
- Lower "Min Sweep Wick" to 0.3 ATR (less strict)
- Turn OFF "Require Volume Spike" for more sweeps
- Check that price actually swept a level (wick beyond, close back)

### **No order blocks appearing:**
- Check Detection Method is selected
- Lower Scalper Lookback value
- Disable some filters (FVG, MSB)
- **NEW in v2.4.1:** Lower `dispAtrBodyMult` to 0.6-0.7
- **NEW in v2.4.1:** Set `fvgMode` to "Loose" or "Off"
- **NEW in v2.4.1:** Increase `obScanWindow` to 5-6
- Market may be ranging (not displacing)

### **Too many order blocks:**
- Use Institutional mode (stricter)
- Enable all filters
- Increase VP Strength Multiplier
- **NEW in v2.4.1:** Increase `dispAtrBodyMult` to 1.0+
- **NEW in v2.4.1:** Set `fvgMode` to "Strict"
- **NEW in v2.4.1:** Increase `volScoreMult` to 1.8-2.0
- Focus on higher timeframes

### **Dashboard shows FRESH for tested blocks:**
- This is fixed in v2.0+
- Ensure you're using latest version
- Reload indicator if needed

### **Elite★ blocks not showing:**
- Requires Volume Profile Enhancement = ON
- Requires TradingView Premium subscription
- Increase VP Analysis Period
- Lower VP Strength Multiplier

### **Different signals on historical vs real-time:**
- **FIXED in v2.2!** This was the ATR indexing bug
- Update to v2.4.1 for consistent historical detection
- Historical and real-time signals now match perfectly

### **MSB filter too strict/unreliable:**
- **FIXED in v2.2!** Direction logic was inverted
- **NEW in v2.4.1:** Use `msbLookbackMode = "User override"` to control lookback
- Adjust `msbLookback` to your preference (5-30 bars)

### **Displacement settings not working in Institutional mode:**
- **FIXED in v2.4.1!** Displacement controls now work in BOTH modes
- Both Scalper and Institutional respect `dispBodyToRangeMin` setting
- Update to v2.4.1 for consistent displacement behavior

### **Charts hitting TradingView object limits (500 boxes/lines):**
- **NEW in v2.4.1:** Set `renderMode` to "Simple fill" or "Borders only"
- Reduces objects per block from ~15 to ~3-5 (Simple) or ~2-3 (Borders)
- Set `maxBlocks` to lower value (e.g., "5" or "8")
- Turn off `showCornerAccents` for additional savings
- **IMPROVED in v2.3.2!** Added pivot fallback
- Update to v2.4 for proper structure break detection
- MSB confirmations now scan correct bar range with fallback

### **"Script took too long to execute" error:**
- **FIXED in v2.4!** VP auto-scaling for low timeframes
- Ensure Auto-Adjust for Timeframe = ON
- Script automatically reduces VP lookback on 1m/3m/5m
- If still occurring, manually lower VP Analysis Period

---

## 📈 Example Trade Setup

```
BTCUSDT 5m Chart - Bull Order Block

1. Scalper mode detects Bull OB at $42,500
   - Last bearish candle before 200 pip move up
   - Strength: Elite★ (VP confirmed)
   - Volume: 2.1x average

2. Price moves to $43,000, then retraces

3. Price touches $42,500 zone
   - Dashboard shows: ACTIVE
   - Long wick forms (rejection)
   - Volume spike on rejection candle

4. Entry: $42,520 (above OB)
   Stop Loss: $42,450 (below OB)
   Take Profit: $43,000 (previous high)
   
5. Risk: 70 pips | Reward: 480 pips | R:R = 1:6.9

6. Result: Price bounces, hits TP ✅
```

---

## 📚 Learn More

- **Full Documentation**: `ORDER_BLOCK_FORMULA_DOCUMENTATION.md`
- **Version History**: `CHANGELOG.md`
- **ICT Concepts**: YouTube - "Inner Circle Trader"
- **SMC Trading**: Search "Smart Money Concepts"

---

## ⚠️ Risk Disclaimer

- This indicator is for educational purposes only
- No indicator is 100% accurate
- Always use proper risk management
- Never risk more than you can afford to lose
- Backtest thoroughly before live trading
- Past performance doesn't guarantee future results

---

## 🔍 Technical Notes (v2.4)

### **Major Improvements Explained:**

**1. VP Auto-Scaling (v2.4 - PERFORMANCE)**
```pinescript
// Auto-scale based on timeframe
if autoMode
    if tf_in_minutes <= 1
        vpLookbackEff := math.min(60, vpLookback)  // Cap at 60 bars for 1m
    else if tf_in_minutes <= 5
        vpLookbackEff := math.min(100, vpLookback)  // Cap at 100 for 5m
    else if tf_in_minutes <= 60
        vpLookbackEff := math.min(200, vpLookback)  // Cap at 200 for 1h
    // ... etc
else
    vpLookbackEff := vpLookback  // Manual mode: use exact value
```
**Why this matters:**
- Volume Profile analysis uses nested loops (bars × grid segments)
- On 1m charts with 500-bar lookback, this causes timeout errors
- v2.4 intelligently reduces lookback on fast timeframes
- Your setting acts as maximum cap - script never exceeds it
- **Result:** No more "script took too long" errors on scalping timeframes

**2. MSB Pivot Fallback (v2.3.2)**
```pinescript
// After scanning lookback period, also check pivot as minimum structure
if high[pivotIdx] > recentHigh
    recentHigh := high[pivotIdx]  // Pivot is fallback minimum
```
**Why this matters:**
- Ensures displacement is at least stronger than the order block itself
- Prevents weak structure breaks from passing filter
- More robust detection across all market conditions

**3. ATR Indexing Fix (v2.2 - CRITICAL)**
```pinescript
OLD: body > atr * 0.8  // Wrong: current ATR
NEW: body > atr[idx] * 0.8  // Correct: historical ATR
```
**Why this matters:**
- Each candle evaluated with its own historical volatility context
- No more "ghost signals" appearing/disappearing
- Backtesting now accurately reflects historical performance

**4. MSB Direction Fix (v2.2 - CRITICAL)**
```pinescript
OLD: for i = 1 to lookback: high[pivotIdx + i]  // Wrong direction
NEW: scanStart = dispIdx + 1; for i = scanStart to scanEnd: high[i]
```
**Why this matters:**
- MSB now scans forward from displacement (correct direction)
- Properly detects if displacement broke recent structure
- Filter works as intended

**5. Defensive Label Guards (v2.3.1)**
```pinescript
// Only update label if it exists AND features are enabled
if (showVolLabel or showStrength or showRetests) and not na(block.volLabel)
    label.set_text(block.volLabel, labelText)
```
**Why this matters:**
- Prevents crashes when label features are disabled
- Safer code execution
- No unexpected errors

### **Performance Warnings:**

⚠️ **Object Limits:** Each block creates ~12-15 objects in Gradient mode
- With maxBlocks=10 and gridSegments=20: ~150-200 objects total
- TradingView limits: 500 boxes, 500 lines max
- **NEW in v2.4.1:** Use `renderMode` to reduce objects:
  - **Gradient**: ~12-15 objects per block (full visuals)
  - **Simple fill**: ~3-5 objects per block (70% reduction!)
  - **Borders only**: ~2-3 objects per block (85% reduction!)
- If you hit limits, set renderMode to "Simple fill" or reduce maxBlocks

⚠️ **VP Analysis:** Nested loops can be CPU intensive
- v2.4.0+ auto-scaling mitigates this
- Manual mode with high VP lookback may still timeout on 1m
- Recommendation: Keep Auto-Adjust ON for best performance

### **Impact on Your Trading:**

✅ **Fast execution** - VP auto-scaling prevents timeouts  
✅ **Backtesting reliability** - Historical matches real-time (v2.2 fix)  
✅ **Better MSB detection** - Pivot fallback + direction fix  
✅ **Stability** - Defensive coding prevents crashes  
✅ **Consistent performance** - Across all timeframes and conditions  

**Recommendation:** Use v2.4.1 with Auto-Adjust ON for optimal performance!

---

## 🔄 Migrating from v2.4.0 to v2.4.1

### **What Changed:**

✅ **New Advanced Settings** - 30+ parameters added in "Advanced" groups  
✅ **Displacement Fix** - Now works in both Scalper AND Institutional modes  
✅ **MSB Control** - Added "User override" mode to actually control MSB lookback  
✅ **Alert Granularity** - Split into 3 separate toggles (New OB/Touch/Reject)  
✅ **Type Fix** - Fixed type mismatch in max blocks conversion  

### **Breaking Changes:**

**None!** All defaults match v2.4.0 behavior exactly.

### **Recommended Actions:**

1. **Update to v2.4.1** - Copy new code to TradingView
2. **Verify version** - Check indicator title shows "v2.4.1"
3. **Keep defaults initially** - Signals should match your v2.4.0 results
4. **Explore Advanced Settings** - Experiment one setting at a time
5. **Read tooltips** - Each setting explains its impact

### **If You Experience Issues:**

- **Signals changed?** Reset all Advanced settings to defaults
- **Performance issues?** Set `renderMode` to "Simple fill"
- **Displacement not working in Institutional?** Update to v2.4.1 (this was fixed)
- **MSB lookback not applying?** Set `msbLookbackMode` to "User override"

---

---

## 📖 New Feature Deep Dive: Liquidity Sweeps (v3.1.0)

### **What are Liquidity Sweeps?**

Liquidity sweeps are a key ICT/SMC concept where price:
1. Moves beyond a swing high (BSL) or swing low (SSL)
2. Grabs stop losses clustered at those levels
3. Reverses direction (sweep) or continues (run)

**Why they matter:**
- Institutions intentionally sweep liquidity before major moves
- Sweeps near order blocks = high-probability reversal setups
- Equal highs/lows = clustered stops = stronger magnet for price

### **How to Use:**

**Step 1: Enable Features**
```
Liquidity Sweeps section:
- Show Liquidity Levels: ON (to see BSL/SSL lines)
- Mark Sweep Events: ON (to highlight sweeps)
- Highlight Equal Highs/Lows: ON (to see clusters)
```

**Step 2: Identify Liquidity Pools**
- BSL (dashed cyan lines above price) = Buy-Side Liquidity
- SSL (dashed orange lines below price) = Sell-Side Liquidity
- "EQ" prefix = Equal highs/lows (stronger)

**Step 3: Watch for Sweeps**
- Price wicks beyond level then closes back
- Sweep box appears with quality label (Strong/Mid/Weak)
- Look for "Strong" quality (large wick + volume + OB confluence)

**Step 4: Trade the Reversal**
```
Bullish Sweep (SSL taken):
- Price wicks below SSL
- Closes back above
- Strong quality preferred
- Check for nearby Bull OB (confluence!)
- Enter LONG on confirmation
- Stop below swept low

Bearish Sweep (BSL taken):
- Price wicks above BSL
- Closes back below
- Strong quality preferred
- Check for nearby Bear OB (confluence!)
- Enter SHORT on confirmation
- Stop above swept high
```

**Step 5: Use Dashboard**
- Shows nearest BSL/SSL with distance
- "EQ BSL" or "EQ SSL" = equal levels (prioritize these)
- Distance % helps time entries

### **Quality Ratings Explained:**

**Strong** (Best):
- Large wick (>1.0 ATR beyond level)
- Volume spike confirmed
- Near order block (confluence)
- Equal high/low (clustered stops)

**Mid** (Good):
- 2-3 of the above criteria met
- Still tradeable with confirmation

**Weak** (Caution):
- Only 1 criterion met
- Wait for additional confirmation

### **Sweep vs Run:**

**Sweep** (Reversal):
- Wick beyond level, close back inside
- = Reversal signal
- Trade AGAINST the sweep direction

**Run** (Continuation):
- Break and close beyond level
- = Continuation signal
- Trade WITH the break direction
- Enable "Mark Liquidity Runs" to see these

### **Best Practices:**

✅ Focus on **Strong quality** sweeps  
✅ Look for sweeps **near order blocks** (confluence)  
✅ Prioritize **equal highs/lows** (EQ BSL/SSL)  
✅ Wait for **reversal confirmation** after sweep  
✅ Use **proximity alerts** for BSL/SSL levels  
✅ Combine with **higher timeframe** structure  
✅ Set stops **beyond the swept level**  

### **Example Setup:**

```
BTCUSDT 15m Chart

1. SSL identified at $42,000 (equal lows)
2. Alert: "Approaching SSL" triggers
3. Price drops to $41,950 (sweeps SSL)
4. Large wick, volume spike, closes at $42,020
5. Quality: "Strong" (all criteria met)
6. Nearby Bull OB at $42,000 (confluence!)
7. Enter LONG at $42,030
8. Stop at $41,930 (below swept low)
9. Target: $42,500 (next resistance)
10. R:R = 1:4.7 ✅
```

---

**Last Updated:** January 18, 2026  
**Mode:** ICT/SMC Edition with Liquidity Sweeps  

Happy Trading! 🚀
