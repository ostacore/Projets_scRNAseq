# Projets_scRNAseq: GO Enrichment Analysis

Tutorial on **Gene Ontology (GO) enrichment** of single-cell RNA-seq data. We compare two methods for interpreting the differentially expressed genes of a cell cluster:

- **ORA (Over-Representation Analysis)**: hypergeometric test on a *filtered* list of significant genes (up or down).
- **GSEA (Gene Set Enrichment Analysis)**: uses *all* genes ranked by log2FC, with no cutoff; the NES gives the direction (activated or suppressed).

Dataset: [10k brain cells from an E18 mouse](https://www.10xgenomics.com/datasets/10-k-brain-cells-from-an-e-18-mouse-v-3-chemistry-3-standard-3-0-0) (10x Genomics).
Main tools: `Seurat`, `scDblFinder`, `clusterProfiler`, `org.Mm.eg.db`, `enrichplot`.

## Pipeline

1. QC, doublet removal, normalization, PCA, clustering, UMAP (Seurat)
2. Cluster annotation with canonical markers and differential expression
3. ORA and GSEA on GO Biological Process terms for a target cluster

## Repository structure

```
code/GO_Tutorial.qmd     Quarto tutorial (full pipeline + GO enrichment)
data/raw_data/           10x count matrix (not tracked, see below)
data/processed_data/     Cached .rds results (not tracked)
plots/                   Generated figures
```

## Usage

1. Download the `raw_feature_bc_matrix` folder from the dataset page and place it in `data/raw_data/`.
2. Open `Projets_scRNAseq.Rproj` in RStudio.
3. Run or render `code/GO_Tutorial.qmd`. Missing packages are installed automatically.

## Authors

Corentin OSTA, Azzeddine Aliliche & Anais Hluszko
