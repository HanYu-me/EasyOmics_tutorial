---
title: GWAs
category: Analysis
order: 4
---

### Analysis Process

- Converts the input data to the format required by the GCTA software.
- Uses GCTA to conduct a mixed linear model association analysis for each SNP and phenotype. 
- If the inflation factor is bigger than 1.1, lambda adjusted p value will be used. 
- If "Show Top SNPs" is selected, EasyOmics extracts and merges SNPs based on their significance, physical distance, and Linkage Disequilibrium (LD),  and annotates the most significant independent SNPs on the Manhattan plot.
- Visualizes the results of the analysis.

### Input and Output

> Input Parameters

|Parameter|Description|
|--|--|
|Upload Phenotype Data File|The phenotype data, format is shown in "Data Preparation".|
|Upload VCF Data File|The VCF data, format is shown in "Data Preparation".|
|Select a model|The model used for the association analysis. Mixed linear model is the default and most commonly used.|
|Threshold|  A value setting the significance threshold (P-value) for GWAS analysis. SNPs with P-values below this threshold are retained. Supports numeric input, defaulting to 5e-8. For users unsure of the significance threshold, entering "Bonferroni" sets it to 0.05 divided by the number of SNPs.|
|Color|Sets adjacent chromosome colors in the Manhattan plot. Hexadecimal colors are connected by "_"|
|Show Top SNPs|Whether to show the top SNPs in the Manhattan plot.|
|Other Parameters|Other parameters of the main invoked software for this analysis.|

> Output Results

|Filename|Description|
|--|--|
|Time_phename_mlm.log&mlma|The output of the invoked software for the association analysis.|
|Time_phenamemanhattan.pdf&png|The visualized results of the association analysis. Includes a Manhattan plot of the association results.|
|Time_phenametop_snps.txt|The association result of the top SNPs.|
|Time_pheqqplot.pdf&png|The visualized results of the association analysis. Includes a QQ plot of the association results and a regression line of inflation factor.|
|Time_phenamemanhattan_corrected.pdf&png|If the inflation factor is bigger than 1.1, the p value of SNPs will be adjusted and visualized in this plot.|
|Time_phenametop_snps_corrected.txt|The top SNPs after p value adjustment.|

### Main Results Interpretation

- Manhattan plot.
  
![Alt text](../../figures/Fig3A.png)

- QQ plot.



<div align=center><img src="../../figures/Fig3B.png" width="50%"/></div>

- The p-value: p-value means the significance of association between genetic variation and phenotype. If some SNPs pass the threshold,  these SNPs are statistically significant association between the genetic variant and the trait.
- The inflation factor: The inflation factor λ is typically calculated as the median of the observed chi-squared test statistics divided by the median of the theoretical chi-squared distribution under the null hypothesis. When λ is significantly greater than 1.1, suggests an overdispersion of test statistics, which may be due to population stratification, cryptic relatedness among samples, or other forms of systematic bias.
- Result from different model
  - Mixed linear model: This model is the default and most commonly used model for GWAS analysis. A kinship matrix calculated from the genotype data is used to account for population structure and relatedness among samples.
  - Generalized mixed linear model: This model is used for binary traits. A kinship matrix calculated from the genotype data is used to account for population structure and relatedness among samples.
  - Linear regression model: This model is the fastest model for GWAS analysis, which does not account for population structure and relatedness among samples. It is suitable for geneticly evenly distributed data. In addition, this model provide a preview of the association between genetic variation and phenotype.
  - Multi-loci mixed linear model: A Bayesian-information and Linkage-disequilibrium Iteratively Nested Keyway (BLINK) model is used to account for population structure and relatedness among samples. This model is used for multi-loci association analysis. **However, due to the association basic unit of genotype is multi-loci, the association is not suitable for downstream function, except for the Locus Zoom function.**

### Citation

For Mixed Linear Model, Generalized Mixed Linear Model, and Linear Regression Model:

Yang, J., Lee, S.H., Goddard, M.E., Visscher, P.M., 2011. GCTA: A tool for genome-wide complex trait analysis. Am. J. Hum. Genet. 88, 76–82. https://doi.org/10.1016/j.ajhg.2010.11.011

For Multi-loci Mixed Linear Model:

Huang, M., Liu, X., Zhou, Y., Summers, R. M., and Zhang, Z. (2019). BLINK: A package for the next level of genome-wide association studies with both individuals and markers in the millions. Gigascience. 8, 1–12. https://doi.org/10.1093/gigascience/giy154