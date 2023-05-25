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

```

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

```

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

Four approaches to making structural modifications in drug candidates:

1. fragment-based approach
2. combinatorial library
3. peptidomimetics
4. iososterism

### Combinatorial library approach

A broad brush, brute-force approach to screening candidate compounds.

Start with a lead compound ---> generate a combinatorial library ---> do pharmacological evaluation of results ---> stop when desired activity or safety profile is achieved.

The lead compound is the reference compound; the results of the combinatorial library approach is to generate **derivative **compounds. Often it will turn out that one of the derivative compounds is more optimal w.r.t. bioactivity, toxicity, etc.

Then, you can generate more derivatives, now using the optimal compound from the first iteration as the lead compound.

e.g. raf-kinase inhibitor with IC50=17 micromoles per litre was used as a lead compound. One of the derivatives was found to have IC50=0.54 micromoles per litre, then a derivative of the derivative of IC50=0.012 micromoles per litre, which is more desirable.

### Structural modification

A more focused and constrained approach to screening by changing particular structural elements and substituting with various functional groups. The goal is to optimise activity, and/or safety and/or bioavailability.

e.g. antimalarial drugs derived from quinine.

### Fragment based approach

The compound is divided into, say, two fragments. The bioactivity / other parameters are predicted for the individual fragments. (note to self: This presumably assumes approximate chemical independence of the fragments and reduces the size of the configuration space to be searched.)

### Peptidomimetics

Peptidomimetics is a strategy in drug design that focuses on creating molecules that mimic the bioactivity of peptides. This is important because the body often recognizes peptides as nutrients and digests them, rendering the therapeutic peptides inactive. Peptidomimetics aim to overcome these limitations by enhancing stability, selectivity, and potency while retaining the beneficial biological activity of the original peptides.

Case study: HIV protease inhibitors prevent the cleavage of peptides into structural proteins used to assemble the HIV virus. Pseudopeptides (ritonavir, saquinavir) resemble proteins but can not be cleaved by HIV protease.

### Biososterism

Chemical substitutes or radicals that resemble a reference compound but have some substitutions. (Not sure of difference from above.)

e.g. antibacterial chalcones with increased solubility and change in the bioactivity from bactericidal to bacteriostatic, Nielsen et al. 2004.




## Section 5. Proteins

Proteins serve many functions:

- cell transport
- cell division
- cell respiration
- DNA replication
- cytoskeleton
- apoptosis
- gene transcription
- etc.

Protein structure can be described on multiple levels:

1. Primary structure:

Proteins are chains of amino acids. There are about 22 types in biological systmes. Each has an alpha carbon, hydrogen, amine group, carboxyl group and a radical. Peptides are chains of amino acids. These peptides are the primary structure.

2. Secondary structure:

Longer chains of peptides can have hydrogen bonds between amino acids; even non-adjacent amino acids. The two types of secondary structure are "alpha helix" and "beta sheet".

3. Tertiary structure:

The alpha helix and beta sheet can fold on top of each other.

4. Quarternary structure:

(Larger scale folding.... even more complex. Generally unsolved.)


Amino acids come in polar and apolar forms. The chemical features of amino acids are determined by the radical.

### Relevance of proteins in drug discovery

Most of the proteins that play a role in cells are enzymes. Here are some definitions:

**Enzymes: **Enzymes are biological catalysts, typically proteins, that speed up chemical reactions in the body. They do this by lowering the energy required for the reaction to occur (the activation energy). Each enzyme is highly specific, typically catalyzing only one type of reaction or working only on a specific type of molecule, known as its substrate.

**Substrates:** A substrate is the molecule upon which an enzyme acts. The enzyme binds to the substrate at a specific location called the active site, facilitating the chemical reaction. Once the reaction occurs, the substrate is converted into one or more different molecules, known as products.

**Byproducts (or Products)**: Products are the molecules that result from the enzymatic reaction. They are formed by the chemical modification of the substrate. Once the reaction is complete, the products are released from the enzyme's active site, freeing the enzyme to catalyze another reaction.

**Inhibitors**: Inhibitors are molecules that reduce or prevent the activity of enzymes. They do this by binding to the enzyme, often at the active site, which reduces the rate at which the substrate is converted into products.


### [Protein Data Bank](rcsb.org)(PDB)

Can filter by resolution; sub 2 Angstroms is preferred, but not always possible.

Can filter by enzyme classification:

hydrolase
transferase
oxidoreductase
lyase
isomerase
ligase
translocase

Files are in .pdb format.

The three main experimental methods used to determine protein structures are X-ray crystallography, nuclear magnetic resonance (NMR) spectroscopy, and cryo-electron microscopy (cryo-EM)

### Molecular docking

Predicting the binding of ligands with molecules computationally. An initial ligand / protein conformation is used, then binding affinity at various sites is sampled and the binding energy is calculated.


