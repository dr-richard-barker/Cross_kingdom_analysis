# Methods:

### GeneLab API: Exploring Space Biology Data

The NASA GeneLab provides an API (Application Programming Interface) for accessing information about biological samples and related data from spaceflight experiments. This data can be useful for researchers interested in the effects of space travel on various organisms.



[Link to Matrix 2 spread sheet](https://docs.google.com/spreadsheets/d/1JnNUCQ-FOr2\_AI0yXlc0boexObLqYGxJGUxFe9hBtYg/edit?usp=sharing).



{% embed url="https://docs.google.com/spreadsheets/d/1JnNUCQ-FOr2_AI0yXlc0boexObLqYGxJGUxFe9hBtYg/edit?usp=sharing" %}

Here's how to use the GeneLab API to retrieve metadata (descriptive information) about samples:

**GeneLab training:** [**https://genelab.nasa.gov/genelabAPIs**](https://genelab.nasa.gov/genelabAPIs)

1. **Choose your organism of interest:** The API allows you to filter samples by the organism they come from. Provided are pre-built queries for popular research models:
   * **Mouse:** [**https://visualization.genelab.nasa.gov/GLOpenAPI/samples/?study.characteristics.organism=Mus%20musculus\&file.datatype**](https://visualization.genelab.nasa.gov/GLOpenAPI/samples/?study.characteristics.organism=Mus%20musculus\&file.datatype)
   * **Arabidopsis:**[**https://visualization.genelab.nasa.gov/GLOpenAPI/samples/?study.characteristics.organism=Arabidopsis%20thaliana\&file.datatype**](https://visualization.genelab.nasa.gov/GLOpenAPI/samples/?study.characteristics.organism=Arabidopsis%20thaliana\&file.datatype)
   * **Human:** [**https://visualization.genelab.nasa.gov/GLOpenAPI/samples/?study.characteristics.organism=Homo%20sapiens\&file.datatype**](https://visualization.genelab.nasa.gov/GLOpenAPI/samples/?study.characteristics.organism=Homo%20sapiens\&file.datatype)
   * **Fly (Drosophila melanogaster):** [**https://visualization.genelab.nasa.gov/GLOpenAPI/samples/?study.characteristics.organism=Drosophila%20melanogaster\&file.datatype**](https://visualization.genelab.nasa.gov/GLOpenAPI/samples/?study.characteristics.organism=Drosophila%20melanogaster\&file.datatype)
2. **Get all GeneLab samples metadata:** If you're interested in all samples regardless of organism, use this link: [**https://visualization.genelab.nasa.gov/GLOpenAPI/samples/**](https://visualization.genelab.nasa.gov/GLOpenAPI/samples/)
3. **Get all GeneLab datafiles metadata:** If you're interested in all datafiles regardless of organism, use this link [**https://genelab-data.ndc.nasa.gov/genelab/data/glds/files/1-700**](https://genelab-data.ndc.nasa.gov/genelab/data/glds/files/1-500)



**Metadata Filters**

The GeneLab API application stands out by offering an extensive array of space biology metadata. This feature empowers users with the tools to efficiently sift through vast data sets, facilitating the identification of studies that are most relevant to their research inquiries. With these metadata filters, researchers can streamline their search process, honing in on the information that most closely aligns with their investigative focus.

By implementing selection criteria and significance cutoff values, the GeneLab API ensures that users are equipped with the necessary tools to uncover the most pertinent genes and molecular signatures for their research endeavors. This approach not only enhances the user experience but also significantly contributes to the advancement of biological research, paving the way for new discoveries.



#### Enhanced Insights in Data Visualization User Experience for Biological Research

Qlik cloud was used to pull data from the Open Science Archive data access API into an interactive graphical databases allowing exploration of the GeneLab derived gene expression analysis statictics. This enabled the identification of related studies which had their counts merged for the application of deep learning RNAseq analysis systems derived from the IDEP2.0 pipeline.&#x20;

**Fold Change Filtering and Significance Filtering**

Critical to discerning vital information in biological research, **Fold Change Filtering** and **Significance Filtering** emerge as pivotal features. These methodologies assist researchers in identifying key genes and molecular signatures that are not just statistically significant but also biologically relevant:

* **Fold Change Filtering** focuses on the magnitude of change, helping in pinpointing genes or proteins that exhibit substantial alterations under specific conditions.
* **Significance Filtering** applies stringent statistical criteria to ensure the observed changes are not due to random variations but reflect true biological alterations.





_**GeneLab X-Kingdom graph database uses  b**_**iological filters :**

1. Gene start site and basic isoform model -> Ensemble / Biomart
2. Gravitropism filters ->TAIR
3. Genome Ontology -> GOSLIM filters
4. Gene Family filters -> TAIR
5. ARA-CYC -> metabolism filter
6. Reactome -> metabolism filter
7. ROS filters -> ROS wheel(REF)
8. REDOX interactome -> ROS filters&#x20;
9. Cellular site -> Genome ontology  (REF)
10. Root cell markers -> Brady et al.,(REF)
11. Post translational modification -> PTM database (REF)
12. MicroRNA targets -> TAIR (REF)
13. Gene Othologues -> ENSMBLE compara (REF)
14. Protein Orthologues -> OMA (REF)
15. Hormone interactome -> (REF)
16. Mitocarta -> broad institute (REF)
17. Arabidopsis Mitochondria -> Australia paper ? Suba5 (REF)
18. Plasmodesmata -> paper? (REF)
19. Transcripitona factor database -> Agris\_TF\_List
20. H2O2 responsive transcription factors -> Hieno et al., (2019)
21. "Methylation Filters, Xu et al., (2018)" -> ref Xu et al., (2018)











