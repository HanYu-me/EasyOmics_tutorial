---
title: Data Match
category: Analysis
order: 2
---

### Analysis Process
- load the phenotype data and the variant call format (VCF) file. IF the phenotype name is longer than 10 characters, it will be truncated to 10 characters.
- Extract individual codes from phenotype and variant call format (VCF) files
- Excluding individuals lacking phenotype or genotype data. 
- Plink was used to filter the VCF file for minor allele frequency greater than 0.03 and pairwise r2 smaller than 0.99.


### Input and Output
> Input Parameters

|Parameter|Description|
|--|--|
|Upload Phenotype Data File|The phenotype data, format is shown in "Data Preparation".|
|Upload VCF Data File|The VCF data, format is shown in "Data Preparation".|
|VCF File Type|The variant type of the VCF file.|
|Family Information|Whether the family information is included in the phenotype data and vcf data.|
|Other parameters|Other parameters for Plink, which was used to filter the VCF file.|

> Output Results

|Filename|Description|
|--|--|
|a|a|
|a|a|





