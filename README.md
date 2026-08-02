# Soft-Tissue Sarcoma Survival Analysis — CoxPH vs DeepSurv

End-to-end radiomics and machine learning pipeline for progression-free survival (PFS) analysis in soft-tissue sarcoma using clinical and MRI-derived features.

This project is a portfolio version of my MSc in Data Analytics dissertation at CCT College Dublin. It demonstrates the complete workflow from medical imaging preprocessing and radiomic feature extraction to survival modelling and evaluation.

## Project Overview

The project investigates whether radiomic features extracted from MRI scans can improve progression-free survival prediction in patients with soft-tissue sarcoma.

Two survival modelling approaches were evaluated:

- Cox Proportional Hazards (CoxPH)
- DeepSurv neural survival model

The pipeline combines clinical information with quantitative radiomic features extracted from medical images.

## Pipeline

```text
DICOM + RTSTRUCT
        |
        v
DICOM / RTSTRUCT Mapping
        |
        v
NIfTI Conversion
        |
        v
Tumour Segmentation Masks
        |
        v
PyRadiomics Feature Extraction
        |
        v
Patient-Level Feature Aggregation
        |
        v
Clinical + Radiomic Features
        |
        v
Data Validation & Preprocessing
        |
        v
Train / Validation / Test Split
        |
        +------------------+
        |                  |
        v                  v
      CoxPH             DeepSurv
        |                  |
        +--------+---------+
                 |
                 v
       Survival Model Evaluation

Technology Stack
Python
PyTorch
Scikit-learn
Pandas
NumPy
PyRadiomics
lifelines
pycox
torchtuples
DICOM / NIfTI
Google Cloud Storage
Jupyter / Google Colab
Git
Dataset

The project uses the publicly available Soft-Tissue Sarcoma (STS) collection from The Cancer Imaging Archive (TCIA).

The workflow processes MRI imaging, RTSTRUCT tumour segmentation data and associated clinical outcome information.

The original imaging dataset is not redistributed through this repository.

Engineering Workflow

The project was implemented as a multi-stage data and machine learning pipeline:

Map RTSTRUCT tumour structures to the corresponding DICOM imaging series.
Convert medical imaging data into NIfTI format.
Generate and validate tumour segmentation masks.
Extract quantitative imaging features using PyRadiomics.
Consolidate features across imaging series at patient level.
Integrate radiomic and clinical information.
Perform data cleaning, feature engineering and leakage prevention.
Create patient-level training, validation and test splits.
Train CoxPH and DeepSurv survival models.
Evaluate model discrimination and survival-risk stratification.
Engineering Challenges & Troubleshooting

Building the pipeline required troubleshooting across multiple technologies and data formats.

Examples included:

DICOM series inconsistencies and duplicate slices
RTSTRUCT-to-image mapping
DICOM to NIfTI conversion failures
Medical-image orientation issues
Segmentation mask validation
Dependency and library compatibility issues
Large medical-imaging workloads
Cloud storage and compute management
Feature consolidation across multiple imaging series
Prevention of outcome leakage during machine learning
Reproducible patient-level dataset splitting

These challenges required systematic debugging, validation and iterative pipeline development.

Machine Learning
Cox Proportional Hazards

A regularised CoxPH model was used as the classical survival-analysis baseline.

Preprocessing included feature filtering, missing-value handling, correlation reduction and patient-level data splitting.

DeepSurv

DeepSurv was implemented as a neural-network-based survival model using PyTorch and the pycox ecosystem.

The modelling workflow included feature standardisation, training/validation separation, regularisation and early stopping.

Evaluation

Models were evaluated using survival-analysis techniques including:

Concordance Index (C-index)
Bootstrap evaluation
Kaplan-Meier risk stratification
Clinical-only and clinical+radiomics comparisons
Repository Structure
sts-survival-ml/
|
|-- notebooks/
|   |-- 01_rtstruct_dicom_mapping.ipynb
|   |-- 02_radiomics_extraction.ipynb
|   |-- 03_feature_consolidation.ipynb
|   |-- 04_clinical_survival_analysis.ipynb
|   |-- 05_data_preparation.ipynb
|   `-- 06_coxph_vs_deepsurv.ipynb
|
|-- results/
|-- docs/
|-- requirements.txt
`-- README.md

The public portfolio version intentionally excludes patient-level datasets, institutional documents and other material that should not be redistributed.

Key Skills Demonstrated
Python engineering
Machine learning
Survival analysis
Medical imaging pipelines
Data preprocessing
Feature engineering
Cloud-based data processing
Technical troubleshooting
Root cause investigation
Reproducible ML workflows
Data validation
AI/ML experimentation
Author

Ricardo Alves de Souza

MSc Data Analytics
BSc (Hons) Information Technology
Dublin, Ireland

LinkedIn: linkedin.com/in/ricardo-alves-de-souza
GitHub: github.com/ricardoasouz
