# Motorway Sign Automated Validation Correction System

A geospatial AI system to validate traffic sign placements using satellite imagery and HERE location data. Automates detection of missing signs and updates road topology characteristics.

## Features

- **Scenario 1**: Satellite imagery-based validation of sign existence using deep learning
- **Scenario 2/3**: Geospatial analysis of sign-road proximity with automatic topology updates
- **Scenario 4**: Legitimate exception identification through pedestrian access validation
- Automated report generation with visual verification maps
- Integration with HERE platform data and APIs

## Tech Stack

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.12-orange)
![GeoPandas](https://img.shields.io/badge/GeoPandas-0.12-green)
![HERE API](https://img.shields.io/badge/HERE%20API-v3-lightgrey)

## Installation

1. Clone repository:
```bash
git clone https://github.com/irfan7587/here-hackathon-2025.git
cd here-hackathon-2025
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Set up HERE API key:
```python
# In scenario1.ipynb and satellite_imagery_tile_request.py
API_KEY = "<your-api-key>"
```

## Project Structure
```
├── data/
│   ├── validations.geojson
│   ├── signs.geojson
│   └── full_topology_data.geojson
├── scenario1.ipynb          # Sign validation ML model
├── main.ipynb               # Main processing workflow
├── satellite_imagery_tile_request.py  # HERE API integration
└── corrected_*.geojson      # Output files
```

## Usage

1. **Satellite Imagery Processing**:
```python
# In scenario1.ipynb
model = build_model()  # EfficientNet-based classifier
resolve_missing_signs(validations_gdf)  # Automated sign validation
```

2. **Geospatial Analysis**:
```python
# In main.ipynb
process_violations()  # Handles all 4 scenarios
generate_verification_report()  # HTML report with maps
```

3. **Output Generation**:
```python
# Creates corrected datasets
corrected_signs.geojson
corrected_topology_access_chars.geojson
corrected_validations.geojson
```

## Key Components

- **Deep Learning Model**:
  - EfficientNetB0 base with custom classifier
  - 15-epoch training with early stopping
  - Satellite image processing at 224x224 resolution

- **Geospatial Features**:
  - Automatic UTM zone detection
  - 10m precision distance calculations
  - Dynamic CRS transformations

## Contributing

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Acknowledgments

- HERE Technologies for mapping data and APIs
- TensorFlow for deep learning framework
- GeoPandas for geospatial processing
