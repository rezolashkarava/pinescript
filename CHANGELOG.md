# ICT Order Block Pro [Pagani] - What's New

Your professional order block indicator keeps getting better! Here's everything new in each version.

---

## 🏛️ v5.1.0 (February 2026) - ICT STANDARD COMPLIANCE

### What's New: Real ICT Order Block Detection

This release overhauls the core detection and scoring engine to match actual ICT (Inner Circle Trader) methodology. If you wanted proper institutional order blocks - this is it.

**FVG Now Mandatory (Scalper Mode):**
- ICT says displacement MUST leave a Fair Value Gap to validate institutional intent
- Scalper Auto mode now forces FVG confirmation ON
- Dedicated `checkScalperFVG` validates gap between impulse and OB candle
- Supports Classic, Strict (body gap), and Loose (wick gap) modes

**Swing-Based Dealing Range:**
- Premium/Discount zones now use actual pivot swing highs/lows
- Replaces the old rolling N-bar window with proper ICT dealing range
- Configurable pivot length (Auto adapts: 10 Scalping, 15 Swing, 20 Position)
- OTE (Optimal Trade Entry) zone calculated from real dealing range

**Tier-Based Quality Scoring:**
- Tier 1 (Core OB Quality): displacement strength, FVG (+2), MSB (+1), volume spike (+1) - max 6
- Tier 2 (Context, capped +3): session, zone alignment, crypto, trend
- Context alone can NO LONGER promote a weak OB to Elite
- Elite requires: core >= 4, total >= 6, AND volume confirmation

**Consequent Encroachment (CE) Mitigation:**
- All presets now default to CE (50% of OB) for mitigation
- ICT standard: price mitigates at the midpoint, not the wick or close

**OB Age Decay:**
- Fresh OBs are stronger per ICT - untested OBs gradually lose rating
- Elite -> Strong -> Mid -> Weak over configurable decay window
- Auto-scales: 50 bars (Scalping), 100 (Swing), 200 (Position)
- Retested OBs reset their decay clock

**Full Candle Sizing Default:**
- Zone now spans entire candle wick-to-wick (ICT standard)
- New Block Sizing input: "Full candle" / "Body Only" / "Smart"
- Smart sizing remains optional for compact zones

**Displacement Threshold Raised:**
- From 0.8x to 1.0x ATR - body must at least equal ATR
- Filters out marginal moves that don't represent true institutional displacement

**Why This Matters:**
- Fewer but higher-quality order blocks
- Blocks that actually match what ICT teaches
- Scoring reflects real OB quality, not inflated context points
- Age decay removes stale zones automatically

---

## 🎯 v3.4.0 (January 2026) - PRODUCTION UX FINALIZATION

### What's New: Smarter Defaults + Stability + Alerts-Only Mode

This release focuses on user experience, stability, and making the indicator "just work" out of the box.

**Settings Mode (Auto/Manual):**
- **Auto mode is now default** - optimizes all settings based on your timeframe
- Scalping, Swing, and Position presets auto-selected
- Power row stability settings forced for consistency
- Performance guardrails prevent object overload

**Signal Timing (Confirmed Mode Fix):**
- **Power row no longer flickers intrabar** when using "Confirmed (bar close)"
- All Power values (side, %, count) now latch properly until candle close
- Shows "—" instead of fake "0%" when data is invalid

**Liquidity Module - Now Opt-In:**
- **Master toggle `Enable Liquidity Module`** (OFF by default)
- No liquidity clutter until you explicitly enable it
- Safer defaults: levels=OFF, runs=OFF, alerts=OFF
- **Alerts-only mode**: Enable alerts without any visual drawings!
- Dashboard shows BSL/SSL info even when drawings are disabled
- Auto mode caps levels (4 for Scalping, 5 for Swing)

**Anti-Spam Alert System:**
- **OB Touch alerts are edge-triggered** - fires once per zone entry, re-arms on exit
- **Liquidity proximity alerts are edge-triggered** - one alert per approach
- No more alert spam when price stays in a zone

