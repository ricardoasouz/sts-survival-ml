# Portfolio-safe upload guide

## Recommended repository structure

```text
sts-survival-ml/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   ├── 01_rtstruct_dicom_mapping.ipynb
│   ├── 02_radiomics_extraction.ipynb
│   ├── 03_feature_consolidation.ipynb
│   ├── 04_clinical_survival_analysis.ipynb
│   ├── 05_data_preparation.ipynb
│   └── 06_coxph_vs_deepsurv.ipynb
├── docs/
└── results/
```

## What was intentionally removed or generalized

- Executed notebook outputs and embedded tables/plots
- Exact Google Cloud bucket name
- Exact Google Drive / Colab paths
- Exact example patient IDs
- Environment-specific authentication cells
- Patient-level CSV/XLSX data
- Institutional / ethics documents

## What was preserved

- Six-stage research/engineering workflow
- DICOM/RTSTRUCT mapping logic
- NIfTI / radiomics extraction workflow
- Clinical survival-analysis methodology
- Patient-level preprocessing and splitting logic
- CoxPH modelling
- DeepSurv implementation with PyTorch + pycox + torchtuples
- Anti-leakage logic and repeated evaluation structure

## Before pushing

1. Keep the repository data-free.
2. Do not upload `INFOclinical_STS.xlsx`, mapping CSVs, consolidated patient-level feature CSVs, or processed splits.
3. Review each notebook once in GitHub after upload.
4. Add only non-sensitive aggregate figures/results you explicitly want public.
5. If you later publish results, include sample-size and validation limitations in the README.
