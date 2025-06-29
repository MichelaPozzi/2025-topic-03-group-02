# 2025-topic-03-group-02
# 🧬 Proteome-wide Screen for RNA-dependent Proteins

Welcome to the **Proteome-wide Screen for RNA-dependent Proteins** project! This repository will serve as the central place for exploring, analyzing, and visualizing data related to RNA-protein interactions across the proteome.

# Final Days Plan und TO-DO

- Code aufräumen und einemal bei leerem Enivornment vollständig runnen (inkl. Namen)
- ReedMe schreiben und sichergehen, dass alle Projektdateien am richtigen Ort liegen
- Präsentation: 
--> Plan überlegen (Story Line und Storry Telling, Plotts udn Themen besonderer Wichtigkeit auswählen)
--> Complex auswählen, den wir hoffentlich gefuden haben und recherche dazu machen, was macht der?, wieso ist dieser Komplex nurn in Mitose aktiv?, vlt. Teile des Komplexes die wir nicht gefunden haben, wieso?, etc. 
--> Poster erstellen in PowerPoint 

# Projektplan Draft
Working in sprints and Correction loops (1.week cooding, 2.week adaptation to feedback)

**14.05.-03.06. 🧹 Data Cleanup & Reproducability Analysis**

--> Description of the Dataset (Dimensions, etc... partly done for Proposal)

--> Restructuration of coloums e.g. per freactions or CTRL. vs RNase (maybe subtabels and factors) --> gemeinsam besprechen, Verantwortliche: Lina

--> Handeling of missing values (if present) --> Verantwortlicher: Cihan

--> Reproducibility of the experiement:comparison of protein amounts/ data between triplicates (of a randomly choosen franction) for all proteins --> Verantwortliche: Sofia

--> Normalisation of the triplicates (compute means --> one value per protein, fraction and CTRL/RNase) --> Verantwortliche: Lina

--> Normalization of protein amount to 100 (determination of normalization factor and application) --> Verantwortlicher: Cihan


Deliverable: Normalized MS_Table ready to work with, Description of Dataset & Statement regarding reproducibility

**3.06.-24.06. 🧐 Data Analysis** full focus (no exams)

--> Gaussian fitting --> Lina

--> Determination of: number of peaks, position and hight of local maxima, quantification/amount of protein --> von der Gaußkurve --> erstmal Cihan (in neuem Data Frame machen, für jedes ctrl und rnase)

--> Comparison between CTRL. vs RNase / Determination of Shift Characteristics: 
    - distance of shift
    - direction of shift
    - number of shifts
    - difference between protein amounts
    - difference between amplitudes
    
--> Statistical Test for shift significance / RBP postive
    - Definition of criteria for a RBP postive shift and significance level
    - Application for each protein
    
-->Validation of the test using a listed postive RBP and a listed negative RBP as control


Deliverable: Shift characteristics for each protein, classification of each protein as RBP or RNA-independent

_Optional stuff generally_ 

If favorit Idea is not possible: 
--> Comparison of identificated RBPs with already listed RBPs

--> Use quantification to further categorize the RBPS as dependent, partly dependent and independent 

(but I think since we have a Mitosis sataset, we should focus on questions regarding mitosis)
    
_Optional stuff mitosis related_ (but wee need to do a clustering and linear regression analysis)

Favorit idea: 
--> Comparison with data of nonsynchronizied celles (has already been done)
    - run through the same pipeline and compare RBP positiv proteins (similaritys and new RBPs)
    - 1) define RBPs, that are only active in Mitosis
    
--> 1.1) Clustering and eventually PCA of mitosis relvant RBPs regarding Shift traits (has not been done, as far as I know; only for whole all proteins in nonsynchronizised cells)

    - find similar working RBPs or even RBP complexes 
    
--> 1.2) Idea for linear regression analysis: plot Molecular weight and peak maximums against each other + LRA

    - Predecting Molecular Weight of RBP in Mitosis by peak maximum 
*******************************************************************************************
In case we have time, not in project proposal before we promise something we cannot deliver:
--> Phosphorylation check of mitosis relvant RBPs

    - integrate protein data with databases like "phosphositet" oder "olsen et.al"
*******************************************************************************************
    
--> Describe a certain protein/set of proteins more deeply (relevant for mitosis) --> story telling

_--> Regression analysis, where how, for what????_


**24.06.-7.07. 🎯 Preparation of Report and Presentation** 

--> Graphical depiction of certain findings (specific proteins,clusterings, etc.) make it pretty :)

--> Finalise R-Markdown (Cleanup and description of the code)

--> Write ReedMe

--> Design Poster


 

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
