# 🌍 Global Population Estimate & Projections — Power BI Dashboard

## Overview

This project presents an interactive **Power BI dashboard** built using the *Global Population Estimate & Projections* dataset (historical 1960–2022, projections to 2050).

The dashboard transforms demographic data into a structured analytical story:

> Overview → Comparison → Trend → Geography

It enables exploration of:
- Long-term global population growth
- Regional demographic transition patterns
- Urban vs rural composition
- Income group population structure
- Birth, death, and life expectancy trends

This repository contains:
- 📊 `ASDV Task 1 dashboard.pbix` — Full interactive Power BI file
- 📄 PowerBI dashboard report (design justification + DAX + modelling explanation)

---

## Dataset

**Source:** Global Population Estimate & Projections dataset  
**Coverage:** All recognised countries  
**Time period:** 1960–2050  

Core indicators:
- Total population (male/female)
- Urban & rural population
- Life expectancy
- Birth rate (per 1,000)
- Death rate (per 1,000)
- Income group classifications
- Regional groupings

---

## Dashboard Objectives

### 1. Trend Objective
Visualise global and regional population trajectory (1960–2050).

### 2. Structure Objective
Explain composition:
- Income group distribution
- Rural vs Urban share

### 3. Comparative Objective
Compare:
- Population vs Birth/Death rates by region
- Demographic transition patterns

### 4. Exploratory Objective
Enable slicing by:
- Region
- Country
- Year

---

## Data Preparation & Modelling

### Power Query (Data Cleaning)
- Imported CSV population dataset
- Imported Excel country grouping dataset
- Trimmed and cleaned country names & codes
- Renamed indicators to user-friendly labels
- Validated year range consistency (1960–2050)
- Checked duplicate (Country, Year) pairs

### Star Schema Design

**Fact Table**
- Population Figures & Projections (1 row per Country–Year)

**Dimension Tables**
- List of Economies
- Year (Calendar table)
- Metric Selector (Field parameter)

Cross-filter direction: Single (for predictable propagation and performance)

---

## DAX Measures (Core Examples)

### Totals
- `Total Population`
- `Total Population (Latest Year)`
- `Total Female Population`
- `Total Male Population`
- `Total Urban Population`
- `Total Rural Population`

### Composition
- `% Urban`
- `% Rural`

### Rates
- `Avg Life Expectancy`
- `Avg Birth Rate`
- `Avg Death Rate`

### Time-Based Change
- `Population Growth %`
- `Population YoY %`

Heavy logic implemented via measures (not calculated columns) to improve performance and maintainability.

---

## Visualisations & Design Rationale

### KPI Cards
Display:
- Total Population
- Population Growth %
- Life Expectancy
- Birth Rate
- Death Rate

Designed for:
- Quick executive overview
- Minimal cognitive load
- High contrast readability

---

### Donut Chart — Population by Income Group
Communicates part-to-whole composition.
Limited slices to preserve perceptual accuracy.

---

### Pie Chart — Rural vs Urban Share
Efficient representation for two-category split.
Immediate % interpretation.

---

### Combo Chart — Regional Comparison
- Columns: Total Population
- Line (secondary axis): Birth & Death Rates

Captures demographic transition narrative:
High fertility → declining fertility → ageing patterns.

---

### Line Chart — Long-Term Trend
Time-series view with:
- Metric selector (field parameter)
- Forecast (10-year horizon, 95% CI)

---

### Map — World Population Distribution
Bubble map:
- Size: Total Population
- Colour: Region
- Tooltip: Country + Population + Growth %

Transparency used (40–50%) to avoid overplotting.

---

## Key Findings (From Dashboard Analysis)

- Global population rises from ~3B (1960) to projected ~9–10B (2050).
- Growth slows after 1990, reflecting declining fertility.
- South Asia & Sub-Saharan Africa drive most future growth.
- Europe & Central Asia show plateau or decline.
- Urban population share exceeds 50% globally and continues rising.
- Birth rates decline across regions; death rates rise slightly in ageing regions.

These patterns align with demographic transition theory.

---

## Performance & Best Practices

- Star schema model
- Single-direction relationships
- Measures over calculated columns
- Organised measure folders
- Centralised dark theme for consistency
- Accessible contrast ratio (white text on dark panels)

---

## Limitations

- Gaps in life expectancy and rate indicators for early years in some countries.
- Built-in forecast is heuristic (not causal).
- Bubble map may visually compress small countries.

---

## Future Enhancements

- Add decomposition tree ("what changed?")
- Add GDP, CO₂, or health expenditure integration
- Scenario analysis (low/medium/high fertility paths)
- Regional small-multiple comparisons
- Drill-through from Region → Country

---

## How to Use

1. Open `dashboard.pbix` in Power BI Desktop.
2. Use slicers (Region, Country, Year).
3. Use metric selector above the trend chart.
4. Hover over visuals for detailed tooltips.
5. Reset to full view for global overview.

---

## Academic Context

This dashboard was developed as part of an analytical task focusing on:

- Data modelling
- DAX measure construction
- Visual perception theory (Cleveland & McGill)
- Interaction design (Shneiderman’s mantra)
- Dashboard storytelling

---

## Author

**Muhammed Fahim Englampurath**  
MSc Data Science — University of Salford  
GitHub: https://github.com/MUHAMMEDFAHIM-2  
LinkedIn: https://www.linkedin.com/in/muhammed-fahim-03209b1bb/

---

