# Protein Structure Prediction

## Primary structure
The primary structure is the protein sequence itself, retrieved as FASTA from NCBI (see `data/LYZ_protein.fasta`).

## Secondary structure — PSIPRED
Predicted using [PSIPRED](https://bioinf.cs.ucl.ac.uk/psipred/) by submitting the protein FASTA sequence.

**Result:** Lysozyme C has a mixed α+β structure — several α-helices (mostly in the first half of the sequence) and a few short β-strands scattered throughout. This arrangement creates distinct α and β domains with the enzyme's active-site cleft located between them. The sequence includes an 18-residue signal peptide; the mature (secreted) protein is 130 amino acids long (without the signal peptide).

## Tertiary structure — SWISS-MODEL
Predicted using [SWISS-MODEL](https://swissmodel.expasy.org/) by submitting the protein FASTA sequence and starting a modeling job.

**Best model (Model 01):**

| Parameter | Value | Interpretation |
|---|---|---|
| Template | P61634.1.A — lysozyme C of *Erythrocebus patas* (patas monkey) | Best available template in PDB, not a human structure |
| Sequence identity | 89.86% | Very high — model is reliable |
| GMQE | 0.95 | Near 1 = very high model quality |
| Oligo-state | Monomer | Functions as a single chain |

The predicted structure is a compact, globular monomer combining α-helix and β-sheet domains, with the active-site cleft between them — consistent with the expected lysozyme fold. Blue regions correspond to α-helices; the pink/red region is a less-structured terminal segment (likely the N-terminus, not yet fully folded, or a free coil).

**Note on template choice:** SWISS-MODEL selects the best available PDB template based on structural quality, resolution, and sequence coverage — regardless of species. That the best template came from a non-human primate (patas monkey), with 89.86% sequence identity, is itself evidence of strong evolutionary conservation of LYZ/lysozyme C among primates: despite millions of years of evolutionary divergence, the sequence and structure have changed little. This is likely due to lysozyme's essential role in innate immunity (antibacterial defense), where deleterious mutations would have been selected against.

## Physicochemical properties — ExPASy ProtParam
Calculated using [ExPASy ProtParam](https://web.expasy.org/protparam/) on the human protein sequence.

| Property | Value |
|---|---|
| Number of amino acids | 148 |
| Molecular weight | 16537.02 Da |
| Theoretical pI | 9.56 |
| Total negative residues (Asp+Glu) | 11 |
| Total positive residues (Arg+Lys) | 20 |
| Formula | C₇₁₉H₁₁₄₆N₂₂₀O₂₀₇S₁₁ |
| Total atoms | 2303 |
| Extinction coefficient | 36940 M⁻¹cm⁻¹ (disulfides formed) / 36440 (Cys reduced) |
| Estimated half-life | 30h (mammalian, in vitro) / >20h (yeast) / >10h (*E. coli*) |
| Instability index | 27.71 → classified as **stable** |
| Aliphatic index | 85.68 |
| GRAVY | −0.195 (slightly hydrophilic) |

### Summary
Human Lysozyme C (148 aa, ~16.5 kDa) is a basic (pI = 9.56) and stable protein (instability index = 27.71). Its 8 cysteines and likely 4 disulfide bonds give it a compact, resistant structure. The negative GRAVY value (−0.195) indicates a hydrophilic, soluble nature, consistent with its biological role as an enzyme secreted in body fluids (tears, saliva, egg white in other species). The net positive charge (from an excess of Lys+Arg over Asp+Glu) plays an important role in electrostatic attraction to the negatively charged bacterial cell wall and in its antibacterial activity.

Lysozyme C is an antibacterial enzyme that hydrolyzes the β(1,4) glycosidic bond between N-acetylmuramic acid and N-acetylglucosamine in the cell wall of Gram-positive bacteria, causing lysis. Its physicochemical properties (positive charge, high stability) directly support this functional role.
