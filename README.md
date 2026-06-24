# MTBLS4461 — Serum Lipidomics Workflow

Exploratory lipidomics analysis of [MTBLS4461](https://www.ebi.ac.uk/metabolights/MTBLS4461):
*An Unbiased Lipid Phenotyping Approach To Study the Genetic Determinants of Lipids and Their Association with Coronary Heart Disease Risk Factors.*

Data were acquired by direct-infusion MS (Thermo Exactive Orbitrap) from human serum samples
collected from a Pakistani control cohort. Biological covariates include gender, age, and
self-reported diabetes status.

---

## Workflow

The analysis is contained in a single R Markdown notebook:
**`MTBLS4461_lipidomics_notebook.Rmd`**

| Section | Description |
|---|---|
| 1. Data Acquisition | Automated download from the MetaboLights REST API |
| 2. Data Import | ISA-Tab metadata parsing; MAF abundance matrix extraction |
| 3. Quality Control | Missing value assessment, feature/sample filtering, total ion signal inspection |
| 4. Normalisation | Probabilistic Quotient Normalisation (PQN), log₂ transform, KNN imputation |
| 5. Lipid Class Summarisation | Name standardisation to LIPID MAPS abbreviations; class-level abundance |
| 6. Exploratory Analysis | PCA, scree plot, sample–sample correlation heatmap, feature heatmap |
| 7. Differential Abundance | limma eBayes; contrasts: Diabetes (Yes vs No), Gender (Male vs Female) |
| 8. Species Visualisation | Chain length and unsaturation distributions; top hit boxplots |

---

## Requirements

R ≥ 4.2. Packages are installed automatically on first run.

**CRAN:** `tidyverse`, `janitor`, `pheatmap`, `ggrepel`, `patchwork`, `RColorBrewer`, `knitr`, `kableExtra`

**Bioconductor:** `limma`, `impute`

---

## Data

Study files are downloaded automatically from the MetaboLights REST API on first run
and saved to `data/MTBLS4461/`. This directory is excluded from version control.

All data are publicly available at:
[https://www.ebi.ac.uk/metabolights/MTBLS4461](https://www.ebi.ac.uk/metabolights/MTBLS4461)

---

## Rendered Notebook

A rendered HTML version of the notebook is available on RPubs:
[https://rpubs.com/jaysmitachaliha/MTBLS4461-lipidomics](https://rpubs.com/jaysmitachaliha/MTBLS4461-lipidomics)

---

## References

| | |
|---|---|
| Castro et al. (2024) | A lipidomic dataset for epidemiological studies of acute myocardial infarction. *Data in Brief* 57:110925 |
| Harshfield et al. (2019) | An unbiased lipid phenotyping approach to study the genetic determinants of lipids and their association with coronary heart disease risk factors. *J. Proteome Res.* 18(6):2397–2410 |
| Dieterle et al. (2006) | PQN normalisation. *Anal. Chem.* 78:4281 |
| Ritchie et al. (2015) | limma. *Nucleic Acids Res.* doi:10.1093/nar/gkv007 |
| Troyanskaya et al. (2001) | KNN imputation. *Bioinformatics* 17:520 |
| Liebisch et al. (2020) | LIPID MAPS shorthand. *J. Lipid Res.* 61:1650 |

---

*Jaysmita Chaliha · [github.com/jaysmitachaliha](https://github.com/jaysmitachaliha)*
