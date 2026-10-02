## Project Overview

This project investigates genetic variants in the **CHAT (Choline O-Acetyltransferase) gene** in dogs in the context of **canine congenital myasthenic syndrome (CMS)**.

Publicly available variant data were analyzed to identify and prioritize potentially relevant single nucleotide variants (SNVs). The analysis focuses particularly on protein-altering variants and compares a candidate missense variant with a previously reported disease-associated CHAT variant.

---

## Objective

The main objectives of this project were to:

- Explore publicly available canine CHAT gene variants.
- Identify protein-changing missense variants.
- Compare candidate variants with a known disease-associated CHAT variant.
- Evaluate amino acid substitutions using basic physicochemical substitution scores.
- Examine the positions of variants within the CHAT protein.
- Investigate whether intronic variants are located close to exon–intron boundaries and potential splice sites.
- Prioritize identified SNVs according to their predicted relevance.

---

## Data Sources

The project uses canine variant data based on the **CanFam3.1 genome assembly**.

Main sources referenced in the analysis include:

- **European Variation Archive (EVA)** — canine variant data
- **OMIA**
- **Proschowsky et al. (2007)** — previously reported disease-associated CHAT variant
- **NCBI RefSeq**
  - CHAT protein: `XP_005637542.1`
  - CHAT transcript: `XM_005637485.3`
- **UCSC canFam3 / CanFam3.1** — exon coordinates

---

## Analysis Workflow

### 1. Variant Dataset Exploration

The EVA-derived CHAT variant dataset was loaded and variants were examined according to their annotated consequence types.

Variants were grouped into categories including:

- Missense variants
- Synonymous variants
- Intronic variants

Missense variants were initially considered the primary candidates because they directly alter the amino acid sequence of the protein.

---

### 2. Candidate Missense Variant Identification

A missense variant identified from EVA was selected as the primary candidate:

- Chromosome: **28**
- Position: **1,485,045**
- Reference allele: **A**
- Alternate allele: **G**
- Protein change: **p.K75R**

This candidate was compared with a previously reported disease-associated CHAT variant:

- Chromosome: **28**
- Position: **1,484,906**
- Reference allele: **G**
- Alternate allele: **A**
- Protein change: **p.V29M**

---

## Amino Acid Substitution Comparison

The two substitutions were compared using:

- **BLOSUM62 scores**
- **Grantham distances**

| Variant | Amino Acid Change | BLOSUM62 | Grantham Distance | Interpretation |
|---|---|---:|---:|---|
| p.V29M | Valine → Methionine | 1 | 21 | Conservative |
| p.K75R | Lysine → Arginine | 2 | 26 | Conservative |

Both amino acid substitutions are relatively conservative according to these metrics.

Therefore, amino acid substitution severity alone is not sufficient to determine pathogenic relevance, and the position and biological context of the variants must also be considered.

---

## Protein Position Analysis

The canine CHAT protein analyzed in this project contains **641 amino acids**.

The positions of the two missense variants were visualized along the protein sequence:

- **p.V29M** — amino acid position 29
- **p.K75R** — amino acid position 75

Both variants are located toward the **N-terminal region** of the CHAT protein.

Local amino acid sequence windows surrounding each variant were also extracted from the RefSeq protein sequence to examine their sequence context.

---

## Intronic Variant and Splice-Site Analysis

Exon coordinates for the canine CHAT transcript `XM_005637485.3` were used to calculate the distance between each variant and the nearest exon boundary.

Intronic variants were assessed according to their proximity to potential splice regions.

The analysis showed that:

- None of the intronic variants were located within the canonical **1–2 bp splice-site region**.
- The closest intronic variant was approximately **142 bp** from an exon boundary.
- Therefore, the intronic variants were considered to have relatively low splice-site relevance in this preliminary analysis.

The missense and synonymous variants were located within **exon 3**.

---

## Variant Prioritization

Variants were classified using their consequence type and proximity to exon boundaries.

General prioritization logic:

- **High priority:** Missense variants
- **Medium priority:** Synonymous variants or intronic variants close to splice sites
- **Low priority:** Intronic variants located far from exon boundaries

An integrated prioritization table was generated for all analyzed SNVs.

---

## Key Findings

The main candidate identified in the dataset was:

**CHAT p.K75R**

This variant was prioritized because it is a missense variant affecting the protein sequence.

However, both p.K75R and the known p.V29M variant represent relatively conservative amino acid substitutions according to BLOSUM62 and Grantham scores.

The analysis therefore highlights that further functional or structural investigation would be required before drawing conclusions about the biological significance of p.K75R.

Intronic variants identified in the dataset were located relatively far from canonical splice-site boundaries and were therefore considered lower-priority candidates in this analysis.

---

## Tools and Libraries

The analysis was performed in **Google Colab / Python** using:

- Python
- Pandas
- NumPy
- Matplotlib

---

## Repository Contents

```text
canine-CHAT-variant-analysis/
│
├── README.md
└── project.ipynb
