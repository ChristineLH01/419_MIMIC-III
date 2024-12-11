# Prediction of ICU Patient's Deterioration Risk with Long Short-Term Memory (LSTM) Recurrent Neural Network

# About
This repositorty contains code for the project of AI for Health, which predicts ICU Patient's deterioration risk with time-series health records and LSTM models. The deterioration evaluation and prediction primarily involves 3 derived metrics: [SOFA score](https://en.wikipedia.org/wiki/SOFA_score), [OASIS scores](https://alistairewj.github.io/project/oasis/), and length of stay (LOS).<br>
The repo has been divided into the following folders:
- Data: Local original datasets to be extracted.
- Notebooks: Pipelines to extract, preprocess, and model the predictive LSTM models.
- Resources: Synthesized and preprocessed datasets, which is the main files used in modeling.

# Datasets
- [MIMIC-III](https://physionet.org/content/mimiciii/): The database contains critical care data for over 40,000 patients admitted to ICUs at the BIDMC between 2001 - 2012. It includes information such as demographics, vital sign measurements made at the bedside (~1 data point per hour), laboratory test results, procedures, medications, caregiver notes, imaging reports, and mortality (including post-hospital discharge).
- Major datasets used: 
