# claude-alphafold-database-skill

A Claude Code skill for retrieving and interpreting predicted protein structures from the AlphaFold Database.

## Overview

This skill helps access predicted protein structures, retrieve coordinate files, inspect prediction confidence, and incorporate structural models into computational biology workflows.

Predicted structures can support hypothesis generation and structural analysis, but they are not equivalent to experimentally determined structures.

## Main Capabilities

- Search for protein structure predictions using identifiers.
- Retrieve structure records and metadata.
- Download PDB or mmCIF coordinate files where available.
- Inspect confidence measures such as pLDDT.
- Interpret predicted aligned error (PAE) information where available.
- Compare predicted structures with experimental structures.
- Integrate coordinate files into downstream structural workflows.
- Organize structure retrieval and analysis for reproducibility.

## When to Use This Skill

Use this skill when:

- Looking up a predicted structure for a protein.
- Working with UniProt identifiers or protein accessions.
- Downloading coordinate files for visualization or analysis.
- Reviewing confidence information for predicted regions.
- Preparing structure-based computational workflows.
- Comparing predicted and experimentally determined structures.

## Installation

```bash
git clone https://github.com/Brajesh31/claude-alphafold-database-skill.git ~/.claude/skills/alphafold-database
```

## Usage

Invoke the skill for protein structure retrieval and interpretation:

```text
/alphafold-database
```

Provide a protein identifier, organism, sequence, or research question. Include the desired structure format and downstream analysis objective.

## Typical Workflow

1. Identify the protein and confirm its accession.
2. Retrieve the matching structure record.
3. Check the protein sequence and isoform context.
4. Download the coordinate file in the required format.
5. Inspect confidence metrics and per-region reliability.
6. Identify missing or low-confidence regions.
7. Compare against known experimental evidence where available.
8. Record the retrieval date, identifier, and file version.

## Confidence Interpretation

- pLDDT provides a per-residue estimate of local structure confidence.
- PAE describes uncertainty in the relative placement of residues or domains.
- High local confidence does not automatically establish the correctness of domain orientation or biological assembly.
- Low-confidence regions may be flexible, disordered, or poorly modeled.

Do not interpret a predicted structure as direct experimental proof of a binding interaction, mechanism, or biological state.

## Reference Guide

The repository includes `references/api_reference.md` for retrieval patterns, metadata, structure files, confidence information, caching, and reproducibility considerations.

## Validation Checklist

- Protein identity and isoform are correct.
- Sequence matches the intended target.
- Coordinate file format is suitable for downstream tools.
- Confidence values are interpreted at the appropriate structural scale.
- Missing residues and uncertain regions are noted.
- Retrieval details are recorded.
- Biological conclusions are supported by additional evidence.

## Repository Contents

- `SKILL.md`: Main structure retrieval and analysis instructions.
- `references/api_reference.md`: API and data-handling guide.
- `README.md`: Overview and workflow guidance.

## Important Note

A high-confidence prediction is still a computational model. Use experimental validation and biological context for conclusions that affect research or development decisions.
