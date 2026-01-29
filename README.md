# Territorial Risk Analysis using Geospatial Data  
## INSQUI – Exploratory Environmental & Territorial Risk Project

---

## Overview

This project performs an **exploratory territorial risk analysis** for company locations in Colombia using **minimal geospatial input data**: type of on-site activity and geographic coordinates.

It integrates **open environmental and geodynamic datasets** to characterize the **contextual exposure of the territory** where industrial and service activities operate.

The approach deliberately avoids confidential or operational data (e.g. inventories, quantities, processes), focusing instead on **territorial context as a first layer of risk analysis**.

The resulting dataset is designed to support:

- Exploratory multivariate analysis (PCA)
- Unsupervised learning techniques (e.g. clustering)
- Geospatial visualization and dashboards (Looker Studio)

---

## Project Motivation

In Occupational Safety (SST) and Process Safety, risk analysis is usually centered on:

- people  
- substances  
- equipment  
- installations  

However, **the territorial context where these systems are located is often overlooked**, despite being a key factor in exposure, vulnerability, and impact.

This project starts from a simple premise:

> **Risk does not start at the plant; it starts in the territory.**

---

## Data Source: INSQUI

The base dataset originates from **INSQUI – Inventario Nacional de Sustancias Químicas de Uso Industrial**, using **reported and publicly available data up to 2025**.

INSQUI provides the **geographic reference of company locations**, which serves as the backbone of the analysis.

Only the following information is used:

- geographic coordinates  
- type of on-site activity  

No confidential, operational, or chemical inventory data is included.

---

## Input Data

### Base Dataset (INSQUI)

Minimal structured dataset:

| Column           | Description |
|------------------|-------------|
| `tipo_actividad` | Type of site activity (administrative, operational, storage, etc.) |
| `latitud`        | Latitude |
| `longitud`       | Longitude |

This design enables scalability to **hundreds or thousands of locations**, while keeping the analysis reproducible and lightweight.

---

## External Data Sources

### USGS – Seismic and Geodynamic Context

Open datasets from the **United States Geological Survey (USGS)** are used to characterize the **seismic and geodynamic context** of each location, including:

- spatial distribution of seismic events  
- historical seismic activity around each coordinate  
- relative exposure to seismic hazards  

The objective is **territorial context characterization**, not earthquake prediction.

---

### WDPA – World Database on Protected Areas

The **World Database on Protected Areas (WDPA)** is used to identify:

- whether a location lies **inside a protected area**
- or its **proximity to environmentally protected zones**

This adds an **environmental sensitivity layer**, relevant for:

- territorial risk assessment  
- environmental impact considerations  
- land-use and regulatory context  

---

## Methodology

General workflow implemented so far:

1. Load and validate INSQUI coordinate data  
2. Spatial visualization of company locations  
3. Integration of seismic context using USGS data  
4. Environmental overlay with WDPA protected areas  
5. Construction of territorial indicators  
6. Preparation of an analytical dataset ready for multivariate analysis  

Future analytical steps (planned):

- normalization and scaling  
- Principal Component Analysis (PCA)  
- unsupervised clustering  

---

## Current Outputs

At the current stage, the project delivers:

- Geospatial mapping of INSQUI-reported locations  
- Seismic and geodynamic context indicators per coordinate  
- Environmental sensitivity indicators based on WDPA  
- A clean dataset ready for:
  - PCA  
  - clustering  
  - BI and geospatial visualization tools  

---

## Scope & Limitations

### Included

- Coordinate-based territorial analysis  
- Public and open data sources (INSQUI, USGS, WDPA)  
- Exploratory and comparative analytical approach  

### Not Included (yet)

- Chemical inventory or substance-specific hazard modeling  
- Event-level prediction models  
- Climate trend or extreme weather analysis  
- Socioeconomic vulnerability indicators (e.g. DANE)  

---

## Future Extensions

Potential next steps include:

- Construction of a **Composite Territorial Risk Index**  
- Integration of socioeconomic and demographic indicators  
- Climate and extreme weather layers  
- Automated territorial risk scoring per location  
- Decision-support dashboards for SST and process safety  

---

## Visualization

The visualization layer focuses on:

- interactive geospatial maps  
- spatial distribution of risk-related indicators  
- comparison across regions and activity types  

Dashboards are designed to be implemented using **Looker Studio**.

---

## Author

**Leonardo Guzmán**  
Chemical Engineer  
Occupational Safety & Chemical Risk Consultant  
MSc Student – Data Analytics & Intelligence  

---

## License

This project uses **open public data sources** (INSQUI – reported data up to 2025, USGS, WDPA).

All methodologies, transformations, and derived datasets are intended for **analytical, research, and exploratory purposes**.
