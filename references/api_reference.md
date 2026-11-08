# AlphaFold Database API Reference

This guide summarizes common public AlphaFold Database access patterns. Confirm endpoint behavior and dataset versions against the current official API documentation before building production workflows.

## 1. Protein lookup
The AlphaFold DB website supports lookup by UniProt accession. Use the official API documentation to identify current search and prediction endpoints. Validate the accession format and handle proteins with no available prediction.

## 2. Prediction metadata
A prediction record may provide:
- UniProt accession and protein description
- Organism and sequence metadata
- Model version and database release
- PDB/mmCIF download locations
- Confidence JSON and Predicted Aligned Error (PAE) file locations
- Model identifiers and provenance

Treat returned URLs as data. Validate that downloads originate from the official AlphaFold domain or another explicitly trusted host.

## 3. Common structure files
Typical file families include:
- Predicted structure in PDB or mmCIF format
- Per-residue confidence data, often named with a confidence/version suffix
- PAE matrix JSON, often named with a predicted-aligned-error/version suffix

File naming and available formats can change across database releases. Prefer URLs returned by current API metadata over constructing them from memory.

## 4. Confidence interpretation
- pLDDT is a local per-residue confidence estimate, not a probability that the structure is biologically correct.
- PAE describes confidence in the relative placement of residue pairs or domains.
- High local confidence does not guarantee correct domain arrangement, ligand binding, oligomeric state, or functional interpretation.
- Compare predictions with experimental structures and biological evidence where available.

## 5. Download and caching
- Cache results by accession and model/database version.
- Record retrieval timestamp, source URL, response status, and checksum.
- Use timeouts and bounded retries for transient failures.
- Stream large files rather than loading them entirely into memory.
- Avoid repeated requests and respect service policies.

## 6. Bulk data
For large-scale analysis, use official bulk datasets or cloud-hosted data exports rather than issuing one request per protein. Check current dataset partitions, schemas, and update cadence.

## 7. 3D-Beacons and related sources
PDBe 3D-Beacons can provide structure model metadata from multiple providers. Keep AlphaFold predictions distinguishable from experimental structures and other computational models.

## 8. Reproducibility checklist
Record accession, database release, model version, sequence checksum, file format, download URL, retrieval date, and confidence interpretation method.

## Official resources
- AlphaFold Protein Structure Database: https://alphafold.ebi.ac.uk/
- AlphaFold DB API documentation: https://alphafold.ebi.ac.uk/api-docs
- PDBe 3D-Beacons: https://www.ebi.ac.uk/pdbe/pdbe-kb/3dbeacons/
- Biopython AlphaFold DB interface: https://biopython.org/docs/dev/api/Bio.PDB.alphafold_db.html
