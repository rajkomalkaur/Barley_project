

# Barley_project
This repository contains the R script and phenotypic data used for  analysis of phosphate starvation response traits in an initial subset of 26 lines from a 318-accession Eastern European barley collection.

# Contents
# File	Description

Barley Project.txt:	R script for genotype processing, principal component analysis, and GWAS using the FarmCPU model in GAPIT

Statistical Test.txt: R script for two-way ANOVA, assumption checks, and post-hoc comparisons for phenotypic traits

all_phenotypes.csv:	Phenotypic data for all 26 lines across 36 traits (biomass, tissue Pi concentration, and root system architecture under low and high phosphorus conditions, and response values)

# Analysis overview
# Genome-wide Association Studies
The script performs the following steps:
1. Loads an imputed VCF file (Beagle/Eagle, Morex V3 reference genome)
2. Subsets genotypes to the 26 lines phenotyped in this study
3. Converts genotype calls to numeric format (0, 1, 2)
4. Applies minor allele frequency filtering (MAF > 1%)
5. Loads the phenotype file and matches genotype and phenotype rows by line order
6. Performs principal component analysis (PCA) on the genotype data
7. Runs genome-wide association analysis for 12 response traits (YesP − NoP) using the FarmCPU model in GAPIT
8. Extracts top-ranking SNPs for each trait based on nominal p-values

# Statistical Analysis
1. Loads biomass, RSA, and phosphate phenotype data
2. Runs two-way ANOVA (genotype × treatment) for each measured trait
3. Checks normality of residuals using Shapiro-Wilk tests and Q-Q plots
4. Checks homogeneity of variance using Levene's test
5. Runs Welch's ANOVA as a sensitivity check where variances are unequal
6. Performs Tukey HSD post-hoc comparisons for total biomass, root Pi, and shoot Pi
7. Exports a summary table of ANOVA results
# Data
The phenotypic dataset contains mean values per line per treatment for:

-Biomass: root, shoot, and total fresh weight

-Tissue phosphate (Pi) concentration: root and shoot

-Root system architecture: total root length, root tips, root volume, root depth, average root diameter, root surface area, and root width

Values are provided for the low phosphorus (NoP) and high phosphorus (YesP) treatments, and for the response (YesP − NoP).

# Requirements
The script requires the following R packages:
vcfR

dplyr

tidyr

ggplot2

GAPIT

readx1

car

# Notes
The VCF file used for genotyping is not included in this repository, as it was provided by the Peter Dracatos group (La Trobe University) and is not the author's data to redistribute. The analysis can be reproduced by substituting the corresponding VCF file path in the script
