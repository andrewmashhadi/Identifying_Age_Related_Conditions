# ICR - Identifying Age Related Conditions

Goal is to use modern machine learning methods to detect conditions with measurements of anonymous characteristics. This repository contains the code for the InVitro Cell Research's competition hosted on Kaggle at https://www.kaggle.com/competitions/icr-identify-age-related-conditions/overview.

This project is a "work in progress". Exploratory Data Analysis, XGBoost (with resampling), and PCA + XGBoost (with resampling) are performed / fit in the "baseline" script. Additional scripts are from the brainstorming shown below...

From the link https://sebastianraschka.com/blog/2022/deep-learning-for-tabular-data.html, consider trying the following:

1. Use TabPFN for another model. Since the model ensembles multiple input encodings by default, try to tune the **N_ensemble_configurations** parameter. Might make more sense to use Sage-Maker or Google Colab for hyper-parameter tuning with 5-fold CV.

2. Use XBNet for another model.

3. Instead of randomly oversampling, try using GReaT (Generation of Realistic Tabular data) to synthetically create the minority class's training data for all models used.

4. Create ensembles using logistic regression or average of multiple predicted probabilities (maybe an additional simple model like SVM or something).