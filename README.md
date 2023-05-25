# Udemy: Introduction to Cheminformatics and medicinal chemistry

## Section 1

### Cheminformatics and medicinal chemistry

Three main applications of *cheminformatics*:

- Drug discovery
- Environmental science
- Materials science

*Cheminformatics* involves:

- storage of chemical data (databases)
- data analysis (features, [num pi bonds, polarity etc.], visualisation)
- representation (encodings; SMILES, SMARTS, InChl)

*Medicinal chemistry* involves:

- biology
- chemistry
- pharmacology (study of drugs)

*Medicinal chemistry* can be done in three ways:

- computational
- synthetic
- experimental (both computational and synthetic)

Process of drug discovery:

1. discovery and screening
2. optimisation
3. ADMET (absorption, distribution, metabolism, excretion, toxicity)
4. clinical studies
5. approval

Testing can be done:

- *in vitro* (in individual cells)  
- *in vivo*  (in living organisms, esp. mice)  
- *in silico* (simulation)

Types of drug:
    - biologics (proteins, antibodies)  
    - vaccines  
    - naturals  
    - botanical extracts  
    - derived from natural products (occurring in plants, fungi)  
    - synthetic (made in lab)

### Units of biological activity

Concentrations are measured in units of ml/mL, (micro)g/mL, ng/mL, pg/mL. Those with lower concentrations usually have high biological activity, and vice versa.

Biological activity is also measured in **molarity** (moles of solute per litre of solution).

**IC50 **- means the concentration (e.g. 2.5 mg/mL) needed to kill half the population of organisms exposed (e.g. bacteria in an in vitro experiment).

Molecular weight is measured in **g/mol**.

For in vivo stuff, units are usually mg/kg.

When concentrations are expressed in units like ppm (parts per million), ppb etc. it refers to the **mass ratio**.

Standard parameters of biological activity:

EC50 - effectory concentration for 50%  
IC50 - inhibitory concentration for 50%  
CC50 - cytotoxic concentration for 50%  
LD50 - lethal dose for 50%  
ED50 - effectory dose for 50%

*XX50 - general format*

etc. 

### SMILES

Simplified Molecular Input Line Entry System


A 1D sequence of symbols used to represent a 3D molecule. e.g.:

CN1CCC[C@H]1c2cccnc2

SMILES are used for input to computational models and software.

Bond type notation:

- CCO (simple bonds)  
- O=C=O (double bonds)  
- C#N (triple bonds)  
- [Na+].[Cl-] non-covalent bonds  

Rings and cycles:

- C1CCCCC1 (closed ring of 6 carbons; cyclohexane) (seems like the H are ignored)

Aromaticity has three different notations: (all three of these mean the same, I think)

- C1=CC=CC=C1      
- C1:C:C:C:C:C:C1  
- c1ccccc1

Radicals are denoted in parentheses, e.g.

CCC=CO(C)CC (5-methyl heptene)
CCC(C)CC    (3-methyl pentane)

Cis and trans bonds:

/\ : cis bonds 
// : trans bonds  

e.g. 

F/C=C\F (cis-1,2-difluorethylene)
F/C=C/F (trans-1,2-difluorethylene)


## Section 2

Three large databases:

PubChem, ZINC, ChemSpider.

### PubChem

Filters for search include:
compounds, substances, pathways, bioassays, literature, patents.

Contents:
1. structures
2. names and identifiers
3. chemical and physical properties
4. spectra
5. related records
6. vendors
7. drug and medication information
8. pharmacology and biochemistry
9. use and manufacturing
10. identification
11. safety and hazards
12. toxicity
13. disorders and diseases
14. literature
15. patents
16. biomolecular interactions and pathways
17. biological test results
18. classification
19. information sources

Some types of chemical structure:

cyclics, polycyclics, amino acids, furanoses, pyranoses, nucleotides


### ZINC

Physical/chemical features include:

mwt, logP, mol formula, rings, heavy atoms, hetero atoms, fraction sp3, pH range, net charge, H-bond donors, H-bond acceptors, tPSA, rotatable bonds, apolar desolvation, polar desolvation


### ChemSpider

As above - lots of filters and info.





## Section 3: ADME(T)

- Administration
- Distribution
- Metabolism
- Excretion
- (Toxicity)

### Bioavailability descriptors

Example descriptor values of a drug that relate to ADME from Lipinski et al.:

- molecular weight <= 500g/mol
- hydrogen bond acceptors <= 10
- hydrogen bond donors <= 6
- logP < 5

This is the **Rule of 5** (because these four quantities are divisible by 5). Lots of drugs satisfy the rule of 5 but not all.

logP is a measure of hydrophilicity. Drugs can't be too hydrophobic.

"Rule of 5" is one of the filters in PubChem.

Two more descriptors that relate to bioavailability / absorption:

