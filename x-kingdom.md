# X Kingdom&#x20;

**Title:** X Kingdom

_**About to push a new update…**_





Link to app: [XKINGDOM (11) (Gravity-Ara-Human-Astronaut)](https://gilroy-qlik.botany.wisc.edu/a/sense/app/77aa616d-8f7d-489c-8501-4196aa731d0d/sheet/34d94e76-40e0-4c4a-a338-1f113fa39470/state/analysis) in action



**Abstract / Summary:**

This document describes a method for analyzing data from multiple species using NASA’s Genelab Open Science Data Repository. The method involves creating species-specific matrices and cross-kingdom matrices, and then using these matrices to identify significant genes. The significant genes are then analyzed to determine their biological functions. The method is demonstrated using data from humans, flies, mice, and Arabidopsis. The results show that the method can be used to identify genes that are important for specific biological processes.

In detail, the researchers first created species-specific matrices for human, fly, mouse and arabidopsis using data from NASA’s Genelab Open Science Data Repository. Then they created cross-kingdom matrices based on the orthologs of the four different species. Finally, they used PCA plots to identify significant genes in both the species-specific and the cross-kingdom matrices. The significant genes were then analyzed to determine their biological functions.

This method can be used to identify genes that are important for specific biological processes across different species. For example, the researchers found that the significant genes identified in the Arabidopsis orthologous matrices were all genes related to roots and root growth. This suggests that these genes are important for plant development.

**Keywords:** Mouse, Human, Plant, Fly, Worm, Spaceflight, RNAseq,&#x20;



**Introduction:**

The NASA Open Science Data Repository is a space-biology related open omics database.  Users can upload and search for specific data based on a given number of factors including species, tissue, gravitational factor, assay type, factor, and project type. Users can then analyse data of individual studies based on their specifications. We have created a comprehensive cross-kingdom matrix that allows users to analyse and compare data across multiple kingdoms at once. This allows for a comprehensive understanding of the effects of spaceflight at the molecular level in different organisms. We are now able to analyse and visualize patterns across multiple kingdoms that may have gone unnoticed or deemed as insignificant without the broad patterns this ensembled matrix provides. As space-related research continues to compile, the need for an application to cross-compare and analyze the omics of species is essential in systematizing further research as well as understanding the gravity of current publications and omics data.

\


**Objectives The Matrix Empire App**

The creation of this app is intended to allow users to access the omics datasets from Genelab and easily explore, compare and predict molecular responses through specific filters across multiple species. &#x20;



**Navigating the Matrix Empire App**

The Matrix Empire App utilizes dashboards as a visual index to navigate through different datasets. Each dashboard is complemented with a visual, description and links to related pages. Each dashboard is a starting base to further filter and streamline specific data. The dashboards are linked to allow for intuitive and easy data filtering throughout the app.



**Data Structure**

The datasets are imported from Nasa Genelab and compiled in the Qlik data App. The data for this matrix is selected based on assay technology type. Studies using RNA sequencing are chosen. The matrix filters genes by specific species, accession numbers, mission ID’s, strain, tissue, treatment, and gravitational factor.

\
**Empire Genelab App User Interface**

The Qlik App allows users to streamline data based on specific filters over across multiple species. Users are not only able to compare the effects of spaceflight versus terrestrial cellular function in one species, but can compare the effects of spaceflight versus terrestrial cellular function in multiple organisms. The app offers users the ability to quickly retrieve large amounts of data and efficiently analyize large amounts of metadata at once.

\


**Creation of focused subsets of studies identified using Empire Application**

The final M.muscus matrix consists of 470 samples and 41,649 genes, 25196 of which passed through filter and 3765 were converted to Ensembl gene IDs in our database. The remaining 21427 genes were kept in the data using the original IDs. The original mouse matrix created was so extensive that quality control became an issue; therefore, OSDS-272 and OSDS-273 were removed from the final matrix as they were preservation studies which did not align with any other research methods in the matrix. There was a sequence depth bias detected by Idep based on ANOVA.

D. melanogaster has 77 samples and 16,083 genes. 16083 genes passed filter with 0 being converted to Ensembl gene IDs and were kept using the original ID’s. There was sequence depth bias detected by Idep based on ANOVA.

The H. Sapien (Human) matrix (including JAXA6 data) consisted of 21 samples and 50930 genes, 13188 of these were converted to Ensemble gene IDs in our database; the remaining 37742 genes were kept in using the original ID’s.&#x20;

