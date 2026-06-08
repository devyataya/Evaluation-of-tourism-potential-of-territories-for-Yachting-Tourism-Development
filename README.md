### Coastal Yachting Tourism Potential Assessment

This project is a Python-based geospatial tool for assessing the tourism potential of coastal territories for yachting development. It combines open geodata, coastal morphology, service accessibility, and bathymetric analysis to produce a comparable territorial score.

## Overview

The script analyzes a selected coastal city or territory and extracts key indicators from open sources such as OpenStreetMap and bathymetric datasets. It identifies marinas, coastline length, nearby infrastructure, tourist objects, islands, protected areas, and depth suitability for yacht access.

The workflow is designed to support marina location planning, yachting route analysis, and territorial comparison across coastal regions.

## Main Features

- Loads and processes coastal geodata from OpenStreetMap.
- Builds coastal buffers for spatial analysis.
- Detects marinas, islands, marine reserves, and tourist infrastructure.
- Calculates coastal length and service accessibility indicators.
- Extracts and analyzes bathymetry from a GEBCO dataset.
- Generates a map with layers for coastal features and bathymetry.
- Stores intermediate results and city parameters in persistent Google Drive folders.
- Supports repeatable analysis through caching.

## Data Sources

- OpenStreetMap.
- GEBCO bathymetric data.
- Google Drive storage for cached outputs and parameters.

## Core Logic

The script includes two main classes:

### `DataHandler`
Handles data acquisition, coastline detection, feature extraction, buffering, caching, and saving/loading geodata.

### `CityAnalyzer`
Calculates derived indicators such as coastal length, infrastructure counts, water area, and tourist object proximity.

## Bathymetry Processing

The code extracts a bathymetric subset around the selected city, checks whether the city is covered by the dataset, and calculates the mean depth in meters. This value is then added to the city parameters and can be used in further scoring.

## Output

The script produces:

- coastal feature datasets,
- a city-level indicator table,
- bathymetric statistics,
- a map visualization,
- cached JSON files with parameters,
- a CSV ranking file for final scores.

## Requirements

Recommended Python packages:

- `osmnx`
- `geopandas`
- `pandas`
- `numpy`
- `matplotlib`
- `shapely`
- `folium`
- `xarray`
- `rasterio`
- `contextily`
- `cdsapi`

## Usage

1. Run the script in Google Colab.
2. Mount Google Drive.
3. Enter the desired city name.
4. Wait for geodata extraction and analysis.
5. Review the calculated indicators and map outputs.

## Notes

- The script is optimized for Colab and Google Drive storage.
- Cached results speed up repeated runs.
- Bathymetry coverage depends on the spatial extent of the GEBCO dataset.

## Purpose

The project is intended for research and planning tasks related to coastal and yachting tourism development. It provides a structured way to compare territories using open geospatial data and simple, reproducible analytical steps.

