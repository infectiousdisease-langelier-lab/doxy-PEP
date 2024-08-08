# Impact of doxycycline post-exposure prophylaxis (doxy-PEP) on the gut microbiome and resistome

This repository contains the code for the paper **Impact of doxycycline post-exposure prophylaxis for sexually transmitted infections on the gut microbiome and antimicrobial resistome**.

## Code

DoxyPEP - Resistome Main Analysis.Rmd is used to analyze the resistome data and produce manuscript tables 1, figures 2-5, supplemental tables 1-2, and supplemental figures 1-4. This code uses the following input files: 
* [final_AMR.csv](../Inputs/Resistome/final_AMR.csv): antimicrobial resistance genes and the associated metadata detected in the final samples, after QC and background filtering with the negative binomial model
* [final_samples.csv](../Inputs/final_samples.csv): final samples included in the study after QC
* [final_metadata.csv](../Inputs/final_metadata.csv): deidentified metadata for all included participants

DoxyPEP - Microbiome DNA-seq.Rmd is used to make manuscript supplemental figure 5a, c, e and 6. It also provides the code for the differential abundance testing. This code uses the following additional input files: 
* [final_samples.csv](../Inputs/final_samples.csv): final samples included in the study after QC
* [microbiome_reports.csv](../Inputs/Microbiome/DNA/microbiome_reports.csv): CZID output of the bacterial microbiome (genera-level) data for DNA-sequencing, after background filtering with the negative binomial model
* [microbiome_reports_species.csv](../Inputs/Microbiome/DNA/microbiome_reports_species.csv): CZID output of the bacterial microbiome (species-level) data for DNA-sequencing, after background filtering with the negative binomial model
* [dds_object_doxy_genus.rds](../Inputs/Microbiome/DNA/dds_object_doxy_genus.rds): DESeq2 object with the bacterial microbiome data for differential abundance testing
  
DoxyPEP - Microbiome RNA-seq.Rmd is used to make supplemental figure 5b, d, f. This code uses the following additional input files: 
* [final_samples.csv](../Inputs/final_samples.csv): final samples included in the study after QC
* [microbiome_reports.csv](../Inputs/Microbiome/RNA/microbiome_reports.csv): CZID output of the bacterial microbiome (genera-level) data for RNA-sequencing, after background filtering with the negative binomial model

DoxyPEP - Correlation Plot.Rmd is used to analyze data at the human gene expression data and make supplemental figure 7. This code uses the following additional input files: 
* [bacterial_genera_dna_corrplot.csv](https://github.com/infectiousdisease-langelier-lab/doxy-PEP/blob/main/Input/Corr%20Plot/bacterial_genera_dna_corrplot.csv): bacteria genera data

Each Rmd file can take 1-5 minutes to run.

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
 [1] parallel  splines   stats4    stats     graphics  grDevices utils     datasets  methods   base     

other attached packages:
 [1] gamlss_5.4-22               nlme_3.1-164                gamlss.dist_6.1-1           gamlss.data_6.0-6          
 [5] ALDEx2_1.30.0               zCompositions_1.5.0-3       truncnorm_1.0-9             NADA_1.6-1.1               
 [9] survival_3.5-7              MASS_7.3-58.1               metagenomeSeq_1.40.0        RColorBrewer_1.1-3         
[13] glmnet_4.1-8                Matrix_1.6-4                limma_3.54.2                ggrepel_0.9.4              
[17] DESeq2_1.38.3               SummarizedExperiment_1.28.0 Biobase_2.58.0              MatrixGenerics_1.10.0      
[21] matrixStats_1.2.0           GenomicRanges_1.50.2        GenomeInfoDb_1.34.9         IRanges_2.32.0             
[25] S4Vectors_0.36.2            BiocGenerics_0.44.0         scales_1.3.0                vegan_2.6-4                
[29] lattice_0.22-5              permute_0.9-7               idseqr_0.1.0                ggpubr_0.6.0               
[33] rstatix_0.7.2               ggcorrplot_0.1.4.1          corrplot_0.92               lubridate_1.9.3            
[37] forcats_1.0.0               stringr_1.5.1               dplyr_1.1.4                 purrr_1.0.2                
[41] readr_2.1.4                 tidyr_1.3.0                 tibble_3.2.1                ggplot2_3.5.1              
[45] tidyverse_2.0.0            

loaded via a namespace (and not attached):
 [1] colorspace_2.1-0       ggsignif_0.6.4         modeltools_0.2-23      XVector_0.38.0         rstudioapi_0.16.0     
 [6] flexmix_2.3-19         bit64_4.0.5            AnnotationDbi_1.60.2   fansi_1.0.6            codetools_0.2-20      
[11] cachem_1.0.8           geneplotter_1.76.0     knitr_1.41             Formula_1.2-5          jsonlite_1.8.8        
[16] broom_1.0.6            annotate_1.76.0        cluster_2.1.6          png_0.1-8              compiler_4.2.1        
[21] httr_1.4.7             backports_1.4.1        RcppZiggurat_0.1.6     fastmap_1.1.1          cli_3.6.2             
[26] htmltools_0.5.7        tools_4.2.1            gtable_0.3.5           glue_1.6.2             GenomeInfoDbData_1.2.9
[31] Rcpp_1.0.11            carData_3.0-5          jquerylib_0.1.4        vctrs_0.6.5            Biostrings_2.66.0     
[36] iterators_1.0.14       betareg_3.1-4          lmtest_0.9-40          xfun_0.41              timechange_0.2.0      
[41] lifecycle_1.0.4        gtools_3.9.5           XML_3.99-0.16          zlibbioc_1.44.0        zoo_1.8-12            
[46] hms_1.1.3              sandwich_3.1-0         yaml_2.3.8             memoise_2.0.1          sass_0.4.8            
[51] stringi_1.8.3          RSQLite_2.3.4          foreach_1.5.2          caTools_1.18.2         BiocParallel_1.32.6   
[56] shape_1.4.6.1          rlang_1.1.2            pkgconfig_2.0.3        bitops_1.0-7           Wrench_1.16.0         
[61] evaluate_0.24.0        Rfast_2.1.0            bit_4.0.5              tidyselect_1.2.0       magrittr_2.0.3        
[66] R6_2.5.1               gplots_3.1.3.1         generics_0.1.3         DelayedArray_0.24.0    DBI_1.2.3             
[71] mgcv_1.9-1             pillar_1.9.0           withr_3.0.0            KEGGREST_1.38.0        abind_1.4-5           
[76] RCurl_1.98-1.13        nnet_7.3-19            crayon_1.5.2           car_3.1-2              KernSmooth_2.23-22    
[81] utf8_1.2.4             tzdb_0.4.0             rmarkdown_2.18         locfit_1.5-9.8         grid_4.2.1            
[86] blob_1.2.4             digest_0.6.33          xtable_1.8-4           RcppParallel_5.1.7     munsell_0.5.1         
[91] bslib_0.4.1

```

## Code usage

The full data sets are available in the folder [Inputs_Final](Inputs_Final). To reproduce the results in the paper, the uploaded codes could be run directly. The codes' output are located in the folder [Output_Finals](Output_Finals).
