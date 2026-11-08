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

## Reproducible Structure Analysis

A structure retrieval task should produce more than a coordinate file. Preserve enough context for another researcher to identify the exact protein, retrieve the same model, and understand how confidence was assessed.

### Recommended analysis sequence

1. **Resolve the target.** Confirm the organism, accession, isoform, sequence, and expected protein length before downloading a model.
2. **Record the model version.** Save the AlphaFold entry identifier, database version, retrieval date, file format, and file checksum.
3. **Inspect coverage.** Determine whether the target is represented by one structure or multiple fragments. Note missing residues and sequence mismatches.
4. **Review local confidence.** Inspect the pLDDT distribution across regions. A single mean score can hide low-confidence loops or termini.
5. **Review relative positioning.** Use PAE when conclusions depend on domain orientation or inter-domain relationships.
6. **Add biological context.** Consider ligands, cofactors, partner chains, membranes, post-translational modifications, and known experimental structures.
7. **Separate observation from hypothesis.** State which structural features are supported, which are uncertain, and what additional evidence is needed.

### Supporting resources

| Resource | Purpose |
|---|---|
| [Structure analysis plan](resources/structure-analysis-plan-template.md) | Define the scientific question, target, methods, controls, and reproducibility record. |
| [Confidence interpretation checklist](resources/confidence-interpretation-checklist.md) | Review pLDDT, PAE, coverage, biological context, and downstream limitations. |
| [Structure review record](resources/structure-review-record-template.md) | Capture model identity, quality findings, and suitability for downstream work. |
| [API reference](references/api_reference.md) | Detailed retrieval, metadata, file, and bulk-access guidance. |

## Working with Model Confidence

Use confidence information at the scale that matches the question. pLDDT is useful for assessing local residue-level reliability. PAE helps assess uncertainty in relative residue or domain positioning. Neither metric establishes that a predicted conformation represents the active biological state.

For interface, docking, or mechanistic work, check whether the biological system requires components that are absent from the predicted model. A single-chain prediction does not by itself validate a protein-protein interface, ligand pose, oligomer, or functional mechanism.

## Expected Analysis Output

A useful handoff should include:

- Protein identity, accession, organism, and isoform.
- Structure entry, model version, coordinate format, and retrieval date.
- Sequence coverage and any fragments or missing regions.
- pLDDT summary with region-level observations.
- PAE interpretation where domain relationships matter.
- Comparison evidence and its limitations.
- Explicit distinction between supported findings and exploratory hypotheses.
- Scripts, parameters, and file locations needed to reproduce the analysis.

## Common Failure Checks

Before accepting a result, investigate accession/isoform mismatches, stale local files, truncated downloads, incorrect coordinate format assumptions, and code that averages confidence across unrelated regions. Do not turn a high-confidence predicted fold into an unsupported claim about function or binding.
