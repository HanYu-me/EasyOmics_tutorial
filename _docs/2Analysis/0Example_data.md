---
title: Data Preparation
category: Analysis
order: 1
---

## Example Data

- Example data have been deposited in https://github.com/HanYu-me/EasyOmics/tree/main/examples
- phe_FT16.txt: Flowering time of *Arabidopsis thaliana* at 16°C.
- phe_10env.txt: Flowering time of *Arabidopsis thaliana* at 10 different environments.
- Matched_phe_sub5000.txt: Gene expression RPKM matrix of sampled 5000 genes.
- Arabidopsis_thaliana.TAIR10.55.gff3.zip: A gff3 format file of gene annotation. Please uncompress it before performing analysis.
- sample_10000_snps.vcf: Vcf file containing 10,000 SNPs, which were sampled from the raw 1001 SNP data.

## Data Format

### Phenotype Data
- Phenotype text files are split by "tab", containing at least three columns: family code, individual code, and phenotypic value of the trait (supports multiple phenotypes).
  - If no family information is available, the family code can be **set as the individual code** or **just contain the id and phenotype columns** in file.
```txt
family id FT16
108 108 52.25
139 139 52.75
159 159 56.75
265 265 47.25
350 350 51.5
351 351 65.33333333
403 403 54.25
410 410 65.25
424 424 68.25
```

### Genotype Data

- Standard VCF format genotype file, where the individual code must follow the format "family code_individual code". The content of first 9 columns are fixed, and the 10th+ columns are the genotype information of each individual.
  - If no family information is available, the family code can be **set as the individual code** (eg. 108_108) or **just contain the id** (eg. 108) in file.
```txt
#CHROM  POS     ID      REF     ALT     QUAL    FILTER  INFO    FORMAT  108_108 139_139
1       73      1:73    C       A       .       .       PR      GT      0/0     0/0
1       92      1:92    A       C       .       .       PR      GT      1/1     1/1
1       110     1:110   G       T       .       .       PR      GT      0/0     0/0
1       253     1:253   T       C       .       .       PR      GT      0/0     0/0
1       353     1:353   G       A       .       .       PR      GT      0/0     0/0
1       363     1:363   C       G       .       .       PR      GT      1/1     1/1
1       425     1:425   C       T       .       .       PR      GT      0/0     0/0
1       502     1:502   T       C       .       .       PR      GT      0/0     0/0
1       508     1:508   C       T       .       .       PR      GT      0/0     0/0
```

### Genome Annotation Data

- Standard GFF3 format file, which contains the gene annotation information of the genome. This file is suitable for gene-probe based Omic data analysis (eg. transcriptome).
  - The file should contain at least 9 columns: seqid, source, type, start, end, score, strand, phase, and attributes.
  - The attributes column should contain the gene ID, gene name, gene biotype, and gene description.