More conversations with GPT-4:
```
User
There are presumably all sorts of local energy minima on the surfaces of proteins where the ligand can bind. How many sites on the surfaces of proteins have some enzymatic function? Presumably in real applications, many ligand molecules need to used to cover the proteins? (sorry for the very naive question...)


ChatGPT
Your question is very thoughtful and it addresses an important point in protein function and enzymatic activity!

Enzymes typically have one active site where the catalytic activity occurs. This site is a unique region of the protein where the substrate binds and the chemical reaction is facilitated. However, proteins can also have additional binding sites known as allosteric sites, where other molecules (known as effectors or modulators) can bind to influence the activity of the enzyme. These sites can either increase (activators) or decrease (inhibitors) the enzymatic activity.

That said, proteins are indeed covered with various nooks, crannies, and surfaces that could theoretically bind a variety of molecules, and there could be many local energy minima where a ligand might bind. However, not all of these sites will have an effect on the protein's function. Some may simply result in "non-specific" binding, which doesn't do much of anything. Others might interfere with the protein's function, even if they're not at the active site.

The concentration of the ligand (or substrate, in the case of an enzyme) indeed matters. As the concentration increases, more enzyme molecules will have their active sites occupied and the rate of the reaction increases, until all active sites are occupied and the enzyme is working at its maximum rate (this state is known as saturation).

In drug design, a common strategy is to design drugs (ligands) that specifically target the active site or an allosteric site of an enzyme. By doing this, the drug can either block the activity of the enzyme (in the case of an inhibitor) or increase its activity (in the case of an activator). The goal is always to have a strong and specific interaction with the protein to elicit the desired effect, while minimizing non-specific interactions that could lead to side effects.

To sum it up, not all potential binding sites on a protein will have an effect on its function, and it's the careful design and use of ligands (such as drugs or substrates) that allows us to harness the power of these proteins for biological or therapeutic purposes.



User
And what reason is there to assume that a ligand which is known to block an enzymatically relevant site on one protein won't go and bind with some other type of protein and have unintended (or un-studied) effects elsewhere?


ChatGPT
You've touched upon an important challenge in drug development. The scenario you've described is indeed a real concern. When a drug is designed to bind to a specific protein target and inhibit its activity, it might also interact with other proteins in the body, leading to what are known as "off-target effects" or "side effects."

This is why selectivity is a key parameter in drug design. Ideally, a drug should bind to its target protein very selectively and with high affinity, while interacting very little with other proteins. However, achieving this is not easy, because many proteins in the body have similar structures or binding sites.

To improve selectivity, scientists study the structure of the target protein in great detail and design the drug to fit into its unique features as closely as possible. Computer modelling, like molecular docking, can be used to predict how well a potential drug will bind to its target protein versus other proteins.

Once potential drug candidates are identified, they are tested in laboratory experiments and clinical trials to see if they have the desired effect and to monitor for any potential side effects. This testing process helps to identify and eliminate drug candidates that have significant off-target effects.

Despite these efforts, it's not always possible to eliminate all off-target effects. Some drugs are approved for use despite having known side effects because the benefits of the drug are considered to outweigh the risks. This is a decision that is made on a case-by-case basis, taking into consideration the severity of the disease being treated and the severity of the potential side effects.

So in essence, the scenario you've described is a key challenge in drug design, and it's one of the reasons why developing a new drug is a long, complex, and costly process.



User
What level of physical / chemical modelling typically is used when calculating binding energies in docking studies? It's clearly not quantum chemistry methods since these are too intensive, and presumably not DFT either.

ChatGPT
Molecular docking is usually carried out using molecular mechanics or semi-empirical methods. These methods are computationally less intensive compared to quantum mechanical (QM) methods or Density Functional Theory (DFT), making them suitable for the large systems encountered in protein-ligand docking.

The main aspects involved in the calculation of binding energies in docking studies involve:

Force Field Methods: These use classical physics to model the molecules and their interactions. They employ parameterized mathematical functions to predict the energy of a system based on its conformation. Force fields like CHARMM, AMBER, or GROMOS are used to calculate energies. They include terms for bond stretching, angle bending, dihedral angle torsion, non-bonded interactions, etc.

Scoring Functions: These are algorithms used to predict the strength of the interaction between the protein and the ligand (the binding affinity). They use a simplified, empirical approach to estimate the binding energy. Various scoring functions such as Dock, ChemScore, GoldScore, etc., are used, each having their strengths and limitations. Scoring functions typically consider factors like hydrogen bonding, van der Waals interactions, electrostatic interactions, solvation effects, and sometimes entropic effects.

These methods are considerably less computationally demanding than QM or DFT methods, which makes them suitable for large-scale virtual screening studies where thousands or even millions of compounds need to be evaluated.

However, for cases where a high degree of accuracy is needed (like when refining the top hits from a docking study), more advanced methods like QM/MM (Quantum Mechanics/Molecular Mechanics) or even DFT might be used. These methods can provide a more detailed understanding of the electronic structure and can accurately model chemical reactions, but they come with a higher computational cost.
```


### SwissDock

A web UI for predicting protein-ligand interactions. Can upload .pdb files and get docking results.


### Foldit - game for solving protein folding

Designed to harness human intuition in finding protein conformations.



## Section 6: AI in drug discovery

Feature vectors comprise various 2D/3D descriptors such as SMILES, InChl, ECFP, and physicochemical descriptors such as molecular weight, solubility, hydrogen donors and acceptors, polar surface etc.

Classification methods can be used to predict things like (non)activity.
Regression methods can be used to predict things like potency, IC50, etc.






