# Territorial Risk Analysis using Geospatial Data
## INSQUI – Exploratory Environmental & Climate Risk Project

---

## Overview

This project performs an **exploratory territorial risk analysis** for company locations in Colombia using **minimal geospatial input data**: type of on-site activity and geographic coordinates.

It integrates **open climate and environmental datasets** to characterize the **contextual exposure** of each location, without relying on confidential operational or chemical inventory data.

The resulting dataset is designed to support:

- Multivariate analysis (PCA)
- Unsupervised learning techniques (e.g. clustering)
- Interactive dashboards and geospatial visualization (Looker Studio)

---

## Project Objective

The main objective is to **assess relative environmental and climate-related territorial risk** of geographic locations by combining:

- Climate context derived from NASA datasets
- Environmental sensitivity based on protected areas (WDPA)
- Type of on-site activity (contextual risk factor)

The final vision is a framework where **a single geographic coordinate can be evaluated in terms of territorial risk exposure**, enabling comparative analysis across regions and activities.

---

## Data Source: INSQUI

The base dataset originates from **INSQUI**, using **reported and publicly available data up to 2025**.

[text](https://insqui.sical.gov.co/BI/tableros_insqui.html)

INSQUI data provides the **geographic reference of company locations**, which serves as the foundation for all subsequent environmental and climate enrichment performed in this project.

No confidential, operational, or chemical inventory information is used.

---

## Input Data

### Base Dataset (INSQUI)

Minimal structured dataset:

| Column           | Description |
|------------------|-------------|
| `tipo_actividad` | Type of site activity (administrative, operational, storage, etc.) |
| `latitud`        | Latitude |
| `longitud`       | Longitude |

This structure allows the analysis to scale easily to **hundreds or thousands of locations** while remaining computationally simple and reproducible.

---

## External Data Sources

### NASA – Climate Data

Open NASA datasets are used to characterize the **climatic context** of each coordinate, including:

- Aggregated climate indicators
- Historical or long-term average climate behavior
- Environmental conditions associated with geographic location

The objective is **contextual characterization**, not short-term forecasting or event-level prediction.

[text](https://power.larc.nasa.gov/parameters/)
---

### WDPA – World Database on Protected Areas

The **World Database on Protected Areas (WDPA)** is used to determine:

- Whether a location lies **inside a protected area**
- Or its **proximity to environmentally protected zones**

This adds a critical **environmental sensitivity dimension**, relevant for:

- Territorial risk assessment
- Environmental impact considerations
- Regulatory and planning context

[text](https://www.protectedplanet.net/country/COL)

---

## Methodology

General workflow implemented in the project:

1. Load and validate INSQUI coordinate data
2. Spatial visualization of company locations
3. Climate data integration using NASA sources
4. Environmental overlay with WDPA protected areas
5. Feature construction and indicator generation
6. Data normalization and scaling
7. Exploratory multivariate analysis  
   - Principal Component Analysis (PCA)  
   - Clustering (planned future stage)
8. Generation of a dashboard-ready analytical dataset

---

## Current Outputs

At its current stage, the project delivers:

- Geospatial mapping of company locations
- Climate-related contextual variables per coordinate
- Environmental protection indicators (WDPA-based)
- A clean analytical dataset ready for:
  - PCA
  - Unsupervised machine learning
  - Business intelligence and visualization tools

---

## Scope & Limitations

### Included

- Coordinate-based territorial analysis
- Use of public and open datasets
- Exploratory and comparative analytical approach

### Not Included (yet)

- Chemical inventory or hazard-specific modeling
- Event prediction models (e.g. extreme weather forecasting)
- Socioeconomic vulnerability indicators (e.g. DANE)
- Seismic or geological risk layers

---

## Future Extensions

Potential future developments include:

- Construction of a **Composite Territorial Risk Index**
- Integration with socioeconomic vulnerability indicators
- Inclusion of seismic and geological risk layers
- Automated territorial risk scoring per coordinate
- Decision-support dashboards for inspection, planning, or SST analysis

---

## Visualization

Planned visualization layer:

- Interactive geospatial maps
- Risk comparison across regions
- Aggregated indicators by type of activity

Visualization and reporting are implemented using **Looker Studio**.

---

## Author

**Leonardo Guzmán**  
Chemical Engineer  
Occupational Safety & Chemical Risk Consultant  
MSc Student – Data Analytics & Intelligence

---

## License

This project uses **open public data sources** (NASA, WDPA) combined with **publicly reported INSQUI data (up to 2025)**.

Methodologies, transformations, and derived datasets are intended for **analytical, research, and exploratory purposes**.
