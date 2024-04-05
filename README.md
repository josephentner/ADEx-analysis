# ADEx-analysis

This project performed a computational analysis on gene expression samples across multiple autoimmune diseases from the ADEx gene expression database. We used R to conduct various computational techniques to validate the database as a basis to conduct cross-disease analysis as well as perform downstream bioinformatics analyses. 

## Pipeline

### Data Preprocessing
We first downloaded samples from the database that contained gene expression counts and came from PBMC populations. In `data_preprocessing.Rmd`, we combined these samples and their metadata into one file that we could then use for downstream data exploration and analysis, which is uploaded as `combined_data.csv.zip`.

### Data Exploration
We used multiple dimensionality reduction techniques (PCA, UMAP, tSNE) to visualize the data in the `combined_data.csv` file. We found that PCA was the best way to display the gene expression data across multiple studies and tissue types. Running `data_exploration.Rmd` will show the significant PCA graphs that best represent the data. From these results, we narrowed down our next analyses to specific tissue types and diseases we thought would present the most relevant and interesting results.

### Data Analysis
We chose to focus on systemic lupus erythematosus, rheumatoid arthritis, and Sjögren's syndrome for this analysis. We began by conducting differential gene expression analyses on each disease through the Wilcoxon Rank Sum test. We then used the Reactome gene sets and Biogrid protein interaction networks to run a pathway enrichment analysis on the top differentially expressed genes for each of the diseases. We performed hierarchical clustering on the resulting pathways to determine the broader biological impact of each of these dysregulated pathways. `data_analysis.Rmd` displays the code used for these analyses, and the resulting graphs displaying these genes and associated pathways is shown in the `term_visualizations/` folder.

## Results and Discussion
Because the ADEx database is relatively new, there has not been much research published analyzing the data present in the database. By focusing on a subset of the data in the database, this project served as a first-pass for how an in-depth analysis on the database could be carried out. We discovered unique and shared dysregulated genes across these diseases and their associated biological pathways. These results serve as a basis for further understanding the pathogenesis of different autoimmune diseases and their relationship to one another. Further discussion of our results can be found on our poster presented at Northeastern University's 2024 RISE Expo found here (add link to poster).

## Authors and Acknowledgements
This project was performed by Joseph Entner and Melis Akinci under the mentorship of Anne Van De Ven-Moloney, Ph.D. This project was funded by the Northeastern University Undergraduate Research and Fellowships PEAK Experiences Award.

## References

1. Jordi Martorell-Marugán, Raúl López-Dominguez, Adrián García-Moreno, et al. (2021) A comprehensive database for integrated analysis of omics data in autoimmune diseases. BMC Bioinformatics. 22, 343, [https://doi.org/10.1186/s12859-021-04268-4](https://doi.org/10.1186/s12859-021-04268-4)
2. Hu Y, Carman JA, Holloway D, Kansal S et al. Development of a Molecular Signature to Monitor Pharmacodynamic Responses Mediated by In Vivo Administration of Glucocorticoids. Arthritis Rheumatol 2018 Aug;70(8):1331-1342. PMID: 29534336
3. Lessard CJ, Li H, Adrianto I, Ice JA et al. Variants at multiple loci implicated in both innate and adaptive immune responses are associated with Sjögren's syndrome. Nat Genet 2013 Nov;45(11):1284-92. PMID: 24097067
4. Li, Y., Ge, X., Peng, F. et al. Exaggerated false positives by popular differential expression methods when analyzing human population samples. Genome Biol 23, 79 (2022). [https://doi.org/10.1186/s13059-022-02648-4](https://doi.org/10.1186/s13059-022-02648-4)
5. Ulgen E, Ozisik O, Sezerman OU. 2019. pathfindR: An R Package for Comprehensive Identification of Enriched Pathways in Omics Data Through Active Subnetworks. Front. Genet. [https://doi.org/10.3389/fgene.2019.00858](https://doi.org/10.3389/fgene.2019.00858)