# Territorial Risk Analysis using Geospatial Data
## INSQUI – Exploratory Environmental & Territorial Risk Project

---

## Overview

This project performs an **exploratory territorial risk analysis** for company locations in Colombia using **minimal geospatial input data**: type of on-site activity and geographic coordinates.

It integrates **open environmental and geodynamic datasets** to characterize the **contextual exposure** of each location, without relying on confidential operational, chemical, or inventory-level data.

The resulting dataset is designed to support:

- Multivariate analysis (PCA)
- Unsupervised learning techniques (e.g. clustering)
- Interactive dashboards and geospatial visualization (Looker Studio)

---

## Project Objective

The main objective is to **assess relative territorial risk exposure** of geographic locations by combining:

- Environmental sensitivity (protected areas – WDPA)
- Geodynamic and seismic context (USGS)
- Type of on-site activity (contextual risk factor)

The final vision is a framework where **a geographic coordinate can be evaluated in terms of territorial risk**, enabling comparison across regions, activities, and environmental contexts.

---

## Data Source: INSQUI

The base dataset originates from **INSQUI**, using **reported and publicly available data up to 2025**.

INSQUI data provides the **geographic reference of company locations** (coordinates and activity type), which serves as the foundation for all subsequent spatial and contextual enrichment performed in this project.

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

This structure allows the analysis to scale to **hundreds or thousands of locations**, while remaining computationally simple and reproducible.

---

## External Data Sources

### USGS – Seismic and Geodynamic Data

Open datasets from the **United States Geological Survey (USGS)** are used to characterize the **seismic and geodynamic context** of each coordinate, such as:

- Historical seismic activity
- Spatial distribution of seismic events
- Relative seismic exposure of geographic zones

The objective is **territorial context characterization**, not short-term earthquake prediction.

---

### WDPA – World Database on Protected Areas

The **World Database on Protected Areas (WDPA)** is used to determine:

- Whether a location lies **inside a protected area**
- Or its **proximity to environmentally protected zones**

This adds a critical **environmental sensitivity dimension**, relevant for:

- Territorial and environmental risk assessment
- Impact analysis
- Regulatory and land-use planning context

---

## Methodology

General workflow implemented in the project:

1. Load and validate INSQUI coordinate data
2. Spatial visualization of company locations
3. Integration of seismic context using USGS data
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
- Seismic and geodynamic context indicators per coordinate
- Environmental protection indicators (WDPA-based)
- A clean analytical dataset ready for:
  - PCA
  - Unsupervised machine learning
  - Business intelligence and visualization tools

---

## Scope & Limitations

### Included

- Coordinate-based territorial analysis
- Public and open data sources (INSQUI, USGS, WDPA)
- Exploratory and comparative analytical approach

### Not Included (yet)

- Chemical inventory or hazard-specific modeling
- Event-level prediction models
- Socioeconomic vulnerability indicators (e.g. DANE)
- Climate trend or extreme weather modeling

---

## Future Extensions

Potential future developments include:

- Construction of a **Composite Territorial Risk Index**
- Integration with socioeconomic vulnerability indicators
- Climate and extreme weather layers
- Automated territorial risk scoring per coordinate
- Decision-support dashboards for SST, inspection, or planning

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

This project uses **open public data sources** (USGS, WDPA) combined with **publicly reported INSQUI data (up to 2025)**.

Methodologies, transformations, and derived datasets are intended for **analytical, research, and exploratory purposes**.
