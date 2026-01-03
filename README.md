# <img src="https://github.com/user-attachments/assets/6467a42f-afae-4dc7-8ede-46f12a087c6f" width="25" /> Trade Pattern Extraction & Financial Market Structure Discovery Framework for Quantitative Trading

A quantitative trading–oriented time series analysis framework designed to systematically extract, identify, expand, and statistically validate recurring market and trade setup patterns from financial price series, returns, indicators, and derived trading signals.
This system is designed to work on **price, returns, indicators, or derived trade signals** and enables:

- Automated feature engineering for trading windows  
- Discovery of repeating market patterns (setups)  
- Expansion of patterns using similarity & DTW  
- Statistical validation and visual inspection of trade structures  

Built for **quants, algo traders, researchers, and market microstructure analysis**.


## <img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="25px" style="position: bottom;">  Trading Context : Understanding the Market Problems This Framework Solves. 

In trading context, this framework helps us answer:

❓ Do certain price movements repeat before profitable trades?  
❓ How often does a specific setup reappear?  
❓ Are these patterns time-scaled versions of the same market behavior?  
❓ How stable is a trade pattern statistically?  

It treats **trade setups as patterns** and discovers them directly from historical price series.


## <img src="https://github.com/user-attachments/assets/6672ee8c-15ed-4fb5-9cd5-63c04ac747c1" height="24px" style="vertical-align: bottom; margin-right: 10px;"> Core Analytical Capabilities for Trade Pattern Extraction
A structured set of analytical tools designed to transform raw market data into discoverable, interpretable, and reusable trade patterns.
## 1️⃣ Sliding Window Trade Feature Extraction

Transforms **raw market data** into structured trade contexts using a sliding window approach.

### How it works ?
- The price series is split into overlapping windows of fixed length  
- Each window represents a potential trade setup at that point in time  
- Features are computed only from past data within the window (no leakage)  

### Supported inputs
- OHLC / price series  
- Returns and log-returns  
- Volatility segments  
- Indicator-based signals (RSI, MACD, etc.)  

### Why This Is Important for Trading ?
- Converts time series into tabular ML-ready data  
- Enables supervised / unsupervised learning on trade setups  
- Aligns naturally with how traders reason about entries  

<img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="15px" style="position: bottom;">  **Output: one row per trade window with engineered features**  


## 2️⃣ Automated Trade Feature Engineering (TSFresh)

Automatically extracts hundreds of statistically meaningful features from each trade window.

### Feature categories
- Momentum & trend statistics  
- Volatility structure  
- Autocorrelation & lag behavior  
- Entropy & complexity (market regime indicators)  

### Adaptive behavior
- Feature generation scales with window size  
- Prevents unnecessary feature explosion  
- Automatically disables invalid statistics for short windows  

### Presets
- **minimal** → fast prototyping and quick experiments  
- **efficient** → default for trading ML models  
- **comprehensive** → research-grade pattern analysis  

<img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="15px" style="position: bottom;">  **Output: Eliminates manual indicator engineering**
  
<img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="15px" style="position: bottom;">  **Output: Captures market structure beyond classic indicators**  


## 3️⃣ Trade Pattern Discovery (Matrix Profile)

Discovers repeating price action patterns directly from historical data using  
**STUMPY (Matrix Profile)**.

### What it finds ?
- Bullish and bearish trade setups  
- Consolidation and breakout structures  
- Mean-reversion and pullback patterns  

### How it works ?
- Searches for similar subsequences across the entire price history  
- Groups recurring structures into **Trade Pattern** objects  
- Each pattern contains multiple historical occurrences (instances)  

<img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="15px" style="position: bottom;">  **Output: Patterns are discovered data-driven, not rule-based.**  

<img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="15px" style="position: bottom;">  **Output: No predefined candle patterns required**  



## 4️⃣ Pattern Expansion (Real Trading Power)

Once a core trade pattern is found, the framework can expand it to uncover more opportunities.

