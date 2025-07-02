# TLR Identification and Ontogenetic/Tissue-specific Expression Analysis in *Pleurodeles waltl*

This repository documents the full annotation and expression analysis of Toll-like receptor (TLR) genes in the Iberian ribbed newt (*Pleurodeles waltl*), conducted as part of a bachelor’s thesis in evolutionary immunogenomics.

## 🎯 Project Goal

To identify the TLR genes in the *Pleurodeles waltl* genome, and to quantify their expression across developmental stages and bodyparts' tissues using RNA-seq data and TPM/FPKM based estimation.

## ❓ Hypothesis

I hypothesise elevated general TLR and particularly fish-type TLRs expression in early, aquatic larval stage in *P. waltl*, showing retained aquatic immune strategy. Also, i suppose that TLR generally have elevated expression in the early, aquatic environmental stages.

---

## 🧪 Workflow Summary

The analysis was conducted in R using RStudio, terminal tools and external programs. The scripts and steps done in R are reproducible.

### 1. **TLR Gene Annotation**  
See: [`anot.Rmd`](./01_annotation/anot.Rmd)  
- BLAST-p search using *Lissotriton* TLR proteins  
- Parsing top hits (E=0, highest bit score), linking to gene IDs from `.gtf`  
- Generation of a filtered annotation table

### 2. **Multiple-sequence alignment for particular TLR genes**  
See: [`anot.Rmd`](./03_alignment/align.Rmd)  
- Selecting uncertain annotations for multiple-sequence alignment  
- Using the script that automatically cuts the sequences of *Pleurodeles* and reference *Lissotriton* 
- Runing the MAFFT algorithm locally and the visual analysis

### 3. **Expression Quantification**  
See: [`exp.Rmd`](./02_expression/exp.Rmd)  
- RNA-seq alignment (paired-end)  
- Quantification with `featureCounts` using CDS features  
- Normalization to TPM-like and FPKM values  
- Sample classification into developmental groups

### 4. **Data Visualization**
See: [`exp.Rmd`](./02_expression/exp.Rmd)
- TPM-based relative expression plotted per gene and stage
- TPM-based relative expression plotted per gene, stage and tissue for fish-type TLRs
- FPKM-based global expression for each developmental group  


---

## 📁 Project Structure

README.md <-- You are here

[`01_annotation`](./01_annotation) <-- # Annotation files & anot markdown

[`02_expression`](./02_expression) <-- # Expression files & exp markdown

[`03_alignment`](./03_alignment) <-- # Alignment files & align markdown
>>> [`aligned_files`](./03_alignment/aligned_files) <-- # Alignment subdirectory with used alignment files

---

## ⚙️ Requirements

- R ≥ 4.2  
- R packages: `tidyverse`, `gtools`, `rmarkdown`, `ggplot2`, `dplyr`
- External: `featureCounts` (Subread), `BLAST+`, `MAFFT`

The exact versions of the used programs is available in the corresponding markdowns

---

## 📚 Citation and resources

This project was developed by Krystian Budzik as part of a bachelor’s thesis in the Genomics and Experimental Evolution Team, Jagiellonian University

Supervisor: Prof. dr. hab. Wiesław Babik, Institute of Environmental Sciences, Faculty of Biology, JU

Reviewer: Dr. hab. Katarzyna Tomala, Institute of Environmental Sciences, Faculty of Biology, JU

Materials used for the expression quantification (BAM files) come from the work done in the Genomic and Experimental Evolution Team, JU:

> https://www.ebi.ac.uk/ena/browser/view/PRJEB90989

Genomic data comes from the work:

> https://pubmed.ncbi.nlm.nih.gov/39874962/
