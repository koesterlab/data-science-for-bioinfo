# Data formats and tools

This section gathers common bioinformatics data formats, where you can find specifications of them and which tools you can use to handle them sanely.

## bioconvert: converting between bioinformatics file formats

There's a plethora of bioinformatics file formats, and you often need to convert from on to another.
[`bioconvert`](https://bioconvert.readthedocs.io/en/dev/) is a tool that integrates as many of these conversions as possible.
It's a community effort, so feel free [to contribute a converter](https://github.com/bioconvert/bioconvert/issues/1) if the one you need doesn't exist, yet, but you found (or implemented) a tool that can do it.

## Liftover between reference genomes

Tasks liks read mapping and variant calling are executed with respect to a reference genome. For Homo sapiens there are currently two commonly used reference genomes: grch37 (hg19) and grch38 (hg38). Sometimes a conversion (liftover) of resulting files from one reference to another is needed.

For VCF files Picard offers the command [`LiftoverVcf`](http://broadinstitute.github.io/picard/command-line-overview.html#LiftoverVcf).

Example liftover chain from grch37 to grch38: http://ftp.ensembl.org/pub/assembly_mapping/homo_sapiens/GRCh37_to_GRCh38.chain.gz

**Usage for a referene fasta and a callset vcf:**
 ```
 mamba create -n picard picard
 mamba activate picard
 picard CreateSequenceDictionary  -R {input.reference} -O {input.reference}.dict
 picard LiftoverVcf  -I {input.callset}  -O {output} --CHAIN {input.liftover_chain} --REJECT {output}_rejected_variants.vcf -R {input.reference}```

 

