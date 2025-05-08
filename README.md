# 2025-topic-03-group-02
# 🧬 Proteome-wide Screen for RNA-dependent Proteins

Welcome to the **Proteome-wide Screen for RNA-dependent Proteins** project! This repository will serve as the central place for exploring, analyzing, and visualizing data related to RNA-protein interactions across the proteome.

Fragen: 
- Dürfen/Sollen wir die selben Kriterien zur bestimmung des Shifts (1 Fraction) verwenden, wie das original paper? wie wird das begründet? wofür haben die dann die ganzen anderen shift characteristics berechnet?
- Reicht die Analyse des Protein amounts between replicates als reproducibility check?
- immernoch die Frage, wie kommen wir von der Lyse ganzer Zellen zu Mass spectromity daten einzelner proteine? wie kann man die proteine genau idenyifizieren, sicher sein, dass in control und RNase probe wirklich genau das Protein betrachtet wird?
- Wenn man sich R-Deep 3.0 anguckt, dann wurde doch alles was wir machen sollen schon getan oder? Sinn????
    Können wir die Daten dann nutzen um zu schauen, ob wir alles richtig gemacht haben?
- Wie genau kann man sich die Quantifikation vorstellen, "Amount of protein" = Fläche unter der Kurve, aber sind das nicht immer 100% ?? und wieso braucht man dieses Parameter, wofür?

# Project plan Draft
Working in sprints and Correction loops (1.week cooding, 2.week adaptation to feedback)

**14.05.-06.06. 🧹 Data Cleanup & Reproducability Analysis**

- Description of the Dataset (Dimensions, etc... partly done for Proposal)
- Restructuration of coloums e.g. per freactions or CTRL. vs RNase (maybe subtabels and factors)
- Handeling of missing values (if present)
- Reproducibility of the experiement:comparison of protein amounts/ data between triplicates (of a randomly choosen franction) for all proteins
- Normalisation of the triplicates (compute means --> one value per protein, fraction and CTRL/RNase)
- Normalization of protein amount to 100 (determination of normalization factor and application)

_**Deliverable**: Normalized MS_Table ready to work with, Description of Dataset & Statement regarding reproducibility_


**6.06.-20.06. 🧐 Data Analysis** full focus (no exams)

- Gaussian fitting 
- Determination of: number of peaks, position and hight of local maxima, quantification/amount of protein 
- Comparison between CTRL. vs RNase / Determination of Shift Characteristics: 
    - distance of shift
    - direction of shift
    - number of shifts
    - difference between protein amounts
    - difference between amplitudes
- Statistical Test for shift significance / RBP postive
    - Definition of criteria for a RBP postive shift and significance level
    - Application for each protein
- Validation of the test using a listed postive RBP and a listed negative RBP as control

_**Deliverable**: Shift characteristics for each protein, classification of each protein as RBP or RNA-independent_


_Optional stuff generally_ 

- Comparison of identificated RBPs with already listed RBPs
- Use quantification to further categorize the RBPS as dependent, partly dependent and independent 

(but I think since we have a Mitosis sataset, we should focus on questions regarding mitosis)

    
_Optional stuff mitosis related_ (but wee need to do a clustering and linear regression analysis)

- Comparison with data of nonsynchronizied celles (has already been done)
    - run through the same pipeline and compare RBP positiv proteins (similaritys and new RBPs)
    - define RBPs, that are only active in Mitosis
- Clustering of mitosis relvant RBPs regarding Shift traits (has not been done, as far as I know; only for whole all proteins in nonsynchronizised cells)
    - find similar working RBPs or even RBP complexes    
- Phosphorylation check of mitosis relvant RBPs
    - integrate protein data with databases like "phosphositet" oder "olsen et.al"  
- Describe a certain protein/set of proteins more deeply (relevant for mitosis) --> story telling

_--> Regression analysis, where how, for what????_


**20.06.-7.07. 🎯 Preparation of Report and Presentation** 

- Graphical depiction of certain findings (specific proteins,clusterings, etc.) make it pretty :)
- Finalise R-Markdown (Cleanup and description of the code)
- Write ReedMe
- Design Poster

Test


> ⚠️ _Note: This README is a starting template. Please update it as your project evolves._
>
For inspiration on writing a comprehensive and engaging README, check out the [Awesome README](https://github.com/matiassingers/awesome-readme?tab=readme-ov-file) repository.

MS_Table <- read.table("C://Users//Sofi//Downloads//RDeeP_HeLa_Mitosis//RDeeP_HeLa_Mitosis.csv", header=TRUE, row.names=1, sep = ";")
head(MS_Table)

# For example: 
# MS_Table <- read.table("~/Desktop/2024_Data_Analysis_Proteom/RDeeP_HeLa_NS.csv", header=TRUE, row.names=1, sep = ";")



# 📚 Papers

# Reviews
- [Sternburg et al., Global Approaches in Studying RNA-Binding Protein Interaction Networks, 2020, Trends in Biochemical Sciences.pdf](https://github.com/user-attachments/files/19981693/Sternburg.et.al.Global.Approaches.in.Studying.RNA-Binding.Protein.Interaction.Networks.2020.Trends.in.Biochemical.Sciences.pdf)
- [Corley et al., How RNA-Binding Proteins Interact with RNA Molecules and Mechanisms, 2020, Molecular Cell.pdf](https://github.com/user-attachments/files/19981705/Corley.et.al.How.RNA-Binding.Proteins.Interact.with.RNA.Molecules.and.Mechanisms.2020.Molecular.Cell.pdf)
- [Gebauer et al., RNA-binding proteins in human genetic disease, 2020, Nature Reviews Genetics.pdf](https://github.com/user-attachments/files/19981707/Gebauer.et.al.RNA-binding.proteins.in.human.genetic.disease.2020.Nature.Reviews.Genetics.pdf)

# Experimental methods
- [Caudron-Herger et al., R-DeeP Proteome-wide and Quantitative Identification of RNA-Dependent Proteins by Density Gradient Ultracentrifugation, 2019, Molecular Cell.pdf](https://github.com/user-attachments/files/19981712/Caudron-Herger.et.al.R-DeeP.Proteome-wide.and.Quantitative.Identification.of.RNA-Dependent.Proteins.by.Density.Gradient.Ultracentrifugation.2019.Molecular.Cell.pdf)
- [Caudron-Herger-Identification, quantification and bioinformatic analysis of RNA-dependent proteins by RNase treatment and density gradient ultracentrifugation using R-DeeP-2020-Nature Protocols_1.pdf](https://github.com/user-attachments/files/19981715/Caudron-Herger-Identification.quantification.and.bioinformatic.analysis.of.RNA-dependent.proteins.by.RNase.treatment.and.density.gradient.ultracentrifugation.using.R-DeeP-2020-Nature.Protocols_1.pdf)
- [Rajagopal-Proteome-Wide Identification of RNA-Dependent Proteins in Lung Cancer Cells-2022-Cancers.pdf](https://github.com/user-attachments/files/19981723/Rajagopal-Proteome-Wide.Identification.of.RNA-Dependent.Proteins.in.Lung.Cancer.Cells-2022-Cancers.pdf)
- [Rajagopal et al., An atlas of RNA-dependent proteins in cell division reveals the riboregulation of mitotic protein-protein interactions. Nat. Commun. 16, 2325 (2025).pdf](https://github.com/user-attachments/files/19981728/Rajagopal.et.al.An.atlas.of.RNA-dependent.proteins.in.cell.division.reveals.the.riboregulation.of.mitotic.protein-protein.interactions.Nat.Commun.16.2325.2025.pdf)
