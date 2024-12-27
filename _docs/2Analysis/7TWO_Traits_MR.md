---
title: Two Traits MR
category: Analysis
order: 8
---

### Analysis Process

- Converts the input data to the format required by the GCTA software.
- Uses GCTA software's Mendelian randomization function to analyze whether the instrumental variable SNP affects trait in file one through the trait in file two
- Determining the causal relationship between the two traits. 
- Visualizes the results of the analysis.

### Input and Output

> Input Parameters

|Parameter|Description|
|--|--|
|Upload GWAs Result of Exposure| The .mlma file from the "GWAs" analysis of the exposure trait. Exposure trait means the trait that is a potential cause of outcome trait.|
|Upload GWAs Result of Outcome| The .mlma file from the "GWAs" analysis of the outcome trait. Outcome trait means the trait that is a potential result of exposure trait.|
|Upload VCF Data File| The VCF data, format is shown in "Data Preparation".|
|Threshold| A value setting the significance threshold (P-value) for MR analysis. SNPs with P-values below this threshold are retained. Supports numeric input, defaulting to 5e-8. For users unsure of the significance threshold, entering "Bonferroni" sets it to 0.05 divided by the number of SNPs.|
|Other Parameters|Other parameters of the main invoked software for this analysis.|

> Output Results

|Filename|Description|
|--|--|
|Time_gsmr_result.log&.gsmr&png&eff_plot.gz|The output of the invoked software for the Two Traits MR analysis.|

### Main Results Interpretation

- Correlation of effect values of SNPs passing the threshold on the two traits. Please Note: The example result is not a significant result, it is just for showing the plot.

<div align=center><img src="../../figures/gsmr_result.png" width="60%"/></div>

- Significant MR in p-value: After filtering SNPs p-value passed the threshold in the outcome and exposure, SNPs located in common region will be analysed.The significance is determined through the use of genetic variants as instrumental variables (IVs) to estimate the causal effect of the exposure on the outcome. If the p-value in result file passes the threshold, causal relationship is true.