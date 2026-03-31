# Malaria-scrna-clustering
Benchmarking unsupervised machine learning clustering algorithms (Leiden, Louvain, KMeans, and Autoencoder-based KMeans) on Plasmodium falciparum dihydroartemisinin-treated single-cell RNA sequencing data (GEO: GSE234872).
# Benchmarking Unsupervised Machine Learning Clustering Algorithms for *Plasmodium falciparum* Single-Cell Transcriptomics

This repository contains the source code for the manuscript:

> **Benchmarking Unsupervised Machine Learning Clustering Algorithms for *Plasmodium falciparum* Single-Cell Transcriptomics**
> Rachael Emmanuel, Jelili Oyelade
> Department of Computer & Information Sciences, Covenant University, Ota, Nigeria
> *(Manuscript under review)*

---

## Overview

This study benchmarks four unsupervised machine learning clustering algorithms — Leiden, Louvain, KMeans, and Autoencoder-based KMeans (AE-KMeans) — applied to single-cell RNA sequencing (scRNA-seq) data from dihydroartemisinin (DHA)-treated *Plasmodium falciparum* 3D7 parasites. Models are evaluated using the Adjusted Rand Index (ARI), Silhouette Coefficient, execution time, and memory consumption, complemented by biological validation via marker gene analysis, UMAP, and t-SNE visualization.

---

## Dataset

The dataset used in this study is publicly available on the NCBI Gene Expression Omnibus (GEO):

- **Accession:** GSE234872
- **Sample used:** GSM7476110 (*P. falciparum* 3D7, 3 hours post-DHA treatment, 150 nmol/L)
- **BioProject:** PRJNA983399
- **Link:** https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE234872

> Sun J. et al., "Double-kill mechanism of artemisinin against Plasmodium." SSRN preprint. doi: 10.2139/ssrn.4218058

---

## Requirements

The notebook was developed and executed in **Google Colab**. The following Python libraries are required:
```
scanpy
scikit-learn
tensorflow
matplotlib
seaborn
psutil
igraph
leidenalg
python-louvain
numpy
pandas
```

To install all dependencies in Colab or a local environment:
```bash
pip install scanpy scikit-learn tensorflow matplotlib seaborn psutil igraph leidenalg python-louvain numpy pandas
```

---

## How to Run

### Option 1 — Google Colab (recommended)
1. Open the `.ipynb` file in this repository
2. Click **Open in Colab** (or upload it manually to [colab.research.google.com](https://colab.research.google.com))
3. Mount your Google Drive and update the `data_path` variable to point to your local copy of the GSE234872 dataset
4. Run all cells sequentially

### Option 2 — Local environment
1. Clone this repository:
```bash
   git clone https://github.com/Rachael-EO/malaria-scrna-clustering.git
   cd malaria-scrna-clustering
```
2. Install dependencies (see Requirements above)
3. Download the dataset from GEO (GSE234872) and update `data_path` in the notebook accordingly
4. Launch Jupyter and run the notebook:
```bash
   jupyter notebook
```

---

## Repository Structure
```
malaria-scrna-clustering/
│
├── Technical_report.ipynb    # Main analysis notebook
└── README.md                 # This file
```

---

## Results Summary

| Model | ARI | Silhouette Score | Time (s) | Memory (MB) |
|---|---|---|---|---|
| Leiden | 0.7317 | 0.0772 | 10.3047 | 1.97 |
| Louvain | 0.6710 | 0.0514 | 0.8063 | 2.04 |
| KMeans | 0.5282 | 0.1129 | 0.0626 | 0.00 |
| Autoencoder | 0.3769 | 0.0700 | 8.6679 | 0.00 |

---

## Citation

If you use this code or findings in your work, please cite:
```
Rachael Emmanuel, Jelili Oyelade.
Benchmarking Unsupervised Machine Learning Clustering Algorithms for
Plasmodium falciparum Single-Cell Transcriptomics.
Manuscript under review, 2025.
```

*This section will be updated with the full citation upon acceptance.*

---

## Funding

This work was supported by the Covenant Applied Informatics and Communication African Centre of Excellence (CApIC-ACE) and Covenant University Centre for Research, Innovation and Discovery (CUCRID), through the World Bank Africa Centre of Excellence (ACE)-Impact project.

---

## License

This repository is shared for academic reproducibility purposes. Please contact the authors before reuse in other projects.
