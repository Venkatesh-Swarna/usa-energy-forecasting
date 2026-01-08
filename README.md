# USA Energy Forecasting

**Production-ready forecasting pipeline** analyzing **50+ years** of U.S. primary energy consumption data (1973-2025). **Prophet model achieves 97.3% accuracy**, beating 5 classical baselines.

## 🎯 **Target Audience**
- **Energy analysts** & **grid operators**
- **Policy makers** & **investment analysts**  
- **Data scientists** learning time series
- **Students** in energy economics/ML

## 📋 **What This Project Does**
Complete end-to-end pipeline:

DATA: EIA monthly energy (1973-2025, 633 obs)

EDA: Seasonal decomposition (25% Winter-Spring swing)

MODELS: 6 algorithms benchmarked (Prophet, ARIMA, SARIMA, Holt-Winters, Naive baselines)

EVAL: Train(44yr)/Val(4yr)/Test(4yr) → Test MAPE leader

FORECAST: 2026 production-ready predictions

## Seasonal Pattern
| Season | Avg QBTU | % Annual |
|--------|----------|----------|
| **Winter** | **7.9** | **108.4%** |
| Summer | 7.2 | 99.1% |
| Spring | 7.0 | 96.7% |
| **Fall** | 7.0 | **95.7%** |

**Prophet advantage**: Learned 13% seasonal cycle + long-term trend automatically (no manual tuning).

## 🏆 Model Benchmark Results

**Prophet dominates with 2.68% test MAPE** (47% better than ARIMA, 6% better than Seasonal-Naive)

| Model | Val MAE | Val RMSE | Val MAPE | **Test MAE** | **Test RMSE** | **Test MAPE** |
|-------|---------|----------|----------|--------------|---------------|---------------|
| **Prophet** | 0.312 | 0.385 | **4.05%** | **0.217** | **0.263** | **🥇 2.68%** |
| Seasonal-Naive(12) | 0.419 | 0.587 | 5.46% | 0.234 | 0.341 | 🥈 2.87% |
| ARIMA(2,1,2) | 0.497 | 0.615 | 6.48% | 0.406 | 0.530 | 4.97% |
| SARIMA(1,1,1)x(1,1,1,12) | 0.513 | 0.657 | 6.64% | 0.471 | 0.630 | 5.74% |
| Holt-Winters | 0.577 | 0.714 | 7.52% | 0.479 | 0.649 | 5.87% |
| Naive | 0.473 | 0.605 | 6.09% | 0.468 | 0.594 | 5.88% |

### 📈 **Key Insights**
- **Prophet**: 97.3% accuracy on unseen test data (2022-2025)
- **Test > Val gap small**: Models generalize well (no overfitting)
- **Seasonal-Naive strong**: Confirms 12-month seasonality exists
- **Classical models lag**: ARIMA/SARIMA/Holt-Winters need manual tuning

### 🎯 **Methodology**
Train: 1973-2017 (44 years)
Val: 2018-2021 (4 years)
Test: 2022-2025 (4 years) ← Never-seen data
Metrics: MAE, RMSE, MAPE on held-out test


**Prophet wins because it automatically captures:**
- ✅ Long-term downward trend
- ✅ 12-month seasonal cycle (Winter 25.8 → Spring 22.7 QBTU)
- ✅ Recent structural changes


## Quick Start
```bash
pip install -r requirements.txt
jupyter notebook USA-Energy-Forecasting.ipynb
```
## Files
* USA-Energy-Forecasting.ipynb - Complete analysis
* PrimaryEnergyOverview.xlsx - EIA data (1973-2025)
