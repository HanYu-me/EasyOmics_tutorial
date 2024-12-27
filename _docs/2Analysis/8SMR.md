---
title: SMR
category: Analysis
order: 9
---

### Analysis Process

- Converts the input data to the format required by the SMR software.
- Uses SMR software to analyze whether the instrumental variable SNP affects the trait through the molecular trait.
- Conducting parallel analysis for each molecular trait. 
- Visualizes the results of the analysis.

### Input and Output

> Input Parameters

|Parameter|Description|
|--|--|
|Upload Omic QTL Result of Exposure| The eqtl.txt file from the "Omic QTLs" analysis of the exposure trait. Exposure trait means the trait that is a potential cause of outcome trait.|
|Upload GWAs Result of Outcome| The .mlma file from the "GWAs" analysis of the outcome trait. Outcome trait means the trait that is a potential result of exposure trait.|
|Upload VCF Data File| The VCF data, format is shown in "Data Preparation".|
|Upload GFF Data File| The genome annotation GFF data, format is shown in "Data Preparation".|
|Select GFF Type| The type of GFF file. If the probe of omic data is located in the genome and (1) is gene, upload the genome annotation GFF file. (2) is not gene, upload the probe position GFF like file.|
|Threshold| A value setting the significance threshold (P-value) for SMR analysis. SNPs with P-values below this threshold are retained. Supports numeric input, defaulting to 5e-8. For users unsure of the significance threshold, entering "Bonferroni" sets it to 0.05 divided by the number of SNPs.|
|Other Parameters|Other parameters of the main invoked software for this analysis.|

> Output Results

|Filename|Description|
|--|--|
|Time_smr.smr|The output of the invoked software for the SMR analysis.|
|Time_probename_smr.png|The visualized results of the SMR analysis of each Omic trait.|
|plot|A directory containing the data for visualizing the SMR results.|

### Main Results Interpretation

-  Prioritizing genes at a GWAS locus using SMR analysis. Shown are results at Omic data loci for phenotype. Top plot is the P values for SNPs from GWAs. Middle plot is the P values for SNPs from omicQTL. Bottom plot is the gene position in the selected region.

![Alt text](../../figures/Fig5A.png)

- Scatter plot of detected SNP effect on Omic data and phenotype.

<div align=center><img src="../../figures/Fig5B.png" width="80%" /></div>

- Significant MR in p-value: If the p-value from the SMR analysis passes the genome-wide significance threshold, and the p-value from the HEIDI (Heterogeneity In Dependent Instruments) test exceeds 0.05 in the results file, it supports the validity of the causal relationship.