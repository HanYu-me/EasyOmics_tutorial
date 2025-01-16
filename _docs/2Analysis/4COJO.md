---
title: COJO
category: Analysis
order: 5
---

### Analysis Process

- Converts the input data to the format required by the GCTA software.
- Utilizes GCTA software COJO function to remove significant SNPs in the "GWAs" analysis
- Analyze whether any SNPs are still significant.
- Visualizes the results of the analysis.

### Input and Output

> Input Parameters

|Parameter|Description|
|--|--|
|Upload GWAs Data File| The .mlma file from the "GWAs" analysis.|
|Upload VCF Data File| The VCF data, format is shown in "Data Preparation".|
|Threshold| A value setting the significance threshold (P-value) for COJO analysis. SNPs with P-values below this threshold are retained. Supports numeric input, defaulting to 5e-8. For users unsure of the significance threshold, entering "Bonferroni" sets it to 0.05 divided by the number of SNPs.|
|Color|Sets adjacent chromosome colors in the Manhattan plot. Hexadecimal colors are connected by "_"|
|Show Top SNPs|Whether to show the top SNPs in the Manhattan plot.|
|Other Parameters|Other parameters of the main invoked software for this analysis.|

> Output Results

|Filename|Description|
|--|--|
|Time_GWAs_cojoed.log&.jma.cojo&.ldr.cojo&.cma.cojo|The output of the invoked software for the COJO analysis.|
|Time_GWAs_cojoedmanhattan.pdf&png|The visualized results of the COJO analysis. Includes a Manhattan plot of the association results.|
|Time_GWAs_cojoedtop_snps.txt|The association result of the top SNPs.|
|Time_GWAs_cojoedqqplot.pdf&png|The visualized results of the COJO analysis. Includes a QQ plot of the association results and a regression line of inflation factor.|


### Citation

Yang, J., Ferreira, T., Morris, A.P., Medland, S.E., Madden, P.A.F., et al., 2012. Conditional and joint multiple-SNP analysis of GWAS summary statistics identifies additional variants influencing complex traits. Nat. Genet. 44, 369–375. https://doi.org/10.1038/ng.2213

