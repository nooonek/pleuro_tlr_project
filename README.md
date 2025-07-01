# TLR Expression in *Pleurodeles waltl*

This repository documents the full annotation and expression analysis of Toll-like receptor (TLR) genes in the Iberian ribbed newt (*Pleurodeles waltl*), conducted as part of a bachelor’s thesis in evolutionary immunogenomics.

## 🎯 Project Goal

To identify the TLR genes in the *Pleurodeles waltl* genome, and to quantify their expression across developmental stages and bodyparts' tissues using RNA-seq data and TPM/FPKM based estimation.

## ❓ Hypothesis

I hypothesise elevated general TLR and particularly fish-type TLRs expression in early, aquatic larval stage in *P. waltl*, showing retained aquatic immune strategy.

---

## 🧪 Workflow Summary

The analysis was conducted in R using R Markdown and terminal tools. All scripts and steps are reproducible.

### 1. **TLR Gene Annotation**  
See: [`anot.Rmd`](./anot.Rmd)  
- BLAST-p search using *Lissotriton* TLR proteins  
- Parsing top hits (E=0), linking to gene IDs from `.gtf`  
- Generation of a filtered annotation table

### 2. **Multiple-sequence alignment for particular TLR genes**  
See: [`anot.Rmd`](./anot.Rmd)  
- BLAST-p search using *Lissotriton* TLR proteins  
- Parsing top hits (E=0), linking to gene IDs from `.gtf`  
- Generation of a filtered annotation table

### 3. **Expression Quantification**  
See: [`exp.Rmd`](./exp.Rmd)  
- RNA-seq alignment (paired-end)  
- Quantification with `featureCounts` using CDS features  
- Normalization to TPM-like and FPKM values  
- Sample classification into developmental groups

### 4. **Visualization and Statistical Analysis**
See: [`exp.Rmd`](./exp.Rmd)
- TPM-based relative expression plotted per gene and stage
- TPM-based relative expression plotted per gene, stage and tissue for fish-type TLRs
- FPKM-based global expression for each developmental group  


---

## 📁 Project Structure

---

## ⚙️ Requirements

- R ≥ 4.2  
- R packages: `tidyverse`, `gtools`, `rmarkdown`, `ggplot2`, `dplyr`
- External: `featureCounts` (Subread), `BLAST+`, `MAFFT`

The exact versions of the used programs is available in the corresponding markdowns

---

## 📚 Citation and resources

> This project was developed by Krystian Budzik as part of a bachelor’s thesis in the Genomics and Experimental Evolution Team, Jagiellonian University.  
> Supervisor: Prof. dr. hab. Wiesław Babik, Institute of Environmental Sciences, Faculty of Biology, JU
> Reviewer: Dr. hab. Katarzyna Tomala, Institute of Environmental Sciences, Faculty of Biology, JU  
> Materials used for the expression quantification (BAM files) come from the work *ref Babik*, done in the Genomic and Experimental Evolution Team, JU
> Genomic data comes from the work *ref Pleuro genome*
