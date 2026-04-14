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

## Key findings from the summary file
## Clinically Relevant Variants Identified
| Sample | Impact | Variant Type | Amino Acid Change | Clinical Relevance |
|--------|--------|--------------|-------------------|---------------------|
| SRR15274440 | **HIGH** | Splice_acceptor_variant | - | Potentially disrupts mRNA splicing → may affect protein function |
| SRR15274440 | **MODERATE** | Missense | p.Gly269Glu | Amino acid substitution → may alter protein structure |
| SRR15274433 | **MODERATE** | Missense | p.Glu274Val | Amino acid substitution → may alter protein structure |
| SRR15274430 | **MODERATE** | Missense | p.Met263Val | Amino acid substitution → may alter protein structure |
| SRR15274432 | **MODERATE** | Missense | p.Met263Val | Amino acid substitution → may alter protein structure |
| SRR15274529 | **MODERATE** | Missense | p.Ser991Leu | Amino acid substitution → may alter protein structure |

## Impact Distribution Summary
High -- 1 (Likely damaging - affects splicing)
Moderate -- 6 (May affect protein function - missense variants)
Low -- 4 (Likely benign - synonymous variants (no amino acid change)
Modifier -- ~350 (Usually benign - intronic or UTR variants)

## Biological Interpretation
ABL1 is a proto - oncogene that fuses with BCR to form the BCR-ABL1 fusion gene.
This fusion drives Chronic Myeloid Leukemia (CML)
TKI Drugs target this fusion
Mutations in ABL1 are a major cause of TKI resistance
The high impact splice- acceptor variant may (SRR15274440) may alter ABL1 mRna processing
The moderate impact missense variants may change ABL1 protein structure
These variants could potentially contribute to TKI resistance in affected patients.



