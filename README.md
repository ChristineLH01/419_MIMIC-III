# Prediction of ICU Patient's Deterioration Risk with Long Short-Term Memory (LSTM) Recurrent Neural Network

# About
This repositorty contains code for the project of AI for Health, which predicts ICU Patient's deterioration risk with time-series health records and LSTM models. The deterioration prediction primarily involves 3 derived metrics which evaluate patients' condition from different general aspects: [SOFA score](https://en.wikipedia.org/wiki/SOFA_score), [OASIS scores](https://alistairewj.github.io/project/oasis/), and length of stay (LOS). 

# Repo Structure
The repo has been divided into 3 folders: `Data`, `Resources`, `Notebooks`.

`Data` folder contains the local raw datasets from the MIMIC-III database, which is omitted (reference to the section of Datasets).

`Resources` folder includes preprocessed and derived data, which are model-ready datasets.
- `A_ICU_Info.csv`: Merged admission, demographic, and mortality information for each ICU admission.
- `A_Components_Data_2h.csv`: All time-series components (include the feature to derive metrics) tracked at every 2 hours.
- `A_Components_Data_6h.csv`: All time-series components tracked at every 6 hours.

Notebooks are pipelines to extract, preprocess, and model the predictive LSTM models.
- ``

# Original Datasets
Data is from [MIMIC-III](https://physionet.org/content/mimiciii/) (**Require Credential**), a relational database consisting of 26 tables. Instrcutions to access the database is available on [Physionet](https://mimic.mit.edu/docs/gettingstarted/).

The database contains critical care data for over 40,000 patients admitted to ICUs at the BIDMC between 2001 - 2012. It includes information such as demographics, vital sign measurements made at the bedside (~1 data point per hour), laboratory test results, procedures, medications, caregiver notes, imaging reports, and mortality (including post-hospital discharge). 

Only some of the tables from MIMIC-III are required to derive the metrics for modeling:
-  `PATIENTS.csv`: Demographic information and hospital admission of each patient
- `ICUSTAYS.csv`: Basic infomation to each ICU admission
- `CHARTEVENTS.csv` (linked with `D_ITEMS.csv`): Electronic chart data for the patient at the bedside.
- `LABEVENTS.csv`(linked with `D_LABITEMS.csv`): Laboratory test results for a patient
- `INPUTEVENTS_MV.csv` and `INPUTEVENTS_CV.csv` (linked with `D_ITEMS.csv`): Inputs for patients monitored with the CareVue system and Metavision system
- `OUTPUTEVENTS.csv` (linked with `D_ITEMS.csv`): Measurements related to output for a given patient
