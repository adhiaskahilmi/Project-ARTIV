# ARTIV — Multi-Criteria Evaluation of Exploration Zones (EZ) Within NASA's Nine Candidate Landing Regions for Artemis IV
This repository contains the multi-criteria decision-making (MCDM) framework used to evaluate and rank NASA's nine candidate lunar south pole landing regions for the Artemis IV surface mission. It utilizes a landing-spot-centered Exploration Zone (EZ) selection algorithm combined with CRITIC-weighted TOPSIS.

The extended abstract is published on Zenodo: https://doi.org/10.5281/zenodo.21431608


## Overview
NASA identified nine candidate landing regions near the lunar south pole, each spanning between 255 and 4,429 km². Because the operational footprint of a single landing mission is much smaller, this project develops a spatially explicit framework to identify the optimal 2 km-radius Exploration Zone within each region.

The evaluation relies on four operational criteria derived from NASA safety and mission planning requirements:
1) Slope compliance (flat landing spot and accessible terrain)
2) Solar illumination thresholds
3) Direct-to-Earth (DTE) communication visibility
4) Permanently Shadowed Region (PSR) accessibility, including the hydrogen abundance for water-ice resource potential


## Methodology
Landing spot search: Identifying 100x100m grid cells with safe slope characteristics.

EZ construction: Creating a 2km-radius circular zone around each valid spot.

Multi-criteria filter: Applying thresholds for slope, illumination, and DTE.

PSR optimization: Using a mini-TOPSIS framework to evaluate accessible PSR pixels based on proximity and hydrogen abundance.

Site-level ranking: Applying CRITIC-TOPSIS across all nine regions.


## Data Sources
All datasets are publicly available from NASA PGDA, NASA PDS, and LROC QuickMap:

• Topography (slope, elevation): LOLA, NASA PGDA (40 m/px)

• Solar illumination: LOLA illumination model (120 m/px)

• Direct-to-Earth visibility: LOLA Earth-visibility model (120 m/px)

• Permanently Shadowed Regions: LPSR product (20 m/px)

• Hydrogen abundance: Lunar Prospector Neutron Spectrometer (0.5° bins)

Raw data files are excluded from this repository due to size. Download instructions can be found inside the scripts folder.


## Repository Structure
02_scripts/: Jupyter notebooks containing the full analysis pipeline from data extraction to final site ranking.

tableau/: Tableau workbook (.twbx) containing the interactive geospatial dashboard.

quickmap-lroc.png: Reference basemap used for site visualization.


## Key Results
Seven of the nine candidate regions satisfied all operational criteria. "Mons Mouton Plateau" ranked highest due to superior solar exposure and DTE visibility. "Haworth" ranked second, offering the highest localized hydrogen abundance but with reduced DTE coverage. "Peak near Cabeus B" and "Slater Plain" failed the initial safety filters and were excluded from the final compliant ranking.


## Tech Stack
Python (rasterio, numpy, pandas, scipy, shapely, matplotlib, ...)

Tableau (interactive geospatial dashboard)


## Citation
Hilmiyanda, M. A. (2026). Multi-Criteria Evaluation of Exploration Zones (EZ) within NASA's Nine Candidate Landing Regions for Artemis IV. Zenodo. https://doi.org/10.5281/zenodo.21431608

## Author
Muhammad Adhiaska Hilmiyanda

adhiaska04@gmail.com
