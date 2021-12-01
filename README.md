# MeStudio
MeStudio is a tool which allows us to analyse and combine genome-wide methylation profiles with genomic features.
MeStudio connects several procedural software components that can be run either individually or as part of a pipeline.

*MeStudio version 1.0*

## Table of Content

- Quick start
- Usage
- MeStudio ReplacR
- MeStudio Core
- MeStudio AnalyzR
- Results
- Reference


## Quick start

Inside the [toyset](/toyset/) folder you are going to find three files:

- FSMMA_genomic.fna
- FSMMA_genomic.gff
- FSMMA_methylation.gff

```FSMMA_genomic.fna``` is the the genome of FSMMA strain of *Sinorhizobium meliloti*. You can get more informations [here](https://www.ncbi.nlm.nih.gov/data-hub/taxonomy/382/?utm_source=None&utm_medium=referral&utm_campaign=KnownItemSensor:taxname).
```FSMMA_genomic.gff``` is the product of the genomic annotation executed via [Prokka](https://github.com/tseemann/prokka) annotator. The file is reported in GFF3 format.
```FSMMA_methylation.gff``` is the GFF3 file with methylation positions obtained through the sequencer. We performed the analysis using the PacBio RT-SMRT sequencing.


## Usage

to add

## MeStudio ReplacR
In order to properly run MeStudio Core, a pre-processing python-based script named ms_replacR has been implemented and is highly suggested to be used. You can find the source code here.
ms_replacR expects seven arguments:
1. *input directory*, where the file to analyse are located
2. *output directory*, in which results and log files will be written
3. *genomic annotation*, in the GFF3 format
4. *methylation annotation*, a sequencer-produced modified base calls in the GFF3 format
5. *genomic sequence*, in fasta or fna file format
6. *input* string type field
7. *output* string type field


The last flags (.6 and .7) are used to communicate a certain character or string to replace.
As a matter of fact MeStudio requires consistent formatting as far as the sequence identifiers are concerned but sometimes the annotation process can lead to
genomic headers alterations for what concern “seqid” fields identity and special characters (e.g. a pipe symbol replaced by the underscore).

An example is reported here down below:

```FSMMA_genomic.fna```

> 000000F|arrow
> 
> GCCGGTCCAGCGCAAAACCCTCGCTCGGCGTGATCGAGAGTATGCGCTGCGAGCCGAGGT
> CGGGCCAGAAGAGCTTCGAATTCACGAGCCGGAAATGCGGTGCGACGATAACGCGTTCGA
> GCTGCTCTTCCGAAACATTGGCGAGCGCGAACACGGCCCAGTCACCCTGGTGATTTTCCG
> TGCTGGAACGCACTTCGATGCGTCTGACGATGCCGTCCGTGCCGGGGGCGGTCGAAACCT
> GAAAGGCGTCGCCTCTGCCGCTGTAGATCTCCGTCGTGGCGGTAAGATCGAGCGCCGTGT

```FSMMA_genomic.gff```
> 000000F_arrow	Prodigal:2.6	CDS	95	538	.	+	0	ID=JPHAALHC_00001

As you can see, the header of the fasta file has a pipe as delimeter while the *seqid* column of the GFF3 file as the underscore as delimeter.
This difference in the formatting syntax can create some troubles and here the last flags are crucial to fix the problem.

More over, depending on the annotator, we noticed that sometimes we can find different order of the contigs between fasta and GFF3 files.
```ms_replacR``` also fix this kind of anomaly in order to avoid biased results.



