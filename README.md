# ABL1- Germline Variant Calling

## Overview
This project performs germline variant calling on Chronic Myeloid Leukemia (CML) patient samples, focusing on the ABL1 gene – a key oncogene involved in Tyrosine Kinase Inhibitor (TKI) resistance.

Dataset - GSE180965 (NCBI GEO) 
Samples 17 - (PBMC + BMMC from CML patients) 
Target Gene - ABL1 
Reference Genome Ensembl - GRCh38 (release 115) 
Platform - Ubuntu Linux (Conda environment)

## Objectives
- Download WGS data from NCBI SRA using AWS CLI
- Perform quality control and adapter trimming
- Align reads to chr9 reference genome using STAR
- Process BAM files (Add Read Groups, Mark Duplicates, SplitNCigar)
- Call variants using GATK HaplotypeCaller
- Filter and annotate variants using SnpEff
- Extract ABL1-specific variants for clinical interpretation

  ##  Tools & Technologies

 Category | Tools 
|----------|-------|
**Environment** | Conda / Mamba 
**Data Download** | AWS CLI, SRA Tools, Entrez Direct 
 **Quality Control** | FastQC, MultiQC, Trim Galore 
**Alignment** | STAR (splice-aware aligner) 
 **BAM Processing** | SAMtools, GATK 
 **Variant Calling** | GATK HaplotypeCaller 
 **Filtering** | GATK VariantFiltration 
**Annotation** | SnpEff, SnpSift 
**Reference** | Ensembl GRCh38 (chr9 FASTA + GTF) 


