# Primer Design for LYZ Screening

## Goal
Design primers that are:
1. Specific — bind only the LYZ gene, not similar genes
2. Capable of amplifying/detecting the gene by PCR
3. Suitable for diagnostic or fast research assays (e.g. qPCR)

## Method
Primers were designed with [NCBI Primer-BLAST](https://www.ncbi.nlm.nih.gov/tools/primer-blast/) using the mRNA FASTA sequence (NM_000239.3). Default parameters were kept as-is. Database: **RefSeq mRNA**; Organism: **Homo sapiens**.

## Result
Primer-BLAST confirmed that all designed primers were specific to the LYZ gene, with no other targets found in the human genome — exactly what's required for screening use.

### Candidate primer pairs

| Pair | Product length | Tm (F/R) | GC% (F/R) | Best suited for |
|---|---|---|---|---|
| Primer pair 1 | 356 bp | 59.96 / 60.11 °C | 55 / 55 | Conventional PCR |
| **Primer pair 2** | **73 bp** | **59.89 / 59.89 °C** | **55 / 60** | **qPCR / Real-time PCR** |
| Primer pair 3 | 90 bp | 60.04 / 59.82 °C | 50 / 55 | qPCR |
| Primer pair 4 | 109 bp | 59.59 / 60.53 °C | 50 / 55 | qPCR |

### Selected pair: Primer pair 2

```
Forward primer: 5'-GTCCAGGGCAAGGTCTTTGA-3'   (Tm = 59.89 °C, GC = 55%)
Reverse primer: 5'-CCCTGTAGCCATCCATTCCC-3'   (Tm = 59.89 °C, GC = 60%)
Product length: 73 bp
```

**Why this pair:**
1. Nearly identical Tm (59.89 °C for both) — ideal, since both primers anneal at the same temperature.
2. Short product length (73 bp) — ideal for screening and qPCR (shorter products amplify more efficiently).
3. Low self-complementarity (5.00 and 2.00) — low risk of hairpin/dimer formation.
4. Balanced GC content (55% / 60%) — within the ideal 40–60% range.

## Summary
Primer-BLAST returned 10 candidate primer pairs on the LYZ mRNA sequence; 4 were compared in detail (table above). Pair 2 was the clear best choice for qPCR/real-time PCR use. Specificity testing confirmed no off-target binding within the human RefSeq mRNA database, and the near-identical Tm plus low self-complementarity make this pair well-suited to PCR and qPCR reactions.
