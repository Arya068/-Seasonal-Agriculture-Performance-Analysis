# Seasonal Agriculture Performance Analysis
## Problem
Agricultural performance shifts between the Kharif, Rabi and Zaid seasons, but raw farm data
does not show by how much, why, or where it hurts most. This project analyses 4,000 farm records
(28 variables · 8 states · 8 crops · 4 irrigation methods · 3 seasons) to quantify those
differences and turn them into recommendations.

## Repository
| File | Description |
|---|---|
| `seasonal_agriculture_analysis.ipynb` | Full documented analysis — cleaning, feature engineering, statistical testing, visualisation, conclusions |
| `seasonal_agriculture_performance_dataset.csv` | Raw dataset |
| `charts/` | The seven generated visualisations |
| `VOIS_Major_Project_Seasonal_Agriculture_Analysis.pptx` | Submission deck |

## Method
1. Data understanding and internal consistency checks (Production = Yield × Area, etc.)
2. Cleaning — group-median imputation of Rainfall/Soil Moisture (Season × State) and Yield (Crop × Season)
3. Feature engineering — `Yield_Index` (crop-normalised), `Profit_per_ha`, `Is_Loss`
4. Univariate and bivariate analysis by season, crop, irrigation method and state
5. Significance testing — Kruskal-Wallis, one-way ANOVA, chi-square
6. Interpretation, conclusions and recommendations

## Key findings
- Yield index: Kharif 1.11 · Rabi 0.96 · Zaid 0.79 (all differences p < 0.001)
- Kharif leads in all eight crops — the gap is not a crop-mix artefact
- Loss-making farms: 42.2% (Kharif) → 51.1% (Rabi) → 64.5% (Zaid)
- Revenue falls ₹1.9 lakh from Kharif to Zaid while cost rises slightly — cost is season-inelastic
- Water efficiency is the strongest correlate of yield (r = 0.92); fertiliser, pesticide and seed
  quality show no linear effect
- In Zaid, sprinkler (0.89) and drip (0.84) hold their yield index; flood (0.73) and rainfed (0.74) do not
- Kharif's downside is biological: pest/disease risk 54.5% vs 38.2% in Zaid
- Punjab and Karnataka stay profitable in Zaid; Andhra Pradesh and Gujarat fall below -₹7,400/ha

## Run it
```bash
pip install pandas numpy matplotlib seaborn scipy jupyter
jupyter notebook seasonal_agriculture_analysis.ipynb
```
