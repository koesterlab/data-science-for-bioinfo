# differential expression analysis

A classic case of bioinformatic data analysis to check whether expression levels of individual transcripts differs between two (or more) groups of samples.
These can be a treatment group compared to a control group, different time points, or groups differing according any other annotation variable from their metadata.
Up to a certain point, these analyses differ depending on the raw data you start from (for example expression microarrays, full transcriptome RNA-seq data, or specialized RNA sequencing methods).
Thus, we have [one section per data type](#data-types) here, and include linkouts to standardized (snakemake) workflows wherever available, which will make it much quicker for you to get started with your analysis, and much easier to update and/or redo it later.
However, after the initial data processing, differential expression analysis is usually performed by the same (statistical) methods.
Thus, we have [another section dedicated to differential expression analysis tools](#differential-expression-analysis-tools).
Finally, transcripts (or genes) that have been found to be differentially expressed, can be analyzed further---for example via gene set or enrichment or pathway perturbation analysis.
We list some tools for these tasks in the [section `analysis of differentially expressed transcripts`](#analysis-of-differentially-expressed-transcripts)

## data types

### microarray data

While fewer and fewer new microarray data sets are being generated, a lot of existing microarray data sets can be re-analyzed for new research questions.
If you want to get started with such analyses, there is a great hands-on tutorial by Greg Tucker-Kellogg: [Introduction to gene expression microarray analysis in R and Bioconductor](https://gtk-teaching.github.io/Microarrays-R/).
It includes an introduction to Bioconductor, works on publicly available data and is completely self-contained.
You can work through it at your own pace and all it requires is some basic R knowledge---for the latter, see our section on [learning R](../languages/r.md#learning-programming-with-r).

Once you are familiar with the data type and the analysis, there's a [standardized snakemake workflow for microarray analysis](https://snakemake.github.io/snakemake-workflow-catalog/?usage=zifornd/arrays) by James Ashmore.
While we haven't used this workflow ourselves (but might in the future, we'll try to update the info here if we do), this workflow is:
* is standardized, so:
  * the above link should take you through all of the setup steps you will need to run this workflow on your own data
  * it is well-structured, so modifying it to your needs should be relatively easy
* based on a thoroughly peer reviewed walk-through manuscript on microarray analysis: https://doi.org/10.12688/f1000research.8967.2

### RNA-seq data

TODO: provide good self-contained tutorial for working with RNA-seq data

There are several standardized snakemake workflows, the following ones are maintained by the Kösterlab and associated people: 
* a workflow using `kallisto` for quantifying transcript expression and [`sleuth`](#sleuth) for determining differentially expressed transcripts: https://snakemake.github.io/snakemake-workflow-catalog/?usage=snakemake-workflows/rna-seq-kallisto-sleuth
* a workflow using `Star` to align reads to the transcriptome and [`DESeq2`](#deseq2) for determining differentially expressed transcripts: https://snakemake.github.io/snakemake-workflow-catalog/?usage=snakemake-workflows/rna-seq-star-deseq2

## differential expression analysis tools

### sleuth

TODO: add some info
[`sleuth` walkthroughs for different analyses types](https://pachterlab.github.io/sleuth/walkthroughs)

### DeSEQ2

TODO: add some info
[extensive HTML documentation page for `DESeq2`](https://bioconductor.org/packages/release/bioc/vignettes/DESeq2/inst/doc/DESeq2.html)
[main bioconductor package page for `DESeq2`](https://bioconductor.org/packages/release/bioc/html/DESeq2.html)

### edgeR

TODO: add some info
[extensive PDF user guide for `edgeR`](https://bioconductor.org/packages/release/bioc/vignettes/edgeR/inst/doc/edgeRUsersGuide.pdf)
[main bioconductor package page for `edgeR`](https://bioconductor.org/packages/release/bioc/html/edgeR.html)

## analysis of differentially expressed transcripts

### gene set enrichment

### pathway enrichment

### pathway perturbation