- TPSA (total polar surface area). Ideally less than 140 Angstrom)^2 for good absorption.
- ROTB (number of rotatable) bonds. < 10 rotatable bonds for good oral bioavailability.

<u>*Notes on (inter- and intra-) molecular hydrogen bonding:</u>*
    Carbon that's covalently bonded to Hydrogen is not particularly electronegative, whereas when H is bonded to F, N or N (denote them X), these latter three are quite electronegative. This means that X-C bonds are dipoles, and bond with other, similar dipoles on other molecules. e.g. intermolecular bonds F-H-F, O-H-N, etc.

Hydrogen bonds are asymmetric. The Hydrogen in the X-H covalent bond has its electron density pulled towards X due to X's electronegativity, resulting in a partial positive charge on the H atom. This H atom can then be attracted to a lone pair of electrons on an electronegative Ẍ atom (which has a partial negative charge), forming a hydrogen bond.

The **Ẍ is the H bond acceptor**, in the sense that it's "accepting" the X-H bond for hydrogen bonding.

The **X-H is the H bond donor**, in the sense that it's donating the bond to the Ẍ.

````bash

GPT-4's take on it:

Can you provide me with a cheat sheet that rougly summarises the various descriptors (such as molecular weight <= 500mg/mol) for molecules in drug discovery, and how these descriptors relate to the various considerations in the ADMET framework?

ChatGPT
Sure, here is a high-level cheat sheet for some key considerations for drug-like molecules within the ADMET (Absorption, Distribution, Metabolism, Excretion, Toxicity) framework. These considerations help scientists in the early stages of drug discovery evaluate the potential of a compound to become a successful drug.

Absorption and Distribution

Molecular Weight: Typically, drug-like molecules have a molecular weight of ≤ 500 g/mol. This relates to absorption and distribution as smaller molecules are generally more readily absorbed and can more easily reach their target in the body.
Lipophilicity (LogP)

This is a measure of a drug's solubility in fat compared to water. A LogP of around 2 - 5 is generally desirable for a drug candidate. Too lipophilic (high LogP) can lead to poor solubility and issues with absorption and distribution, while too hydrophilic (low LogP) might result in rapid renal excretion and a lack of penetration across lipid membranes, thus impacting absorption and distribution.
Polar Surface Area (PSA) and Number of Hydrogen Bond Donors/Acceptors

These descriptors relate to a molecule's ability to form hydrogen bonds. A high PSA or a high number of hydrogen bond donors/acceptors can reduce a molecule's ability to cross cell membranes, which can affect absorption and distribution. The "Rule of 5" suggests that molecules with a PSA of ≤140 Å², ≤5 hydrogen bond donors, and ≤10 hydrogen bond acceptors are more likely to have good oral bioavailability.
Metabolism

Cytochrome P450 enzymes: Molecules that are substrates for these enzymes can be metabolized more quickly, reducing their effective concentration. Molecules that inhibit these enzymes can cause drug-drug interactions.
Excretion

Size and polarity: Larger, more polar molecules are more likely to be excreted in the urine.
Toxicity

Reactive groups: Certain chemical groups can react with cellular molecules, leading to toxicity.
hERG inhibition: Molecules that inhibit the hERG potassium ion channel can cause cardiac toxicity.
Please note that these are rough guidelines and many successful drugs do not fit all these criteria. In addition, the importance of each descriptor can vary depending on the specific drug and target in question. Drug discovery involves a complex interplay of these and many other factors.

````

### Molinspiration / SwissADME

These packages have lots of functionality. For e.g. can calculate bioactivity scores based on a SMILES code:

Bioactivity scores for OC=CSc2cc1cnccc1cc2O:

GPCR ligand:-0.28
ion channel modulator: 0.20
kinase inhibitor: -0.04
nuclear receptor ligand -0.33
protease inhibitor: -0.31
enzyme inhibitor: 0.14

Such scores indicate that this molecule is likely an enzyme inhibitor and ion channel modulator, but not a protease inhibitor, etc.

Can also calculate physicochemical properties and ADME paramaters, pharmacokinetic properties etc.

### Pro-Tox-II

Theoretical prediction of chemical toxicity endpoints such as acute toxicity, hepatoxicity, cytotoxicity, carcinogenicity, mutagenicity, immunotoxicity, etc. Good for reducing *in vivo* experiments.

Toxicity classes:

Class I: fatal if swallowed (LD50 <= 5mg/kg)
Class II: fatal if swallowed (5mg/kg < LD50 <= 50mg/kg)
Class III: toxic if swallowed (50mg/kg < LD50 <= 300mg/kg)
Class IV: harmful if swallowed (300mg/kg < LD50 <= 2000mg/kg)
Class V: may be harmful if swallowed (2000mg/kg < LD50 <= 5000mg/kg)
Class VI: non-toxic (LD50 > 5000mg/kg)

## Section 4: Structure and biological activity