**Touch Mode Consistency:**
- OB Touch alerts now respect your `touchMode` setting
- "Close inside zone" mode only triggers when close is inside (not wick overlap)

**Clearer Liquidity Run Alerts:**
- Renamed from confusing "Bullish/Bearish Liquidity Run"
- Now: **"BSL Run (Upside Continuation)"** and **"SSL Run (Downside Continuation)"**
- New dedicated `Alert on Run` toggle (separate from drawings)
- Messages clearly explain what happened

**Volume Profile:**
- Remains ON by default for enhanced signal quality
- User can disable if not using TradingView Premium

**Dashboard Location:**
- All 4 corners work reliably
- Proper table recreation when changing position

**Why You'll Love It:**
- Zero configuration needed - just add to chart
- Cleaner default experience (no liquidity clutter)
- Stable Power readings (no intrabar noise in Confirmed mode)
- Smarter alerts that don't spam you
- Alerts work even without visual drawings

---

## 🚀 v3.3.0 (January 2026) - POWER ROW

### What's New: Real-Time Market Pressure Indicator

Ever wish you could see WHO is in control right now - buyers or sellers? Now you can!

**The Power Row shows you live BUY/SELL pressure** by analyzing price action on lower timeframes. Think of it like having X-ray vision into each candle to see what's really happening inside.

**How It Helps You:**
- ✅ **Confirm Your Trades**: Bull OB + Power showing BUY = strong LONG setup
- ✅ **Avoid Bad Entries**: If Power shows SELL at your Bull OB, wait for better conditions
- ✅ **Catch Reversals Early**: See momentum shifts before they're obvious on price
- ✅ **No More Guessing**: Know if buyers or sellers are winning RIGHT NOW

**Smart Auto-Settings:**
The indicator automatically picks the best lower timeframe for your chart:
- Trading on 15-minute? It analyzes 1-minute bars inside
- Trading on 4-hour? It analyzes 15-minute bars inside
- Always gives you the perfect granularity, zero setup needed!

**What You'll See in Dashboard:**
```
─── POWER @5m ───
Power    BUY    72.3%    15 bars
```
Translation: Looking at 5-minute intrabars, buyers dominating with 72% control, based on 15 candles.

**Why You'll Love It:**
- Works on ANY timeframe (1-minute to Weekly)
- Auto mode = zero configuration needed
- Reduces false signals with smart noise filters
- Adds powerful confluence to your order block trades

---

## 💧 v3.1.0 (January 2026) - LIQUIDITY SWEEPS

### What's New: Track Where Smart Money Hunts Stops

**You know that frustrating moment when:**
- Price hits your stop loss...
- Then immediately reverses in your original direction?

That's called a liquidity sweep - and institutions do it ON PURPOSE. Now you can see them coming!

**What This Does:**
- 📍 **Shows Where Stop Losses Cluster**: See levels above highs (BSL) and below lows (SSL)
- 🎯 **Identifies Sweep Events**: Alerts when price grabs stops then reverses
- 💎 **Quality Ratings**: "Strong" sweeps = highest probability setups
- 🔔 **Smart Alerts**: Get notified when sweeps happen near your order blocks

**Real Trading Example:**
```
1. Price approaching SSL at $42,000 (stops below this level)
2. Alert: "Approaching SSL" 
3. Price drops to $41,950 (sweep!)
4. Large wick, closes back at $42,020
5. Quality: "Strong" + nearby Bull OB = EXCELLENT LONG
6. Enter trade with confidence
```

**Why Traders Love This:**
- See institutional manipulation BEFORE it happens
- Trade WITH the smart money instead of against them
- Higher win rates on reversal setups
- Finally understand why price "faked you out"

**Getting Started:**
1. Enable "Show Liquidity Levels" to see BSL/SSL lines
2. Enable "Mark Sweep Events" to highlight reversals
3. Watch for "Strong" quality sweeps near order blocks
4. These are your BEST trade setups!

---

## ⚠️ v3.0.1 (January 2026) - PROXIMITY ALERTS

### What's New: Advance Warning System

**Stop missing trades because you weren't watching the chart!**

