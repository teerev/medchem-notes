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

### PUBCHEM

