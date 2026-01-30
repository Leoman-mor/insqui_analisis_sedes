# Territorial Risk Analysis using Geospatial Data  
## INSQUI – Exploratory Territorial Risk Analysis Project

---

## Overview

This project develops an **exploratory territorial risk analysis** for company locations in Colombia using **minimal geospatial input data**: type of on-site activity and geographic coordinates.

It integrates **open climate, geodynamic, and socioeconomic datasets** to characterize the **risk context of the territory** where industrial and service activities operate.

The approach deliberately avoids confidential or operational data (e.g. inventories, quantities, processes), focusing instead on **territorial-scale drivers of risk**.

The resulting dataset is designed to support:

- Exploratory multivariate analysis (PCA)
- Construction of composite territorial indices
- Geospatial visualization and dashboards (Looker Studio)

---

## Conceptual Risk Framework

The project follows a classical and widely accepted formulation:

**Risk = Threat × Vulnerability × Exposure**

Rather than estimating absolute risk values, the objective is to **compare and characterize territorial risk patterns** across locations using publicly available data.

Each component of the equation is addressed explicitly.

---

## Risk Components in This Project

### Threat (Amenaza)

Threat represents the **presence and intensity of potentially damaging natural phenomena** affecting a territory.

In this project, Threat is characterized using:

- **Climate-related hazards** derived from NASA data  
- **Seismic and geodynamic hazards** derived from USGS data  

This component captures **natural hazard pressure at the territorial level**, without attempting event-level prediction.

---

### Vulnerability (Vulnerabilidad)

Vulnerability represents the **susceptibility of the territory to suffer adverse impacts** when a hazardous event occurs, shaped by social, economic, and infrastructural conditions.

In this project, Vulnerability is characterized using **DANE data**, including indicators related to:

- population distribution  
- basic needs and living conditions  
- territorial and socioeconomic characteristics at municipal or regional scale  

This component reflects **structural and social conditions that influence impact severity**, not environmental protection status.

---

### Exposure (Exposición)

Exposure represents the **presence of activities and assets that may be affected** by hazardous events.

In this project, Exposure is characterized using **INSQUI data**, specifically:

- geographic location of reported sites  
- type of on-site activity (administrative, operational, storage, etc.)  

This component captures **where industrial and service activities are located within the territory**.

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
| tipo_actividad   | Type of site activity (administrative, operational, storage, etc.) |
| latitud          | Latitude |
| longitud         | Longitude |

This structure allows the analysis to scale to **hundreds or thousands of locations**, while remaining reproducible.

---

## External Data Sources

### NASA – Climate Hazard Context

NASA open datasets are used to characterize **climate-related territorial threats**, such as:

- temperature variability  
- precipitation patterns  
- indicators of extreme climate behavior  

Climate variables are synthesized using **Principal Component Analysis (PCA)**.

Five principal components were selected, representing dominant climate threat patterns.

---

### USGS – Seismic and Geodynamic Hazard Context

USGS open datasets are used to characterize **seismic and geodynamic threats**, including:

- frequency of seismic events  
- magnitude-related indicators  
- spatial proximity to seismic activity  

Seismic variables are synthesized using **PCA**, with three principal components retained.

---

### DANE – Socioeconomic Vulnerability Context

Open datasets from **DANE** are used to characterize **territorial vulnerability**, including demographic and socioeconomic indicators at municipal or regional level.

These indicators provide context on **structural conditions influencing potential impact**, complementing the hazard-focused threat component.

---

## Methodology

### Threat Modeling

**Climate Threat (NASA)**  
- Extraction of climate indicators per coordinate  
- Standardization of variables  
- PCA application  
- Selection of five principal components  

**Seismic Threat (USGS)**  
- Extraction of seismic indicators around each coordinate  
- Construction of seismic metrics  
- Standardization of variables  
- PCA application  
- Selection of three principal components  

Climate and seismic components are combined to construct a **Territorial Threat Index**, summarized into five interpretable categories:

- Amenaza por clima variable  
- Amenaza por clima húmedo  
- Amenaza por sismos  
- Amenaza por clima extremo  
- Amenaza alta combinada  

---

### Vulnerability Modeling (DANE)

- Selection of socioeconomic and demographic indicators  
- Spatial linkage between DANE data and company locations  
- Construction of vulnerability indicators at territorial scale  

---

### Exposure Modeling (INSQUI)

- Spatial distribution of reported sites  
- Classification by type of activity  
- Aggregation and density analysis (planned)

---

## Current Outputs

At the current stage, the project delivers:

- Geospatial mapping of INSQUI-reported locations  
- Climate threat components (5 PCA-based dimensions)  
- Seismic threat components (3 PCA-based dimensions)  
- Territorial threat classification  
- Integrated dataset ready for:
  - multivariate analysis  
  - clustering  
  - visualization  

---

## Scope & Limitations

### Included

- Territorial-scale threat modeling  
- Socioeconomic vulnerability context  
- Public and open data sources (INSQUI, NASA, USGS, DANE)  
- Exploratory and comparative analysis  

### Not Included (yet)

- Chemical inventory or process-level hazard modeling  
- Event-level prediction models  
- Dynamic exposure modeling  
- Full quantitative risk estimation  

---

## Future Extensions

Planned next steps include:

- Construction of a full **Territorial Risk Index**  
- Integration of threat, vulnerability, and exposure into a single framework  
- Temporal analysis of risk evolution  
- Decision-support dashboards for SST and process safety  

---

## Visualization

The visualization layer focuses on:

- spatial distribution of threat and vulnerability  
- comparison across regions and activity types  
- aggregated territorial risk patterns  

Dashboards are designed using **Looker Studio**.

---

## Author

**Leonardo Guzmán**  
Chemical Engineer  
Occupational Safety & Chemical Risk Consultant  
MSc Student – Data Analytics & Intelligence  

---

## License

This project uses **open public data sources** (INSQUI – reported data up to 2025, NASA, USGS, DANE).

All methodologies, transformations, and derived datasets are intended for **analytical, research, and exploratory purposes**.
