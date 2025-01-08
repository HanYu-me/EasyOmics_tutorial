---
title: Locus Zoom
category: Analysis
order: 6
---

### Analysis Process

- Converts the input data to the format required by the software LDBlocShow.
- The software uses LDBlockShow to calculate linkage disequilibrium between the selected SNP and other nearby SNPs.
- Displaying this in conjunction with association analysis results ,gene locations, and LDBlocks arranged around the selected SNP. 
- It also analyzes and plots phenotypes of individuals with different genotypes of the selected SNP, aiding users to check the effect of the SNP on traits. 
- Visualizes the results of the analysis.

### Input and Output

> Input Parameters

|Parameter|Description|
|--|--|
|Upload VCF Data File|The VCF data, format is shown in "Data Preparation".|
|Upload GFF Data File|The genome annotation GFF data, format is shown in "Data Preparation".|
|Upload GWA Data File|The .mlma file from the "GWAs" analysis.|
|Upload Phenotype Data File|The phenotype data, format is shown in "Data Preparation".|
|SNP ID|The SNP ID of the selected SNP. Usually, the significant association SNPs from GWAs analysis are used.|
|Region(bp)|The region of the conjunction of association analysis results, gene locations, and LDBlocks arranged around the selected SNP.|
|Other Parameters|Other parameters of the main invoked software for this analysis.|

> Output Results

|Filename|Description|
|--|--|
|Time_result_SNPID.blocks.gz&.site.gz&TriangleV.gz|The output of the invoked software for the Locus Zoom analysis.|
|Time_result_SNPID.svg&.png|The visualized results of the Locus Zoom analysis. Includes a Locus Zoom plot of the association results.|
|Time_phename_SNPID_boxplot_data.csv|The phenotype data of individuals with different genotypes of the selected SNP.|
|Time_phename_SNPID_boxplot.pdf|The visualized results of the phenotype data, which is divided by the genotypes of the selected SNP.|

### Main Results Interpretation

- Visualization of results including linkage and P-values of the selected SNP and other SNPs; genes in the interval; linkage between all SNPs in the interval. 
  - In the top panel, the top red square means the SNP you selected, the other snp are colored by their LD with the selected SNP, and the height of each SNP means the -log10(p-value) of the SNP. 
  - The middle panel shows the genes in the region. For each gene, the gene structure was annotated. Red colored region means the CDS region, and the purple colored region means the UTR region. Each line in this panel mean the location of SNP.
  - In the bottom panel, the LD between the selected SNP and other SNPs are shown. The color of the triangle means the LD value between the two SNPs. The darker color means the higher LD value. The green line from middle panel to bottom panel means the location of the SNP in the genome region.
  
![Alt text](../../figures/Fig3C.png)
- Phenotypes of individuals with different genotypes of the selected SNP.

<div align=center><img src="../../figures/image-4.png" width="70%"/></div>

- Gene in selected region: Genes located in the selected zoom region are specifically annotated in the LocusZoom plot. The presence of these genes is crucial because it provides clues about potential biological pathways or mechanisms that might be influencing the trait of interest
- LD in selected region: A region of high LD around a significant SNP suggests that these variants are inherited together frequently. Areas of low LD indicate that genetic linkage breaks down, which helps in narrowing down the possible regions where the causal variants might reside.