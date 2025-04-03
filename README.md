# ICU Mortality Prediction – Classification Project

In this project, the goal was to predict the probability that a patient dies during their hospital stay after being admitted to an Intensive Care Unit (ICU).

We worked with supervised classification models, including:

- Support Vector Machines (SVM)
- Tree-based models such as Decision Trees, Random Forest, XGBoost, and CatBoost

## Dataset

The data comes from the MIMIC-III database — a large and publicly available collection of medical records from over 40,000 ICU patients treated at the Beth Israel Deaconess Medical Center between 2001 and 2012.  
More info: [MIMIC-III official site](https://mimic.physionet.org/)

Each row in `mimictrain.csv` represents one ICU stay.

The target variable is `HOSPITAL_EXPIRE_FLAG`, which equals:

- `1` → if the patient died during the hospital stay  
- `0` → if the patient survived

The input features include:

- Vital signs and general patient characteristics (age, gender, etc.) taken at ICU admission
- The main diagnosis code (`ICD9_diagnosis`), which can be decoded using `MIMIC_metadata_diagnose.csv`
- Additional comorbidities from `MIMIC_diagnoses.csv`

**Important:** Only features that would realistically be available on the first day in the ICU were allowed in the prediction models.

## Evaluation Metric

The main performance metric for this binary classification task is **AUC (Area Under the Curve)**.  
Other metrics like **precision**, **recall**, or **F1-score** could also be reported if relevant to the modeling approach.
