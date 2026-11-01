# 🧪 Scientific Methods & Reporting Standards

[← Back to README](../README.md)

This page lists what should be recorded when using PROTEX-Insight.

> [!NOTE]
> It describes good practice. It is **not** proof that every method below has already been run.

## Contents

1. [Protein structure selection](#1-protein-structure-selection)
2. [Receptor preparation](#2-receptor-preparation)
3. [Ligand preparation](#3-ligand-preparation)
4. [Molecular docking](#4-molecular-docking)
5. [Protein–ligand interactions](#5-proteinligand-interactions)
6. [Mutation investigation](#6-mutation-investigation)
7. [Small-molecule descriptors](#7-small-molecule-descriptors)

---

## 1. Protein structure selection

For every structure, record:

- [ ] Protein name and organism
- [ ] PDB ID and source
- [ ] Chain ID
- [ ] Resolution and experimental method
- [ ] Residues present or missing
- [ ] Ligands, ions, cofactors and waters kept or removed
- [ ] Any mutations or engineered parts in the deposited structure

For the EGFR demo (PDB **1M17**), confirm the chain and ligand directly from the structure file used.

## 2. Receptor preparation

Record exactly how you handled:

- [ ] Chain selection
- [ ] Waters and non-protein molecules
- [ ] Adding hydrogens
- [ ] Protonation states
- [ ] Partial charges
- [ ] Alternate locations
- [ ] Missing atoms or residues
- [ ] Conversion to the docking input format

> Preparation choices can change the pose and score. Don't call a receptor "prepared" unless the steps were really done.

## 3. Ligand preparation

For each ligand, record:

| Item | Notes |
|------|-------|
| Name and database ID | e.g. common name + identifier |
| SMILES | Canonical or isomeric |
| Stereochemistry | Keep it correct |
| Protonation / tautomer state | State what was used |
| 3D conformer method | How it was generated |
| Geometry optimisation | Method used |
| Charge method | Method used |
| Output format | e.g. file type |

> [!WARNING]
> Make sure the ligand shown in the interface is the **same** ligand used for descriptors, interactions and docking. Never mix a counterion or crystallographic additive with the drug molecule.

## 4. Molecular docking

For every docking run, record:

- [ ] Software and version
- [ ] Receptor and ligand input files
- [ ] Search box centre and size
- [ ] Exhaustiveness (or similar setting)
- [ ] Number of poses requested
- [ ] Energy range / pose retention settings
- [ ] Random seed, if used
- [ ] Full output and log files

> A docking score is a scoring-function output. It is **not** a measured binding free energy, Kd, IC50 or clinical efficacy.

## 5. Protein–ligand interactions

When you report an interaction, give:

- atom or residue IDs
- distance
- interaction type
- the geometric rules you used

Common types:

| Type | Notes |
|------|-------|
| Hydrogen bonds | Check geometry and chemistry |
| Salt bridges | |
| Hydrophobic contacts | |
| Aromatic interactions | |
| Metal coordination | Only where chemically relevant |

Lists based only on distance should be called **proximity contacts**, not confirmed interactions.

## 6. Mutation investigation

For each mutation, record:

- [ ] Reference sequence and numbering system
- [ ] Reference and alternate amino acid
- [ ] Transcript or protein accession, if applicable
- [ ] Evidence source and clinical/functional class, if relevant
- [ ] Type of analysis: **sequence annotation**, **structural mapping**, or **explicit mutant modelling**

> Don't infer a mutation's effect only because it sits near a binding pocket.

## 7. Small-molecule descriptors

If you use RDKit or similar tools, record the **version** and the **exact input** used.

Common descriptors: molecular weight, cLogP, TPSA, H-bond donors and acceptors, rotatable bonds.

> Descriptors are calculated properties. They are not direct measurements of absorption, toxicity or clinical performance.
