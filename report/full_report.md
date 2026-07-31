# Comparative Bioinformatics Analysis of Human Lysozyme (LYZ)

**Author:** Parmida Mehranfarid — B.Sc. Student, Cellular and Molecular Biology


## Abstract

This report presents an in-silico comparative analysis of the human Lysozyme C (LYZ) gene and protein. Using publicly available databases and web-based bioinformatics tools, we retrieved the reference mRNA and protein sequences, searched for homologous sequences with BLAST, built a multiple sequence alignment to identify conserved and variable regions, predicted secondary and tertiary protein structure, calculated physicochemical properties, constructed a phylogenetic tree spanning mammals and bacteria, and designed PCR/qPCR primers for gene screening. Across every level of analysis, LYZ showed strong evolutionary conservation, consistent with its essential role in innate antibacterial immunity.

## 1. Gene selection

- Gene: **Lysozyme C (LYZ)**
- Organism: *Homo sapiens* (eukaryote)
- NCBI Gene ID: **4069**
- mRNA RefSeq: **NM_000239.3**
- Protein RefSeq: **NP_000230.1**

Sequences were retrieved from NCBI (Nucleotide and Protein databases) as FASTA files — see `data/`.

## 2. Homology search (BLAST)

Both `blastn` (nucleotide) and `blastp` (protein) searches were run against NCBI databases.

- **blastn:** LYZ nucleotide sequence is >94% identical to primates such as bonobo (98.34%), orangutan (97.27%), and gibbon (97.01%).
- **blastp:** LYZ protein sequence is up to 99.32% identical to gorilla, with orangutan (97.97%) and gibbons (95–96%) close behind; even baboon and macaque exceed 87% identity.
- Protein-level conservation extends across a *wider* range of species than nucleotide-level conservation, due to codon degeneracy (synonymous nucleotide substitutions, especially at the third codon position, that don't alter the amino acid sequence).

Full results: `blast/blast_results.md`.

## 3. Conserved regions and mutations (alignment)

Sequences from the top BLAST hits were aligned with Clustal Omega, separately for the protein and mRNA sequences.

- **Protein alignment:** the middle of the protein (~positions 7–59) is highly conserved; the C-terminal region (from ~position 121) is more variable.
- **mRNA alignment:** conserved positions are present but more scattered, again reflecting silent mutations at the third codon position.
- Example conservative substitution: position 4 (Leu ↔ Val). Example non-conservative substitution: position 59 (Arg ↔ Gln, changes charge).
- Overall, >70% of protein positions are fully conserved across the compared species.

Full results: `alignment/alignment_notes.md`.

## 4. Protein structure prediction

- **Primary structure:** the 148-aa sequence retrieved from NCBI (18-aa signal peptide + 130-aa mature protein).
- **Secondary structure (PSIPRED):** mixed α+β fold — several α-helices (mostly in the first half of the sequence) and short β-strands, forming the α/β domains that flank the active-site cleft.
- **Tertiary structure (SWISS-MODEL):** best model built on a patas monkey (*Erythrocebus patas*) lysozyme template (89.86% sequence identity, GMQE = 0.95) — a compact, globular monomer. That the best available PDB template is non-human, yet still >89% identical, is itself further evidence of strong evolutionary conservation of lysozyme structure among primates.
- **Physicochemical properties (ExPASy ProtParam):** 148 aa, 16537.02 Da, pI = 9.56 (basic), instability index 27.71 (stable), GRAVY = −0.195 (hydrophilic). The net positive charge supports electrostatic attraction to the negatively charged bacterial cell wall, consistent with lysozyme's antibacterial role (hydrolysis of the β(1,4) bond between N-acetylmuramic acid and N-acetylglucosamine in Gram-positive bacterial cell walls).

Full results: `protein_structure/structure_prediction.md`.

## 5. Phylogenetic analysis

Because human lysozyme is far more similar to other animal lysozymes than to bacterial ones, only a handful of bacterial hits appeared, all below 80% identity. The 10 sequences with highest similarity (all below 80%, mostly bacterial "lysozyme family protein" hits) plus the human sequence were aligned in MEGA (MUSCLE) and used to build a Neighbor-Joining tree with Poisson-corrected distances.

- Human LYZ clusters closest to *Acinetobacter baumannii* lysozyme (WP_353804458.1, distance = 0.2532).
- The most distant relationship is with *Salmonella* sp. (WP_411027131.1, distance = 1.1421).
- Distances range from 0.25 to 1.14 — reflecting the very large evolutionary separation between eukaryotes and prokaryotes, while still showing measurable conservation of the lysozyme fold/function.

Full results: `phylogenetic_tree/phylogenetic_analysis.md`.

## 6. Primer design for screening

Using NCBI Primer-BLAST on the mRNA sequence (RefSeq mRNA database, *Homo sapiens*), 10 candidate primer pairs were generated; all were confirmed specific to LYZ with no other targets in the human genome.

**Selected pair (Primer pair 2):**
```
Forward: 5'-GTCCAGGGCAAGGTCTTTGA-3'   (Tm = 59.89 °C, GC = 55%)
Reverse: 5'-CCCTGTAGCCATCCATTCCC-3'   (Tm = 59.89 °C, GC = 60%)
Product length: 73 bp
```
Chosen for matched Tm, short product length (ideal for qPCR), low self-complementarity, and balanced GC content.

Full results: `primer_design/primer_design.md`.

## 7. Conclusion

Across sequence identity, alignment conservation, structural modeling, and phylogenetic distance, human LYZ shows consistently strong evolutionary conservation — strongest in primates, and still measurable even relative to bacterial lysozymes. This pattern reflects the enzyme's essential and non-redundant role in the innate immune system's antibacterial defense, which appears to have placed strong selective pressure against disruptive mutations throughout mammalian (and to a lesser extent, broader) evolution.

## References

See `references/references.md` for the full list of tools, databases, and accession numbers used.
