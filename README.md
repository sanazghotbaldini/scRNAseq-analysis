markdown
# scRNA-seq Analysis Pipeline

## Overview
End-to-end single-cell RNA sequencing analysis pipeline for tumor 
transcriptomics, including QC, clustering, annotation, and downstream 
functional analysis.

## Pipeline Steps
| Step | Script | Description |
|------|--------|-------------|
| 1 | 01_ambient_removal | Ambient RNA removal (SoupX) |
| 2 | 02_doublet_removal | Doublet detection (scDblFinder) |
| 3 | 03_qc_filtering | Quality control filtering |
| 4 | 04_merge_metadata | Sample merging + metadata integration |
| 5 | 05_normalization | Normalization, PCA, UMAP |
| 6 | 06_annotation | Cell type annotation |
| 7 | 07_subclustering | Cell-type-specific subclustering |
| 8 | 08_proportion | Cell proportion analysis |
| 9 | 09_pathways | Pathway enrichment analysis |
| 10 | 10_visualization | Figures and plots |

## Key Methods
- **Normalization:** SCTransform
- **Batch correction:** Harmony
- **Annotation:** SingleR + UCell + manual curation
- **Pathway analysis:** fgsea

## Dependencies
```r
Seurat, SoupX, scDblFinder, harmony,
UCell, fgsea, ComplexHeatmap, ggplot2
```

## Cell Types Analyzed
Immune, stromal, and epithelial compartments including major and 
rare cell populations identified via unsupervised clustering and 
marker-based annotation.

## Note
Raw data not included. Analysis begins from post-CellRanger count matrices.
