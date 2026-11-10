# Topological Network Analysis of Papua New Guinea Development Indicator System (1960–2025)

**Author:** Reynolds Lyakisa  
**Supervisor:** Dr. Manshoore Kazimilare  
**Institution:** School of Mathematics and Computer Science, Papua New Guinea University of Technology (Lae, Papua New Guinea)  
**Degree:** Master of Science in Applied Mathematics (November 2026)

---

## Overview
This repository contains the datasets, MATLAB scripts, Python notebooks, Minimum Spanning Tree (MST) objects, and topological metrics for the thesis *"Topological Network Analysis of Papua New Guinea Development Indicator System (1960–2025)"*. 

Using a strict complete-case filter on 1,516 raw World Bank World Development Indicators (WDI), this study isolates **86 continuous indicators** (1960–2024) partitioned into four functional domains across the full period and two historical eras:
* **Group A (Macro/Financial):** 20 indicators
* **Group B (Population):** 20 indicators
* **Group C (Age 0–44):** 24 indicators
* **Group D (Age 45+):** 22 indicators
* **Study Periods:** Full Period (1961–2024), Era 1 (1961–1994), and Era 2 (1995–2024)

---

## Repository Structure
```text
├── README.md
├── LICENSE
├── .gitignore
├── data/
│   ├── raw/
│   │   └── WDI_PNG_Raw_Data.xlsx
│   ├── processed/
│   │   ├── Group_A_Macro.xlsx
│   │   ├── Group_B_Population.xlsx
│   │   ├── Group_C_AgeYoung.xlsx
│   │   └── Group_D_AgeOlder.xlsx
│   └── metadata/
│       └── WDI_PNG_Indicator_Metadata.xlsx
├── networks/
│   ├── Group_A_Full_MST.mat
│   ├── Group_A_Era1_MST.mat
│   ├── Group_A_Era2_MST.mat
│   ├── Group_B_Full_MST.mat
│   ├── Group_B_Era1_MST.mat
│   ├── Group_B_Era2_MST.mat
│   ├── Group_C_Full_MST.mat
│   ├── Group_C_Era1_MST.mat
│   ├── Group_C_Era2_MST.mat
│   ├── Group_D_Full_MST.mat
│   ├── Group_D_Era1_MST.mat
│   ├── Group_D_Era2_MST.mat
│   └── Group_Distance_Matrices/
├── code/
│   ├── preprocessing/
│   │   ├── 01_complete_case_filter.m
│   │   ├── 02_domain_classification.m
│   │   ├── 03_log_modulus_transform.m
│   │   └── 04_first_differencing.m
│   ├── network_construction/
│   │   ├── 05_pearson_correlation.m
│   │   ├── 06_distance_transformation.m
│   │   └── 07_mst_construction.m
│   ├── metrics/
│   │   ├── 08_node_metrics.m
│   │   ├── 09_global_metrics.m
│   │   └── 10_domain_era_summary.m
│   └── python/
│       └── colab_exploratory_and_visualization.ipynb
└── results/
    ├── PNG_Domain_Metrics.xlsx
    └── All_Topological_Measures.xlsx
```

---

## Reproduction Instructions

### 1. Local Machine (MATLAB Pipeline)
1. Clone or download this repository to your local machine.
2. Open **MATLAB** and set the repository root folder as your Current Folder.
3. Run the scripts inside `code/` in numerical order (`01` through `10`):
   * **Preprocessing (`01`–`04`):** Filters raw WDI data, partitions domains, applies log-modulus transformation, and computes first differences.
   * **Network Construction (`05`–`07`):** Computes Pearson correlation matrices, transforms correlations into Euclidean metric distances ($d_{ij} = \sqrt{2(1 - r_{ij})}$), and constructs the 12 domain-era Minimum Spanning Trees.
   * **Metrics (`08`–`10`):** Calculates the 4 node-level and 6 global topological metrics and exports them to `results/`.

### 2. Google Colab (Python Supplementary Analysis)
1. Open the `.ipynb` notebook(s) located in `code/python/` directly in **Google Colab** using the *Open in Colab* badge or via `File > Open notebook > GitHub`.
2. Mount or upload the spreadsheets from `data/processed/` and `results/` to reproduce summary tables and cross-domain visualizations.

---

## License & Copyright
**Copyright © 2026 Reynolds Lyakisa. All Rights Reserved.**  
This repository is proprietary. Academic examiners and authorized reviewers are granted permission solely to view and execute the code for thesis evaluation. See the `LICENSE` file for full terms.
