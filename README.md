# Molecular Fingerprint Analysis of Potential Aromatase Inhibitors Using Clustering Methods

## Author
**Jihan Fadila**  
📧 Email: jihan4han97@gmail.com

## Introduction
Breast cancer is a major global health threat, with 2.3 million new cases reported in 2020, accounting for 11.7% of all cancer cases worldwide. The prevalence in Indonesia ranks first, with 68,858 cases and over 22,000 deaths. One of the key factors in breast cancer development is the increase in estrogen levels mediated by the **aromatase enzyme**, which converts androgens into estrogens.

Aromatase inhibitors (AIs) have been widely used to suppress estrogen production, but existing inhibitors often cause significant side effects. Computational techniques, such as **molecular fingerprint analysis and clustering methods**, offer an alternative approach to discovering new, safer AIs.

This study aims to:
- Identify structural features essential for optimal aromatase inhibition.
- Provide a foundation for developing new and more effective inhibitors.

## Methodology

### 1. Dataset Preparation
- The dataset is obtained from **ChEMBL (Target ID: CHEMBL1978)**, focusing on human aromatase inhibitors.
- Initial data consists of **157 bioactivity records**; only compounds with **IC50 values** were retained.
- After curation and deduplication, **3,068 unique compounds** with **SMILES notations** were selected.

### 2. Lipinski’s Rule of Five Analysis
To ensure **drug-likeness**, the dataset was filtered using **Lipinski’s Rule of Five**:
- **Molecular Weight (MW) ≤ 500 Da**
- **LogP ≤ 5** (lipophilicity)
- **≤ 5 Hydrogen Bond Donors**
- **≤ 10 Hydrogen Bond Acceptors**
- **pIC50 values** were used as the primary bioactivity measure.

### 3. Molecular Fingerprint Transformation
- SMILES representations were converted into **molecular fingerprints** using **PaDEL**.
- Each compound was represented by **307 structural features**, capturing essential molecular characteristics.

### 4. Clustering Analysis
To group similar compounds, two clustering methods were applied:

#### **K-Means Clustering**
- Dimensionality reduction using **Principal Component Analysis (PCA)**.
- Clustering based on the **sum of squared distances**.
- **Silhouette Score Analysis** determined the optimal **number of clusters = 2**.

#### **DBSCAN Clustering**
- Density-based clustering approach to handle **noise and outliers**.
- **K-Distance Plot Analysis** identified the optimal **epsilon (ε) = 2.58** and **minimum points = 8**.
- Resulted in **two distinct clusters** with a **Silhouette Score of 0.617**.

## Results & Discussion
- **Cluster 0** compounds have:
  - **Higher hydrogen bond donors and acceptors**, improving solubility.
  - **Aromatic rings** that enhance **π–π stacking** interactions.
  - **More rotatable bonds**, allowing better conformational flexibility.

- **Cluster 1** compounds are characterized by:
  - **More primary and secondary carbon atoms**.
  - **1,3- and 1,5-Tautomerization properties**, affecting bioavailability.
  - **Stronger lipophilicity**, which may influence drug absorption.

## Conclusion
This study successfully identified key molecular features influencing aromatase inhibition. **K-Means clustering** provided a clearer separation of bioactive compounds, while **DBSCAN** highlighted structural variations among potential inhibitors. These findings can serve as a basis for **computational drug discovery** of novel aromatase inhibitors.

## Installation & Usage
1. Install required Python libraries:
   ```bash
   pip install pandas numpy seaborn matplotlib scikit-learn
