# Impact of doxycycline post-exposure prophylaxis (doxy-PEP) on the gut microbiome and resistome

This repository contains the code for the paper **Doxycycline post-exposure prophylaxis for sexually transmitted infections impacts the gut antimicrobial resistome**.

## Code

DoxyPEP - Resistome Main Analysis.Rmd is used to analyze the resistome data and produce manuscript figures 1-4, supplemental tables 1-4, and supplemental figures 2-4. This code uses the following input files: 
* [final_AMR_0116.csv](../Inputs/Resistome/final_AMR_0116.csv): antimicrobial resistance genes and the associated metadata detected in the final samples, after QC and background filtering with the negative binomial model
* [final_sample_0116.csv](../Inputs/final_sample_0116.csv): final samples included in the study after QC
* [final_metadata_0116.csv](../Inputs/final_metadata_0116.csv): deidentified metadata for all included participants

DoxyPEP - Microbiome DNA-seq.Rmd is used to make manuscript figure 5a-d and supplemental figure 6. This code uses the following additional input files: 
* [samples_w_ptid2.csv](../Inputs/Microbiome/samples_w_ptid2.csv): samples with deidentified patient ID
* [sample_overviews_combined.csv](../Inputs/Microbiome/DNA/sample_overviews_combined.csv): DNA-sequencing sample information
* [microbiome_reports.csv](../Inputs/Microbiome/DNA/microbiome_reports.csv): CZID output of the bacterial microbiome (genera-level) data for DNA-sequencing, after background filtering with the negative binomial model
* [microbiome_reports_species.csv](../Inputs/Microbiome/DNA/microbiome_reports_species.csv): CZID output of the bacterial microbiome (species-level) data for DNA-sequencing, after background filtering with the negative binomial model
* [dds_object_doxy_genus.rds](../Inputs/Microbiome/DNA/dds_object_doxy_genus.rds): DESeq2 object with the bacterial microbiome data for differential abundance testing
  
DoxyPEP - Microbiome RNA-seq.Rmd is used to make supplemental figure 7. This code uses the following additional input files: 
* [sample_overviews_rna.csv](../Inputs/Microbiome/RNA/sample_overviews_rna.csv): RNA-sequencing sample information
* [microbiome_reports.csv](../Inputs/Microbiome/RNA/microbiome_reports.csv): CZID output of the bacterial microbiome (genera-level) data for RNA-sequencing, after background filtering with the negative binomial model

DoxyPEP - Correlation Plot.Rmd is used to analyze data at the human gene expression data and make figure 5e and supplemental figure 7. This code uses the following additional input files: 
* [bacterial_genera_dna_corrplot.csv](../Inputs/Corr Plot/bacterial_genera_dna_corrplot.csv): bacteria genera data

## Outputs

Final figures and supplemental figures generated from the above code are placed in this folder. Figures were exported from R as pdf files. Final edits to the figures (font standardization and panel layout) were made in Adobe Illustrator.

## Required hardware and software dependencies

The codes were run on a Mac laptop. The required R packages (see below for more details) could be installed with the command `install.package()` and `BiocManager::install()`. Each package can take up to 1 minute to install. Please refer to each package's website for more information on the installation.

