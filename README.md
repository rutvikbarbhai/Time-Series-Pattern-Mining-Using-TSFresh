# <img src="https://github.com/user-attachments/assets/6467a42f-afae-4dc7-8ede-46f12a087c6f" width="25" /> Trade Pattern Extraction & Financial Market Structure Discovery Framework for Quantitative Trading

A quantitative trading–oriented time series analysis framework designed to systematically extract, identify, expand, and statistically validate recurring market and trade setup patterns from financial price series, returns, indicators, and derived trading signals.
This system is designed to work on **price, returns, indicators, or derived trade signals** and enables:

- Automated feature engineering for trading windows  
- Discovery of repeating market patterns (setups)  
- Expansion of patterns using similarity & DTW  
- Statistical validation and visual inspection of trade structures  

Built for **quants, algo traders, researchers, and market microstructure analysis**.

---

## 🎯 What This Framework Is About (Trading Context)

In trading terms, this framework helps answer:

- ❓ Do certain price movements repeat before profitable trades?  
- ❓ How often does a specific setup reappear?  
- ❓ Are these patterns time-scaled versions of the same market behavior?  
- ❓ How stable is a trade pattern statistically?  

It treats **trade setups as patterns** and discovers them directly from historical price series.

---

## 🧠 Core Trading Capabilities

### 1️⃣ Sliding Window Trade Feature Extraction

Converts raw price series into **feature-rich trade windows**

- Each window = potential trade context  
- Supports:
  - OHLC-derived signals  
  - Returns  
  - Volatility segments  
  - Indicator-based windows  

✔ Produces **ML-ready trade datasets**

---

### 2️⃣ Automated Trade Feature Engineering (TSFresh)

Smart, adaptive feature generation per window

Extracts:
- Momentum statistics  
- Volatility structure  
- Autocorrelation & lag behavior  
- Entropy & complexity (market regime clues)  

Presets:
- `minimal` → fast prototyping  
- `efficient` → trading ML defaults  
- `comprehensive` → research-grade analysis  

---

### 3️⃣ Trade Pattern Discovery (Matrix Profile)

Uses **STUMPY (Matrix Profile)** to detect repeating price movements

Finds:
- Bullish / bearish setups  
- Consolidation breakouts  
- Mean-reversion structures  

Each detected pattern becomes a **Trade Pattern Object**

---

### 4️⃣ Pattern Expansion (Real Trading Power)

#### 🔹 Similarity Expansion
Finds same-length price setups across history  

Useful for:
- Fixed-horizon strategies  
- Candle-pattern style systems  

#### 🔹 DTW Expansion (Advanced)
Finds time-warped versions of the same trade  

Detects:
- Fast vs slow breakouts  
- Accelerated vs delayed reversals  

Crucial for real markets where **timing varies**

---

### 5️⃣ Trade Pattern Validation & Visualization

Static & interactive visualization

Inspect:
- Entry-to-exit shapes  
- Overlapping trades  
- Frequency & stability  

Interactive **Bokeh UI**:
- Zoom  
- Hover  
- Instance priority handling  

---

## 📦 Installation

```bash
pip install numpy==2.0.2
pip install pandas==2.2.2
pip install matplotlib==3.10.0
pip install bokeh==3.7.3
pip install pathos==0.3.4
pip install stumpy==1.13.0
pip install tsfresh==0.21.1
