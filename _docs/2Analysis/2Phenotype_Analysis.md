---
title: Phenotype Analysis
category: Analysis
order: 3
---

### Analysis Process

- Converts the input data to the format required by the Plink and GCTA software.

- For multi-trait analyses
- EasyOmics calculates: 
  - Distribution of phenotypes.
  - Phenotypic variance.
  - Genetic variance.
  - Narrow-sense heritability. 

- For single trait 
- EasyOmics calculates:
  - Narrow-sense heritability.
  - Phenotype distribution in a density plot
  - visualizes population structure through PCA analysis of SNP data in a scatter plot


### Input and Output

> Input Parameters

|Parameter|Description|
|--|--|
|Upload Phenotype Data File|The phenotype data, format is shown in "Data Preparation".|
|Upload VCF Data File|The VCF data, format is shown in "Data Preparation".|
|Analysis type| Whether the phenotype data is multi-trait or single trait.|
|Other Parameters|Other parameters of the main invoked software for this analysis.|

> Output Results

|Filename|Description|
|--|--|
|Time_h2_single_1.hsq&log|The output of invoked software for heritability analysis.|
|Time_Single_Trait_result.pdf&png|The visualized results of single trait analysis. Includes a density plot of the phenotype distribution and a scatter plot of the population structure.|
|Time_phe_info.txt|The analysis results of the multi-trait. Includes the phenotypic variance, genetic variance, and narrow-sense heritability of each trait.|
|Time_Multitrait_phenotype_summary.pdf&png|The visualized results of multi-trait analysis. Includes phenotypic distribution, phenotypic variance, genetic variance, and narrow-sense heritability of each trait.|
|Time_phe_cor.txt|The correlation data between phenotypes.|
|Time_Multitrait_phenotype_cor.pdf&png|The visualized results of multi-trait analysis. Includes the correlation between phenotypes.|


### Main Results Interpretation
- Multi-trait analysis results, with different colors distinguishing the results of different traits. 

<div align=center><img src="../../figures/Fig2A.png" width="70%" /></div>

- For single-trait analysis, the results display phenotype distribution in a density gradient format with marked individual codes, assisting users in inspecting unreasonable phenotypic data. The genetic structure, shown in a two-dimensional principal component analysis along with marked individual codes, helps users check the genetic composition of the analyzed population. 

<div align=center><img src="../../figures/image-8.png" width="80%" /></div>

- Heritability: High heritability indicates that a significant proportion of the variation in a specific trait within a population is due to genetic differences among individuals. This suggests that the trait is strongly influenced by genetic factors.
- Outlier of phenotype: If the distribution of the phenotype is abnormal or disordered, some individuals may have phenotypic values that were erroneously collected, and these need to be identified as outliers. An outlier in phenotypic values can influence the association results disproportionately, potentially leading to false positives or negatives.
- Outlier of genetic structure: Outlier often refers to an individual individual whose genetic background is substantially different from the rest of the study population.