# 2025-topic-03-group-02
# 🧬 Proteome-wide Screen for RNA-dependent Proteins of HeLa cells synchronized in mitosis


## **Introduction** 
Welcome to our quest to follow a protein on its journey, where it searches for its friends and family, while it adapts and learns new things about itself.
### Introduction to RNA Binding Proteins – Spoiler alert!:
RNA-binding proteins (RBPs) are essential regulators of gene expression, controlling everything from splicing and localization to translation and degradation of RNA. RBPs are dynamic players whose behavior can change dramatically depending on the cell’s current “season.”
During the cell cycle, and especially in the high-stakes phase of mitosis, RBPs undergo striking redistributions and functional shifts. Some vanish into the background, while others emerge as key orchestrators of the mitotic program, helping the cell divide its internal world with precision.
By exploring how RBP activity and localization change during mitosis, we uncover clues to how cells coordinate this tightly regulated process — and perhaps, how dysregulation leads to disease. This project dives deep into the shifting world of RBPs in mitosis. 
### Introduction to Our Data
All proteins originate from mass spectrometry data of HeLa cells in mitosis.

    Total number of proteins:7159

    Number of fractions: 25

    Number of replicates per protein: 3
### Overview of Goals

**RNA-dependent Proteins**
The first goal of our pipeline was to develop a method to determine, as reliably as possible, whether a protein is an RBP or not. We approached this by comparing the two experimental conditions under which the proteins were analyzed: Ctrl and RNase. By characterizing the change—or shift—in protein distribution, we identified RNA-dependent proteins.

**RNA-dependent Proteins Active in Mitosis**
Our second goal was to take advantage of our specific dataset from synchronized HeLa cells in mitosis. Using the results from the first step, we applied the same pipeline to the synchronized dataset. We then overlaid both results and extracted all proteins that, according to our logic, should only be active in mitosis—i.e., proteins that exhibited RBP-like behavior exclusively during mitosis.

**Complex Finding**
As our third goal, we aimed to deepen our analysis by identifying protein clusters and determining whether they could represent potential RBP-dependent complexes active in mitosis. To help interpret these findings, we compared our predicted complexes with known complexes from the CORUM database.

**Molecular Weight Prediction**
Finally, we explored whether our data could support other types of predictions beyond RBPs. Specifically, we investigated whether the sucrose gradient (i.e., the positions of the fractions) correlates with molecular weight.

## **Results**

### Who is RiboSix?
RS6_Human or as we call it RiboSix is one of the RNA-dependent proteins we identified.
What makes it so unique is that is only active during mitosis and works in a complexe 
with other RNA-dependent proteins. How we found that out, is described in the following.
> ![RS6_Human Plot](Images/RBP_RS6_HUMAN.png)
**Fig. 1: Intensity profile of RS6_HUMAN across 25 fractions.**
Normalized intensities across control and RNase treatment reveal a clear leftward 
shift in elution after RNase treatment, indicative of RNA-dependent behavior. 
Additional panel summarizes shift distance, complex membership (CORUM), and molecular weight.



### Identification of RNA-dependent proteins 
To detect RNA-dependent behavior, proteins were classified as RNA-binding candidates 
if their center of mass (CoM) shifted more than one fraction toward the top of 
the gradient upon RNase treatment. This shift indicates loss of RNA interactions 
that otherwise stabilize their complex or position in the gradient.
The resulting list of RNA-dependent proteins was then cross-referenced with UniProt 
annotations to evaluate how many of them were already known and how many may represent novel candidates.

**Total RNA-dependent proteins identified: 794** 

**Validated by UniProt annotation: 230**

**Novel RNA-binding candidates: 564**

> ![Validation t-Test via UniProt](Images/Validation_TTest_UniProt_2.png)
**Fig. 2: Validation of RNA-dependence by T-Test using UniProt annotation.**
Scatterplot comparing Center of Mass (CoM) values between control and RNase-treated 
samples for all proteins. Each point represents one protein, color-coded by RNA-binding 
significance: proteins overlapping with UniProt RBPs (dark blue), novel RNA-dependent candidates 
identified by T-Test (light red), UniProt RBPs not detected as significant (cyan), and non-significant 
proteins (grey). The dashed diagonal line marks equal CoM values, with leftward deviation indicating 
RNA-dependent shift behavior. This visualization highlights both confirmed and potentially novel RBPs.


### Identification of mitosis specific proteins 
To assess whether RNA-binding activity was specific to the mitotic phase, the same 
shift-based analysis was applied to non-synchronized HeLa cells. Shift profiles 
were then compared between conditions. Proteins that showed a significant shift 
only during mitosis, but not in the non-synchronized state, were considered mitosis-specific 
RNA-dependent proteins. 

**RBPs uniquely active in mitosis: 237**
> ![Comparison of Shift Distances between mitosis and non-synchronized condition](Images/Shift_Distance_Mitosis_vs_NS_2.png)
**Fig. 3: Comparative Shift Scatterplot (Mitosis vs. Non-Synchronized).**
Scatterplot displays shift distances derived from center of mass (CoM) 
values for all proteins under both conditions. Each point represents one protein, 
color-coded by statistical significance. The red dashed identity line marks equal 
shift behavior; proteins below the line show mitosis-specific leftward shifts, suggesting 
RNA dependency unique to mitosis.

### Finding Complexes of mitotic RBPs
To explore whether these RBPs act in shared complexes, density-based clustering 
(DBSCAN) was performed using shift and peak features. Known complexes such as the 
40S ribosomal subunit and the Nop56p-associated pre-rRNA complex served as validation benchmarks.

**Proteins from 40S complex clustered together: 3/4**

**Proteins from Nop56p complex clustered together: 4/9**

**Proteins in relevant cluster (Cluster 4): 13**

### Predicting Molecular Weight
It was hypothesized that shift behavior might correlate with molecular weight due 
to sedimentation properties. However, linear regression between RNase-shift-based 
elution profiles and known molecular weights showed no significant relationship.

**Spearman correlation (peak position vs. MW): 0.014**

**R² of linear regression: 0.00017 (p = 0.25)**

## Repository 









# Was here before (delete when finished the Readme)
> ⚠️ _Note: This README is a starting template. Please update it as your project evolves._
>
For inspiration on writing a comprehensive and engaging README, check out the [Awesome README](https://github.com/matiassingers/awesome-readme?tab=readme-ov-file) repository.



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
