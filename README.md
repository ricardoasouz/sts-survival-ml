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
