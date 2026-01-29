# Territorial Risk Analysis using Geospatial Data  
## INSQUI – Exploratory Territorial Threat Analysis Project

---

## Overview

This project performs an **exploratory territorial threat analysis** for company locations in Colombia using **minimal geospatial input data**: type of on-site activity and geographic coordinates.

It integrates **open climate and geodynamic datasets** to characterize the **hazard context of the territory** where industrial and service activities operate.

The approach deliberately avoids confidential or operational data (e.g. inventories, quantities, processes), focusing instead on **territorial threats as a first analytical layer** for risk-informed decision-making.

The resulting dataset is designed to support:

- Exploratory multivariate analysis (PCA)
- Construction of composite threat indices
- Geospatial visualization and dashboards (Looker Studio)

---

## Conceptual Risk Framework

This project is aligned with the classical risk formulation:

> **Risk = Threat × Vulnerability × Exposure**

At its current stage, the project focuses **exclusively on the Threat component**, understood as the **presence and intensity of potentially damaging natural phenomena** affecting a location.

Vulnerability and exposure are acknowledged as future extensions but are **not modeled yet**.

---

## Threat Definition in This Project

In this framework, **Threat (Amenaza)** represents **territorial hazard conditions**, independent of assets, inventories, or populations.

Threat is characterized through two main dimensions:

- **Climate-related threats** (NASA)
- **Seismic and geodynamic threats** (USGS)

---

## Data Source: INSQUI

The base dataset originates from **INSQUI – Inventario Nacional de Sustancias Químicas de Uso Industrial**, using **reported and publicly available data up to 2025**.

INSQUI provides the **geographic reference of company locations**, which serves as the backbone of the spatial analysis.

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

This structure allows the analysis to scale to **hundreds or thousands of locations** while remaining reproducible.

---

## External Data Sources

### NASA – Climate Hazard Context

NASA open datasets are used to characterize **climate-related territorial threats**, including:

- temperature variability  
- precipitation behavior  
- extreme climate indicators  

These variables are **not used directly**. Instead, they are synthesized using **Principal Component Analysis (PCA)**.

---

### USGS – Seismic and Geodynamic Hazard Context

USGS open datasets are used to characterize **seismic and geodynamic threats**, including:

- frequency of seismic events  
- magnitude-related indicators  
- spatial proximity to seismic activity  

These variables are also synthesized using **PCA**.

---

## Methodology

### Climate Threat Modeling (NASA)

1. Extraction of climate indicators per coordinate
2. Standardization of variables
3. Application of **PCA**
4. Selection of **5 principal components**, capturing the dominant climate variability patterns
5. Interpretation of components as climate threat dimensions

---

### Seismic Threat Modeling (USGS)

1. Extraction of seismic indicators around each coordinate
2. Construction of seismic metrics
3. Standardization of variables
4. Application of **PCA**
5. Selection of **3 principal components**, representing dominant seismic threat patterns

---

### Composite Territorial Threat Index

Climate and seismic components are combined to construct a **Territorial Threat Index**, summarized into five interpretable categories:

```python
map_amenaza = {
    0: "Amenaza por clima variable",
    1: "Amenaza por clima húmedo",
    2: "Amenaza por sismos",
    3: "Amenaza por clima extremo",
    4: "Amenaza alta combinada"
}
