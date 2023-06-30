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
A very nice illustration that shows the overall structure of data download via ncbi-datasets:
![ncbi-datasets-structure](https://camo.githubusercontent.com/126831e1b7a97c746e0007e6f974f470d68f56d2aec8f31986e9158d1ca7fb73/68747470733a2f2f7777772e6e6362692e6e6c6d2e6e69682e676f762f64617461736574732f646f63732f76322f64617461736574735f736368656d615f636f6d706c6574655f7631342e706e67)
