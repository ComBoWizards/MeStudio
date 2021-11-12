# MeStudio
MeStudio is a tool which allows us to analyse and combine genome-wide methylation profiles with genomic features.
MeStudio connects several procedural software components that can be run either individually or as part of a pipeline: 
- ms_replacR
- ms_core
- ms_analyzR

In particular, input data are represented in three files:
i) a FASTA format file containing the genome sequence
ii) a GFF3 format file of genomic features (e.g. CDS)
iii) a GFF3 format of methylated nucleotide positions

