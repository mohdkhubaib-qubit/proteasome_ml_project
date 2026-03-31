# Proteasomal Cleavage Prediction using Machine Learning

## Overview

This project focuses on predicting proteasomal cleavage sites involved in antigen processing for MHC class I presentation. The goal is to develop a machine learning framework to identify cleavage patterns in peptide sequences and explore differences between self, non-self (viral), and neoantigen peptides.

---

## Biological Background

Proteasomes degrade intracellular proteins into peptides that are presented by MHC class I molecules. The C-terminal residue of peptides is primarily determined by proteasomal cleavage, making it a critical step in antigen presentation and immune recognition.

---

## Objective

* Predict proteasomal cleavage sites using sequence-based features
* Analyze differences between:

  * Viral (non-self) peptides
  * Human (self) peptides *(future work)*
  * Neoantigens *(future work)*
* Identify biological patterns influencing cleavage specificity

---

## Methodology

### 1. Data Collection

* Viral MHC-I ligands obtained from IEDB
* Peptides mapped to source proteins

### 2. Cleavage Window Generation

* Constructed **11-mer windows**
* Center position (P0) = C-terminal cleavage site
* Positive samples = known cleavage sites
* Negative samples = internal non-cleavage positions

### 3. Feature Engineering

* One-hot encoding
* Amino acid frequency
* PSSM (Position-Specific Scoring Matrix)
* Physicochemical properties (AAindex + PCA)

### 4. Model

* Random Forest classifier
* Evaluated using ROC, PR curves, and feature importance

---

## Results

* Achieved ~79% accuracy
* Identified important sequence-based features influencing cleavage
* Generated performance metrics and visualization plots

---

## Repository Structure

```
proteasome_ml_project/
│
├── notebooks/        # Data processing and modeling notebooks
├── results/          # Model evaluation plots and metrics
├── requirements.txt  # Dependencies
└── .gitignore        # Ignored large files (data, models)
```

---

## Important Note

Due to GitHub file size limitations, raw datasets and trained models are not included in this repository. All data can be regenerated using the provided notebooks.

---

## Future Work

* Comparative analysis: self vs non-self cleavage patterns
* Neoantigen-specific cleavage prediction
* Deep learning models (CNN / BiLSTM / Transformer)
* Integration with immunogenicity prediction

---

## Author

Khubi
Master’s Research Project — Immunoinformatics / Machine Learning
