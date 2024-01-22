# ncbi-datasets: gathering data across NCBI databases

[ncbi-datasets](https://github.com/ncbi/datasets) is a very-well documented open source tool from NCBI (National Center for Biotechnology Information) for gathering various kinds of data including genes, genomes, annotations etc. belonging to the desired species.
As a side note, it has specific options for retrieving SARS-CoV-2 data.

## Installation

It is offered as a conda package and can be installed via:

```
conda create -n ncbi-download -c conda-forge ncbi-datasets-cli
```

## Example usage

Retrieval of human reference genome:
```
datasets download genome taxon human --reference --filename human-reference.zip
```
Retrieval of genomic assemblies for a specific SARS-CoV-2 lineage with the host being homo sapiens:
```
datasets download virus genome taxon SARS-CoV-2 --complete-only --filename B.1.525.zip --lineage B.1.525 --host "homo sapiens"
```
A very nice illustration that shows the overall structure of data download in the [ncbi-datasets repositories documentation ](https://github.com/ncbi/datasets#use-the-datasets-command-line-tools).
