# Single-Cell MR Discovery, Replication, and Colocalization Pipeline

This repository contains an end-to-end R pipeline for integrating single-cell eQTL data with GWAS summary statistics to perform:

1. **Discovery Mendelian Randomization (MR)**  
2. **Replication MR**  
3. **Colocalization Analysis**

as applied to 14 immune cell types in PBMCs and any outcome of choice.

---

## 📖 Overview

Bulk transcriptome-wide association studies (TWAS) can miss cell-specific regulatory effects. This pipeline uses:

- **Single-cell cis-eQTLs** from the OneK1K cohort (N=982) for discovery  
- **Single-cell cis-eQTLs** from 1M-scBloodNL (N=120) for replication  
- **MR** (TwoSampleMR) to infer causal links between gene expression and disease  
- **Colocalization** (coloc.abf / coloc.susie) to confirm shared causal variants  

---

## 🚀 Prerequisites

- R (≥4.0)  
- PLINK (for local LD clumping)  
- R packages:
  ```r
  install.packages(c(
    "readxl", "readr", "dplyr", "data.table", "writexl", "meta",
    "genetics.binaRies", "TwoSampleMR", "MRInstruments", "coloc"
  ))
  # For coloc.susie:
  remotes::install_github("chr1swallace/coloc")
