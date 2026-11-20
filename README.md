# CERRA Reanalysis for Snow Load Characteristic Values in Italy

This repository contains Python scripts and workflows for processing high-resolution meteorological reanalysis data and estimating characteristic snow load values across Italy.

The main objective is to investigate the spatial and temporal distribution of snow loads using updated reanalysis datasets, providing an alternative and complementary source of information to conventional approaches based on historical ground-based observations.

The resulting estimates are intended to support the assessment and updating of characteristic ground snow loads for structural design applications in Italy.

## Research Objective

The repository focuses on the estimation of characteristic ground snow loads across the Italian territory using meteorological reanalysis data.

In particular, the workflow aims to:

- Retrieve updated meteorological reanalysis data covering Italy.
- Extract and process the variable snow depth water equivalent.
- Reconstruct snow load time series at the spatial and temporal resolution of the reanalysis dataset.
- Identify seasonal maximum snow loads (from November to May).
- Perform statistical analyses of extreme snow load values, based on Extreme Value Theory.
- Estimate characteristic snow loads for structural design.
- Investigate the spatial variability of Gumbel parameters of snow loads across Italy.
- Produce spatially distributed estimates suitable for comparison with existing regulatory maps and reference values.

The approach aims to exploit the spatial continuity and temporal consistency of reanalysis datasets to investigate snow load distributions beyond the limitations associated with the availability and geographical coverage of conventional weather stations.

## Data Source

The meteorological data are obtained from the **Copernicus European Regional ReAnalysis (CERRA)** dataset, provided by the Copernicus Climate Change Service (C3S).

CERRA is a high-resolution regional atmospheric reanalysis covering Europe. It combines numerical weather prediction modelling and observational data assimilation to provide spatially and temporally consistent reconstructions of past atmospheric conditions.

Official resources:

- [Copernicus Climate Data Store](https://cds.climate.copernicus.eu/)
- [CERRA – Reanalysis: Single Levels](https://cds.climate.copernicus.eu/datasets/reanalysis-cerra-single-levels?tab=overview)

The selected reanalysis products and variables are chosen according to their suitability for snow load estimation.

## Methodology and Workflow

The analysis is organised into the following main stages.

### 1. Reanalysis Data Acquisition

Meteorological data are retrieved from the Copernicus Climate Data Store using Earthkit and the CDS API.

Data requests are configured according to the selected variables, temporal coverage, spatial domain, and temporal resolution.

### 2. Snow Variable Processing

The downloaded datasets are processed to obtain the snow-related quantities required for the estimation of ground snow loads.

### 3. Snow Load Time Series Reconstruction

The variable is processed to reconstruct snow load time series over the Italian territory.

The resulting time series provide the basis for identifying seasonal maximum values at each reanalysis grid point.

### 4. Extreme Value Analysis

Extreme snow load values are investigated through statistical analysis of the reconstructed time series.

The analysis aims to estimate characteristic values associated with the reference return period adopted for structural design.

### 5. Spatial Analysis and Mapping

The estimated characteristic snow load values are analysed across the Italian territory to investigate their spatial variability.

The resulting spatial datasets can be used to:

- Generate maps of characteristic ground snow loads.
- Identify regional patterns and spatial gradients.
- Compare reanalysis-based estimates with existing Italian regulatory provisions.
- Investigate potential differences between conventional and reanalysis-based approaches.

## Repository Structure

```text
Reanalysis_Copernicus/
│
├── CERRA/
│   └── Scripts and notebooks for data acquisition,
│       processing and snow load analysis
│
├── .gitattributes
└── README.md
```

## Requirements

The workflows are developed in Python and rely on scientific computing and meteorological data processing libraries.

The main packages include:

- `numpy` – numerical computations.
- `pandas` – data manipulation and statistical analysis.
- `xarray` – multidimensional meteorological datasets.
- `dask` – parallel and out-of-core data processing.
- `matplotlib` – data visualisation.
- `earthkit-data` – meteorological data access and processing.
- `eccodes` – GRIB data handling.
- `netCDF4` – NetCDF data access.

Additional dependencies may be required depending on the specific script or notebook.

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/costanza485/Reanalysis_Copernicus.git
```

### 2. Set up the Python environment

Create and activate a Python environment:

```bash
conda create -n cerra python=3.11
conda activate cerra
```

Install the required dependencies for the selected workflow.

### 3. Configure Copernicus CDS access

A Copernicus Climate Data Store account is required to retrieve the reanalysis data.

Configure the CDS API credentials according to the official instructions:

[Copernicus CDS API documentation](https://cds.climate.copernicus.eu/how-to-api)

**Important:** API credentials must be stored locally and must never be committed to the repository.

### 4. Run the analysis

Navigate to the relevant directory and execute the Python scripts or notebooks.

Data requests, input paths, output directories, and processing parameters may need to be adapted to the user's environment.

## Data Management

Reanalysis datasets can require substantial storage and computational resources.

Raw data, intermediate files, and generated outputs should generally be stored locally rather than committed to the Git repository.

## Scientific Scope and Limitations

Reanalysis-based snow load estimates depend on the accuracy and spatial resolution of the underlying meteorological products, the conversion of snow-related variables into ground snow loads, and the statistical methods adopted for extreme value estimation.

The resulting characteristic values should therefore be interpreted considering the assumptions and limitations of the reanalysis products and the adopted statistical framework.

Comparisons with ground-based observations and existing regulatory values are important for assessing the reliability and applicability of the estimates.

## Data Acknowledgement

CERRA data are provided by the Copernicus Climate Change Service (C3S) and the European Centre for Medium-Range Weather Forecasts (ECMWF).

Users should acknowledge the original data providers and comply with the applicable dataset licence and citation requirements.

## Author

**Costanza Guarducci**

PhD Candidate in Civil and Environmental Engineering

- Department of Civil and Industrial Engineering (DICI), University of Pisa (UNIPI), Italy
- Escuela Técnica Superior de Ingeniería de Caminos, Canales y Puertos, University of Granada (UGR), Spain

Research activities focus on climate-related actions affecting structural reliability, with particular emphasis on snow loads and their spatial and temporal variability in Italy.

**Repository:** [Reanalysis_Copernicus](https://github.com/costanza485/Reanalysis_Copernicus)