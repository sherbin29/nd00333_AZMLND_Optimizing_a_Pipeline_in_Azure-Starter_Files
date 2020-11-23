# Optimizing an ML Pipeline in Azure

## Overview
This project is part of the Udacity Azure ML Nanodegree.
In this project, we build and optimize an Azure ML pipeline using the Python SDK and a provided Scikit-learn model.
This model is then compared to an Azure AutoML run.

## Summary
**This dataset is an bankmarketing data which as 32950 data has present. The data has 20 coloumns with 1 label coloumn 'y'. We can use the column 'y' for training the ML model.
link -- > https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv**

## Scikit-learn Pipeline
Scikit-learn Pipeline includes  Random Parameter Sampler, Bandit Policy and SKLearn estimator these are the Hyperdrive configuration for ML optimization. It include the file train.py is passed to the estimator. The estimator has some parameter has policy, Parameter Sampler,primary metric (Accuracy) these parameter are passes to the HyderDrive Config Method and we can see the output of the model.

**Random sampling --> parameters are --C, max iter.**

**Bandit policy --> parameters are slack_factor = 0.1, evaluation_interval=1, delay_evaluation=5.**

## AutoML
We have tested with vaiours model around 24 pipelines with different ML Algorithms are run but the best one is **Voting Ensemble**. Some Parameters like task, primary metric, experiment timeout, training data are passed into the AutoMlConfig to create an optimzed pipeline run on AutoMl that test various models.

**Voting Ensemble with Accuracy of 0.9175**

## Pipeline comparison

**HyperDrive Model has Accuracy of 0.9072.**

**AutoML Model has Accuracy of 0.9175.**
