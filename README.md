# Territorial Risk Analysis using Geospatial Data  
## INSQUI – Exploratory Territorial Risk Analysis Project

---

## Overview

This project develops an **exploratory territorial risk analysis** for company locations in Colombia using **minimal geospatial input data**: type of on-site activity and geographic coordinates.

It integrates **open climate, geodynamic, and socioeconomic datasets** to characterize the **risk context of the territory** where industrial and service activities operate.

The approach deliberately avoids confidential or operational data (e.g. inventories, quantities, processes), focusing instead on **territorial-scale drivers of risk** that are often overlooked in traditional SST and process safety analyses.

The resulting dataset supports:

- Exploratory multivariate analysis (PCA)
- Construction of composite territorial indices
- Geospatial visualization and decision-support dashboards

---

## Project Motivation

In Occupational Safety (SST) and Process Safety, risk analysis is usually centered on:

- people  
- substances  
- equipment  
- installations  

However, **the territorial context where these systems are located is often treated as a background variable**, despite strongly influencing hazard intensity, exposure patterns, and potential impact.

This project is built on a simple but critical premise:

**Risk does not start at the plant; it starts in the territory.**

---

## Conceptual Risk Framework

The project follows a classical and widely accepted formulation:

**Risk = Threat × Vulnerability × Exposure**

Rather than estimating absolute risk values, the objective is to **characterize and compare territorial risk conditions** using publicly available data.

Each component is addressed independently and later integrated.

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

Vulnerability represents the **susceptibility of a territory to suffer adverse impacts** when a hazardous event occurs, shaped by social, economic, and structural conditions.

In this project, Vulnerability is characterized using **open socioeconomic data from DANE**, including indicators related to:

- population characteristics  
- basic living conditions  
- territorial socioeconomic structure  

This component reflects **structural conditions that influence impact severity**, not the presence of hazards themselves.

---

### Exposure (Exposición)

Exposure represents the **presence of activities and assets that may be affected** by hazardous events.

In this project, Exposure is characterized using **INSQUI data**, specifically:

- geographic location of reported sites  
- type of on-site activity  

This component captures **where industrial and service activities are distributed across the territory**.

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

| Column         | Description |
|----------------|-------------|
| tipo_actividad | Type of site activity (administrative, operational, storage, etc.) |
| latitud        | Latitude |
| longitud       | Longitude |

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

Open datasets from **DANE** are used to characterize **territorial vulnerability**, using demographic and socioeconomic indicators at municipal or regional level.

These indicators provide context on **structural conditions influencing potential impact**, complementing the hazard-focused threat component.

---

## Methodology Summary

The methodological workflow implemented so far includes:

1. Spatial validation and visualization of INSQUI locations  
2. Climate hazard modeling using NASA data and PCA (5 components)  
3. Seismic hazard modeling using USGS data and PCA (3 components)  
4. Construction of a **Territorial Threat Index**, combining climate and seismic patterns  
5. Integration of socioeconomic vulnerability indicators (DANE)  
6. Preparation of an integrated analytical dataset for visualization and comparison  

---

## Territorial Threat Classification

The Territorial Threat Index is summarized into five interpretable categories:

- Amenaza por clima variable  
- Amenaza por clima húmedo  
- Amenaza por sismos  
- Amenaza por clima extremo  
- Amenaza alta combinada  

These categories allow **comparative interpretation of territorial hazard conditions**, not absolute risk estimation.

---

## Dashboard and Visualization

An interactive dashboard has been developed to visualize the results of the analysis:

🔗 **Looker Studio Dashboard**  
https://lookerstudio.google.com/reporting/cc88e672-a7d1-4737-ab51-68913ea8b533

The dashboard enables:

- visualization of company locations across the territory  
- exploration of climate and seismic threat patterns  
- comparison of territorial conditions across regions  
- integration of multiple analytical layers in a single interface  

The dashboard is intended as a **decision-support and exploratory tool**, not a compliance report.

---

## Current Outputs

At the current stage, the project delivers:

- Geospatial mapping of INSQUI-reported locations  
- Climate threat components (5 PCA-based dimensions)  
- Seismic threat components (3 PCA-based dimensions)  
- Territorial threat classification  
- Socioeconomic vulnerability context  
- Interactive dashboard for exploration and communication  

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

## Final Risk Perspective

The current stage of the project provides a **territorial-level risk perspective**, where:

- **Threat** is characterized through climate and seismic hazards  
- **Vulnerability** is represented by socioeconomic territorial conditions  
- **Exposure** is defined by the spatial distribution of reported activities  

This framework establishes a **structured foundation for future risk integration**, where Threat × Vulnerability × Exposure can be combined into a comprehensive Territorial Risk Index.

---

## Future Extensions

Planned next steps include:

- Explicit integration of Threat, Vulnerability, and Exposure into a single index  
- Temporal analysis of risk evolution  
- Refinement of exposure metrics  
- Decision-support dashboards for SST and process safety applications  

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
