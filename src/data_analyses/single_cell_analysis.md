# single-cell analysis

## tools

### Moscot

[Moscot](https://moscot.readthedocs.io/en/latest/) is an extremely versatile framework for Optimal Transport (OT) applications in single-cell genomics.
It scales to large datsets and can be used for a variety of applications across different modalities.
This includes trajectory inference, mapping expression to spatial data, aligning spatial transcriptomics slides, and integrating modalities (e.g. RNA-seq and ATAC-seq).

Klein, D., Palla, G., Lange, M. et al.
**Mapping cells through time and space with moscot**
Nature (2025)
https://doi.org/10.1038/s41586-024-08453-2



### LEMUR

The [LEMUR](https://bioconductor.org/packages/release/bioc/html/lemur.html) framework offers a new approach to single cell differential expression analysis.
The "classic" approach is to generate clusters and perform a so-called pseudobulk analysis with conventional statistical approaches for differential gene expression analysis.
Instead, LEMUR integrates the cell clustering with the differential expression analysis, thereby trying to find groups of cells that are separated by consistent fold change patterns.

Ahlmann-Eltze, C., Huber, W.
**Analysis of multi-condition single-cell data with latent embedding multivariate regression**
Nat Genet (2025)
https://doi.org/10.1038/s41588-024-01996-0
