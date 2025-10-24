# Alpine Ibex Altitudinal Shift

## Project Overview
This repository contains the analysis pipeline for investigating altitudinal shifts of the Alpine ibex (*Capra ibex*) over time (1980–2024). The main goal is to assess whether the mean elevation of ibex observations has increased and to estimate the rate of change (m/year or m/decade).  

Key research questions:
- Is there a significant altitudinal shift over time?
- Does the rate of shift vary among Alpine massifs or countries?
- Are observed patterns robust to sampling bias and observational effort?

## Repository Structure
```plaintext
alp_ibex_altitudinal_shift/
├── data/
│   ├── raw/          # Raw data downloaded from GBIF
│   └── processed/    # Cleaned data with elevation
├── src/
│   ├── 1_download_gbif.py
│   ├── 2_clean_and_qc.py
│   ├── 3_extract_elevation.py
│   ├── 4_exploratory_analysis.py
│   ├── 5_statistical_models.py
│   ├── 6_bootstrap_and_sensitivity.py
│   └── 7_visualization.py
├── results/
│   ├── figures/      # Generated plots
│   └── tables/       # Generated tables
├── notebooks/        # Interactive notebooks for exploration
└── LICENSE

```

## Data
- **Raw data** are downloaded from GBIF using `1_download_gbif.py` and stored in `data/raw/`.
- **Processed data** are cleaned, filtered, and augmented with elevation and time-period information in `data/processed/`.

## Analysis Pipeline

1. **Data Download (`1_download_gbif.py`)**  
   Download occurrences filtered by coordinates, year ≥1980, and basis of record.

2. **Data Cleaning & QC (`2_clean_and_qc.py`)**  
   Remove unreliable records, duplicates, and points outside plausible geographic range. Add columns for decade and period. Optionally, calculate sampling effort proxies.

3. **Elevation Extraction (`3_extract_elevation.py`)**  
   Assign elevation to each occurrence either from GBIF or by extracting from DEM rasters (SRTM or Copernicus DEM).

4. **Exploratory Analysis (`4_exploratory_analysis.py`)**  
   Summary statistics, outlier detection, temporal and spatial distribution, maps, histograms, and boxplots per decade.

5. **Statistical Models (`5_statistical_models.py`)**  
   - Simple linear regression: `elevation ~ year`  
   - Models with covariates: `elevation ~ year + sampling_effort_proxy + coordinateUncertainty`  
   - Hierarchical models (GLMM): include random effects for massifs/regions  
   - Bayesian modeling (optional)

6. **Bootstrap & Sensitivity (`6_bootstrap_and_sensitivity.py`)**  
   Assess robustness via bootstrap resampling, spatial blocking, and sensitivity to coordinate uncertainty.

7. **Visualization (`7_visualization.py`)**  
   Generate final plots for temporal trends, boxplots, maps, and random effect visualizations.

## Requirements

**Python (recommended):**
- pandas, numpy, geopandas, rasterio, pyproj
- matplotlib, seaborn, statsmodels, scikit-learn
- pymc / bambi (optional for Bayesian models)
- pymer4 (optional, requires R)

**R (optional, especially for GLMMs):**
- tidyverse, sf, raster, lme4, mgcv, emmeans, broom.mixed  

## Outputs
All figures and tables are saved in the `results/` folder:  
- `results/figures/`: PNG/SVG plots  
- `results/tables/`: summary statistics and model outputs  

## Reproducibility
- All scripts are organized in sequential order in `src/`.  
- Each script can be executed independently, with clear inputs and outputs.  
- Metadata for data downloads and processing steps are stored to ensure reproducibility.  

## How to Run
1. Install required Python/R packages.  
2. Run scripts in order from `1_download_gbif.py` to `7_visualization.py`.  
3. Check outputs in the `results/` folder.  
4. Optionally, explore data interactively in `notebooks/`.  




