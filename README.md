# GEE Water Quality ML Pipeline

An automated Google Earth Engine (GEE) and machine-learning workflow for estimating and mapping freshwater water-quality parameters using Landsat imagery and in-situ observations.

## Overview

This repository contains a reproducible Google Colab workflow developed for satellite-based monitoring of freshwater water quality. The pipeline integrates in-situ water-quality observations with Landsat imagery accessed through Google Earth Engine, performs satellite–field matchup, spectral feature engineering and selection, Random Forest model development and evaluation, and spatio-temporal prediction and mapping.

The current implementation was developed and evaluated using lakes in New York State, USA, and is designed so that the workflow can be adapted to other study areas and datasets.

## Workflow

The notebook includes the following major components:

1. **In-situ data preparation and exploration**
2. **Landsat spectral extraction**
3. **Satellite–field matchup**
4. **Feature engineering and selection**
5. **Random Forest model development and evaluation**
6. **Spatio-temporal water-quality mapping**
7. **Visualization and output products**

The modelling workflow includes training-only feature selection, Random Forest hyperparameter optimization, and repeated Monte Carlo train/test evaluation.

## Current Implementation

The current notebook supports:

* Landsat 8 and Landsat 9 imagery
* Top-of-atmosphere (TOA) and surface reflectance (SR) products
* Google Earth Engine-based image access and spectral extraction
* Configurable 3 × 3, 5 × 5, and 7 × 7 pixel sampling windows
* Satellite–field temporal matchup
* Automated spectral feature generation and selection
* Random Forest regression
* Monte Carlo model evaluation
* Spatial prediction from Landsat imagery
* Spatio-temporal water-quality mapping

The current study evaluates Secchi disk depth (SDD) and chlorophyll-a (Chl-a).

## Notebook

The complete workflow is provided as a Google Colab-compatible Jupyter notebook:

`GEE_Water_Quality_ML_Pipeline.ipynb`

The notebook is organized sequentially and is intended to be run from top to bottom.

## Requirements

The workflow is designed primarily for **Google Colab** and requires:

* A Google account
* Access to Google Drive
* A Google Earth Engine account and Cloud Project
* Python 3
* Internet access for Google Earth Engine operations

Required Python packages are installed or imported within the notebook.

## Input Data

### In-situ Water-Quality Data

The current implementation uses in-situ water-quality observations from the **Citizens Statewide Lake Assessment Program (CSLAP)** administered by the New York State Department of Environmental Conservation (NYSDEC).

CSLAP and other New York State water-quality monitoring data can be accessed through the **NYSDEC Division of Water Monitoring Data Portal**:

**NYSDEC Water Quality Data:**
https://dec.ny.gov/environmental-protection/water/water-quality/monitoring/water-quality-data 


Users should download and prepare the required in-situ observations according to the input structure used in the notebook.

### Lake Boundary Data

Lake polygons used for spatial processing and water-quality mapping can be obtained from the **New York State Hydrography Dataset** provided by NYS ITS Geospatial Services.

**New York State Hydrography:**
https://gis.ny.gov/hydrography 


The Hydrography Waterbody dataset contains polygon representations of surface-water features, including lakes and ponds. Users applying the workflow outside New York State may substitute an appropriate lake or waterbody polygon dataset for their study area.

### Satellite Data

Landsat imagery is accessed directly through **Google Earth Engine** and therefore does not need to be downloaded manually before running the spectral-extraction workflow.

Large input datasets and generated satellite imagery are not stored directly in this repository.

## Running the Workflow

1. Open the notebook in Google Colab.
2. Mount Google Drive.
3. Authenticate Google Earth Engine using your own Earth Engine-enabled Google Cloud Project.
4. Configure the input/output directories and user-adjustable settings in the notebook.
5. Provide the required in-situ and spatial input data.
6. Run the notebook sequentially from top to bottom.

Some Google Earth Engine export operations run asynchronously. Where applicable, allow the exports to finish before running subsequent cells that use the exported files.

## Outputs

Depending on the selected configuration, the workflow generates outputs including:

* Processed satellite–field matchup datasets
* Selected spectral features
* Model evaluation metrics
* Monte Carlo evaluation results
* Final Random Forest model configuration
* Predicted water-quality rasters
* Spatio-temporal maps
* Monthly prediction summaries
* Supporting figures and tables

## Associated Publication

This repository accompanies the manuscript:

**“A GEE-based automated machine learning pipeline for estimation and spatio-temporal mapping of water quality for freshwater lakes: A multi-lake evaluation in New York, USA.”**

Publication details will be added following publication.

## Citation

If you use or adapt this workflow, please cite the associated publication.

A formal citation and DOI will be added to this repository when available.

## Author

**Rabia Munsaf Khan**

SUNY College of Environmental Science and Forestry (SUNY-ESF)

For questions, bug reports, or suggestions, please use the GitHub Issues section of this repository.

## License

License information will be added to this repository.
