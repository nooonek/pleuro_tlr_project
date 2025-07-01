# TLR Expression in *Pleurodeles waltl*

This repository documents the full annotation and expression analysis of Toll-like receptor (TLR) genes in the Iberian ribbed newt (*Pleurodeles waltl*), conducted as part of a bachelor’s thesis in evolutionary immunogenomics.

## 🎯 Project Goal

To identify the complete set of TLR genes in the *Pleurodeles waltl* genome, and to quantify their expression across developmental stages and tissue types using RNA-seq data. Particular emphasis was placed on normalizing read counts and visualizing relative TLR activity across ontogeny.

---

## 🧪 Workflow Summary

The analysis was conducted in R using R Markdown and terminal tools. All scripts and steps are reproducible.

### 1. **TLR Gene Annotation**  
See: [`anot.Rmd`](./anot.Rmd)  
- BLAST-p search using *Lissotriton* TLR proteins  
- Parsing top hits (E=0), linking to gene IDs from `.gtf`  
- Generation of a filtered annotation table

### 2. **Expression Quantification**  
See: [`exp_markdown.Rmd`](./exp_markdown.Rmd)  
- RNA-seq alignment (paired-end)  
- Quantification with `featureCounts` using CDS features  
- Normalization to TPM-like and FPKM values  
- Sample classification into developmental groups

### 3. **Visualization and Statistical Analysis**  
- TPM-based relative expression plotted per gene and stage  
- Global FPKM patterns summarized by group  
- Developmental structure inferred from individual metadata

---

## 📁 Project Structure

---

## ⚙️ Requirements

- R ≥ 4.2  
- R packages: `tidyverse`, `gtools`, `rmarkdown`, `ggplot2`, `dplyr`
- External: `featureCounts` (Subread), `BLAST+`, `MAFFT`

---

## 📚 Citation

> This project was developed by Krystian Budzik as part of a bachelor’s thesis in the Genomics and Experimental Evolution Team, Institute of Environmental Sciences.  
> Supervisor: Prof. dr. hab. Wiesław Babik
> Reviewer: Dr. hab. Katarzyna Tomala  
> Institute of Environmental Sciences, Faculty of Biology
