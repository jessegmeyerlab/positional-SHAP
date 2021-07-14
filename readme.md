positional-SHAP (PoSHAP)

PoSHAP is a method to analyze SHAP contributions of sequential amino acid data to final predictions of machine learning models.

As it is currently programmed, PoSHAP can handle sequence data of up to ten positions of peptides. Adaptation to additional positions or input data types is possible and likely straightforward.

PoSHAP consists of three jupyter notebook files, one for each of the MAMU allele data, the human MHC data, and the CCS data. Each performs the same task, but are specific to the input data.

The calculated SHAP values for each dataset are also provided, as the calculation takes a significant amount of time.

Additionally, the trained models, the jupyter notebook files for the generation of the models, and the split training, validation, and testing data are provided.

 