### 🔹 Similarity Expansion
Finds same-length trade setups using Euclidean similarity.

**Use cases**
- Fixed-horizon strategies  
- Candle-pattern style systems  
- High-confidence, tightly controlled setups  

<img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="15px" style="position: bottom;">  **Output: Preserves timing and structure.**  

<img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="15px" style="position: bottom;">  **Output: Expands pattern frequency conservatively**  



### 🔹 DTW Expansion (Advanced)

Finds time-warped versions of the same trade using **Dynamic Time Warping (DTW)**.

### Detects
- Fast vs slow breakouts  
- Accelerated vs delayed reversals  
- Compressed or stretched market moves  

### Why This Is Important for Trading ?
- Real markets rarely move at fixed speeds  
- DTW captures the *shape* of a trade, not its exact timing  

<img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="15px" style="position: bottom;">  **Output: Enables scale-invariant pattern discovery.** 

<img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="15px" style="position: bottom;">  **Output: Crucial for live-market robustness.**  


## 5️⃣ Trade Pattern Validation & Visualization

Provides both static and interactive tools to visually validate discovered trade patterns.

### What you can inspect ?
- Entry-to-exit price shapes  
- Pattern overlap and clustering  
- Frequency, stability, and consistency  

### Interactive Bokeh UI
- Zoom and pan across the full price series  
- Hover to inspect individual pattern instances  
- Priority handling for overlapping patterns  
- Toggle pattern types (base / similarity / DTW)  

<img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="15px" style="position: bottom;">  **Output: Bridges quantitative analysis with trader intuition**  

<img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="15px" style="position: bottom;">  **Output: Makes pattern quality easy to validate visually**  

## 📦 Installation

This framework is designed to run locally on your machine for research, experimentation, and strategy development.

### 1️⃣ Create a Virtual Environment 

```bash
python -m venv trade-pattern-env
source trade-pattern-env/bin/activate   # macOS / Linux
trade-pattern-env\Scripts\activate      # Windows
```
Note : Using a virtual environment avoids dependency conflicts and keeps experiments isolated.

### 2️⃣ Install Required Dependencies
```bash
pip install numpy==2.0.2
pip install pandas==2.2.2
pip install matplotlib==3.10.0
pip install bokeh==3.7.3
pip install pathos==0.3.4
pip install stumpy==1.13.0
pip install tsfresh==0.21.1
```
⚠️ Note on warnings
Dependency warnings related to datasets can be safely ignored unless you explicitly use that library.

### <img src="https://github.com/user-attachments/assets/6467a42f-afae-4dc7-8ede-46f12a087c6f" width="18" /> Trading-Oriented Project Structure
The codebase mirrors the natural workflow of quantitative trade research:
```bash
.
├── trade_features/          # Feature engineering layer
│   ├── sliding_windows
│   ├── TsFreshConfigurator
│   ├── extract_windowed_features
│
├── trade_patterns/          # Pattern discovery layer
│   ├── find_patterns
│   ├── Pattern
│   ├── Instance
│
├── pattern_expansion/       # Pattern generalization layer
│   ├── extend_instances        # same-horizon trade setups
│   ├── extend_dtw_instances    # time-warped trade setups
│
├── visualization/           # Analysis & validation tools
│   ├── price_overlay
│   ├── pattern_shapes
│   ├── interactive_market_view
│
└── examples/                # Example scripts & experiments
```
Why this structure?
- Modify feature engineering independently
- Swap pattern discovery logic
- Experiment with different expansion strategies
- Validate results visually before strategy deployment

## <img src="https://github.com/user-attachments/assets/96212023-6a4a-4f13-849f-36a8a7812d31" width="35" /> Local Setup

### 📊 Step 1: Generate Trade Features
Convert raw price data into feature-rich trade windows.
```bash
features = extract_windowed_features(
    time_series=price_series,
    window_size=20,
    preset="efficient",
    lags="minimal"
)
```
Interpretation

