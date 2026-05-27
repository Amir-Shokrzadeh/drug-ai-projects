# Project B: Drug-Target Interaction (DTI) Prediction

## Overview
A machine learning pipeline to predict whether a drug compound interacts 
with a target protein, using combined drug fingerprint and protein k-mer features.

## Dataset
- **Drugs:** 2039 compounds from MoleculeNet BBBP dataset
- **Proteins:** 5 real CNS-related targets (DRD2, ACE, BACE1, COX2, EGFR)
- **Pairs:** 10,195 drug-protein pairs with probabilistic binary labels
- **Note:** Labels generated with realistic interaction probabilities 
  based on BBB penetration and protein CNS relevance

## Methods
- **Drug features:** Morgan Fingerprints (radius=2, 1024 bits) via RDKit
- **Protein features:** 3-mer count vectors (406 features)
- **Combined features:** 1430 total features per pair
- **Model:** Random Forest (100 trees, class_weight=balanced)
- **Split:** 80/20 train/test (stratified)

## Results
| Metric | Score |
|--------|-------|
| ROC-AUC | 0.686 |
| Accuracy | 0.69 |
| F1 (interacting) | 0.55 |
| F1 (non-interacting) | 0.76 |

## Notes
- AUC of 0.686 is realistic for a simple baseline DTI model
- More sophisticated models (GNN, transformer-based) would improve performance
- This serves as a baseline for future GNN-based work

## Requirements
- Python 3.9
- RDKit
- scikit-learn
- pandas, numpy, matplotlib