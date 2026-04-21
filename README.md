# Week 9: Remote Sensing Analysis & Validation - ARIA v6.0

## Project Overview

This project implements the ARIA v6.0 (Auditor + Rater + Indicator + Advisor) framework for remote sensing change detection and validation. The case study focuses on the Matai'an Barrier Lake formation and drainage following Typhoon Colo in 2025, using Sentinel-2 satellite imagery for water detection and landslide mapping.

**Course**: Remote Sensing Analysis & Applications | National Taiwan University (NTU)  
**Instructor**: Prof. Su Wen-Ray (Su Wen-Ray)  
**Case Study**: Matai'an Barrier Lake (Typhoon Colo impact assessment)

## Project Structure

```
09_EX/
|
|-- data/                  # Geospatial validation data
|   |-- validation_points.geojson    # 60 field-corrected validation points
|
|-- outputs/               # Analysis results and visualizations
|   |-- W9_L1_difference_maps.png           # NDVI/NDWI change detection
|   |-- W9_L1_enhanced_threshold_analysis.png # Threshold sensitivity analysis
|   |-- W9_L2_masks.png                      # Water detection masks
|   |-- W9_L2_confidence_map.png             # 3-zone confidence mapping
|   |-- W9_L2_f1_threshold.png               # F1 score optimization
|   |-- W9_L3_validation_summary.png         # Validation results visualization
|   |-- AI_Advisor_Prompt_Template.txt       # AI advisor interface
|   |-- ARIA_v6_0_Disaster_Report.txt       # Comprehensive analysis report
|
|-- scripts/               # Analysis notebooks
|   |-- Week9-Student.ipynb    # Main analysis pipeline (ARIA v6.0)
|   |-- pre_lab.ipynb           # Preparatory exercises
|
|-- .env                   # Environment variables (API keys)
|-- .gitignore             # Git ignore rules
|-- README.md              # This file
|-- environment.yml        # Conda environment specification
|-- Pre-lab-Week9.md       # Laboratory instructions
```

## Environment Setup

This project uses the `geospatial` conda environment. To set up the environment:

```bash
# Create the conda environment (if not exists)
conda create -n geospatial python=3.9

# Activate the environment
conda activate geospatial

# Install required packages using conda (preferred)
conda env update -f environment.yml

# Or install manually
conda install -c conda-forge geopandas rasterio matplotlib pandas numpy scipy scikit-learn jupyter
conda install -c conda-forge pystac-client stackstac planetary-computer seaborn

# Additional packages via pip
pip install python-dotenv
```

## Key Features

- **ARIA v6.0 Framework**: Complete Auditor + Rater + Indicator + Advisor workflow
- **Sentinel-2 Integration**: Direct STAC catalog access to Microsoft Planetary Computer
- **Change Detection**: NDVI and NDWI difference mapping for water and vegetation changes
- **Threshold Optimization**: Systematic sensitivity analysis for optimal detection thresholds
- **Ground Truth Validation**: 60 field-corrected validation points with confusion matrix analysis
- **Confidence Mapping**: 3-zone confidence assessment (High/Medium/Low signal)
- **AI Advisor Interface**: Interactive prompt system for operational decision support

## Laboratory Workflow

### Lab 1: Change Detection (35 minutes)
1. **Data Loading**: Stream Sentinel-2 imagery from Microsoft Planetary Computer STAC catalog
2. **Index Computation**: Calculate NDVI and NDWI for three temporal scenes (Pre/Mid/Post)
3. **Difference Mapping**: Create change maps: Mid-Pre and Post-Mid transitions
4. **Threshold Analysis**: Systematic threshold sweep from -0.6 to 0.6 with 0.025 intervals
5. **Visualization**: 2×2 panel showing both indices and temporal transitions

### Lab 2: Accuracy Assessment (50 minutes)
1. **Ground Truth Loading**: Import 60 field-corrected validation points
2. **Mask Creation**: Generate binary water masks using optimal NDWI threshold
3. **Validation Sampling**: Extract predicted values at validation point locations
4. **Confusion Matrix**: Compute TP/TN/FP/FN and accuracy metrics
5. **Confidence Mapping**: Create 3-zone confidence assessment
6. **Report Generation**: Comprehensive validation summary and AI advisor interface

## ARIA v6.0 Framework Components

### Auditor
- Data quality assessment and cloud masking using SCL (Scene Classification Layer)
- Temporal consistency checks across Pre/Mid/Post scenes
- Coordinate system validation and range filtering

### Rater
- Spectral index computation (NDVI, NDWI)
- Threshold sensitivity analysis and optimization
- Binary classification for water detection

### Indicator
- Confusion matrix computation and accuracy assessment
- Producer's Accuracy, User's Accuracy, Overall Accuracy, Cohen's Kappa
- F1 score optimization for threshold selection

### Advisor
- AI-powered decision support interface
- Operational guidance for disaster response
- Scenario-based threshold recommendations

## Key Findings

### Optimal Threshold Analysis
- **Best Threshold**: 0.275 NDWI for maximum lake detection sensitivity
- **Practical Threshold**: 0.10 NDWI for balanced accuracy
- **Maximum Area Difference**: 29,455 pixels between lake appearance and drainage phases

### Validation Results
- **Total Validation Points**: 60 (15 lake, 15 landslide, 30 stable)
- **Processing Range**: Full study area [121.28, 23.56, 121.52, 23.76]
- **Coordinate System**: WGS84 (EPSG:4326) with Sentinel-2 UTM Zone 51N processing

## Dependencies

### Core Remote Sensing Packages
- **pystac-client**: STAC catalog access for Sentinel-2 data
- **stackstac**: Efficient satellite data streaming and processing
- **planetary-computer**: Microsoft Planetary Computer authentication
- **geopandas**: Vector data manipulation for validation points

### Analysis & Visualization
- **numpy**: Numerical computing and array operations
- **pandas**: Data manipulation and validation point management
- **matplotlib**: Scientific visualization and mapping
- **seaborn**: Statistical visualization and plotting
- **scikit-learn**: Machine learning metrics and confusion matrix

### Environment & Utilities
- **jupyter**: Interactive notebook environment
- **python-dotenv**: Environment variable management
- **conda**: Package management and environment isolation

## Usage Instructions

1. **Environment Setup**: Install conda environment using `environment.yml`
2. **Data Access**: Ensure internet connection for STAC catalog access
3. **Notebook Execution**: Run `scripts/Week9-Student.ipynb` sequentially
4. **Validation**: Results automatically saved to `/outputs` directory
5. **AI Advisor**: Use `outputs/AI_Advisor_Prompt_Template.txt` for operational queries

## Project Repository

This project is hosted at: https://github.com/SamHu14/09_EX

**License**: Educational and research use with proper attribution  
**Institution**: National Taiwan University - Department of Geosciences  
**Date**: April 2026
