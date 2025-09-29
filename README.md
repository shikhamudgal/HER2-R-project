# HER2 Biomarker Analysis in Breast Cancer

R scripts from my PhD research at AIIMS Rishikesh exploring HER2 amplification and co-expressed genes (PGAP3, GRB7, STARD3, CDK12, PSMD3, GSDMB) in breast cancer using publicly available datasets from GEO.

---

## Background

HER2 overexpression is an important **prognostic and predictive biomarker** in breast cancer, guiding targeted therapy such as trastuzumab.  
Current testing relies on **IHC** and reflex **ISH** for equivocal (2+) cases, but ISH is expensive and not widely available in low-resource settings.  

This project investigates whether **genes co-amplified with HER2** can act as **surrogate IHC markers**, reducing reliance on ISH.

---

## Data

Data were sourced from the **NCBI Gene Expression Omnibus (GEO)**:  
- Datasets used were: 
-   MAINZ is used for GSE11121 (https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE11121)
-   TRANSBIG is used for GSE7390 (https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE7390)
-   EMC1 is used for GSE2034 (https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE2034)
-   EMC2 is used for GSE5327 (https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE5327)
- Affymetrix HGU133A platform expression data  

---

## Methods

- Download datasets via `GEOquery`
- Process Affymetrix CEL files using **frma** normalization
- Collapse probe-level data to genes
- Classify samples into PAM50 molecular subtypes
- Run **Cox proportional hazards survival analysis**
- Evaluate correlation of HER2 with candidate co-expressed genes

### Key R Packages
`GEOquery`, `affy`, `hgu133a.db`, `Biobase`, `genefu`, `survival`, `coxme`, `WGCNA`, `frma`, `ggplot2`

---

## How to Run

Clone the repo:
```bash
git clone https://github.com/USERNAME/HER2-R-project.git
cd HER2-R-project
