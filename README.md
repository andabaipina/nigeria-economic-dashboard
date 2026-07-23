# Nigeria Economic Dashboard

> 24 years of real economic data + a 30-year machine learning simulation of what happens when Nigerian citizens invest productively in their own economy.

**Live dashboards:** https://andabaipina.github.io/nigeria-economic-dashboard/

---

## What this project is

This project started as a data analysis question — what does 24 years of Nigeria's economic data actually say? It became something bigger: a machine learning simulation exploring how citizen-driven productive investment could reshape Nigeria's economic future.

The project is split into two parts:

### Dashboard 1 — Historical Reality (2000–2024)
An interactive dashboard of Nigeria's real economic performance across four indicators:
- GDP per capita (constant USD)
- Headline inflation
- NGN/USD exchange rate
- Food inflation

**Key finding:** Nigeria's real economy grew every year from 2020 to 2024 in constant price terms. The dollar GDP collapse from $647B to $252B was entirely a currency story — the Naira's 129% devaluation in 2024, not a real economic contraction.

### Dashboard 2 — Citizen Investment Simulation (2025–2054)
A machine learning model trained on Nigeria's real historical economic relationships, projecting three scenarios 30 years forward:

| Scenario | GDP per Capita 2054 | Food Inflation 2054 |
|---|---|---|
| Business as Usual | $2,367 | 16.4% |
| Moderate Civic Investment | $3,767 | 3.0% |
| Full Civic Transformation | $6,765 | 3.0% |

The gap between scenario one and scenario three is not a prediction. It is a choice.

---

## How it was built

### Data sources
- **World Bank Open Data** — GDP, inflation, exchange rate, unemployment (2000–2024)
- **Manual compilation** — Brent crude oil prices, US Federal Funds Rate, Nigerian food inflation (NBS/CBN records)

### Methodology
1. Fetched and cleaned 25 years of macroeconomic data using `wbgapi`
2. Engineered 30 features including lag variables, year-on-year changes, interaction terms, and policy shock flags
3. Trained three separate Random Forest Regression models — one each for GDP per capita, headline inflation, and exchange rate
4. Validated using Leave-One-Out cross validation (23 folds)
5. Simulated three civic investment scenarios forward to 2054 using iterative year-by-year prediction
6. Built interactive dashboards in HTML/JavaScript using Plotly.js
7. Deployed via GitHub Pages

### Model validation results
| Model | Average prediction error |
|---|---|
| GDP per capita | $96 per person (4% of base) |
| Inflation | 2.9 percentage points |
| Exchange rate | 86 NGN per Dollar (normal years) |

### Known limitations
- Only 23 training data points — model intentionally kept shallow (max_depth=3) to avoid overfitting
- Exchange rate projections carry high uncertainty — shown at 800 NGN floor
- Civic investment variable proxied by GDP growth boost — not directly measurable in historical data
- Relationships may shift structurally as Nigeria diversifies away from oil

---

## Tech stack

| Tool | Purpose |
|---|---|
| Python | Data pipeline and modelling |
| wbgapi | World Bank API data fetching |
| pandas / NumPy | Data cleaning and feature engineering |
| scikit-learn | Random Forest Regression models |
| Plotly.js | Interactive chart rendering |
| HTML / CSS / JavaScript | Dashboard frontend |
| GitHub Pages | Free live hosting |
| Google Colab | Development environment |

---

## Files

| File | Description |
|---|---|
| `nigeria_economic_analysis.ipynb` | Full Colab notebook — data fetch, cleaning, modelling, simulation |
| `index.html` | Dashboard landing page |
| `nigeria_historical_dashboard.html` | Dashboard 1 — historical data |
| `nigeria_simulation_dashboard.html` | Dashboard 2 — simulation |

---

## Key economic insights

**On the 2024 devaluation:**
The Central Bank of Nigeria unified and floated the exchange rate in 2024 — a deliberate policy decision. The Naira jumping from 645 to 1,479 NGN/USD was not a gradual slide. It triggered immediate food inflation because Nigeria imports a large share of what it consumes, making the cost of imported goods rise almost overnight.

**On the simulation:**
The most striking finding is food inflation. Under business as usual, food inflation is still 16.4% in 2054. Under full civic transformation it reaches 3% by 2032 and stabilises there. Agricultural investment — cold storage, irrigation, local processing — is the single lever that most directly improves ordinary Nigerians' daily lives.

**On civic investment:**
Countries that have broken cycles of underdevelopment have done so not primarily through better government but through a shift in what citizens, especially those with capacity, believe they owe to the places that made them. That shift is cultural before it is economic.

---

## Author

**Andabai Pinadowari Isaac** — BI and Data Analyst

- GitHub: [github.com/andabaipina](https://github.com/andabaipina)
- LinkedIn: [linkedin.com/in/andabai-isaac-aa217030b](https://linkedin.com/in/andabai-isaac-aa217030b)
- Email: andabaipina@gmail.com

---

*Data: World Bank Open Data. Model: Random Forest Regression. Dashboards: Plotly.js + GitHub Pages.*
