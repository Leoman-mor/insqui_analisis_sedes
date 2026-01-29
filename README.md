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

## Conceptual Risk Framework

This project is guided by a classical and widely used risk formulation:

> **Risk = Threat × Vulnerability × Exposure**

Rather than estimating absolute risk values, the objective is to **characterize and compare territorial risk conditions** using publicly available data.

Each component of the equation is addressed as follows.

---

## Risk Components Mapping

### Threat (Amenaza)

Represents the presence and intensity of **potential hazardous phenomena** affecting a geographic location.

In this project, *Threat* is represented by:

- **Seismic and geodynamic context** derived from **USGS** data  
  - historical seismic activity  
  - spatial distribution of seismic events  
  - relative seismic exposure around each coordinate  

This component captures **natural hazard pressure at the territorial level**, without attempting event prediction.

---

### Vulnerability (Vulnerabilidad)

Represents the **sensitivity of the territory** to potential impacts once a hazardous event occurs.

In this project, *Vulnerability* is represented by:

- **Environmental sensitivity indicators** derived from **WDPA**  
  - presence of protected areas  
  - proximity to environmentally sensitive zones  

This component reflects **potential environmental impact and regulatory sensitivity** associated with the location.

---

### Exposure (Exposición)

Represents the **presence of activities, assets, or systems** that may be affected by a hazardous event.

In this project, *Exposure* is represented by:

- **INSQUI-reported company locations**
- **Type of on-site activity** (administrative, operational, storage, etc.)

This component captures **where and how human and industrial activities are distributed across the territory**.

---

## Project Motivation

In Occupational Safety (SST) and Process Safety, risk analysis is usually centered on:

- people  
- substances  
- equipment  
- installations  

However, **the territorial context where these systems are located is often overlooked**, despite being a key factor influencing threat, vulnerability, and exposure.

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

Open datasets from the **United States Geological Survey (USGS)** are used to characterize the **seismic and geodynamic threat context** of each location.

---

### WDPA – World Database on Protected Areas

The **World Database on Protected Areas (WDPA)** is used to characterize **environmental vulnerability and sensitivity** associated with each coordinate.

---

## Methodology

General workflow implemented so far:

1. Load and validate INSQUI coordinate data  
2. Spatial visualization of company locations  
3. Integration of seismic threat context (USGS)  
4. Environmental vulnerability overlay (WDPA)  
5. Construction of territorial indicators  
6. Preparation of an analytical dataset ready for multivariate analysis  

Planned analytical steps:

- normalization and scaling  
- Principal Component Analysis (PCA)  
- unsupervised clustering  

---

## Current Outputs

At the current stage, the project delivers:

- Geospatial mapping of INSQUI-reported locations  
- Territorial threat indicators (USGS-based)  
- Environmental vulnerability indicators (WDPA-based)  
- Exposure indicators derived from activity type  
- A clean dataset ready for:
  - PCA  
  - clustering  
  - BI and geospatial visualization  

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
- Integration of socioeconomic vulnerability indicators
- Climate and extreme weather layers
- Automated territorial risk scoring per location
- Decision-support dashboards for SST and process safety

---

## Visualization

The visualization layer focuses on:

- interactive geospatial maps  
- spatial comparison of threat, vulnerability, and exposure  
- aggregated indicators by region and activity type  

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
