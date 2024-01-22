# sequencing data (fastq)

## general purpose (swiss army knife) tools

[seqkit](https://bioinf.shenwei.me/seqkit/) has a lot of subcommands for most of the operations you might ever want to do on `fastq` or `fasta` files.
It [is really quick](http://bioinf.shenwei.me/seqkit/usage/#technical-details-and-guides-for-use) and [well-documented](https://bioinf.shenwei.me/seqkit/usage/).

## tools for downloading from repositories

### fastq-dl

[fastq-dl](https://github.com/rpetit3/fastq-dl) lets you download FASTQ data from the European Nucleotide Archive or the Sequence Read Archive repositories.
It allows you to use any ENA/SRA accession number, for a `Study`, a `Sample`, an `Experiment`, or a `Run`.

## Splitting FASTQ data

### fastqsplitter

[Fastqsplitter](https://github.com/LUMC/fastqsplitter) is a tool that allows you to split FASTQ files into a desired number of output files _evenly_.

Installation of fastqsplitter via conda:
```
mamba create -n fastqsplitter -c bioconda fastqsplitter
```
Usage of fastqsplitter:
```
fastqsplitter -i input.fastq.gz -o output_1.fastq.gz -o output_2.fastq.gz -o output_3.fastq.gz
```
In the example above, fastqsplitter divides the input fastq into 3 evenly distributed fastq files through inferring this number from the outputs that are specified by the user.