Get alerts BEFORE price reaches your key zones - giving you time to prepare, set up your trade, and be ready when the action happens.

**How It Works:**
- 🎯 Alert when price is 1% away from order block (you set the distance)
- 📱 Notification to your phone/email via TradingView
- ⏰ Time to open your chart, analyze, and prepare
- 🚀 Ready to trade when price actually hits the zone

**Perfect For:**
- Busy traders who can't watch charts 24/7
- Multi-timeframe traders tracking several pairs
- Anyone who's ever said "I missed that setup!"

**Recommended Settings:**
- Scalping (1m-5m): 0.5-1% warning distance
- Day Trading (15m-1h): 1-2% warning distance  
- Swing Trading (4h-Daily): 2-3% warning distance

---

## ⚡ v3.0.0 (January 2026) - FASTER & SMOOTHER

### What's New: Performance Upgrade

**Your indicator just got 30-50% faster!**

**What This Means:**
- ✅ Smoother chart scrolling
- ✅ Faster loading on 1-minute charts
- ✅ No more "script timeout" errors
- ✅ Works better on older computers
- ✅ More responsive when switching timeframes

**Also Fixed:**
- Order blocks now perfectly aligned with price action
- Better touch detection accuracy
- More precise rejection signals

You probably won't notice the code changes - you'll just notice everything works BETTER!

---

## 🎛️ v2.4.1 (January 2026) - CUSTOMIZATION POWERHOUSE

### What's New: 30+ Advanced Settings

**Want to fine-tune EVERYTHING?** Now you can!

**New Controls:**
- 🎚️ Adjust detection sensitivity (more signals vs higher quality)
- 📊 Choose render mode (beautiful vs performance)
- ⚙️ Individual toggles for each alert type
- 🎨 Control exactly how zones are drawn
- 🔧 Tune for your specific trading style

**Most Users:** Stick with defaults - they're already optimized!

**Advanced Users:** Go wild! Every setting has detailed tooltips explaining what it does.

---

## 📊 v2.4.0 (January 2026) - AUTO-SCALING

### What's New: Smart Timeframe Adaptation

**The indicator now automatically optimizes itself based on YOUR chart timeframe.**

- 1-minute chart? Uses faster, lighter settings
- Daily chart? Uses more thorough analysis
- You don't do anything - it just works!

**Result:** No more timeout errors on fast timeframes, better performance everywhere.

---

## 💎 v2.0.0 (January 2026) - VOLUME PROFILE PREMIUM

### What's New: Elite★ Order Blocks

**If you have TradingView Premium,** you now get access to the ultimate power feature:

**Volume Profile Enhancement** finds where BIG institutions accumulated their positions.

**What's an Elite★ Block?**
- Regular Strong block = good probability
- Elite★ block = institutional confirmation = HIGHEST probability
- Shows where massive volume traded at that level
- These are the "can't miss" setups

**Upgrade Your Trading:**
1. Subscribe to TradingView Premium
2. Enable "Volume Profile Enhancement" in settings
3. Look for ★ Elite blocks - trade THESE first!

---

## 📋 Complete Feature List

### Quality Ratings (What Those Symbols Mean)
- **★ Elite** = Best possible setup (requires Premium feature)
- **◆ Strong** = High probability trade - take these!
- **◇ Mid** = Decent setup - needs extra confirmation
- **○ Weak** = Low confidence - skip these

### Detection Modes
- **Institutional Mode** = Fewer, higher quality signals (best for swing trading)
- **Scalper Mode** = More signals, faster response (best for day trading)

### Alert Types Available
1. **New Order Block** - A new zone just formed
2. **Price Touching Zone** - Price entered an order block (edge-triggered, no spam!)
3. **Rejection Signal** - Price bounced! 🚀 (TRADE THIS)
4. **Proximity Warning** - Price approaching zone (get ready)
5. **Liquidity Sweep** - Stops grabbed, reversal likely
6. **BSL/SSL Run** - Liquidity taken, price continues (continuation signal)
7. **Approaching Liquidity** - Getting close to BSL/SSL (edge-triggered)

