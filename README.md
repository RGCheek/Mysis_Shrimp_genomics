# Mysis_Shrimp_genomics


This repository includes all the data and scripts necessary to replicate analyses for the Mysis shrimp dataset. 

All files in this repository are liscenced under terms of the Creative Commons Attribution-NonCommercial License, which permits use, distribution and reproduction in any medium, provided the original work is properly cited and is not used for commercial purposes.

Scripts are all in R markdown files with annotations and some personal commentary to help interperpret the data:
001- Bioinformatics Pipeline Final.Rmd
          This includes workflow used to de-multiplex, and filter the raw ddRAD data from Admera Health. 
stacks_tests.xlsx
      Shows the result of multiple runs of Stacks denovo_map.pl to optimize the parameter used for final genotype calling. 

002- Population_Genetics_final.Rmd
         Workflow to analyse neutral population structure.
          
003-Identification_of_Population_Structure_Associated_with_Habitat_final.Rmd
         Workflow to generate FST outlier SNP list that were filtered out of the dataset for "neutral" popualtion genetics, code for redundancy analysis and adaptive PCA. 
         

data

blast_fasta_RDA.fasta
      350 bp consensus sequences around each candidate SNP flagged by redundancy analysis. Note some of the reads were flagged as truncated by samtools
      
mysis_10_percent_missing_mac_1.vcf
       3,036 SNPs generated following the recommendations of Schmidt et al. 2021 for popualtion genetic statistics. None of these SNPs were found in the adaptive list from PCAdapt, so they are likely unbiased by strong FST outliers.
       
mysis_clean_imputed_names_fix.vcf
      17,012 SNPs imputed in Linkimpute that were used for redundancy analysis, PCAdapt, and 
      
mysis_clean_imputed_neutral_names_fix.vcf
      16,943 SNPs 
      
mysis_clean_names_fix_non_imputed.vcf
    17,012 SNPs prior to imputation in Linkimpute so users can impose stricter filtering regimes based on missingness.  
      
mysis_env.csv
    Environemntal data for all sampled Lakes. Variabels measured by DS and BJ for all lakes apart form Clearwater Lake include: sate,	county,	water_name,	code,	date_sampled,	area-hectares,	depth-meters,	elevation-meters_above_sea_level,	cond-microSiemens,	secchi-meters,	turbidity-Nephelometric_Turbidity_Units,	min_Dissolved_Oxygen_on_bottom-mg_per_L,	mean_august_surface_temp_C,	num_yrs_Aug_temp,	mysis_detected,	number_stocking_events,	stocked	connected_to_stocked_lake.
    Elevation for Clearwater was taken from google Earth and https://www.bwcawild.com/BWCA-Lakes/Gunflint-District/Clearwater-Lake/Clearwater-Lake.html. Max lake depth came from lake map, "Clearwater lake detailed map info". 

mysis_popmap_pheno.txt
    Popmap used for popualtions in Stacks. Individuals are sepperated by lake with an additional phenotype for "regular" and "jumbo" morphs. 
