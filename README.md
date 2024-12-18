# Advancing Salinity Intrusion Low-cost Monitoring in Estuarine Areas Using Temporal and MODIS Satellite Data: A Machine Learning Approach

This repository contains the code and resources for the Capstone Project titled **"Advancing Salinity Intrusion Low-cost Monitoring in EstuarineAreas Using Temporal and MODIS Satellite Data: A Machine Learning Approach"**.

## Overview
Salinity intrusion, the movement of saline water into freshwater systems, is a critical environmental issue influenced by climate change and human activities. This project leverages MODIS remote sensing data retrieved from the Sentinel Hub API to model and predict salinity intrusion in two study regions:

1. **San Francisco Bay, USA**
2. **Inner Kiel Fjord, Germany**

The aim is to develop a predictive framework that can support decision-making in managing water resources and mitigating the impacts of salinity intrusion.

## Study Step
- **Data Retrieval**: Integration with Sentinel Hub API to download MODIS satellite data for specified regions.
- **Data Mapping**: Mapping Process of bands data and in-situ salinity data in according coordinates and collected time.
- **Data Preprocessing**: Includes quality assessment & training/ testing division.
- **Model Development**: Application of machine learning and statistical techniques to predict salinity levels based on remote sensing indices.

## Data Sources
- **MODIS**: Moderate Resolution Imaging Spectroradiometer data for surface reflectance and derived indices.
- **Sentinel Hub API**: For efficient data retrieval and processing.

# Dataset

## Raw Dataset

- **San Francisco Bay**:
  - [Water Quality Measurements (1969-2015)](https://www.usgs.gov/publications/water-quality-measurements-san-francisco-bay-us-geological-survey-1969-2015)
  - [USGS Water Quality Measurements (2016-2021, Ver. 40, March 2023)](https://www.usgs.gov/data/usgs-measurements-water-quality-san-francisco-bay-ca-2016-2021-ver-40-march-2023)

- **Inner Kiel Fjord**:
  - [Dataset from PANGAEA](https://doi.pangaea.de/10.1594/PANGAEA.930979)

## Processed Dataset (For Training and Testing)

The processed dataset used for the training and testing process can be found in the `/training_dataset` directory.


## Prerequisites
Ensure you have the following installed:
- Python 3.8+
- A valid Sentinel Hub account and API key

## Directory Structure
```
|-- band_data_extraction_from_Sentinel/               
|   |-- Fjord_extraction.ipynb                        #Band Extraction of Fjord area
|   |-- San_Francisco_Bay_Extraction.ipynb            #Band Extraction of SFB area
|-- data_mapping/
|   |-- Fjord_mapping.ipynb                           #Mapping band value (Fjord)
|   |-- San_Francisco_Bay_Data_Mapping.ipynb          #Mapping band value (SFB)
|-- data_preprocessing/
|   |-- fjord-preprocessing.ipynb                     #Preprocessing data and train-test devision (Fjord)
|   |-- sfb-data-preprocessing.ipynb                  #Preprocessing data and train-test devision (SFB)
|-- model_development/
|   |-- Inner Kiel Fjord/
|   |   |-- fjord-decision-tree.ipynb                 #Decision Tree Model Development (Fjord)
|   |   |-- fjord-random-forest.ipynb                 #Random Forest Model Development (Fjord)
|   |   |-- fjord-stack.ipynb                         #Stacking Model Development (Fjord)
|   |   |-- fjord-xgboost.ipynb                       #XGBoost Model Development (Fjord)
|   |-- San Francisco Bay/
|   |   |-- decision-tree-sfb.ipynb                   #Decision Tree Model Development (SFB)
|   |   |-- sfb-random-forest.ipynb                   #Random Forest Model Development (SFB)
|   |   |-- sfb-stack.ipynb                           #Stacking Model Development (SFB)
|   |   |-- sfb-xgboost.ipynb                         #XGBoost Model Development (SFB)
|-- training_dataset/
|   |-- Inner Kiel Fjord/                             #Training & Testing set for Inner Kiel Fjord
|   |   |-- training_set.csv
|   |   |-- testing_set.csv  
|   |-- SFB/                                          #Training & Testing set for San Francisco Bay
|   |   |-- training_set.csv 
|   |   |-- testing_set.csv  
|-- README.md           # Project documentation
```
## Model Performance Comparison

| **Model**                     | **RMSE (Train)** | **MAE (Train)** | **R² (Train)** | **MAPE (Train)** | **RMSE (Test)** | **MAE (Test)** | **R² (Test)** | **MAPE (Test)** |
|--------------------------------|------------------|-----------------|----------------|------------------|-----------------|----------------|---------------|-----------------|
| Decision Tree (PANGAEA)        | 1.309           | 0.948           | 0.763          | 6.15%            | 1.319           | 0.952          | 0.759         | 6.19%           |
| **Random Forest (PANGAEA)**    | **0.573**       | **0.373**       | **0.955**      | **2.41%**        | **0.582**       | **0.378**      | **0.953**     | **2.46%**       |
| XGBoost (PANGAEA)              | 0.860           | 0.651           | 0.898          | 4.17%            | 0.876           | 0.661          | 0.893         | 4.25%           |
| Stack (PANGAEA)                | 0.576           | 0.376           | 0.954          | 2.43%            | 0.585           | 0.381          | 0.952         | 2.47%           |
| Decision Tree (USGS)           | 2.478           | 1.785           | 0.594          | 7.30%            | 2.526           | 1.849          | 0.584         | 7.48%           |
| **Random Forest (SFB)**        | **1.82**        | **1.21**        | **0.77**       | **4.98%**        | **1.32**        | **1.575**      | **0.74**      | **5.34%**       |
| XGBoost (USGS)                 | 1.956           | 1.366           | 0.747          | 5.61%            | 2.086           | 1.464          | 0.716         | 5.97%           |
| Stack (USGS)                   | 1.893           | 1.301           | 0.763          | 5.31%            | 2.060           | 1.422          | 0.723         | 5.75%           |

## Contributing
Contributions are welcome! Please submit issues or pull requests to suggest improvements or report bugs.

## Acknowledgments
- MODIS Data: NASA
- Sentinel Hub API: Sinergise
- Advisors and collaborators for their guidance and support.
