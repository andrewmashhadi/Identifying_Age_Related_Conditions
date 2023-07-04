# ICR - Identifying Age Related Conditions

Goal is to use modern machine learning methods to detect conditions with measurements of anonymous characteristics. This repository contains the code for the InVitro Cell Research's competition hosted on Kaggle at https://www.kaggle.com/competitions/icr-identify-age-related-conditions/overview.

This project is a "work in progress". Exploratory Data Analysis, XGBoost (with standard resampling), and PCA + XGBoost (with standard resampling) are performed / fit in the "baseline" script. The additional scripts consist of using the TabPFN from the paper [here](https://arxiv.org/pdf/2207.01848.pdf) and the TabTransfomer from Amazon. The TabPFN model was trained and tuned locally, while the TabTransformer was trained and tuned using SageMaker SDK (with EC2 GPU instances). All methods tried will ultimately save two files: (1) a CSV with probability estimates for an unseen validation set (2) a CSV with probability estimates for the test set. The probability estimates will be used for the competition submission.

Inspired by the list shown [here](https://sebastianraschka.com/blog/2022/deep-learning-for-tabular-data.html), I will also consider trying the following two things:

1. Instead of randomly oversampling, try using GReaT (Generation of Realistic Tabular data) to synthetically create the minority class's training data for all models used.

2. Create ensembles using logistic regression or average of multiple predicted probabilities (maybe an additional simple model like SVM or something).