---

## 🎯 Quick Setup Guide

### First Time Setup (2 Minutes)
1. Add indicator to your TradingView chart
2. **Settings Mode = Auto** (default) - optimizes everything for your timeframe
3. Choose detection mode:
   - Scalping? Use "Scalper" mode
   - Swing trading? Use "Institutional" mode
4. That's it! Start trading.

### Optional: Enable Liquidity Sweeps
1. Scroll to "Liquidity Sweeps" section in settings
2. Turn ON **"Enable Liquidity Module"** (master toggle)
3. Turn ON "Show Liquidity Levels" (for BSL/SSL lines)
4. Turn ON "Mark Sweep Events" (for sweep highlights)
5. Now you'll see stop hunts before they happen!

**Alerts-Only Mode:** Want alerts without chart clutter? Enable the module + alerts, but leave drawings OFF!

### Optional: Setup Alerts
1. Click the Alert button in TradingView (top right)
2. Choose this indicator
3. Select alert type (recommend "Rejection" alerts)
4. Set notification method (phone, email, etc.)
5. Never miss a trade again!

---

## 🔥 Pro Tips

### Best Practices
✅ **Focus on Elite★ and Strong◆ blocks** - highest win rate  
✅ **Use higher timeframes** (4h, Daily) for more reliable signals  
✅ **Wait for rejection confirmation** before entering  
✅ **Combine order blocks + liquidity sweeps** = powerful confluence  
✅ **Always use stop losses** (5-10 pips beyond the zone)

### What to Avoid
❌ Trading every single order block (be selective!)  
❌ Ignoring volume (low volume = weaker signal)  
❌ Going against strong trends  
❌ Trading Weak○ blocks (skip these)  
❌ Not using stop losses (ALWAYS protect yourself)

---

## 📅 Version History Timeline

- **v5.1.0** (Feb 2026) - 🏛️ ICT Standard Compliance (FVG mandatory, swing dealing range, tier scoring, CE mitigation, age decay)
- **v3.4.0** (Jan 2026) - 🎯 Production UX (Auto mode, anti-spam alerts, opt-in liquidity)
- **v3.3.0** (Jan 2026) - 📊 Power Row (BUY/SELL pressure tracking)
- **v3.1.0** (Jan 2026) - 💧 Liquidity Sweeps (see stop hunts)
- **v3.0.1** (Jan 2026) - ⚠️ Proximity Alerts (advance warnings)
- **v3.0.0** (Jan 2026) - ⚡ Performance (30-50% faster)
- **v2.4.1** (Jan 2026) - 🎛️ Advanced Controls (30+ settings)
- **v2.4.0** (Jan 2026) - 🔧 Auto-Scaling (smart adaptation)
- **v2.0.0** (Jan 2026) - 💎 Elite Blocks (Volume Profile)

---

## 💬 Need Help?

**Questions? Issues? Feature ideas?**

- 💬 **Discord Community:** [discord.gg/RPeAwArXUA](https://discord.gg/RPeAwArXUA)
- 🌐 **Website:** [www.paganie.com](https://www.paganie.com)
- 🛒 **Get Access:** [whop.com/paganie](https://whop.com/paganie/)

We're here to help you succeed! 

---

## ⚠️ Important Disclaimer

**Please Read:**

This indicator is a TOOL, not a crystal ball. It helps you identify high-probability setups based on institutional order flow, but:

- ⚠️ No indicator guarantees profits
- ⚠️ Always use proper risk management (1-2% per trade max)
- ⚠️ Never risk more than you can afford to lose
- ⚠️ Backtest thoroughly before live trading
- ⚠️ Trading involves substantial risk of loss

**The indicator shows you WHERE institutions are likely active. Whether you profit depends on YOUR risk management, discipline, and trading skill.**

Trade smart. Trade safe. 🛡️

---

**Current Version:** 5.1.0
**Last Updated:** February 8, 2026
**Next Update:** We're always improving! Join Discord for update notifications.

---

*Thank you for choosing ICT Order Block Pro [Pagani]. Happy trading! 🚀*
