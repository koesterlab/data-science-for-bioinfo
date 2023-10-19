# differential expression analysis

A classic case of bioinformatic data analysis, is to check whether expression levels of individual transcripts differ between two (or more) groups of samples.
These can be a treatment group compared to a control group, different time points, or groups differing according to any other annotation variable from their metadata.
Up to a certain point, these analyses differ depending on the raw data you start from (for example expression microarrays, full transcriptome RNA-seq data, or specialized RNA sequencing methods).
Thus, we have [one section per data type](#data-types) here, and include linkouts to standardized (snakemake) workflows wherever available, which will make it much quicker for you to get started with your analysis, and much easier to update and/or redo it later.
However, after the initial data processing, differential expression analysis is usually performed by the same (statistical) methods.
Thus, we have [another section dedicated to differential expression analysis tools](#differential-expression-analysis-tools).
Finally, transcripts (or genes) that have been found to be differentially expressed, can be analyzed further---for example via gene set or enrichment or pathway perturbation analysis.
We list some tools for these tasks in the [section `analysis of differentially expressed transcripts`](#analysis-of-differentially-expressed-transcripts)

## data generation / experimental design

A good recap of available research and recommendations is given in the [section `Designing better RNA-seq experiments`](https://www.nature.com/articles/s41576-019-0150-2#Sec13) of this review paper:

[Stark, R., Grzelak, M. & Hadfield, J. **RNA sequencing: the teenage years.** *Nat Rev Genet* 20, 631–656 (2019). https://doi.org/10.1038/s41576-019-0150-2](https://doi.org/10.1038/s41576-019-0150-2)

### number of biological replicates

You should **always include biological replicates** in any RNAseq analysis.
Differential expression analysis tools will either not work at all without biological or the result will not be very useful.
As [Michael Love, the developer of DESeq2 stated](https://support.bioconductor.org/p/95714/#95717), without biological replicates "you have no idea `[of]` the degree of within-group variability, so you can't perform statistical inference (determining if the difference you see is more than you would typically see among replicates within one condition)".

How many biological replicates to include, depends on how sensitive your analysis needs to be and how heterogeneous you expect your replicates to be within sample groups.
Anything below 3 samples is generally discouraged, as [a dedicated study on biological replicate numbers that had low within-group variability/heterogeneity](https://doi.org/10.1261%2Frna.053959.115) could only detect about 85% of expected differentially expressed genes with a fold change of 2 or higher.
Thus, any more sublte fold changes will most likely be missed and the same study required at least 6 biological replicates to detect about 80% of expected differentially expressed genes with a fold change of 1.2 or above.

The general rules here are:

1. If you want to detect differentially expressed genes with smaller effect sizes (lower fold changes), you will need more biological replicates.
2. The more heterogeneity/variability you expect within a group of biological replicates, the more biological replicates you need.
   For example, in vitro experiments with biological replicates from the same cell line should allow for fewer biological replicates, while studies where samples within a group come from different patients will usually require more biological replicates per group.

### sequencing depth

Generally, sequencing depth is not as important a factor as the number of biological replicates.
The above-cited review article concludes that for eukaryotic genomes, around 10 - 30 million reads per sample give good results.

### sequencing length

According to the above-cited review article, if you only want to do general differential expression analysis, single-end reads with a length of at least 50 base pairs should suffice.
If you are also interested in the expression of different transcript isoforms, the detection of fusion gene transcripts or *de novo* transcript assembly, longer paired-end reads will improve the sensitivity of your analyses. 

## data types

### RNA-seq data

TODO: provide good self-contained tutorial for working with RNA-seq data

There are several standardized snakemake workflows, the following ones are maintained by the Kösterlab and associated people: 
* [a workflow using `kallisto` for quantifying transcript expression and `sleuth` (see below)](https://snakemake.github.io/snakemake-workflow-catalog/?usage=snakemake-workflows/rna-seq-kallisto-sleuth) for determining differentially expressed transcripts
* [a workflow using `Star` to align reads to the transcriptome and `DESeq2` (see below)](https://snakemake.github.io/snakemake-workflow-catalog/?usage=snakemake-workflows/rna-seq-star-deseq2) for determining differentially expressed transcripts

### microarray data

While fewer and fewer new microarray data sets are being generated, a lot of existing microarray data sets can be re-analyzed for new research questions.
If you want to get started with such analyses, there is a great hands-on tutorial by Greg Tucker-Kellogg: [Introduction to gene expression microarray analysis in R and Bioconductor](https://gtk-teaching.github.io/Microarrays-R/).
It includes an introduction to Bioconductor, works on publicly available data and is completely self-contained.
You can work through it at your own pace and all it requires is some basic R knowledge---for the latter, see our section on [learning R](../languages/r.md#learning-programming-with-r).

Once you are familiar with the data type and the analysis, there's a [standardized snakemake workflow for microarray analysis](https://snakemake.github.io/snakemake-workflow-catalog/?usage=zifornd/arrays) by James Ashmore.
While we haven't used this workflow ourselves (but might in the future, we'll try to update the info here if we do), this workflow is:
* standardized, so:
  * the above link should take you through all of the setup steps you will need to run this workflow on your own data
  * it is well-structured, so modifying it to your needs should be relatively easy
* based on a [thoroughly peer reviewed walk-through manuscript on microarray analysis](https://doi.org/10.12688/f1000research.8967.2)

This manuscript also gives good and detailed recommendations for microarray analysis in general, so you can also consult it if you are just looking for help on some certain analysis steps.


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
