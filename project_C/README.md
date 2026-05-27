# Project C: Drug Repurposing Pipeline

## Overview
A similarity-based drug repurposing pipeline that ranks existing compounds 
as candidates for CNS (Central Nervous System) activity, using structural 
similarity to known CNS drugs combined with a machine learning classifier.

## Dataset
- **Source:** MoleculeNet BBBP Dataset
- **Size:** 2039 compounds
- **Labels:** Binary (1 = BBB penetrating, 0 = non-penetrating)

## Methods
- **Seed drugs:** Caffeine, Diazepam, Nicotine, Amphetamine
- **Similarity metric:** Tanimoto similarity on Morgan Fingerprints (radius=2, 2048 bits)
- **Model:** Random Forest Classifier (100 trees, class_weight=balanced)
- **Split:** 80/20 train/test (stratified)

## Feature Engineering Improvement
Initial model used only 4 Tanimoto similarity scores as features → ROC-AUC: 0.764

After combining full Morgan Fingerprints (2048 bits) with similarity scores → ROC-AUC: 0.953

This improvement highlights that structural similarity to seed drugs alone is 
insufficient; full molecular fingerprints provide richer chemical information 
that significantly boosts predictive performance.

## Results
| Metric | Score |
|--------|-------|
| ROC-AUC | 0.953 |
| Accuracy | 0.91 |
| F1 (BBB penetrating) | 0.94 |
| F1 (non-penetrating) | 0.78 |

## Output
- Top 15 repurposing candidates ranked by model score
- Similarity distribution plot by class
- Bar chart of top candidate scores

## Requirements
- Python 3.9
- RDKit
- scikit-learn
- pandas, numpy, matplotlib