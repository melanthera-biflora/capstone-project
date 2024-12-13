# Salinity Intrusion Prediction Using MODIS Data

This repository contains the code and resources for the Capstone Project titled **"Utilizing MODIS Data Retrieved from Sentinel Hub API to Predict Salinity Intrusion in San Francisco Bay & Inner Kiel Fjord"**.

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

|-- README.md           # Project documentation
```

## Contributing
Contributions are welcome! Please submit issues or pull requests to suggest improvements or report bugs.

## Acknowledgments
- MODIS Data: NASA
- Sentinel Hub API: Sinergise
- Advisors and collaborators for their guidance and support.
