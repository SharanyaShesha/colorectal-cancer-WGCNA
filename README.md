# colorectal-cancer-WGCNA
Identification of key genes in colorectal cancer diagnosis using Weighted Gene Co-Expression Network Analysis (WGCNA) on GEO and TCGA datasets.

# Identification of Key Genes in Colorectal Cancer Using WGCNA

This project applies **Weighted Gene Co-Expression Network Analysis (WGCNA)** to identify key genes and potential biomarkers involved in the diagnosis and progression of **Colorectal Cancer (CRC)**. Leveraging public gene expression datasets from GEO and TCGA, this study reconstructs co-expression networks, identifies hub genes, explores their functional roles, and evaluates their prognostic value.

Developed as part of the **INFO-B 646: Computational Systems Biology** course at Indiana University, this analysis integrates systems biology, transcriptomics, survival analysis, and drug repurposing techniques.

---

## Overview

Colorectal cancer is one of the most common and deadly cancers worldwide. Early detection can greatly improve survival outcomes, yet current biomarker strategies are limited. This project uses WGCNA, a systems-level approach, to uncover modules of highly correlated genes and identify **hub genes** that are not only differentially expressed but are also clinically significant.

---

## Project Objectives

- Identify **differentially expressed genes (DEGs)** in CRC tissue vs. normal tissue.
- Construct gene co-expression networks using **WGCNA**.
- Discover gene modules correlated with clinical traits such as tumor stage and metastasis.
- Perform **GO and KEGG enrichment analysis** to uncover functional pathways.
- Construct **PPI networks** and identify hub genes using **Cytoscape**.
- Validate hub gene expression in **TCGA** and additional GEO datasets.
- Perform **survival analysis** to evaluate prognostic relevance.
- Explore **miRNA–mRNA interactions** and identify drug targets via **DGIdb**.

---

## Datasets Used

| Dataset      | Source | Description |
|--------------|--------|-------------|
| **GSE41258** | GEO    | mRNA expression from 54 normal & 186 CRC samples |
| **GSE68204** | GEO    | miRNA expression from 8 normal & 37 CRC samples |
| **GSE62322** | GEO    | Validation dataset for CRC (20 normal & 18 tumor) |
| **TCGA-COAD**| TCGA   | Colon Adenocarcinoma cohort for validation and survival analysis |

---

## Analysis Notebook

All steps are documented in a single R Markdown notebook:  
**[CRC_WGCNA_analysis.Rmd](CRC_WGCNA_analysis.Rmd)**

This includes:
- Preprocessing & normalization
- DEG & DEmiR identification using `limma`
- Network construction using `WGCNA`
- Module–trait correlation heatmaps
- GO/KEGG enrichment using `clusterProfiler`
- PPI & hub gene selection using `Cytoscape + CytoHubba`
- Validation using `TCGAbiolinks` & `GEPIA`
- Drug interactions via `DGIdb` and miRNA networks via `multiMiR`

---

## 📈 Results Highlights

- **Identified 746 DEGs** (266 upregulated, 480 downregulated)
- Constructed WGCNA modules and found **Blue & Turquoise modules** linked to CRC stage
- Identified **8 key hub genes** (COL1A1, COL1A2, COL5A1, COL5A2, COL10A1, COL11A1, BGN, THBS2)
- Functional enrichment pointed to **extracellular matrix remodeling** and **collagen formation**
- **7/8 hub genes correlated with poor prognosis** (p < 0.05)
- Found **38 drug-gene interactions**, highlighting repurposable CRC therapies

---

##  Visual Snapshots

| Plot                          | Description                        |
|------------------------------|------------------------------------|
| Volcano Plot                 | DEGs in tumor vs. normal tissue    |
| Module Dendrogram            | Gene clustering from WGCNA         |
| Correlation Heatmap          | Modules vs. clinical traits        |
| PPI Network                  | Protein interactions & hub genes   |
| Survival Curves              | Kaplan-Meier plots for hub genes   |
| Drug Interaction Network     | Drug–gene associations (DGIdb)     |

*You can find visual outputs in the `results/` folder.*
---

## Tools & Packages

### R Packages:
- `WGCNA`, `limma`, `clusterProfiler`, `TCGAbiolinks`, `multiMiR`

- ### External Tools:
- **[Cytoscape v3.7.1](https://cytoscape.org/)**  
  Used for visualizing protein–protein interaction (PPI) networks.
  
- **CytoHubba Plugin for Cytoscape**  
  Used to identify hub genes in the network using three topological methods: Degree, MCC, and MNC.

### Web Resources:
- [STRING database](https://string-db.org/)
- [GEPIA2](http://gepia2.cancer-pku.cn/)
- [DGIdb – Drug-Gene Interaction database](https://www.dgidb.org/)
---
---

## 📦 Installation

Install key R dependencies using:

```r
install.packages(c("WGCNA", "limma", "clusterProfiler", "TCGAbiolinks", "multiMiR"))


## **Authors**
**Sharanya Sheshadri** 
Ellie Cates
Saranya Guvvala
Noah Hamilton

## **Citation** 
If you use this project or parts of the analysis, please cite our course project. 

