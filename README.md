# AI in Drug Discovery — Portfolio Projects

A collection of four machine learning projects exploring AI applications 
in drug discovery, built as a foundation for thesis research in 
graph-based drug-protein interaction modeling.

**Author:** Amir Javad Shokrzadeh  
**Tools:** Python 3.9 · RDKit · Scikit-learn · NumPy · Matplotlib

---

## Projects Overview

### Project A: QSAR-Based BBB Penetration Prediction
Predicts whether a drug compound can cross the Blood-Brain Barrier using 
Morgan molecular fingerprints and a Random Forest classifier.

| Detail | Value |
|--------|-------|
| Dataset | BBBP — 2039 compounds |
| Features | Morgan Fingerprints (2048 bits) |
| Model | Random Forest |
| ROC-AUC | **0.935** |

---

### Project B: Drug-Target Interaction (DTI) Prediction
Predicts whether a drug compound interacts with a target protein by 
combining molecular fingerprints with protein 3-mer count vectors.

| Detail | Value |
|--------|-------|
| Dataset | 10,195 drug-protein pairs (5 CNS targets) |
| Drug features | Morgan Fingerprints (1024 bits) |
| Protein features | 3-mer count vectors (406 features) |
| Model | Random Forest |
| ROC-AUC | **0.686** |

> Baseline model — future work includes GNN-based DTI with attention mechanisms.

---

### Project C: Similarity-Based Drug Repurposing Pipeline
Ranks existing compounds as CNS drug candidates using Tanimoto structural 
similarity to known CNS drugs, combined with a machine learning classifier.

| Detail | Value |
|--------|-------|
| Dataset | BBBP — 2039 compounds |
| Seed drugs | Caffeine, Diazepam, Nicotine, Amphetamine |
| Features | Morgan Fingerprints + Tanimoto similarity scores |
| Model | Random Forest |
| ROC-AUC | **0.935** |

---

### Project D: Explainable GNN for Molecular Property Prediction
Graph neural network-inspired pipeline with atom-level explainability for 
BBB penetration prediction. Message passing is implemented from scratch 
to highlight important atoms driving model predictions.

| Detail | Value |
|--------|-------|
| Dataset | BBBP — 2039 compounds |
| Architecture | 2-step Message Passing (NumPy) |
| Readout | Mean + Max pooling |
| Explainability | Leave-one-atom-out importance |
| Model | Random Forest on graph embeddings |
| ROC-AUC | **0.855** |

> Baseline implementation. Thesis version will incorporate GNNExplainer, 
> Integrated Gradients, and Cross-Attention mechanisms via PyTorch Geometric.

---

## Thesis Direction
These projects serve as groundwork for an upcoming thesis on 
**graph neural networks for drug-protein interaction prediction**, 
with a focus on explainability and drug repurposing applications.

Core thesis topics:
- GNN-based drug-protein interaction modeling
- Explainability via GNNExplainer and Integrated Gradients
- Molecular saliency maps for interpretable predictions
- Drug repurposing using graph-based similarity

---

## Repository Structure
