# Pine Strategy Indicators v4

## Overview

A collection of volatility and trend analysis indicators for TradingView, implemented in Pine Script v5. These indicators provide quantitative measurements of market volatility, trend strength, and price momentum to support technical trading decisions.

## Included Indicators

### Average Directional Index (ADX)

**Purpose:** Measures the strength of a trend regardless of direction.

**Core Logic:** Calculates the smoothed moving average of the difference between positive and negative directional indicators (DI+ and DI-) normalized by their sum. Values above 25 indicate strong trends, while values below 20 suggest weak or ranging markets.

**Key Parameters:**
- ADX Smoothing: 14 (smoothing period for ADX calculation)
- DI Length: 14 (period for directional indicator calculation)

![Average Directional Index](images/Average-Directional-Index.png)

**Typical Use Case:** Identifying trend strength to filter trade signals. Use in conjunction with directional indicators to confirm whether strong trends are bullish or bearish, avoiding trades in weak trend conditions.

---

### Keltner Channels

**Purpose:** Volatility-based envelope indicator that defines price channels around a moving average.

**Core Logic:** Plots three lines: a central exponential or simple moving average, and upper/lower bands set at a multiple of the Average True Range (ATR), True Range, or Range from the center line. Price movement outside the channels can signal breakouts or overbought/oversold conditions.

**Key Parameters:**
- Length: 20 (moving average period)
- Multiplier: 2.0 (band distance from center line)
- Source: close (price source for calculation)
- Use Exponential MA: true (EMA vs SMA toggle)
- Bands Style: Average True Range (ATR/TR/Range selection)
- ATR Length: 10 (ATR calculation period)

![Keltner Channels](images/Keltner-Channels.png)

**Typical Use Case:** Identifying potential breakout points and trend continuation. Price touching or exceeding the upper band may indicate bullish momentum, while touching the lower band suggests bearish pressure. Works well in trending markets.

---

### Relative Volatility Index (RVI)

**Purpose:** Measures the direction of volatility using standard deviation of price changes.

**Core Logic:** Calculates separate exponential moving averages of standard deviation for upward and downward price changes, then expresses the result as a ratio ranging from 0-100. Readings above 50 indicate upward volatility dominance, while readings below 50 suggest downward volatility.

**Key Parameters:**
- Length: 10 (standard deviation calculation period)
- Offset: 0 (horizontal shift for plot)
- MA Type: SMA (moving average type: SMA, EMA, WMA, VWMA, RMA, or Bollinger Bands)
- MA Length: 14 (smoothing period for RVI)
- BB StdDev: 2.0 (standard deviation multiplier for Bollinger Bands option)

![Relative Volatility Index](images/Relative-Volatility-Index.png)

**Typical Use Case:** Confirming trend direction and identifying divergences. RVI above 50 with rising price confirms bullish momentum, while RVI below 50 with falling price confirms bearish momentum. Divergences between RVI and price can signal potential reversals.

---

### Chaikin Volatility

**Purpose:** Quantifies the rate of change of volatility based on the trading range.

**Core Logic:** Calculates the exponential moving average of the high-low spread, then measures the rate of change of this EMA over a specified period. Rising values indicate expanding volatility, while falling values suggest contracting volatility.

**Key Parameters:**
- Length: 10 (EMA period for high-low spread)
- ROC Length: 12 (rate of change lookback period)

![Chaikin Volatility](images/Chaikin-Volatility.png)

**Typical Use Case:** Anticipating breakouts and trend changes. Increasing Chaikin Volatility often precedes significant price movements, while decreasing volatility suggests consolidation. Spikes above zero can signal the start of trending moves.

---

### Volatility Ratio

**Purpose:** Compares current true range to recent price range to identify volatility expansion or contraction.

**Core Logic:** Divides the current true range by the difference between the highest high and lowest low over a lookback period (including a historical close). Values above the breakout level indicate elevated volatility relative to recent range.

**Key Parameters:**
- Length: 14 (lookback period for high/low range)
- Breakout Level: 0.5 (threshold for volatility expansion)

![Volatility Ratio](images/Volatility-Ratio.png)

**Typical Use Case:** Detecting volatility breakouts from consolidation periods. Values exceeding the breakout level suggest the market is breaking out of its recent range, potentially signaling the start of a new trend or increased price movement.

---

## How to Use

1. Open TradingView and navigate to the Pine Editor
2. Copy the desired indicator code from the `indicators/` folder in this repository
3. Paste the code into the Pine Editor
4. Click "Add to Chart" to apply the indicator
5. Adjust parameters in the indicator settings panel as needed
6. Combine multiple indicators for confirmation of trading signals

## Disclaimer

These indicators are provided for educational and informational purposes only. They are technical analysis tools and should not be used as the sole basis for trading decisions. Past performance does not guarantee future results. Always conduct thorough analysis and consider your risk tolerance before trading.
