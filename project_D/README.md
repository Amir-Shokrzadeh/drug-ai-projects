# Project D: Explainable GNN for Drug-Graph Analysis

## Overview
A graph neural network-inspired pipeline for predicting Blood-Brain Barrier 
penetration with atom-level explainability. Due to hardware/environment 
constraints, GNN message passing is implemented from scratch using NumPy, 
without PyTorch Geometric. This serves as a baseline; the full thesis 
implementation will use GNNExplainer and Integrated Gradients via PyTorch.

## Dataset
- **Source:** MoleculeNet BBBP Dataset
- **Size:** 2039 compounds
- **Labels:** Binary (1 = BBB penetrant, 0 = non-penetrant)

## Architecture
- **Graph construction:** SMILES → molecular graph (atoms=nodes, bonds=edges)
- **Node features:** atomic number, degree, formal charge, aromaticity, ring membership
- **Message passing:** 2-step neighborhood aggregation (NumPy implementation)
- **Readout:** mean + max pooling → graph-level embedding

## Explainability
- **Method:** Leave-one-atom-out importance
- **Visualization:** Per-atom importance heatmap overlaid on 2D molecular structure
- **Note:** Full implementation will include GNNExplainer, Integrated Gradients,
  and Cross-Attention mechanisms as outlined in thesis proposal

## Results
| Metric | Score |
|--------|-------|
| ROC-AUC | 0.855 |
| Architecture | 2-step Message Passing |
| Explainability | Leave-one-atom-out |

## Limitations & Future Work
- Current implementation simulates GNN without autograd (no backpropagation)
- Quantitative faithfulness and stability metrics to be added

## Requirements
- Python 3.9
- RDKit
- scikit-learn
- pandas, numpy, matplotlib