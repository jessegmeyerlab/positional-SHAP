# Positional-SHAP (PoSHAP)

PoSHAP is a method to analyze SHAP contributions of sequential amino acid data to final predictions of machine learning models. PoSHAP utilizes SHAP's KernelExplainer to calculate 
feature importance and indexes the positions of the inputs and SHAP values to remove ambiguity from the explanations. PoSHAP also analyzes the dependencies between inputs to 
determine interactions between positions in a peptide. PoSHAP paper can be found here : https://www.biorxiv.org/content/10.1101/2021.03.04.433939v2

To use PoSHAP for your own model, use the jupyter notebook present in the tutorial folder and follow the instructions inside. 
You will need a trained model, your x testing set, your x training set, your y training set, and a dictionary linking your encoded x values to the
corresponding understandable input.

PoSHAP requires the following packages to be installed/imported:
shap
copy
math
pickle
pandas
numpy
tensorflow
seaborn
matplotlib
scipy
statsmodels

PoSHAP consists of the following

### Data
Data used for training the models. There are three datasets corresponding to the Mamu MHC Intensity, A11:01 MHC IC50, and the CCS data.
Each dataset has been split into three sets, train, val, and test
MAMU: 20201230_all5
A11:01: 20210524_A1101
CCS: 20210429_CRT_CCS

### Models
Pre-trained models using the above datasets. Includes the Adam optimized, hyperparameter optimized, LSTM models and the RMSprop, hyperparameter unoptimized, LSTM models.
MAMU: 20201230_MHC_all5.model, 20210830_mamu_rmsprop.model
A*11:01: 20210608_A1101_final.model, 20210830_A1101_rmsprop.model
CCS: 20210603_CCS_200epoch.model, 20210830_CCS_rmsprop.model

### Pickles
Contains pickle files holding the values for each SHAP calculation. Contains SHAP pickles for both LSTM models, the Mamu and CCS extra trees model, and the Mamu and CCS Xgb
model.

Mamu:
ADAM: shapvaluesallMamu.pkl
RMSprop: shapvaluesMAMU_RMSprop.pkl
Extra Trees: shapvalues_mamu_etr.pkl
eXtreme Gradient Boosting: shapvalues_mamu_xgb.pkl

ADAM: shapvaluesA1101.pkl
RMSprop: shapvaluesA1101_RMSprop.pkl

ADAM: shapvaluesCCS.pkl
RMSprop: shapvaluesCCS_RMSprop.pkl
Extra Trees: shapvalues_CCS_etr.pkl
eXtreme Gradient Boosting: shapvalues_CCS_xgb.pkl

### Python
Contains jupyter notebooks for model training and for PoSHAP analysis specific to each dataset
20201230_train_new_model_MHC_all5.ipynb : Split data, Train Mamu Models
20201230_train_new_model_A1101.ipynb : Split data, Train A11:01 Models
20201230_train_new_model_CCS.ipynb : Split data, Train CCS Models

Positional_SHAP_Final.ipynb : Perform PoSHAP analysis as in /Tutorial/PoSHAP.ipynb. Figure display optimized for Mamu
Positional_SHAP_A1101.ipynb : Perform PoSHAP analysis as in /Tutorial/PoSHAP.ipynb. Figure display optimized for A1101
Positional_SHAP_CCS-Final.ipynb : Perform PoSHAP analysis as in /Tutorial/PoSHAP.ipynb. Figure display optimized for CCS
PoSHAP-Top SHAP.ipynb : Copy of /Tutorial/PoSHAP.ipynb. Contains extra cell to display SHAP heatmap of top and bottom predicted peptides.

regression.ipynb : Creates ExtraTrees and XGB models and calculates SHAP values for created model.

### Tutorial
Contains a jupyter notebook to perform PoSHAP. It is set up to run with the model and data also present in the folder.
