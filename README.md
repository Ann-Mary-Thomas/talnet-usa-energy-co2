# TAL-Net: Joint Forecasting of Regional Electricity Demand and CO₂ Emissions

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.9](https://img.shields.io/badge/python-3.9.13-blue.svg)](https://www.python.org/downloads/)

This repository contains the code and notebooks for my research project at Genesis Lab, London Metropolitan University. The project develops **TAL-Net (Temporal Attention LSTM Network)** - a novel deep learning architecture for joint forecasting of regional electricity demand and CO₂ emissions - and benchmarks it against established baselines using U.S. regional grid data.

---

## 🔍 Overview

Accurate joint forecasting of electricity demand and CO₂ emissions is essential for grid planning, emissions reduction, and renewable energy integration. This study proposes **TAL-Net**, a custom attention-augmented LSTM that captures the coupled temporal dynamics between electricity consumption and resulting emissions across two distinct U.S. grid regions: **CAL (California grid region)** and **TEX (ERCOT/Texas grid region)**.

> **Note:** CAL and TEX refer to EIA-930 grid regions, not the U.S. states of California and Texas in their entirety. CAL encompasses a group of balancing authorities within the broader California grid area, while TEX corresponds to a single balancing authority (ERCOT).

### Key Features

- ✅ Joint modeling of regional electricity demand & CO₂ emissions
- ✅ Novel TAL-Net architecture: LSTM with a learnable temporal attention layer
- ✅ Attention weight visualisation for interpretable temporal focus
- ✅ Window sensitivity analysis across lookback horizons (6, 12, 24, 30, 48, 72 hours)
- ✅ Comprehensive baseline comparisons: RNN, LSTM, RBM+MLP, RBM+LSTM
- ✅ Multiple train-test split evaluation: 80-20, 75-25, 70-30, 65-35, 60-40
- ✅ Regional comparison: CAL and TEX grid regions
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
git clone https://github.com/Ann-Mary-Thomas/talnet-usa-energy-co2.git
cd talnet-usa-energy-co2

# Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Environment

| Package | Version |
|---|---|
| Python | 3.9.13 |
| TensorFlow | 2.13.0 |
| Keras | 2.13.1 |
| NumPy | 1.23.5 |
| Pandas | 1.5.3 |
| Scikit-learn | 1.6.1 |
| Matplotlib | 3.5.2 |
| Seaborn | 0.11.2 |

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
- **Dataset DOI**: https://doi.org/10.7910/DVN/OKEATQ
- **Regions**: CAL (California grid region) and TEX (ERCOT/Texas grid region)
- **Period**: July 1, 2018 – June 30, 2023 (5 years, hourly resolution)
- **Key variables**: Electricity demand (MWh), net generation by source (coal, natural gas, nuclear, hydro, solar), CO₂ emissions by fuel (metric tons)

---

## 🔬 Methodology Highlights

- **TAL-Net Architecture**: A learnable attention mechanism sits atop shared LSTM layers, enabling the model to dynamically weight timesteps and focus on the most informative historical windows for each prediction target.
- **Feature Engineering**: 27 engineered features including temporal features (hour, day-of-week, month, season), lagged demand and emissions values (1H, 24H, 1W), rolling statistics (3H and 24H means), and renewable/fossil fuel mix ratios.
- **Window Sensitivity Analysis**: Systematic evaluation of lookback window sizes (6, 12, 24, 30, 48, 72 hours) for both demand and CO₂ targets across both regions. A 30-hour window was selected as the balanced configuration.
- **Baseline Comparison**: RNN, LSTM, RBM+MLP, and RBM+LSTM evaluated under identical experimental conditions.
- **Multi-Split Evaluation**: All models assessed under five train-test splits (80-20, 75-25, 70-30, 65-35, 60-40) for robustness.

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

## 📝 Citation

This repository accompanies a research paper currently under review. Citation details will be updated upon publication.
