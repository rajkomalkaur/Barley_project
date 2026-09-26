# Barley_project
GWAS analysis of phosphate starvation response in East European Barley lines
# GWAS of Phosphate Starvation Response in Barley

barley-project
This repository contains the R script and phenotypic data used for genome-wide association analysis of phosphate starvation response traits in an initial subset of 26 lines from a 318-accession Eastern European barley collection.

Contents
File	Description
barley-project.R	R script for genotype processing, principal component analysis, and GWAS using the FarmCPU model in GAPIT
all_phenotypes.csv	Phenotypic data for all 26 lines across 36 traits (biomass, tissue Pi concentration, and root system architecture under low and high phosphorus conditions, and response values)
Analysis overview
The script performs the following steps:

Loads an imputed VCF file (Beagle/Eagle, Morex V3 reference genome)

Subsets genotypes to the 26 lines phenotyped in this study

Converts genotype calls to numeric format (0, 1, 2)

Applies minor allele frequency filtering (MAF > 1%)

Loads the phenotype file and matches genotype and phenotype rows by line order

Performs principal component analysis (PCA) on the genotype data

Runs genome-wide association analysis for 12 response traits (YesP − NoP) using the FarmCPU model in GAPIT

Extracts top-ranking SNPs for each trait based on nominal p-values

Data
The phenotypic dataset contains mean values per line per treatment for:

Biomass: root, shoot, and total fresh weight

Tissue phosphate (Pi) concentration: root and shoot

Root system architecture: total root length, root tips, root volume, root depth, average root diameter, root surface area, and root width

Values are provided for the low phosphorus (NoP) and high phosphorus (YesP) treatments, and for the response (YesP − NoP).

Requirements
The script requires the following R packages:

vcfR

dplyr

tidyr

ggplot2

GAPIT

Notes
The VCF file used for genotyping is not included in this repository, as it was provided by the Peter Dracatos group (La Trobe University) and is not the author's data to redistribute. The analysis can be reproduced by substituting the corresponding VCF file path in the script
