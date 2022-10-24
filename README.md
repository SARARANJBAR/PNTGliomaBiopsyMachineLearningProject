# PNTGliomaBiopsyMachineLearningProject

## Context

The python scripts here were written as part of preliminary work for a recent PNTlab grant application. The goal of the proposed grant was to build a conceptual framework to understand sex-specific glioma tissue state transition and the ways to interpret MRI related to those changes for key cellular phenotypes using spatially defined biopsies to determine the cellular constituents of tissue states and to inform machine learning algorithm-based approaches to MRI-defined tissue states. 

We deconvolved 128 biopsies with bulk RNAseq into relative abundance of subpopulations. We wanted to predict the relative abundance of different cell populations. Input imaging features include quantitative MRI images (rCBV, FA, MD, EPI, and T2 Mapping) from biopsy locations and Enhancing column that shows if the biopsy was extracted from enhancing tumor.


Functions to perform feature selection and sampling exist in the classification notebook. 

### regression
Targets for regression can be scores for A, B, C state or the relative abbundance of glMes, glPro, or glPN. Since the number of features is not a lot,  feature selection was skipped. 

Modeling approach includes training regression models (direct multioutput regression, wrapper multioutput regression, and chain regression) to simultaneously predict 2+ numerical outputs (different cell populations in this case) represented with their abundance measured using RNASeq.

a model trained on the entire data was saved for creating a map of targets on independent data

### classification

classification targets are states A, B, or C, defined as the state with maximum score. Since the number of features is not a lot,  feature selection was skipped. 

The analysis was done in both sex-specific manner (separate models for males or females) as well as for the combined cohorts. Under and over sampling strategies were used to ensure equal representation of groups during model training.

### testing 
the regression model trained on the entire labeled data was used to create a map of targets on an independent test case.
 
## Requirements
numpy, scipy, pandas, matplotlib, sklearn, seaborn

## Data
Due to the proprietary nature of patient data, we are not at liberty to freely share data on Github and therefore the input csv file is not added here. 