```
R version 4.2.1 (2022-06-23)
Platform: x86_64-apple-darwin17.0 (64-bit)
Running under: macOS Ventura 13.2

Matrix products: default
LAPACK: /Library/Frameworks/R.framework/Versions/4.2/Resources/lib/libRlapack.dylib

locale:
[1] en_US.UTF-8/en_US.UTF-8/en_US.UTF-8/C/en_US.UTF-8/en_US.UTF-8

attached base packages:
[1] stats     graphics  grDevices utils     datasets  methods   base     

other attached packages:
 [1] scales_1.3.0    vegan_2.6-4     lattice_0.20-45 permute_0.9-7   ggpubr_0.5.0    rstatix_0.7.1  
 [7] forcats_1.0.0   stringr_1.5.1   dplyr_1.1.3     purrr_1.0.2     readr_2.1.3     tidyr_1.3.0    
[13] tibble_3.2.1    ggplot2_3.5.0   tidyverse_1.3.2

loaded via a namespace (and not attached):
  [1] googledrive_2.0.0           colorspace_2.0-3            ggsignif_0.6.4             
  [4] ellipsis_0.3.2              XVector_0.36.0              GenomicRanges_1.48.0       
  [7] fs_1.6.3                    rstudioapi_0.14             farver_2.1.1               
 [10] bit64_4.0.5                 AnnotationDbi_1.58.0        fansi_1.0.3                
 [13] lubridate_1.9.0             xml2_1.3.3                  codetools_0.2-18           
 [16] splines_4.2.1               cachem_1.0.6                geneplotter_1.74.0         
 [19] knitr_1.41                  jsonlite_1.8.3              broom_1.0.5                
 [22] annotate_1.74.0             cluster_2.1.4               dbplyr_2.2.1               
 [25] png_0.1-7                   compiler_4.2.1              httr_1.4.4                 
 [28] backports_1.4.1             assertthat_0.2.1            Matrix_1.6-4               
 [31] fastmap_1.1.0               gargle_1.2.1                cli_3.6.1                  
 [34] htmltools_0.5.6.1           tools_4.2.1                 gtable_0.3.4               
 [37] glue_1.6.2                  GenomeInfoDbData_1.2.8      Rcpp_1.0.9                 
 [40] carData_3.0-5               Biobase_2.56.0              jquerylib_0.1.4            
 [43] cellranger_1.1.0            vctrs_0.6.4                 Biostrings_2.64.1          
 [46] nlme_3.1-160                xfun_0.40                   rvest_1.0.3                
 [49] timechange_0.1.1            lifecycle_1.0.3             XML_3.99-0.12              
 [52] googlesheets4_1.0.1         zlibbioc_1.42.0             MASS_7.3-58.1              
 [55] hms_1.1.2                   MatrixGenerics_1.8.1        parallel_4.2.1             
 [58] SummarizedExperiment_1.26.1 RColorBrewer_1.1-3          yaml_2.3.6                 
 [61] memoise_2.0.1               sass_0.4.7                  stringi_1.7.8              
 [64] RSQLite_2.2.19              genefilter_1.78.0           S4Vectors_0.34.0           
 [67] BiocGenerics_0.42.0         BiocParallel_1.30.4         GenomeInfoDb_1.32.4        
 [70] rlang_1.1.1                 pkgconfig_2.0.3             matrixStats_0.63.0         
 [73] bitops_1.0-7                evaluate_0.18               bit_4.0.5                  
 [76] tidyselect_1.2.0            idseqr_0.1.0                magrittr_2.0.3             
 [79] DESeq2_1.36.0               R6_2.5.1                    IRanges_2.30.1             
 [82] generics_0.1.3              DelayedArray_0.22.0         DBI_1.1.3                  
 [85] mgcv_1.8-41                 pillar_1.9.0                haven_2.5.1                
 [88] withr_2.5.0                 survival_3.4-0              KEGGREST_1.36.3            
 [91] abind_1.4-5                 RCurl_1.98-1.9              modelr_0.1.10              
 [94] crayon_1.5.2                car_3.1-1                   utf8_1.2.2                 
 [97] tzdb_0.3.0                  rmarkdown_2.18              locfit_1.5-9.6             
[100] grid_4.2.1                  readxl_1.4.1                blob_1.2.3                 
[103] reprex_2.0.2                digest_0.6.30               xtable_1.8-4               
[106] stats4_4.2.1                munsell_0.5.0               bslib_0.4.1  
```

## Code usage

The full data sets are available in the folder [Inputs_Final](Inputs_Final). To reproduce the results in the paper, the uploaded codes could be run directly. The codes' output are located in the folder [Output_Finals](Output_Finals).