```txt
1	araport11	gene	3631	5899	.	+	.	ID=gene:AT1G01010;Name=NAC001;biotype=protein_coding;description=NAC domain containing protein 1 [Source:NCBI gene (formerly Entrezgene)%3BAcc:839580];gene_id=AT1G01010;logic_name=araport11
1	araport11	mRNA	3631	5899	.	+	.	ID=transcript:AT1G01010.1;Parent=gene:AT1G01010;Name=NAC001-201;biotype=protein_coding;tag=Ensembl_canonical;transcript_id=AT1G01010.1
1	araport11	five_prime_UTR	3631	3759	.	+	.	Parent=transcript:AT1G01010.1
1	araport11	exon	3631	3913	.	+	.	Parent=transcript:AT1G01010.1;Name=AT1G01010.1.exon1;constitutive=1;ensembl_end_phase=1;ensembl_phase=-1;exon_id=AT1G01010.1.exon1;rank=1
1	araport11	CDS	3760	3913	.	+	0	ID=CDS:AT1G01010.1;Parent=transcript:AT1G01010.1;protein_id=AT1G01010.1
1	araport11	exon	3996	4276	.	+	.	Parent=transcript:AT1G01010.1;Name=AT1G01010.1.exon2;constitutive=1;ensembl_end_phase=0;ensembl_phase=1;exon_id=AT1G01010.1.exon2;rank=2
1	araport11	CDS	3996	4276	.	+	2	ID=CDS:AT1G01010.1;Parent=transcript:AT1G01010.1;protein_id=AT1G01010.1
1	araport11	exon	4486	4605	.	+	.	Parent=transcript:AT1G01010.1;Name=AT1G01010.1.exon3;constitutive=1;ensembl_end_phase=0;ensembl_phase=0;exon_id=AT1G01010.1.exon3;rank=3
1	araport11	CDS	4486	4605	.	+	0	ID=CDS:AT1G01010.1;Parent=transcript:AT1G01010.1;protein_id=AT1G01010.1
1	araport11	exon	4706	5095	.	+	.	Parent=transcript:AT1G01010.1;Name=AT1G01010.1.exon4;constitutive=1;ensembl_end_phase=0;ensembl_phase=0;exon_id=AT1G01010.1.exon4;rank=4
1	araport11	CDS	4706	5095	.	+	0	ID=CDS:AT1G01010.1;Parent=transcript:AT1G01010.1;protein_id=AT1G01010.1
1	araport11	exon	5174	5326	.	+	.	Parent=transcript:AT1G01010.1;Name=AT1G01010.1.exon5;constitutive=1;ensembl_end_phase=0;ensembl_phase=0;exon_id=AT1G01010.1.exon5;rank=5
1	araport11	CDS	5174	5326	.	+	0	ID=CDS:AT1G01010.1;Parent=transcript:AT1G01010.1;protein_id=AT1G01010.1
1	araport11	CDS	5439	5630	.	+	0	ID=CDS:AT1G01010.1;Parent=transcript:AT1G01010.1;protein_id=AT1G01010.1
1	araport11	exon	5439	5899	.	+	.	Parent=transcript:AT1G01010.1;Name=AT1G01010.1.exon6;constitutive=1;ensembl_end_phase=-1;ensembl_phase=0;exon_id=AT1G01010.1.exon6;rank=6
1	araport11	three_prime_UTR	5631	5899	.	+	.	Parent=transcript:AT1G01010.1
1	araport11	gene	6788	9130	.	-	.	ID=gene:AT1G01020;Name=ARV1;biotype=protein_coding;description=ARV1 family protein [Source:NCBI gene (formerly Entrezgene)%3BAcc:839569];gene_id=AT1G01020;logic_name=araport11
1	araport11	mRNA	6788	8737	.	-	.	ID=transcript:AT1G01020.2;Parent=gene:AT1G01020;Name=ARV1-202;biotype=protein_coding;transcript_id=AT1G01020.2
1	araport11	exon	6788	7069	.	-	.	Parent=transcript:AT1G01020.2;Name=AT1G01020.2.exon8;constitutive=0;ensembl_end_phase=-1;ensembl_phase=-1;exon_id=AT1G01020.2.exon8;rank=8
1	araport11	three_prime_UTR	6788	7069	.	-	.	Parent=transcript:AT1G01020.2
1	araport11	three_prime_UTR	7157	7314	.	-	.	Parent=transcript:AT1G01020.2
1	araport11	exon	7157	7450	.	-	.	Parent=transcript:AT1G01020.2;Name=AT1G01020.2.exon7;constitutive=0;ensembl_end_phase=-1;ensembl_phase=2;exon_id=AT1G01020.2.exon7;rank=7
1	araport11	CDS	7315	7450	.	-	1	ID=CDS:AT1G01020.2;Parent=transcript:AT1G01020.2;protein_id=AT1G01020.2
1	araport11	exon	7564	7649	.	-	.	Parent=transcript:AT1G01020.2;Name=AT1G01020.1.exon6;constitutive=1;ensembl_end_phase=2;ensembl_phase=0;exon_id=AT1G01020.1.exon6;rank=6
1	araport11	CDS	7564	7649	.	-	0	ID=CDS:AT1G01020.2;Parent=transcript:AT1G01020.2;protein_id=AT1G01020.2
1	araport11	exon	7762	7835	.	-	.	Parent=transcript:AT1G01020.2;Name=AT1G01020.1.exon5;constitutive=0;ensembl_end_phase=0;ensembl_phase=1;exon_id=AT1G01020.1.exon5;rank=5
```

- If the probe of Omic data is not gene, the similar format file can be used to represent the probe information. 
  - For example, the probe name/ID (same as phenotype name in Omic phenotype file), probe position in chromosome, probe start position in base pair, and probe end position in base pair.
  - The end position is optional, The first three columns are necessary.

```txt
G01010	1	3631	5899
G01020	1	6788	9130
G01030	1	11649	13714
G01040	1	23121	31227
G01050	1	31170	33171
G01060	1	33365	37871
G01070	1	38444	41017
G01080	1	44970	47059
G01090	1	47234	49304
G01100	1	49909	51210
G01110	1	51953	54737
G01120	1	57164	59215
G01130	1	61905	63811
G01140	1	64166	67774
G01150	1	69911	72138
G01160	1	72339	74096
G01170	1	73931	74737
G01180	1	75390	76845
G01190	1	82984	84946
G01200	1	86486	88409
G01210	1	88622	90502
```