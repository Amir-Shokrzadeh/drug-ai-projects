# Project A: Blood-Brain Barrier Penetration (BBBP) Prediction

## Overview
A QSAR-style machine learning model to predict whether a drug compound 
can penetrate the Blood-Brain Barrier (BBB), using molecular fingerprints.

## Dataset
- **Source:** MoleculeNet BBBP Dataset
- **Size:** 2039 compounds
- **Labels:** Binary (1 = penetrates, 0 = does not penetrate)

## Methods
- **Featurization:** Morgan Fingerprints (radius=2, 2048 bits) via RDKit
- **Model:** Random Forest Classifier (100 trees, class_weight=balanced)
- **Split:** 80/20 train/test (stratified)

## Results
| Metric | Score |
|--------|-------|
| ROC-AUC | 0.935 |
| Accuracy | 0.90 |
| F1 (class 1) | 0.94 |
| F1 (class 0) | 0.75 |

## Notes
- Dataset is imbalanced (1560 positive vs 479 negative)
- class_weight=balanced used to handle imbalance

## Requirements
- Python 3.9
- RDKit
- scikit-learn
- pandas, numpy, matplotlib