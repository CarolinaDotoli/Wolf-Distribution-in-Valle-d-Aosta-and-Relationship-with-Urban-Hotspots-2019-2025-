# 🐺 Human–Wolf Coexistence in Italy (2005–2025)

## Overview

This project explores the **relationship between human presence and wolf (*Canis lupus*) distribution in Italy** using open-access occurrence data from **GBIF** (Global Biodiversity Information Facility).  
The dataset covers the period **2005–2025**, integrating both **scientific records and citizen-science observations** from across the country.

The analysis aims to:
- Investigate how wolf occurrence varies across **Northern, Central, and Southern Italy**.
- Examine whether **human population density** correlates with the frequency of wolf observations.
- Visualize these patterns through maps and summary statistics produced with **QGIS** and, optionally, **R**.

---

## Objectives

1. **Assess the spatial distribution** of wolves in Italy from GBIF records.  
2. **Compare occurrence density** across macro-areas (North, Center, South).  
3. **Evaluate human–wolf coexistence** by relating observation frequency to human population density.  
4. Produce **visual and quantitative outputs** suitable for ecological interpretation and communication.

---

## Data Sources

### 1. Wolf occurrences
- **Source:** GBIF (Global Biodiversity Information Facility)  
- **Species:** *Canis lupus*  
- **Years considered:** 2005–2025  
- **Type of data:** Museum records, scientific surveys, and citizen-science reports (e.g. iNaturalist)  
- **Main cleaning steps:**
  - Removed non-wolf taxa (e.g. *Canis lupus familiaris*)  
  - Checked and standardized coordinates and taxonomic fields  
  - Removed duplicates and invalid records  
  - Added a column for **macro-area** (North, Central, South)  

### 2. Human population data
- **Source:** Publicly available demographic dataset (aggregated by age and sex)  
- Data were **summed to obtain total resident population per region**, ensuring comparability with the GBIF records.

---

## Methodology

### 1. Data Cleaning
Data were cleaned and standardized manually in **Excel**, following the steps above.  
The cleaned dataset was then saved as CSV and imported into **QGIS** for spatial analysis.

### 2. Mapping in QGIS
- Loaded **regional shapefiles of Italy** as base layers.  
- Imported wolf occurrence points from GBIF.  
- Added population data to the same spatial framework.  
- Grouped observations by macro-area (North, Central, South).  
- Created density maps and visual overlays showing wolf occurrences vs. population distribution.

### 3. (Optional) Quantitative Analysis
Future extensions of this project may include:
- Computing wolf occurrences per 1,000 inhabitants per macro-area.  
- Evaluating temporal trends in wolf reports over the 2005–2025 period.  
- Statistical tests in **R** to quantify correlation between human density and observation frequency.



---

## Macro-area Definitions

| Macro-area | Regions included |
|-------------|------------------|
| **North**   | Valle d’Aosta, Piemonte, Liguria, Lombardia, Trentino-Alto Adige, Veneto, Friuli-Venezia Giulia, Emilia-Romagna |
| **Central** | Toscana, Umbria, Marche, Lazio, Abruzzo |
| **South**   | Campania, Molise, Puglia, Basilicata, Calabria, Sicilia, Sardegna |

---

## Tools

- **QGIS** — mapping and spatial analysis  
- **Excel** — data cleaning and organization  
- **R** *(optional)* — for correlation tests or further analyses  

---

## Author

**Maria Carolina Dotoli**  
Master’s degree in Environmental and Natural Sciences  
Focus: Ecology, biodiversity, and human–wildlife interactions  

---

## License and Data Use

- All data used are **open-access** and **non-restricted**.  
- GBIF records are cited with their official DOI.  

---

