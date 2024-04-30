# Liftover between reference genomes

Tasks liks read mapping and variant calling are executed with respect to a reference genome build or version.
For *Homo sapiens* there are currently two commonly used builds: GRCh37 (hg19) and GRCh38 (hg38).
Sometimes you need to convert (liftover) coordinates from one reference build to another, for example to be able to use coordinate-specific annotations or to correctly compare coordinate-specific results file.
Or you might want to do something funkier, like lifting over coordinates between different species.
Here, we collect tools and resources for different coordinate-specific formats and how to use them.

## chain files

> A [chain file](https://genome.ucsc.edu/goldenPath/help/chain.html) describes a pairwise alignment between two reference assemblies. (From the [CrossMap docs](https://crossmap.sourceforge.net/#chain-file))
All the tools mentioned below use a chain file for the liftover process, so will need one for your pair of reference genomes.

### downloading chain files

The [`CrossMap` documentation on chain files](https://crossmap.sourceforge.net/#chain-file) has a good link collection with chain files available from Ensembl and UCSC.
The [`bcftools +liftover` paper](https://doi.org/10.1093/bioinformatics/btae038) suggests, that the UCSC chain files are more comprehensive than the Ensembl chain files:

> For the liftover from GRCh37 to GRCh38, we did not use the Ensembl chain file (GRCh37_to_GRCh38.chain.gz) generated from Ensembl assembly mappings (http://github.com/Ensembl/ensembl/) as this resulted in a much higher rate of variants dropped compared with using the UCSC chain file.

### creating chain files

These tools are untested, but we document them here to try out in the future.
Please report back to this knowledge base on their usage if you come to try them out:

* [nextflow LiftOver workflow](https://nf-lo.readthedocs.io/en/latest/index.html): automatically downloads NCBI or iGenomes references and implements several aligners to create chain files within or between species
* [transanno](https://github.com/informationsea/transanno) can do VCF /GFF3 / GTF file liftover (but bcftools liftover is supposedly better at this), but also provides the [`transanno minimap2-to-chain` command for creating chain files from minimap2 PAF alignments](https://github.com/informationsea/transanno?tab=readme-ov-file#create-chain-file-from-minimap2-result)

## tools

### VCF liftover

#### picard `LiftoverVcf`

For VCF files, Picard offers the command [`LiftoverVcf`](http://broadinstitute.github.io/picard/command-line-overview.html#LiftoverVcf).

**Tested usage for a referene fasta and a callset vcf:**

```
mamba create -n picard picard
mamba activate picard
picard CreateSequenceDictionary  -R {input.reference} -O {input.reference}.dict
picard LiftoverVcf  -I {input.callset}  -O {output} --CHAIN {input.liftover_chain} --REJECT {output}_rejected_variants.vcf -R {input.reference}
```

### `bcftools +liftover` plugin

This looks like a very thorough tool to lift over indels (in addition to SNVs, which all tools are doing OK), judging from the great [paper introducing `bcftools +liftover` plugin](https://doi.org/10.1093/bioinformatics/btae038).
While installation is not easily automated, yet, it is definitely worth trying out [once it is integrated as a plugin into bcftools itself](https://github.com/freeseek/score/issues/4).
Then, it should be [pretty straightforward to conduct a liftover](https://github.com/freeseek/score/tree/master?tab=readme-ov-file#liftover-vcfs).

### other format liftover

#### CrossMap

[CrossMap](https://crossmap.sourceforge.net/) allows for a wider range of formats to be lifted over, including **SAM/BAM/CRAM, VCF, BED, GFF/GTF, MAF, BigWig and Wiggle format**.
It is [available for installation via `bioconda`](https://bioconda.github.io/recipes/crossmap/README.html) and has [very clear usage instructions](https://crossmap.sourceforge.net/#usage), with detailed information for the different formats it supports.
However, analyses by the authors of `bcftools +liftover` and `transanno` suggest, that the VCF/BCF-specific tools perform better on this data type.