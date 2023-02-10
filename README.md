# Galaxy-RNA-Seq-Pipelines

This pipeline is split into 3 parts:
Part 1: Input: .fastq files from a single sample. Removes adapters (Cutadapt), runs quality control (FastQC), aligns to the Drosophila genome (HISAT2), and counts the number of alignments associated with each gene or transcript (featureCount). Part 1 is further broken up to accommodate paired-end reverse strand and paired-end unstranded sequence. Additionally, the paired-end unstranded pathway can accommodate multiple .fastq files per paired end.
Part 2: Input: featureCount output .tabular files from all samples from an experimental condition and all output .tabular files the appropiate control condition. Determines differential gene or transcript expression.
Part 3. Input: Output from 2 DESeq2 or LRPath (Program for GO enrichment analysis from DESeq2 results, http://lrpath.ncibi.org) analyses. Determines which genes or GOs are significantly changed in both conditions, only one condition, or neither condition. This is further broken up to compare the direction of these changes.

Additionally, Parts 1 and 2 have different versions to perform different annotation of features:
Part 1a/2a: Annotates genes.
Part 1b/2b: Annotates individual transcript variants of each genes.
Part 1c: Annotates genes, but takes in edited files of the Drosophila genome (.fasta file) and annotation file (.gtf file) with transgenic gene sequence(s) inserted and stored as a seperate chromosome. The tutorial (.pptx file) will be updated with specifics on how to edit these files.
