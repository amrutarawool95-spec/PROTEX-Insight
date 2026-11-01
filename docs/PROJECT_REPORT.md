# 📄 PROTEX-Insight: Project Report

[← Back to README](../README.md)

## Contents

1. [Abstract](#1-abstract)
2. [Background](#2-background)
3. [Objectives](#3-objectives)
4. [Demonstration system](#4-demonstration-system)
5. [Expected workflow](#5-expected-workflow)
6. [Current limitations](#6-current-limitations)
7. [Conclusion](#7-conclusion)

---

## 1. Abstract

PROTEX-Insight is a computational biology project idea that combines protein structure exploration, mutation investigation, ligand analysis and docking result display. The aim is to make common structural bioinformatics ideas easier to inspect in one interface.

The demo focuses on the **EGFR kinase domain** (PDB **1M17**) with EGFR inhibitors as example ligands. It is meant for learning and exploration. Computational predictions are **not** experimental evidence.

## 2. Background

Protein structure and binding-site analysis are widely used in drug discovery. Visualising a structure helps researchers look at residues, binding pockets and ligand placement.

Docking can suggest ligand poses and rough scores, but the results depend on:

- how the protein was prepared
- how the ligand was prepared
- the search settings
- the scoring function

So a good learning tool should show the input, the assumptions, the settings and the limits, not just a result.

## 3. Objectives

- Show protein information and structural metadata clearly.
- Support exploring residues and ligand-binding regions.
- Present mutation information in an easy-to-interpret way.
- Show ligand descriptors and protein–ligand contacts when calculated.
- Present docking setup and output openly.
- Encourage reproducible work and careful interpretation.

## 4. Demonstration system

### Protein

| Item | Value |
|------|-------|
| Target | Epidermal growth factor receptor (EGFR) |
| Structure | PDB 1M17 |
| Context | EGFR kinase domain |

### Ligands

The discussion includes **erlotinib, gefitinib and osimertinib**. They bind and behave differently, so a docking score alone cannot rank their clinical effectiveness.

### Docking example (from the screenshot)

| Parameter | Value shown |
|-----------|-------------|
| Receptor | EGFR, PDB 1M17 |
| Ligand | Erlotinib (labelled `AQ4` in the interface) |
| Docking score | −8.6 kcal/mol |
| Ligand efficiency | 0.297 kcal/mol/HA |
| Exhaustiveness | 8 |
| Number of poses | 9 |
| Energy range | 3 kcal/mol |
| Redocking RMSD (reported) | 1.42 Å |

> [!NOTE]
> These numbers are copied from the interface screenshot. This report has **not** reproduced or verified them. Before treating them as validated, record the exact ligand identity, preparation steps, software version, configuration and how RMSD atoms were matched.

## 5. Expected workflow

1. Select and identify a protein structure.
2. Record source, chain, resolution and relevant parts of the structure.
3. Prepare the receptor with a written protocol.
4. Identify and prepare the ligand, keeping its correct chemical identity.
5. Define the binding-site search box and say why.
6. Run docking and record the software and parameters.
7. Inspect poses and interactions using clear geometric and chemical rules.
8. Validate with redocking and, where possible, cross-docking.
9. Compare with experimental evidence, without treating a match as proof.

## 6. Current limitations

- This is **not** the application's source code.
- It has no reproducible environment and no independently generated docking outputs.
- Screenshots alone cannot prove the calculations are correct.

> [!WARNING]
> **Check before public release:** the ligand-analysis view appeared to show `CL (B:102)` next to erlotinib-related information. Chloride and erlotinib are different molecules. Make sure the selected ligand, the displayed descriptors and the interaction calculations all refer to the **same** molecule.

## 7. Conclusion

PROTEX-Insight is a framework for presenting structural bioinformatics and drug-discovery workflows. Its scientific value depends on clear input handling, reproducible calculations, careful validation, and keeping computer predictions separate from experimental findings.