- Each row → one trade context window
- First column → reference price (potential trade entry)
- Remaining columns → engineered market features

**<img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="15px" style="position: bottom;">  Output is immediately usable for ML models or pattern mining.**

### 🔍 Step 2: Discover Trade Patterns
Identify repeating trade setups in historical data.
```bash
patterns = find_patterns(
    time_series=features["ts"],
    lengths=[7, 10, 20],
    min_repeats=5
)
```
Each Pattern represents:

- A recurring trade structure
- Multiple historical occurrences
- Quantified similarity between instances

This step reveals what the market tends to repeat.

### 🔁 Step 3: Expand Trade Opportunities
Similarity-Based Expansion
- Find additional same-length trade setups.
 ```bash
pattern.extend_instances(tolerance=-0.3)
```
- **<img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="15px" style="position: bottom;">  Output: High-confidence trade repeats**
- **<img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="15px" style="position: bottom;">  Output: Suitable for fixed-horizon strategies**

### DTW-Based Expansion (Advanced)
Discover time-warped versions of the same trade.
```bash
pattern.extend_dtw_instances(
    tolerance=-0.3,
    length_range=(0.3, 5.0),
    distance_metric="pattern"
)
```
- **<img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="15px" style="position: bottom;">  Output: Captures fast vs slow market moves**
- **<img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="15px" style="position: bottom;">  Output: Improves robustness in real trading environments**

### 📈 Step 4: Analyze Pattern Statistics
Inspect quantitative stability and consistency.
```bash
pattern.statistics
```
Includes:

- Number of occurrences
- Distance stability (robustness)
- DTW alignment metrics
- Time-scale variability

These metrics help decide whether a pattern is tradable or noise.

### 🖥️ Step 5: Visual Validation
Visually inspect discovered trade setups before using them in a strategy.
```bash
pattern.show()              # interactive market view
pattern.show_shape()        # canonical trade shape
pattern.show_instances()    # overlay of all trade setups
```
Typical Use Cases

- Manual strategy validation
- Pattern sanity checks
- Combining trader intuition with quantitative rigor

## <img src="https://github.com/user-attachments/assets/d3a7713c-0fa3-4fba-a8b3-1cb60e4dafce"  height="20px" style="position: bottom;">  Practical Applications

This framework is designed for real-world quantitative trading and market research.  
Common use cases include:

- **Alpha discovery** — uncover repeatable market behaviors
- **Strategy validation** — test if setups are structurally consistent
- **Pattern-based entries** — identify recurring trade setups
- **Market regime detection** — distinguish trending vs ranging behavior
- **Signal confirmation** — validate indicators with structural patterns
- **Trade clustering** — group similar market movements
- **Feature generation for ML models** — convert price action into ML-ready features


## <img src="https://github.com/user-attachments/assets/64abffeb-9a67-4e47-a3ec-69036aa3a343" height="25px" style="position: bottom;"> Performance & Usage Notes

- **Larger windows → exponential feature growth**  
  Use longer windows only when justified by research goals.

- **DTW is computationally expensive**  
  Apply Dynamic Time Warping selectively on high-quality candidate patterns.


## <img src="https://github.com/user-attachments/assets/fd1f80c8-fedb-4e8f-8d95-7af4e4ce63cb" width="25" /> Recommended Workflow

1. Start with **small windows** and the **efficient preset**
2. Identify **strong, stable patterns**
3. Expand patterns **conservatively**
4. Validate results **visually and statistically**


## <img src="https://github.com/user-attachments/assets/6306c5f7-9cd8-4d69-ab72-9e0a97a900a8" width="20" /> Philosophy

> *Markets repeat — but never exactly.*

This framework focuses on **structure and behavior**, not exact price levels.  
By avoiding naive technical indicators and exact matching, it enables **robust trade pattern discovery** that generalizes across time and market conditions.


