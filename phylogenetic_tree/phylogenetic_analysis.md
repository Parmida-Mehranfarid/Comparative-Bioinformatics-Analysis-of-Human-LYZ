# Phylogenetic Tree & Genetic Distance Analysis

## Sequence selection
Because human lysozyme is much more similar to animal lysozymes than to bacterial or archaeal ones, only a small number of bacterial hits appeared in the protein search, and at lower similarity (<80%) than the mammalian hits identified in the BLAST step (see `blast/blast_results.md`). Most bacterial hits corresponded to generic "lysozyme family protein" / bacterial cell-wall-degrading enzymes rather than close homologs. The 10 sequences with the highest similarity/coverage were selected for the tree, alongside the human LYZ sequence.

## Method
FASTA files for the 10 selected sequences plus the human LYZ sequence were imported into [MEGA](https://www.megasoftware.net/), aligned with **MUSCLE**, and used to build a **Neighbor-Joining** tree based on **Poisson-corrected** genetic distances.

## Tree result
The human lysozyme protein (NP_000230.1) clusters most closely with the *Acinetobacter baumannii* lysozyme (WP_353804458.1) — the shortest evolutionary distance among the sequences studied. The most distant branch is the *Staphylococcus aureus* lysozyme (WP_407809573.1). Overall, despite millions of years of evolutionary separation between humans and bacteria, the tree still shows relative conservation of lysozyme sequence and function — underscoring the enzyme's vital role in antibacterial defense across very different organisms.

## Genetic distance matrix (Poisson correction)

| Species | Accession | Genetic distance from human |
|---|---|---|
| Acinetobacter baumannii | WP_353804458.1 | 0.2532 ⭐ closest |
| Salmonella enterica | WP_472537410.1 | 0.2638 |
| Bacteria (MULTISPECIES) | WP_373093055.1 | 0.3338 |
| Aeromonas veronii | WP_446700399.1 | 0.3969 |
| Acinetobacter baumannii | WP_079864659.1 | 0.5528 |
| Staphylococcus aureus | WP_407809573.1 | 0.8824 |
| Enterobacter hormaechei | WP_133256654.1 | 0.9497 |
| Vibrio harveyi | WP_426682960.1 | 0.9625 |
| Salmonella sp. (partial) | WP_395241730.1 | 1.0986 |
| Salmonella sp. (partial) | WP_411027131.1 | 1.1421 ⭐ farthest |

**Conclusion:** Distances range from 0.25 to 1.14. This shows that, while lysozyme's function is relatively conserved between humans and bacteria, the amino-acid sequence has diverged considerably over evolutionary time — consistent with the very large evolutionary distance between eukaryotes (human) and prokaryotes (bacteria).
 
