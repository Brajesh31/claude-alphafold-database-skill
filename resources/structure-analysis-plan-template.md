# Protein Structure Analysis Plan

Use this brief before retrieving or analyzing a predicted protein structure. Keep the scientific question separate from the computational steps.

## Research question

- Primary question:
- Why is a structure model relevant to this question?
- Expected decision or downstream use:
- What evidence would change the interpretation?

## Target identity

- Protein name:
- Organism and taxonomic identifier:
- UniProt accession:
- Isoform or sequence variant:
- Sequence source and retrieval date:
- Expected sequence length:
- Known domains, mutations, or processing:

## Structure retrieval

- AlphaFold entry identifier:
- Database/model version:
- Retrieval date and time:
- Coordinate format: mmCIF / PDB
- Confidence file retrieved:
- PAE file retrieved:
- Protein fragments or chains expected:
- File checksums:

## Analysis plan

| Question | Method | Input | Expected output | Limitation |
|---|---|---|---|---|
| Is the target identity correct? | Sequence and accession check | Sequence, metadata | Identity confirmation | Accession may refer to an isoform or canonical sequence |
| Which regions are reliable? | pLDDT review | Confidence values | Region-level summary | Local confidence is not global arrangement confidence |
| Are domains positioned confidently? | PAE review | PAE matrix | Domain relationship notes | PAE does not prove biological assembly |
| How does the model compare with evidence? | Structural comparison | Experimental or homologous structure | Alignment and differences | Conditions and constructs may differ |

## Controls and comparisons

- Experimental structure or homolog:
- Sequence alignment method:
- Structural alignment method:
- Regions excluded from comparison and why:
- Alternative explanations considered:

## Interpretation

- High-confidence observations:
- Low-confidence or unresolved regions:
- Domain-orientation uncertainty:
- Missing ligands, cofactors, modifications, or partner chains:
- Findings supported by independent evidence:
- Conclusions that remain provisional:

## Reproducibility record

- Software and version:
- Analysis parameters:
- Scripts or notebooks:
- Input file locations:
- Output file locations:
- Analyst and review date:

## Final decision

State what the model supports, what it does not support, and what additional evidence is required before a biological or development decision is made.
