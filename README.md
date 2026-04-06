# scRNA-seq Analysis of Human PBMCs

Single-cell RNA sequencing analysis of 2,700 human blood cells using Python and Scanpy. Identified 10 distinct immune cell populations from raw sequencing data.

---

## Final UMAP

![Annotated UMAP](figures/umap_annotated.png)

---

## What I did

1. **Loaded** the PBMC 3k dataset (2,700 cells × 32,738 genes)
2. **Quality control** — removed low quality and dying cells using mitochondrial gene percentage
3. **Normalized** gene counts and selected 1,865 highly variable genes
4. **Clustered** cells using PCA + Leiden algorithm
5. **Annotated** each cluster using known immune cell marker genes

---

## Cell types identified

| Cluster | Cell Type | Marker Genes |
|---|---|---|
| 0 | CD4 T naive | CD3E, IL7R, CD4 |
| 1 | CD14 Monocytes | LYZ, CD14 |
| 2 | B cells | CD79A, MS4A1, CD19 |
| 3 | CD4 T memory | IL7R, S100A4, CCL5 |
| 4 | CD8 T cells | CD8A, CD8B |
| 5 | NK cells | GNLY, NKG7, GZMB |
| 6 | CD8 T effector | CD8A, GZMK |
| 7 | NK / T mixed | NKG7, CD3D |
| 8 | Dendritic cells | FCER1A |
| 9 | Platelets | PPBP, PF4 |

---

## Tools used

- Python 3.10
- Scanpy
- Leiden clustering
- UMAP

---

## How to run

```bash
conda create -n scrna python=3.10 -y
conda activate scrna
pip install scanpy leidenalg umap-learn
jupyter lab scRNA_PBMC_analysis.ipynb
```

The dataset downloads automatically on first run — no manual download needed.

---

## Author

Athira
