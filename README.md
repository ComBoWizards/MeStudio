# MeStudio
MeStudio is a tool which allows us to analyse and combine genome-wide methylation profiles with genomic features.
MeStudio connects several procedural software components that can be run either individually or as part of a pipeline.

*MeStudio version 1.0*

## Table of Content

- Quick start
- Usage
- Reference


## Quick start

Inside the [toyset](/toyset/) folder you are going to find three files:

- FSMMA_genomic.fna
- FSMMA_genomic.gff
- FSMMA_methylation.gff

```FSMMA_genomic.fna``` is the the genome of FSMMA strain of *Sinorhizobium Meliloti*. You can get more informations [here](https://www.ncbi.nlm.nih.gov/data-hub/taxonomy/382/?utm_source=None&utm_medium=referral&utm_campaign=KnownItemSensor:taxname).
```FSMMA_genomic.gff``` is the product of the genomic annotation executed via [Prokka](https://github.com/tseemann/prokka) annotator. The file is reported in GFF3 format.
```FSMMA_methylation.gff``` is the GFF3 file with methylation positions obtained through the sequencer. We performed the analysis using the PacBio RT-SMRT sequencing.
