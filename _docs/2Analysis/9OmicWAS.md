---
title: OmicWAS
category: Analysis
order: 10
---

### Analysis Process

- Converts the input data to the format required by the software OSCA.
- Using a mixed linear model-based omic association (MOA) approach implemented in OSCA to test for associations between omic data and complex traits.
- Visualizes the results of the analysis.

### Input and Output

> Input Parameters

|Parameter|Description|
|--|--|
|Upload Phenotype Data File|The phenotype data, format is shown in "Data Preparation".|
|Upload Omic Data File|The omic data, format is shown in "Data Preparation".|
|Upload GFF Data File|The GFF data, format is shown in "Data Preparation".|
|Select GFF Type|The type of GFF file. If the probe of omic data is located in the genome and (1) is gene, upload the genome annotation GFF file. (2) is not gene, upload the probe position GFF like file. If the probe of omic data is not located in the genome, select "Not gene", and users can skip the GFF file upload.|
|Threshold|A value setting the significance threshold (P-value) for OmicWAS analysis. Omic data with P-values below this threshold are retained. Supports numeric input, defaulting to 5e-8. For users unsure of the significance threshold, entering "Bonferroni" sets it to 0.05 divided by the number of Omic data.|
|Color|Sets adjacent chromosome colors in the Manhattan plot. Hexadecimal colors are connected by "_"|
|Show Top Omic Data|Whether to show the top Omic data in the Manhattan plot.|
|Other Parameters|Other parameters of the main invoked software for this analysis.|

> Output Results

|Filename|Description|
|--|--|
|Time_moa_1_1.log&.moa|The output of the invoked software for the OmicWAS analysis.|
|Time_OmicWAs_manhattan.pdf&png|The visualized results of the OmicWAS analysis. Includes a Manhattan plot of the association results.|
|Time_top_genes.txt|The association result of the significant associated Omic data.|


### Main Results Interpretation

- Manhattan plot.
<div align=center><img src="../../figures/Fig6.png" width="80%"/></div>

- The p-value: p-value means the significance of association between omic data and phenotype. If some Omic data pass the threshold, these Omic data are statistically significant association between the omic data and the trait.


### Citation

Zhang, F., Chen, W., Zhu, Z., Zhang, Q., Nabais, M.F., et al., 2019. OSCA: A tool for omic-data-based complex trait analysis. Genome Biol. 20, 1–13. https://doi.org/10.1186/s13059-019-1718-z
