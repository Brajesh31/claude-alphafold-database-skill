# AlphaFold Database

## Overview

This repository contains a Claude skill focused on the AlphaFold Database. It provides structured guidance for working with protein structure predictions and related database resources.

## Scope

- Explains the skill's purpose, terminology, and workflow.
- Supports structured exploration of protein structure information.
- Organizes research questions and expected outputs.
- Preserves the original skill resources and reference material.

## Requirements

- A Claude-compatible environment with skill support.
- Basic familiarity with proteins and structural biology.
- Network access when consulting online database resources.

## Getting Started

1. Read `SKILL.md` to understand the workflow and boundaries.
2. Install the skill in your Claude environment's supported skills directory.
3. Provide a protein, accession, or research question relevant to the task.
4. Follow the skill's instructions to gather and interpret information.
5. Verify important findings against the current database and primary scientific sources.

## Interpretation Notes

Predicted structures are computational models, not direct experimental observations. Consider confidence information, biological context, and independent evidence before drawing conclusions.

## License

MIT. See [LICENSE](LICENSE).

## Supporting reference

Added `references/api_reference.md` covering public database access patterns, structure and confidence files, metadata, caching, and reproducibility. Verify endpoint details and file versions against the current official API before production use.
