# Forest Fire Detection Model

A machine learning project for predicting forest fire risk in Algeria using weather data and Fire Weather Index (FWI) components.

## Overview

This project analyzes the Algerian Forest Fires Dataset to build predictive models for fire detection. The dataset includes weather observations and FWI system indices from two regions in Algeria (Bejaia and Sidi-Bel Abbes) collected from June to September 2012.

**Dataset Statistics:**
- **Total Instances:** 244 (122 per region)
- **Fire Cases:** 138
- **Non-Fire Cases:** 106
- **Time Period:** June 2012 - September 2012

## Dataset Features

### Weather Observations
- **Temperature (Temp):** Noon temperature in Celsius (22-42°C)
- **Relative Humidity (RH):** Humidity percentage (21-90%)
- **Wind Speed (Ws):** Speed in km/h (6-29 km/h)
- **Rain:** Total daily rainfall in mm (0-16.8 mm)

### FWI Components
- **FFMC:** Fine Fuel Moisture Code (28.6-92.5)
- **DMC:** Duff Moisture Code (1.1-65.9)
- **DC:** Drought Code (7-220.4)
- **ISI:** Initial Spread Index (0-18.5)
- **BUI:** Buildup Index (1.1-68)
- **FWI:** Fire Weather Index (0-31.1)

### Target Variable
- **Classes:** Fire / Not Fire (Binary Classification)

## Project Structure

```
Forest_fire_detection_model/
├── README.md                                          # This file
├── requirements.txt                                   # Python dependencies
├── EDA.ipynb                                          # Exploratory Data Analysis
├── Model_training.ipynb                               # Model Training & Evaluation
├── Algerian_forest_fires_dataset_UPDATE.csv           # Original dataset
└── Algerian_forest_fires_dataset_UPDATE_cleaned.csv   # Cleaned dataset
```

## Notebooks

### 1. EDA.ipynb - Exploratory Data Analysis
Performs comprehensive data exploration and cleaning:
- Dataset loading and inspection
- Missing value analysis
- Region separation (Bejaia and Sidi-Bel Abbes)
- Data cleaning and preprocessing
- Statistical summaries

**Key Steps:**
- Load dataset with proper header parsing
- Add region column for dataset segmentation
- Handle missing values
- Data validation and formatting

### 2. Model_training.ipynb - Model Development
Builds and evaluates multiple regression models:
- Data preprocessing and feature engineering
- Correlation analysis for feature selection
- Feature scaling using StandardScaler
- Model training and evaluation

**Models Implemented:**
- Linear Regression
- Lasso Regression
- Ridge Regression
- ElasticNet Regression

**Evaluation Metrics:**
- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- R² Score

## Installation

### Prerequisites
- Python 3.7+
- Jupyter Notebook

### Setup

1. Clone or download the project:
```bash
cd Forest_fire_detection_model
```

2. Install required packages:
```bash
pip install -r requirements.txt
```

## Usage

### Running the Analysis

1. **Start Jupyter Notebook:**
```bash
jupyter notebook
```

2. **Run EDA.ipynb first** to understand and clean the data
3. **Run Model_training.ipynb** to train and evaluate models

### Key Workflow

```
1. Data Loading → 2. Data Cleaning → 3. EDA → 4. Feature Selection → 
5. Feature Scaling → 6. Model Training → 7. Model Evaluation
```

## Dependencies

- **pandas:** Data manipulation and analysis
- **numpy:** Numerical computing
- **matplotlib:** Data visualization
- **seaborn:** Statistical data visualization
- **scikit-learn:** Machine learning algorithms
- **ipykernel:** Jupyter kernel

See `requirements.txt` for exact versions.

## Data Preprocessing Steps

1. **Region Separation:** Dataset split at index 122 to separate the two regions
2. **Missing Value Handling:** Removal of rows with null values
3. **Data Type Conversion:** Ensure correct data types (e.g., Region as int)
4. **Date Feature Removal:** Day, month, year columns dropped for model training
5. **Target Encoding:** Classes converted to numerical values (0 = not fire, 1 = fire)

## Feature Engineering

- **Correlation Analysis:** Features with correlation > 0.85 are identified and removed
- **Feature Scaling:** StandardScaler applied for model normalization
- **Train-Test Split:** 75-25 split for model evaluation

## Results

The models are evaluated using:
- Scatter plots of predictions vs actual values
- Correlation heatmaps of features
- Box plots for understanding feature distributions before and after scaling
- Performance metrics (MAE, MSE, R²)

## Future Improvements

- Classification models for binary fire/not-fire prediction
- Hyperparameter tuning and cross-validation
- Ensemble methods (Random Forest, Gradient Boosting)
- Time-series analysis for temporal patterns
- Feature importance analysis
- Model deployment and API creation

## Dataset Source

Algerian Forest Fires Dataset - UCI Machine Learning Repository
- Two regions: Bejaia (Northeast Algeria) and Sidi-Bel Abbes (Northwest Algeria)
- Weather and FWI component measurements
- Binary fire occurrence classification

## Author Notes

This project demonstrates a complete machine learning pipeline from data exploration through model evaluation using the Algerian Forest Fires Dataset.

## License

Dataset sourced from UCI Machine Learning Repository. Check the original source for license information.

## References

- Algerian Forest Fires Dataset: https://archive.ics.uci.edu/ml/datasets/Algerian+Forest+Fires
- FWI System Documentation: https://en.wikipedia.org/wiki/Forest_Fire_Weather_Index

---

**Last Updated:** August 2026
