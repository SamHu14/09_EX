# Geospatial Analysis Project

## Project Overview

This is a professional geospatial analysis project designed for comprehensive spatial data processing, analysis, and visualization. The project provides a structured framework for handling various types of geospatial data and performing advanced spatial analyses.

## Project Structure

```
project/
|
|-- data/                  # Raw geospatial data
|   |-- *.tif              # Raster data (excluded from git)
|   |-- *.shp              # Vector data
|   |-- *.geojson          # GeoJSON files
|   |-- *.csv              # Tabular data with spatial information
|
|-- outputs/               # Analysis results and outputs
|   |-- figures/           # Generated maps and visualizations
|   |-- reports/           # Analysis reports
|   |-- processed_data/    # Processed geospatial data
|
|-- scripts/               # Analysis scripts and notebooks
|   |-- *.ipynb            # Jupyter notebooks
|   |-- *.py               # Python scripts
|   |-- utils/             # Utility functions
|
|-- .env                   # Environment variables (API keys)
|-- .gitignore             # Git ignore rules
|-- README.md              # This file
|-- environment.yml        # Conda environment specification
```

## Environment Setup

This project requires the `geospatial` conda environment. To set up the environment:

```bash
# Create the conda environment (if not exists)
conda create -n geospatial python=3.9

# Activate the environment
conda activate geospatial

# Install required packages using conda (preferred)
conda install -c conda-forge geopandas rasterio matplotlib pandas numpy scipy scikit-learn jupyter

# If packages are not available via conda, use pip
pip install package_name
```

## Key Features

- **Data Management**: Organized storage for raw and processed geospatial data
- **Analysis Scripts**: Modular Python scripts and Jupyter notebooks for various analyses
- **Visualization**: Comprehensive mapping and visualization capabilities
- **Environment Isolation**: Dedicated conda environment for reproducible results
- **Version Control**: Proper git configuration with sensitive data protection

## Usage Guidelines

### Data Organization
- Place raw geospatial data in the `/data` folder
- Large raster files (.tif, .tiff) are excluded from version control
- Analysis results should be stored in `/outputs`
- All analysis scripts and notebooks go in `/scripts`

### API Keys Configuration
1. Copy the `.env` file and add your API keys
2. Never commit the `.env` file to version control
3. Use `python-dotenv` to load environment variables in scripts

### Package Installation
- Always prefer `conda` for package installation
- Use `pip` only when packages are not available via conda
- Keep the `environment.yml` file updated with all dependencies

## Common Analyses

This project supports various geospatial analyses including:
- Spatial data preprocessing and cleaning
- Raster data processing and analysis
- Vector data operations and spatial joins
- Spatial statistics and modeling
- Map visualization and production
- Remote sensing data analysis

## Best Practices

- Document all analysis steps in Jupyter notebooks
- Use relative paths for data access
- Regularly backup important results from `/outputs`
- Keep the conda environment updated
- Follow the established file naming conventions

## Dependencies

Main packages used in this project:
- geopandas: Vector data manipulation
- rasterio: Raster data I/O and processing
- matplotlib: Visualization
- pandas: Data manipulation
- numpy: Numerical computing
- scipy: Scientific computing
- scikit-learn: Machine learning
- jupyter: Interactive notebooks

## Contributing

When contributing to this project:
1. Follow the established directory structure
2. Update the README.md for new features
3. Use the conda environment for consistency
4. Document code changes and additions
5. Test analyses before committing results

## License

This project is for educational and research purposes. Please ensure proper attribution when using external datasets or code.
