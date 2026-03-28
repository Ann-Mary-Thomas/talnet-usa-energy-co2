# TAL-Net: Joint Forecasting of Regional Electricity Demand and CO₂ Emissions

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)

This repository contains the code and notebooks for my research project at Genesis Lab, London Metropolitan University. The project develops **TAL-Net (Temporal Attention LSTM Network)** — a novel deep learning architecture for joint forecasting of regional electricity demand and CO₂ emissions — and benchmarks it against established baselines using U.S. regional grid data.

---

## 🔍 Overview

Accurate joint forecasting of electricity demand and CO₂ emissions is essential for grid planning, emissions reduction, and renewable energy integration. This study proposes **TAL-Net**, a custom attention-augmented LSTM that captures the coupled temporal dynamics between electricity consumption and resulting emissions across two distinct U.S. grid regions: **California (CAL)** and **Texas (TEX)**.

### Key Features

- ✅ Joint modeling of regional electricity demand & CO₂ emissions
- ✅ Novel TAL-Net architecture: LSTM with a learnable temporal attention layer
- ✅ Attention weight visualisation for interpretable temporal focus
- ✅ Window sensitivity analysis across lookback horizons (6, 12, 24, 30, 48, 72 hours)
- ✅ Comprehensive baseline comparisons: RNN, LSTM, RBM+MLP, RBM+LSTM
- ✅ Dual train-test split evaluation: 80-20 and 75-25
- ✅ Regional comparison: California and Texas grid regions
- ✅ Metrics: MAPE, MAE, RMSE

---

## 📁 Repository Structure

```
TAL-Net-electricity-emissions-forecasting/
│
├── 01_data_cleaning.ipynb       # Data acquisition, preprocessing, and cleaning
├── 02_Feature_engg.ipynb        # Feature engineering and temporal feature construction
├── 03_EDA.ipynb                 # Exploratory data analysis (CAL and TEX regions)
├── 04_RNN.ipynb                 # Baseline RNN model implementation
├── 05_LSTM.ipynb                # Baseline LSTM model (80-20 and 75-25 splits)
├── 06_RBM_MLP.ipynb             # RBM + MLP hybrid model
├── 07_RBM_LSTM.ipynb            # RBM + LSTM hybrid model
├── 08_LSTM_Attention.ipynb      # TAL-Net: attention layer, weight visualisation, window sensitivity
├── 09_result_plots.ipynb        # Prediction visualisation across all models
├── 10_comparison.ipynb          # Cross-model performance comparison (MAPE, MAE, RMSE)
│
├── requirements.txt             # Python dependencies
├── LICENSE                      # MIT License
└── README.md                    # This file
```

---

## 🚀 Quick Start

### Prerequisites

```bash
# Clone the repository
git clone https://github.com/Ann-Mary-Thomas/TAL-Net-electricity-emissions-forecasting.git
cd TAL-Net-electricity-emissions-forecasting

# Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Running the Analysis

```bash
# 1. Data preprocessing and cleaning
jupyter notebook 01_data_cleaning.ipynb

# 2. Feature engineering
jupyter notebook 02_Feature_engg.ipynb

# 3. Exploratory data analysis
jupyter notebook 03_EDA.ipynb

# 4. Baseline models
jupyter notebook 04_RNN.ipynb
jupyter notebook 05_LSTM.ipynb
jupyter notebook 06_RBM_MLP.ipynb
jupyter notebook 07_RBM_LSTM.ipynb

# 5. TAL-Net (proposed model)
jupyter notebook 08_LSTM_Attention.ipynb

# 6. Results and comparison
jupyter notebook 09_result_plots.ipynb
jupyter notebook 10_comparison.ipynb
```

---

## 📊 Data

- **Source**: U.S. Energy Information Administration (EIA) — EIA-930 Hourly Electric Grid Monitor
- **Regions**: California (CAL) and Texas (TEX)
- **Resolution**: Hourly observations
- **Key variables**: Electricity demand, net generation by source (coal, gas, nuclear, hydro, solar), CO₂ emissions by fuel, CO₂ intensity

---

## 🔬 Methodology Highlights

- **TAL-Net Architecture**: A learnable attention mechanism sits atop shared LSTM layers, enabling the model to dynamically weight timesteps and focus on the most informative historical windows for each prediction target.
- **Feature Engineering**: Temporal features (hour, day-of-week, month, season, day-of-year), rolling statistics (3H and 24H means), demand differencing (1H and 24H lags), and renewable energy mix ratios (Renewable%, Fossil%).
- **Window Sensitivity Analysis**: Systematic evaluation of lookback window sizes (6, 12, 24, 30, 48, 72 hours) for both demand and CO₂ targets across both regions.
- **Baseline Comparison**: RNN, LSTM, RBM+MLP, and RBM+LSTM evaluated under identical experimental conditions.
- **Dual-Split Evaluation**: All models assessed under both 80-20 and 75-25 train-test splits for robustness.

---

## 📫 Contact

**Ann Mary Thomas**  
✉️ Email: annmarytttt@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/ann-mary-thomas-6272aa200)  
💻 [Portfolio](https://github.com/Ann-Mary-Thomas)

---

## 📜 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 📝 Note

This repository accompanies a research paper currently under review. Detailed results and metrics will be updated upon publication.
