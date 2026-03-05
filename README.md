# Renewable Energy Production Analysis & Forecasting

> Analysis and forecasting of renewable energy production across Solar, Wind, Hydro, and Geothermal sources. Covers 10 years of monthly data (2014–2023) with exploratory analysis, seasonal decomposition, and 2025 projections using Polynomial Regression and Holt-Winters smoothing. Built with Python, pandas, and matplotlib.

---

## Overview

This project explores **10 years of monthly renewable energy production data** (January 2014 – December 2023) across four major renewable sources. It combines historical trend analysis with forward-looking forecasts through 2025.

The project includes:
- A **Jupyter notebook** with fully reproducible analysis and visualisations
- A **non-technical write-up**  summarising findings with embedded charts

---

## Energy Sources

| Source | Peak Season | 10-Year Growth | Variability |
|---|---|---|---|
| ☀️ Solar | Summer (Jul) | +215% | High |
| 💨 Wind | Winter (Dec) | +252% | Moderate–High |
| 💧 Hydro | Spring (Apr) | +28% | Moderate |
| 🌋 Geothermal | Year-round | +68% | Low |

---

## Project Structure

```
renewable-energy-analysis/
│
├── renewable_energy_analysis.ipynb   # Main analysis notebook
├── renewable_energy_simple_writeup  # Non-technical write-up with charts
├── requirements.txt                  # Python dependencies
└── README.md
```

---

## Analysis Sections

The notebook is organised into 8 sections:

1. **Setup & Data Generation** — Simulated monthly GWh data with realistic seasonality, trend, and noise
2. **Exploratory Data Analysis** — Time-series overview, rolling averages, annual totals
3. **Seasonal & Trend Decomposition** — Monthly seasonality profiles, Savitzky-Golay trend smoothing
4. **Correlation & Efficiency Analysis** — Pearson correlation heatmap, year-over-year growth rates
5. **Polynomial Regression Forecast** — Degree-2 trend model with confidence intervals
6. **Holt-Winters Forecast** — Triple exponential smoothing capturing level, trend, and seasonality
7. **Model Evaluation** — MAE, RMSE, and R² comparison across models and sources
8. **Summary & Insights** — Auto-generated key findings and 2025 outlook

---

## Key Findings

- 📈 **Total renewable output more than doubled** over the decade
- ☀️ **Solar and Wind are the fastest-growing sources**, each roughly tripling since 2014
- 💧 **Hydro** remains the largest single contributor but grows slowly
- 🌋 **Geothermal** is the most stable — consistent output regardless of season
- 🔄 Solar and Wind peak at **opposite times of year**, naturally balancing each other on the grid

---

## Forecast Results

Projected annual output for **2025** using Holt-Winters Exponential Smoothing:

| Source | 2023 Actual (GWh) | 2025 Forecast (GWh) | Change |
|---|---|---|---|
| ☀️ Solar | ~4,850 | ~5,740 | ▲ +18% |
| 💨 Wind | ~6,280 | ~7,410 | ▲ +18% |
| 💧 Hydro | ~5,160 | ~5,330 | ▲ +3% |
| 🌋 Geothermal | ~1,240 | ~1,380 | ▲ +11% |
| **Total** | **~17,530** | **~19,860** | **▲ +13%** |

> Forecasts are based on historical trend and seasonality. They do not account for policy changes, extreme weather events, or rapid shifts in installed capacity.

---

## Requirements

```
numpy
pandas
matplotlib
seaborn
scikit-learn
scipy
jupyter
```

> To use **real data**, replace the data-generation cell in the notebook with `pd.read_csv(...)`.  
> Expected columns: `Date` (YYYY-MM-DD), `Solar`, `Wind`, `Hydro`, `Geothermal` (all in GWh).

---

## Usage

### Running with your own data

The notebook is designed to work with real production data. Simply swap out the simulated data block:

```python
# Replace this:
df = pd.DataFrame({ 'Solar': solar, 'Wind': wind, ... })

# With this:
df = pd.read_csv('your_data.csv', parse_dates=['Date'], index_col='Date')
```

---

## Outputs

| File | Description |
|---|---|
| `renewable_energy_analysis.ipynb` | Full analysis notebook with charts and models |
| `renewable_energy_simple_writeup.pdf` | Plain-language summary with embedded charts |

---
