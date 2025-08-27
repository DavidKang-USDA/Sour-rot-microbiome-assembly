# Microbiome assembly process in *Drosophila suzukii* and host grape

This repository provides supporting information and the code for the following manuscript. <br />
 <br />

## Host Filtering and Ecological Processes Shape the Microbiomes of Wild Spotted Wing Drosophila and Grapes in a Sour Rot System

Rishi Bhandari<sup>1</sup>, Zoe Wills<sup>1</sup>, Jackie Harris<sup>2</sup>, Marnelle Salie<sup>2</sup>, Nana Ankrah<sup>3</sup>, Adam Chun-Nin Wong<sup>4</sup>, Katharine Eastman<sup>1</sup>, Joseph Ringbauer Jr<sup>1</sup>, R. Keith Striegler<sup>2</sup>, and David S. Kang<sup>1</sup>
 <br />
 <br />
<sup>1</sup> Biological Control of Insects Research Laboratory, US Department of Agriculture, Agricultural Research Service, Columbia, Missouri, USA
 <br />
<sup>2</sup> E & J. Gallo Winery, Modesto, California, USA
 <br />
<sup>3</sup> Biological Science Department, State University of New York Plattsburgh, Plattsburgh, New York, USA
 <br />
<sup>4</sup> Department of Entomology and Nematology, University of Florida, Gainesville, Florida, USA

 <br />
 <br />       


Corresponding Author: Dave Kang, Dave.Kang@usda.gov



    
   ### *Note: This study is currently under review.*   <br />  
  <br />  

## Description of R scripts

1. [Preprocessing](https://github.com/DavidKang-USDA/Sour-rot-microbiome-assembly/blob/main/R%20Scripts/Preprocessing.Rmd)—This script preprocesses the raw sequencing reads using [DADA2](https://benjjneb.github.io/dada2/). The script generates statistics, filters and trims, dereplication, clustering, chimera removal, assigns taxonomy, and gets a phyloseq object for downstream analysis. The output from this step is the input for subsequent steps.

2. [Diversity, Differential abundance, Core microbiome and Co-occurence network ](https://github.com/DavidKang-USDA/Sour-rot-microbiome-assembly/blob/main/R%20Scripts/Diversity%2C%20differential%20abundance%2C%20core%2C%20upset%20and%20co-occurence.Rmd)- This script is designed to analyze microbial diversity—covering alpha diversity, beta diversity, and overall abundance—along with their associated statistical metrics. It identifies differentially abundant taxa across various treatment groups and characterizes the core microbial communities in Spotted Wing Drosophila (SWD) and grapes. Additionally, the script includes functionality for assessing co-occurrence patterns among core taxa. It also enables the generation and visualization of microbial co-occurrence networks in SWD, with comparative analysis between male and female flies, including relevant network statistics.

3. [Absolute Abundance](https://github.com/DavidKang-USDA/Sour-rot-microbiome-assembly/blob/main/R%20Scripts/Absolute%20abundance.Rmd) - This script is to compare the absolute abundance of microbial communities across various host types and their associated statistics.

4.  [Abundance classification](https://github.com/DavidKang-USDA/Sour-rot-microbiome-assembly/blob/main/R%20Scripts/Classification%20of%20abundant%20and%20rare%20using%20ulrb%20package.Rmd) - This script is to use ulrb (Unsupervised Learning based Definition of the Rare Biosphere) package that uses unsupervised machine learning to classify ASVs into abundance categories such as "rare," "undetermined," and "abundant".

5.  [Distance decay and Neutral model](https://github.com/DavidKang-USDA/Sour-rot-microbiome-assembly/blob/main/R%20Scripts/Distance%20decay%20and%20neutral%20model.Rmd) - This script analyzes microbial community assembly using geographic distance (via the Haversine formula), phylogenetic turnover (βMNTD), and the Sloan Neutral Model to assess the role of stochastic versus deterministic processes in microbiome structure



   #### *Note: The statistics for network comparison require huge memory and cores. So it is recommended to run this analysis in HPC.*


```

├─ README.md
├─ R Scripts
│  ├─ Co-occurence network.R
│  ├─ Differential abundance, core, cooccurence,  and upset plot.R
│  ├─ Diversity analysis.R
│  └─ Preprocessing.R
├─ Intermediate files
│  ├─ Bacterial abundance
│  │  ├─ 16S.corvallis_PS.rds
│  │  ├─ 16S_taxo2.rds
│  │  ├─ ASVs.fa
│  │  ├─ ASVs_counts.tsv
│  │  ├─ ASVs_taxonomy.tsv
│  │  ├─ corvallis_metadata.csv
│  │  └─ seqtab_final.rds
│  └─ Bacterial co-occurence network
│     ├─ swd_malevsfemale_spring_network.rds
│     └─ swd_spring_network.rds
├─ Figures
│  ├─ Main figures
│  │  ├─ Fig. 1.pdf
│  │  ├─ Fig. 2.pdf
│  │  ├─ Fig. 3.pdf
│  │  ├─ Fig. 4.pdf
│  │  └─ Fig. 5.pdf
│  └─ Supplementary figures
│     ├─ Fig. S1.pdf
│     ├─ Fig. S2.pdf
│     ├─ Fig. S3.pdf
│     └─ Fig. S4.pdf
└─ Table
   └─ Supplementary tables
      ├─ Table S1.xlsx
      ├─ Table S2.xlsx
      ├─ Table S3.xlsx
      ├─ Table S4.xlsx
      ├─ Table S5.xlsx
      └─ Table S6.xlsx
```
## Data Availability

Sequence data generated from this work have been deposited in the SRA (Sequencing Read Archive) database under the BioProject accession number [PRJNA1246986](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA1246986). 


## Acknowledgements
This research used resources provided by the SCINet project and/or the AI Center of Excellence of the USDA Agricultural Research Service, ARS project numbers 0201-88888-003-000D and 0201-88888-002-000D.

## Funding
Rishi Bhandari was supported by a postdoctoral fellowship funded by the USDA Agricultural Research Service's SCINet Program and AI Center of Excellence, ARS project numbers 0201-88888-003-000D and 0201-88888-002-000D, and administered by the Oak Ridge Institute for Science and Education (ORISE) through an interagency agreement between the U.S. Department of Energy (DOE) and the U.S. Department of Agriculture (USDA). ORISE is managed by ORAU under DOE contract number DESC0014664. All opinions expressed in this paper are the authors and do not necessarily reflect the policies and views of the USDA, DOE, or ORAU/ORISE.
