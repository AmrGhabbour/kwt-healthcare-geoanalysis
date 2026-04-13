# Kuwait Pharmacies Accessibility Analysis 🇰🇼💊

## Project Overview
This project evaluates the accessibility and spatial distribution of pharmacies across the State of Kuwait. By integrating real-time OpenStreetMap (OSM) data with high-resolution population grids and official neighborhood boundaries, the analysis identifies "Pharmacy Deserts"—densely populated areas that lack adequate access to essential pharmaceutical services.

## Core Objectives
* **Geospatial Retrieval**: Extracting pharmacy and commercial facility data using the OSMnx API.
* **Accessibility Modeling**: Defining service coverage zones using 1km buffers to pinpoint geographic gaps.
* **Demographic Correlation**: Linking pharmacy density with population data to find underserved communities.
* **Market Intelligence**: Analyzing the distribution of other commercial amenities (Cafes, Banks, Supermarkets) to identify high-traffic business hubs.

## Datasets Used
* **OpenStreetMap (via OSMnx)**: Locations for pharmacies, chemists, and commercial facilities.
* **PACI Neighborhoods (2023)**: Official Kuwaiti neighborhood boundaries.
* **Kontur Population Grid (2023)**: 400m resolution population data.
* **Local Shapefiles**: Healthcare facility points, governorate boundaries, and road networks.

## Project Workflow

### 1. Data Acquisition & Processing
* Retrieval of pharmacies across Kuwait using specific OSM tags (`amenity`, `healthcare`, `shop`).
* Standardizing Coordinate Reference Systems (CRS) to **UTM Zone 39N (EPSG:32639)** for precise metric-based distance calculations.
* Filtering geometries to focus specifically on 'Point' data for accurate marker placement.

### 2. Spatial Analysis
* **Neighborhood Aggregation**: Performing spatial joins to count the number of pharmacies within each PACI neighborhood.
* **Coverage Mapping**: Generating a 1km "Service Area" (buffer) around every pharmacy.
* **Desert Identification**: Identifying population grid cells with >5,000 residents that sit outside the 1km service range.

### 3. Metric Calculation & Insights
* **Pop-to-Pharmacy Ratio**: Calculating the ratio of residents per pharmacy in each neighborhood.
* **Commercial Hotspots**: Analyzing brand frequency (e.g., Starbucks, Caribou Coffee) to identify areas with high commercial activity but potentially low pharmacy coverage.

## Key Findings
* Identification of neighborhoods where the **population-to-pharmacy ratio exceeds 10,000:1**.
* Mapping of "High-Density Deserts"—residential zones with significant populations but zero pharmacy coverage within a 10-minute walk (1km).

## Tech Stack
* **Language**: Python
* **Libraries**: 
    * `Geopandas`: Spatial data manipulation.
    * `OSMnx`: OpenStreetMap data retrieval.
    * `Folium`: Interactive map generation.
    * `Numpy` & `Pandas`: Statistical analysis and data cleaning.

---
*Created as part of the Kuwait Pharmacies Geospatial Project.*
