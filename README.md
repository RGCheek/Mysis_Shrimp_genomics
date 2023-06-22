# Mysis Shrimp Genomics


## This repository includes all the data and scripts necessary to replicate analyses for the Mysis shrimp dataset

All files in this repository are liscenced under terms of the Creative Commons Attribution-NonCommercial License under R. G. C., which permits use, distribution and reproduction in any medium, provided the original work is properly cited and is not used for commercial purposes.

### Scripts

#### All in R markdown files with annotations and some personal commentary to help interperpret the data
**001- Bioinformatics Pipeline Final.Rmd**
This includes workflow used to de-multiplex, and filter the raw ddRAD data from Admera Health. 

**stacks_tests.xlsx**
      Shows the result of multiple runs of Stacks denovo_map.pl to optimize the parameter used for final genotype calling. 

**002- Population_Genetics_final.Rmd**
         Workflow to analyse neutral population structure.
          
**003-Identification_of_Population_Structure_Associated_with_Habitat_final.Rmd**
         Workflow to generate FST outlier SNP list that were filtered out of the dataset for "neutral" popualtion genetics, code for redundancy analysis and adaptive PCA. 
         

### Data

**blast_fasta_RDA.fasta**
      350 bp consensus sequences around each candidate SNP flagged by redundancy analysis.

**blast_fasta_pcadapt.fasta**
      350 bp consensus sequences around each candidate SNP flagged by PCADAPT. Note some of the reads were flagged as truncated by samtools
        
**mysis_clean_10_for_neutral_popstats.vcf**
       3,803 SNPs generated following the recommendations of Schmidt et al. 2021 for popualtion genetic statistics. None of these SNPs were found in the adaptive SNP list from PCAdapt, or RDA, so they are likely unbiased by strong FST outliers or selection.
       
**mysis_clean_imputed_names_fix.vcf**
     18,441 SNPs imputed in Linkimpute that were used for redundancy analysis, PCAdapt, and SNMF.  
      
**mysis_clean_imputed_neutral_names_fix.vcf**
      18,220 putative neutral SNPs with SNPs flagged as FST outliers from PCAdapt filtered out. Dataset was imputed with linkimpute before undergoing further filtering. 
      
**mysis_clean_non_imputed.vcf**
    18,441 SNPs prior to imputation in Linkimpute so users can impose stricter filtering regimes based on missingness or replicate ADMIXTURE analyses. 
      
**mysis_env_final.csv**
    Environemntal data for all sampled Lakes. Variabels measured by DS and BJ for all lakes apart form Clearwater Lake include: sate, county, water_name, code, date_sampled, area-hectares, depth-meters, elevation-meters_above_sea_level, cond-microSiemens, secchi-meters, turbidity-Nephelometric_Turbidity_Units, min_Dissolved_Oxygen_on_bottom-mg_per_L, mean_august_surface_temp_C, num_yrs_Aug_temp, mysis_detected, number_stocking_events, stocked, connected_to_stocked_lake.
    
**mysis_popmap_final.txt**
    Popmap used for popualtions in Stacks. Individuals are sepperated by lake. 
