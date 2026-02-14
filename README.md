# ABL1 Inhibitor Discovery Pipeline  
### Ligand-Based Virtual Screening and Machine Learning  
### Independent Computational Chemistry Project (2024)

---

## Overview

This repository contains an independently developed ligand-based computational workflow for identifying potential inhibitors of the ABL1 tyrosine kinase.

The pipeline integrates physicochemical filtering, structural similarity ranking, scaffold clustering, maximum common substructure analysis, and supervised learning into a coherent cheminformatics framework.

All implementation, dataset preparation, and model development were carried out independently in 2024.

---

## Scientific Context

ABL1 is a non-receptor tyrosine kinase implicated in oncogenic signaling, particularly through the BCR-ABL fusion protein in chronic myeloid leukemia (CML).

This project explores whether molecular fingerprint representations combined with similarity metrics and supervised learning can effectively recover and predict ABL1 inhibitory activity.

---

## Workflow Summary

1. **Dataset Curation**
   - ABL1 bioactivity data collected from ChEMBL.
   - IC50 values converted to pIC50.
   - Activity threshold defined at pIC50 > 6.3.

2. **Filtering**
   - Lipinski Rule of 5 applied.
   - PAINS substructures removed.

3. **Molecular Representation**
   - MACCS fingerprints.
   - Morgan fingerprints (radius = 2, 2048 bits).

4. **Similarity Screening**
   - Dasatinib used as reference ligand.
   - Tanimoto and Dice similarity metrics applied.

5. **Clustering**
   - Butina clustering to ensure scaffold diversity.

6. **Scaffold Analysis**
   - Maximum Common Substructure (MCS) extraction.
   - ringMatchesRingOnly=True to preserve chemical validity.

7. **Supervised Learning**
   - Multi-layer perceptron classifier trained on fingerprint features.
   - Evaluation using ROC–AUC.

---

## Results

- Initial compounds: 2307  
- After filtering: 1251  
- Final candidate molecules: 29  
- Model performance: ROC–AUC = 0.92  

The results suggest that fingerprint-based representations capture relevant structural patterns associated with ABL1 inhibition.

---

## Repository Structure

```
abl1-inhibitor-discovery-pipeline/
│
├── notebooks/
│   abl1_ligand_screening_pipeline.ipynb
│
├── README.md
└── LICENSE
```

---

## Acknowledgements

The conceptual structure of the ligand-based screening workflow was informed by publicly available cheminformatics teaching materials from the Volkamer Lab (Freie Universität Berlin).

All code and analysis presented here were independently implemented and adapted for the ABL1 case study (2024).

---

## License

See LICENSE file.
