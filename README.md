# Solar ROI Analysis

A Jupyter notebook series analyzing the return on investment for a residential solar installation, using real weather station and PG&E utility data.

## Notebooks

1. **[01 - Solar Generation & Usage Offset](notebooks/01-solar-generation-usage-offset-notebook.ipynb)** — Combines solar radiation data from an AmbientWeather station with PG&E 15-minute interval usage data to estimate how much energy 16 solar panels (20.3% efficiency, 31.52 m²) would have generated and offset over a year.

2. **[02 - Energy Cost Calculation](notebooks/02-energy-cost-calculation-notebook.ipynb)** — Models PG&E rate plans (E-TOU-C and E-1) including time-of-use tiers, seasonal baselines, and 3CE generation charges to compare annual energy costs with and without solar.

## Data

### Raw (`data/raw/`)
- `ambient-weather-*.csv` — Solar radiation (W/m²) at 5-minute resolution from AmbientWeather station
- `pge_electric_interval_data_*.csv` — PG&E electricity usage (kWh) at 15-minute resolution via [Green Button Download](https://www.pge.com/en/save-energy-and-money/energy-usage-and-tips/understand-my-usage/energy-data-hub.html)

### Processed (`data/processed/`)
- `usage_data_with_generation.csv` — Usage data enriched with solar generation and offset columns
- `usage_data_with_generation_and_energy_cost.csv` — Further enriched with modeled energy costs per rate plan

## Setup

```bash
pip install pandas matplotlib tqdm pytz
jupyter notebook
```

## Key Findings

Based on Feb 2023 – Jan 2024 data:

- 16-panel system would have generated ~7,385 kWh/year
- ~41% reduction in grid consumption
- ~4,586 kWh sold back to the grid
- ~$1,402/year in energy cost savings (~38%) switching from E-TOU-C to E-1 with solar
