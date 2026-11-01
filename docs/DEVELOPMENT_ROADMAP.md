# 🗺️ Development Roadmap

[← Back to README](../README.md)

This roadmap separates **future ideas** from features that should only be claimed once they are built and tested.

## Overview

| Phase | Focus | Status |
|-------|-------|--------|
| 1 | Data integrity | 🔲 Planned |
| 2 | Reproducible structural analysis | 🔲 Planned |
| 3 | Validation | 🔲 Planned |
| 4 | Mutation-focused analysis | 🔲 Planned |
| 5 | Usability and release quality | 🔲 Planned |

---

## Phase 1: Data integrity

- Standardise protein and ligand identifiers.
- Validate uploaded structure and molecule files.
- Show source, chain, residue numbering and ligand identity.
- Add clear error messages for unsupported or incomplete inputs.

## Phase 2: Reproducible structural analysis

- Document receptor preparation settings.
- Keep clear ligand preparation records.
- Store docking configuration and raw output.
- Export a report with inputs, methods and limitations.

## Phase 3: Validation

- Add redocking workflows with documented atom mapping.
- Add cross-docking for compatible structures.
- Add sensitivity analysis for protonation and water handling.
- Compare results with properly sourced experimental data.

## Phase 4: Mutation-focused analysis

- Map variants to a reference protein sequence.
- Keep variant annotation separate from structural modelling.
- Add evidence links and confidence labels.
- Avoid unsupported claims about pathogenicity or drug resistance.

## Phase 5: Usability and release quality

- Add example datasets with clear licences and sources.
- Add automated tests for input parsing and calculations.
- Record software versions and dependencies.
- Publish reproducible examples and a limitations page.
- Add accessibility and interface testing.

---

## ✅ Release criteria

Call a feature **complete** only when it has:

1. A defined input and output
2. A documented method
3. Tests using known examples
4. Clear error handling
5. Reproducible results, or a stated reason why exact reproduction isn't expected
6. User-facing limitations
