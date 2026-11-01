# 📖 User Guide

[← Back to README](../README.md)

> [!NOTE]
> This guide is based on the available screenshots and project description. The exact controls in the running app may differ.

## Contents

1. [Protein Explorer](#1-protein-explorer)
2. [Ligand analysis](#2-ligand-analysis)
3. [Molecular docking](#3-molecular-docking)
4. [Mutation investigation](#4-mutation-investigation)
5. [Saving and reporting](#5-saving-and-reporting)

---

## 1. Protein Explorer

1. Open the protein exploration area.
2. Select or enter a protein structure ID.
3. Confirm the protein name, chain and structural metadata.
4. Look at the residue sequence or structure view, if available.
5. Check which ligands, ions and waters belong to the structure.

**Demo example:** EGFR, PDB 1M17. Verify the chain and ligand before interpreting any later results.

## 2. Ligand analysis

1. Select the ligand you want.
2. Check its chemical identity and structure.
3. Review the molecular descriptors.
4. Look at the reported contacts or interactions.
5. Confirm that everything shown belongs to the selected ligand.

> [!WARNING]
> Don't mistake a chloride ion, crystallographic additive or other small molecule for the drug ligand. Check ligand IDs carefully.

## 3. Molecular docking

Before reading a docking result, find out:

- Receptor structure and chain
- Ligand identity
- How the receptor and ligand were prepared
- Binding-site centre and size
- Docking software and settings
- Number of poses and the scoring output

Treat the score as a computer estimate. Look at the pose and its chemistry instead of relying on one number.

## 4. Mutation investigation

Check the reference sequence, residue numbering, variant identity and evidence source. Keep these three things separate:

| Level | Meaning |
|-------|---------|
| Sequence annotation | What the variant is |
| Structural modelling | How it might change the structure |
| Experimental validation | What lab data actually show |

## 5. Saving and reporting

Save the input IDs, settings and raw outputs with every analysis. A screenshot is good for sharing, but it can't replace the files and logs needed to reproduce a calculation.
