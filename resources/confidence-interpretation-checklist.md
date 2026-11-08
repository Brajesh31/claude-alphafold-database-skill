# Structure Confidence Interpretation Checklist

Use this checklist before relying on an AlphaFold model in downstream analysis.

## Identity and coverage

- [ ] Confirm the UniProt accession and organism.
- [ ] Confirm the intended isoform or sequence variant.
- [ ] Compare the model sequence with the target sequence.
- [ ] Check whether the protein is represented by multiple fragments.
- [ ] Record unresolved, absent, or truncated residues.

## Local confidence

- [ ] Review the pLDDT distribution, not only its mean.
- [ ] Identify contiguous high- and low-confidence regions.
- [ ] Map low-confidence regions to known domains, linkers, termini, and disordered segments.
- [ ] Avoid treating a high average as proof that every residue is reliable.
- [ ] Record the thresholding rule used in the analysis.

## Relative domain confidence

- [ ] Inspect PAE when domain arrangement matters.
- [ ] Distinguish local fold confidence from relative domain placement.
- [ ] Identify domain pairs with uncertain relative orientation.
- [ ] Avoid making interface claims from a single-chain model without additional evidence.

## Biological context

- [ ] Check whether the biological state requires a ligand, cofactor, membrane, nucleic acid, or partner protein.
- [ ] Consider post-translational modifications and processing.
- [ ] Check for oligomeric or complex-forming behavior not represented by the model.
- [ ] Compare with available experimental structures or independent evidence.
- [ ] Consider whether the model corresponds to the relevant construct and biological conditions.

## Downstream use

- [ ] Confirm that the coordinate format is supported by the target tool.
- [ ] Record model version, retrieval date, and file identifiers.
- [ ] Keep low-confidence regions visible in visualizations and reports.
- [ ] Do not use uncertain coordinates as precise restraints or binding-site evidence without validation.
- [ ] State the limitations alongside conclusions.

## Interpretation guardrail

A confidence score is a model-confidence estimate, not a direct probability that a biological hypothesis is true. Structural predictions can guide prioritization and hypothesis generation, but they do not independently establish binding, mechanism, activity, or biological state.
