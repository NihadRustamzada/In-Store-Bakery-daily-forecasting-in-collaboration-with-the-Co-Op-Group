# README: Team ETA Source Code

This folder contains three files:
- eta_exploratory_data_analysis.Rmd
- eta_preprocessing.Rmd
- eta_modelling.Rmd

This folder also contains an additional directory: data.

## Data directory
This folder contains the original dataset provided by the Co-op alongside the output of the eta_preprocessing.Rmd file for both testing and training datasets.

## Code
### eta_exploratory_data_analysis.Rmd
This file contains code used to perform our exploratory data analysis on the original dataset and produces several graphics such as box plots, a scatterplot and a correlation matrix.

### eta_preprocessing.Rmd
This file processes the raw sales data provided by the Co-op into a form more suited to our models. 

> The training and testing partitions are processed individually to avoid data leakage. To facilitate this, set PROCESS_TRAINING_DATA to TRUE to output the processed training data and FALSE to output the processing testing data. 

- The data is split into training and testing partitions
- Irrelevant columns are removed
- Additional features are added, such as SubSect_PackSize and lag features 
- Missing sales data is imputed using the Amelia library

This formatted data then provides room for additional graphics to be created such as those representing Seasonal Decomposition

### eta_modelling.Rmd
This file takes the training and testing CSVs and applies the following models to the data:

- LASSO
- ES
- SMA
- ARIMA
- ARIMAX

Performance data is collected in data frames and output by plots.