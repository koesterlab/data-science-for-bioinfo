# TCGA and TARGET datasets

## GDC data portal

The [Genomic Data Commons (GDC) data portal](https://portal.gdc.cancer.gov/) is a good place to start exploring the data available via [The Cancer Genome Atlas Program (TCGA)](https://www.cancer.gov/ccg/research/genome-sequencing/tcga) and the [Therapeutically Applicable Research to Generate Effective Treatments (TARGET)](https://www.cancer.gov/ccg/research/genome-sequencing/target) programs.
However, this interface does not really offer any easy ways of programatically accessing and reanalysing this data.
Thus, we provide some tools and resources below, that should make this easier.

## TCGAbiolinks

[`TCGAbiolinks`](https://bioconductor.org/packages/release/bioc/html/TCGAbiolinks.html) is a well-documented bioconductor package for working with GDC data.
In addition to the TCGA and TARGET projects, TCGAbiolinks also provides access to gene expression from healthy individuals via the public [Genotype-Tissue Expression Project (GTEx)](https://www.genome.gov/Funded-Programs-Projects/Genotype-Tissue-Expression-Project) data.
Check out the [main bioconductor landing page for `TCGAbiolinks`](https://bioconductor.org/packages/release/bioc/html/TCGAbiolinks.html) for the original papers introducing the functionality and for links to [the extensive documentation with walkthroughs](https://bioconductor.org/packages/release/bioc/vignettes/TCGAbiolinks/inst/doc/index.html).
In addition, the [`TCGAWorkflow` vignette](https://bioconductor.org/packages/release/workflows/vignettes/TCGAWorkflow/inst/doc/TCGAWorkflow.html) shows how to use it for reanalysis of TCGA data.
