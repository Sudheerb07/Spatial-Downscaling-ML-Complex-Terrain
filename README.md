# Spatial-Downscaling-ML-Complex-Terrain
Intercomparison of ML models for Spatial Downscaling of Temperature in Complex Terrain

This repository contains code and data for the paper:
"Intercomparison of Machine Learning Models for Spatial Downscaling of Daily Mean Temperature in Complex Terrain"
Sudheer Bhakare, Sara Dal Gesso, Marco Venturini, Dino Zardi, Laura Trentini, Michael Matiu, Marcello Petitta
Published in Atmosphere (2024). DOI: 10.3390/atmos15091085

Overview
In this study, we compared three machine learning models—Artificial Neural Network (ANN), Random Forest (RF), and Convolutional Neural Network (CNN)—for spatial downscaling of temperature at 2 meters above ground (T2M) from a 9 km ERA5-Land reanalysis to a 1 km resolution in a mountainous region in the Italian Alps. Our findings indicate that CNN outperforms other models in capturing spatial temperature variations, especially in complex terrains.

Study Region
The focus area includes the Non Valley and Adige Valley in the Trentino-Alto Adige/South Tyrol region of the Italian Alps, characterized by complex topography and elevations ranging from 166 m to 2628 m above sea level.

Data Sources
Predictor Data: ERA5-Land reanalysis data (9 km resolution), including variables like T2M, D2M, U10, V10, surface pressure, and more.
Target Data: High-resolution daily mean temperature at 1 km, created using ground-based measurements.
Elevation Data: SRTM Digital Elevation Model (DEM) aggregated to 1 km.
Methods
Three machine learning models were implemented:

ANN (Artificial Neural Network): A feed-forward network with a hidden layer.
RF (Random Forest): An ensemble model using multiple decision trees.
CNN (Convolutional Neural Network): A neural network with convolutional layers to handle spatial data.
Each model was trained on daily data from 1980 to 2009 and tested on data from 2010 to 2018. The models were evaluated using metrics like RMSE, MAE, and R².

Key Findings
CNN outperformed other models, particularly in capturing spatial temperature patterns.
RF showed similar performance to CNN in spring and summer but lagged in winter.
ANN exhibited the lowest performance, especially at high elevations.
Elevation was an essential predictor for ANN and RF, while CNN captured spatial information without requiring elevation as an additional feature.

Requirements
To replicate this study, you will need the following Python packages:
tensorflow,
scikit-learn,
xarray,
numpy,
matplotlib,
pyproj

Usage
Data Preprocessing: Use the scripts in src/data_preprocessing.py to prepare the ERA5-Land, DEM, and target temperature data.
Model Training: Train each model using src/train_model.py. Adjust hyperparameters in the configuration file.
Evaluation: Run the notebooks/evaluation.ipynb notebook to generate performance metrics and visualizations.


Citation
If you use this code or data in your research, please cite the original paper:
@article{bhakare2024spatialdownscaling,
  title={Intercomparison of Machine Learning Models for Spatial Downscaling of Daily Mean Temperature in Complex Terrain},
  author={Sudheer Bhakare, Sara Dal Gesso, Marco Venturini, Dino Zardi, Laura Trentini, Michael Matiu, Marcello Petitta},
  journal={Atmosphere},
  year={2024},
  volume={15},
  number={1085},
  doi={10.3390/atmos15091085}
}

