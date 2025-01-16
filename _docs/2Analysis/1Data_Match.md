---
title: Data Match
category: Analysis
order: 2
---

### Analysis Process
- Load the phenotype data and the variant call format (VCF) file. IF the phenotype name is longer than 10 characters, it will be truncated to 10 characters.
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
|Other Parameters|Other parameters of the main invoked software (Plink) for this analysis. For example, "--maf 0.1" can be used to set the minor allele frequency threshold to 0.1.|

The example of other parameters:
The "Other Parameters" input box is used to input the parameters of the main invoked software (Plink) for this analysis. This is designed for advanced users who are familiar with the software and want to customize the analysis. After inputting the parameters, the software will automatically generate the command for the analysis.

The command for all the parameters is as follows:
```shell
plink --vcf  --keep --maf 0.03 --indep-pairwise 20 10 0.99 --allow-extra-chr --keep-allele-order --recode vcf --out 
```
If you input other parameters, the command will be:
```shell
plink --vcf  --keep (Other Parameters) --allow-extra-chr --keep-allele-order --recode vcf --out 
```
The other functions also enable users to input the parameters of the main invoked software for this analysis. We suggest users to check the source code for the detailed parameters position and format.



> Output Results

|Filename|Description|
|--|--|
|Time_Matched_vcf.vcf.gz|The matched VCF file.|
|Time_Matched_phe.txt|The matched phenotype file.|
|Time_Phe_name_convert.txt|If the phenotype name is truncated, the original and truncated names are listed in this file.|



### Citation


Chen Z L, Meng J M, Cao Y, et al. A high-speed search engine pLink 2 with systematic evaluation for proteome-scale identification of cross-linked peptides[J]. Nature communications, 2019, 10(1): 3404. https://doi.org/10.1038/s41467-019-11337-z






