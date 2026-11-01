# ✅ Validation Plan

[← Back to README](../README.md)

## Purpose

These are the checks needed before PROTEX-Insight results can be called scientifically reliable.

> [!IMPORTANT]
> A planned test must **not** be called completed until its inputs, steps and results are recorded.

## Contents

1. [Input identity checks](#1-input-identity-checks)
2. [Redocking](#2-redocking)
3. [Cross-docking](#3-cross-docking)
4. [Sensitivity analysis](#4-sensitivity-analysis)
5. [Experimental comparison](#5-experimental-comparison)
6. [Reproducibility record](#6-reproducibility-record)
7. [Release checklist](#7-release-checklist)

---

## 1. Input identity checks

- Confirm the PDB ID, chain and protein sequence.
- Confirm the ligand using a chemical identifier and structure.
- Check that the ligand used for docking is the one shown in the interface.
- Look for duplicate, missing or mismatched ligand records.
- Keep original input files and record file hashes where practical.

## 2. Redocking

Use this when the experimental structure already has a ligand.

1. Extract the crystallographic ligand.
2. Prepare the receptor and ligand using the documented protocol.
3. Remove the ligand from the receptor before docking.
4. Dock the ligand back into the defined site.
5. Align the predicted pose to the crystal pose using a stated atom-mapping method.
6. Calculate heavy-atom RMSD and report the atom matching and symmetry handling.

> An RMSD around **2 Å** is a commonly used threshold, but the meaning depends on the system, atom mapping and protocol. A low RMSD does not prove the scoring function predicts affinity correctly.

## 3. Cross-docking

Where suitable structures exist:

- Dock a ligand into more than one relevant receptor structure.
- Keep ligand preparation and settings the same where possible.
- Record differences in receptor shape and binding-site makeup.
- Compare pose recovery and interaction patterns, not only scores.

## 4. Sensitivity analysis

Check whether conclusions change when reasonable choices are varied:

| What to vary | Examples |
|--------------|----------|
| Protonation | Alternative states for relevant residues |
| Waters | Keep or remove selected crystal waters |
| Receptor | Different structures or conformations |
| Ligand | Other conformers or tautomers |
| Search settings | Box size and exhaustiveness |

Report what you tested and how much results varied. Don't pick only the most favourable result.

## 5. Experimental comparison

If experimental data exist, record the **source, assay type, units and conditions**.

- IC50, Ki and Kd are **not** interchangeable without context.
- A docking score must not be directly converted into any of them.

A useful comparison asks whether the binding modes are chemically plausible and whether broad trends agree with independent evidence. If they disagree, report it.

## 6. Reproducibility record

For every validated result, archive:

- Input structure and ligand files
- Software and version numbers
- Preparation settings
- Docking configuration
- Logs and raw outputs
- Analysis scripts or exact commands
- Validation calculations
- Known limitations

## 7. Release checklist

- [ ] Protein and ligand identities verified
- [ ] Ligand selection and displayed properties are consistent
- [ ] Receptor preparation documented
- [ ] Ligand preparation documented
- [ ] Docking settings recorded
- [ ] Raw docking output kept
- [ ] RMSD method documented, if reported
- [ ] Interaction criteria documented
- [ ] Sensitivity tests reported, if done
- [ ] Experimental comparisons sourced and explained
- [ ] Limitations visible in the user-facing report
