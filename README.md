# Business Intelligence: Climate Change and Energy Transition Analysis

![LaTeX](https://img.shields.io/badge/LaTeX-008080?logo=latex&logoColor=white)
![Qlik Sense](https://img.shields.io/badge/Qlik%20Sense-009848?logo=qlik&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-E97627?logo=tableau&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?logo=powerbi&logoColor=black)

A data analysis project that explores global **climate change** and the **energy transition** by building interactive dashboards across three leading Business Intelligence platforms: **Qlik Sense**, **Tableau**, and **Power BI**. The same datasets are analyzed in each tool, so the project also works as a practical comparison of how the three platforms handle data modeling, visualization, and forecasting.

> Academic project for the Business Intelligence course (Università Politecnica delle Marche). The full report is written in Italian and typeset in LaTeX.

## Overview

The goal of the project is to turn public environmental and economic data into clear, explorable insights about how temperature, CO2 emissions, renewable energy, and economic growth relate to one another at a global scale. Each BI tool is used to answer a slightly different set of questions and to highlight its own strengths, from associative exploration in Qlik to predictive modeling in Tableau and relational modeling in Power BI.

## Datasets

| Dataset | Source | Period | Content |
|---|---|---|---|
| FAOSTAT Temperature Change | FAO, based on NASA-GISS GISTEMP | 1961 to 2020 | Mean surface temperature anomalies relative to the 1951 to 1980 baseline, for roughly 190 countries and 37 territories |
| Global Data on Sustainable Energy | Kaggle (Ansh Tanwar) | 2000 to 2020 | UN SDG 7 indicators: electricity access, renewable capacity, energy by source, CO2 per capita, energy intensity, GDP and GDP per capita, land area, and more |

A complementary FAOSTAT country-code file (M49, ISO2, ISO3 codes) is also used in Power BI as a bridge table to resolve country relationships across sources.

## Tools and Tech Stack

- **Qlik Sense** for associative data exploration and geospatial visualization.
- **Tableau** for relationship-based modeling, dashboards, and built-in time-series forecasting.
- **Power BI** for a relational data model, calculated columns, and interactive reporting.
- **LaTeX** (Legrand Orange Book template) for the written report.

## Repository Structure

```
Business-Intelligence-Project/
├── Report/             # Full LaTeX source of the report
│   ├── main.tex        # Master document
│   ├── structure.tex   # Template configuration and packages
│   ├── bibliography.bib
│   ├── StyleInd.ist
│   ├── Pictures/       # Template and cover images
│   ├── capitolo_1/     # Ch. 1 - Datasets and methodology
│   ├── capitolo_2/     # Ch. 2 - Qlik Sense analysis
│   ├── capitolo_3/     # Ch. 3 - Tableau analysis
│   └── capitolo_4/     # Ch. 4 - Power BI analysis
├── LICENSE
└── README.md
```

## Data Preparation

Before any dashboard was built, the raw data was cleaned and integrated. The starting point was the **Qlik Data Load Editor script**, which loads the source CSV files, normalizes month and field types, harmonizes country names across datasets, and maps each country to its geographic codes for the choropleth maps. The same preparation logic was then reproduced in **Power Query** for Power BI and through dataset **relationships** in Tableau. This initial data-preparation code is documented in the report (Chapter 2) and is the foundation for the analyses in all three tools.

## Analyses and Dashboards

### Qlik Sense
Data is loaded and shaped directly in the load script (month mapping, type conversion, country-to-geography mapping) and explored through the associative engine. The dashboards analyze mean temperature change worldwide, with a geospatial world map and country-level drill-down (Italy, USA, China, India) across the years 2000, 2010, and 2019.

### Tableau
The two datasets are connected through Tableau relationships (Year and Country) rather than manual joins, after harmonizing country names. Dashboards built with Treemaps and histograms compare CO2 emissions and renewable electricity production against land area. A dedicated forecasting section uses Tableau's predictive model (custom, additive trend and seasonality) and the Story feature to project CO2 emissions, electricity production by source, and temperature change through 2026.

### Power BI
Data is cleaned in Power Query and integrated through a relational model that uses a bridge table to work around Power BI's single active relationship limit, plus calculated columns (for example, total GDP from GDP per capita and population). Reports combine KPIs, line charts, scatter plots, and interactive maps to study how GDP relates to CO2 emissions and renewable energy, with bookmark buttons to include or exclude dominant economies such as China and the USA.

## Key Findings

- A country's economic wealth alone does not explain its CO2 emissions or its adoption of renewable energy. Energy policy, technology choices, and the energy mix matter far more than GDP or territorial size.
- Renewable electricity shows strong, near-exponential growth, while fossil and nuclear generation stay broadly stable over the period studied.
- Forecasts point to continued increases in both CO2 emissions and temperature anomalies through 2026, a trajectory consistent with independent real-world measurements.

## Authors

- Anass Chebbaki
- Caterina Sabatini
- Matteo Stronati

## License

This project is released under the MIT License. See the [LICENSE](LICENSE) file for details. The report uses the Legrand Orange Book LaTeX template, distributed separately under CC BY-NC-SA 3.0.
