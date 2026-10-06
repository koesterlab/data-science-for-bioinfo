# Sequencing

Sequencing reads out the order of bases (A, C, G, T) in DNA or RNA fragments. The output is text strings called reads. These are aligned to a reference genome or assembled de novo (from scratch, without a reference). Then they are counted or compared.

The molecule (RNA or DNA) you start from and how you prepare it (the assay) decide what you measure. The sequencer itself is nearly the same for all assays. Most "different sequencing types" are therefore different library preparations.

In library preparation, the sample is turned into fragments the sequencer can read. Illumina sequencers can only read DNA (only Nanopore can read RNA directly), so RNA is first converted into cDNA (complementary DNA): the enzyme reverse transcriptase builds a DNA copy of each RNA molecule. The DNA is then cut into short fragments, and adapters (short known sequences) are attached to both ends. Primers are short DNA pieces that bind to these adapters and serve as starting points for copying. PCR then copies the fragments exponentially, because the starting material (especially from a single cell) is far too little for the sequencer to detect.

Different sequencers produce either short reads (Illumina) or long reads (PacBio HiFi, Oxford Nanopore). Short reads are the standard format: cheap and very accurate. Long reads are more expensive (and Nanopore has more errors), but they span repeats and whole transcripts, which makes alignment and assembly easier.

The type of data to investigate determines the type of assay:

- DNA-based assays (WGS, WES) measure what *can* happen. The genome is (almost) the same in every cell.
- Epigenomic assays (ATAC, ChIP, methylation, Hi-C) measure what is *allowed* to happen. They show which regions are open, marked or silenced, and this differs by cell type.
- RNA-seq measures what *is* happening: which genes are actually transcribed right now.


| Assay | Input | Measures | Typical question | Omics layer |
|---|---|---|---|---|
| WGS (whole-genome sequencing) | DNA | Full genome sequence | Which variants (SNPs, indels, structural variants) does this individual carry? | Genomics |
| WES (whole-exome sequencing) | DNA, exons only | Coding regions (~1–2 % of the genome) | Are there protein-altering mutations? Cheaper than WGS. | Genomics |
| RNA-seq | RNA → cDNA | Which transcripts are present and how many | Which genes are expressed, and how strongly? Differential expression, isoforms | Transcriptomics |
| ATAC-seq | Chromatin (nuclei) | Open / accessible chromatin | Which regulatory regions are active in this cell type? | Epigenomics |
| ChIP-seq / CUT&RUN / CUT&Tag | Chromatin + antibody | Where a specific protein (TF) or histone mark binds | Where does TF X bind? Where are active promoters and enhancers (e.g. H3K27ac)? | Epigenomics |
| Bisulfite-seq (WGBS) / EM-seq | DNA | DNA methylation (CpG) at single-base resolution | Which promoters are silenced by methylation? | Epigenomics |
| Hi-C / 4C-seq | Crosslinked chromatin | 3D contacts in the nucleus (Hi-C: all vs. all, 4C: one region vs. all) | Which enhancer contacts which promoter? | Epigenomics |

## Single-Cell Sequencing

Classical bulk assays measure a tissue sample of thousands to millions of cells and report the average, but tissues are mixtures of cell types. A bulk average hides rare cell types and can mix up two real signals. Single-cell methods measure each cell separately. This works for RNA-seq and ATAC-seq.
All RNA molecules (or DNA fragments for ATAC) from one cell get the same cell barcode. For RNA, each molecule additionally gets a UMI (unique molecular identifier), so PCR copies of the same molecule can be counted only once. Everything is then sequenced together and sorted back to cells by barcode.
