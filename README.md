<div align="center">

# 🧬 PROTEX-Insight

**Protein structure analysis, mutation investigation and computational drug discovery in one place**



![Status](https://img.shields.io/badge/status-documentation%20only-lightgrey)




![Field](https://img.shields.io/badge/field-structural%20bioinformatics-blue)




![Demo](https://img.shields.io/badge/demo-EGFR%20%7C%20PDB%201M17-green)




![Purpose](https://img.shields.io/badge/purpose-learning%20%26%20exploration-orange)



</div>

---

> [!IMPORTANT]
> **Project status:** This repository contains documentation and example screenshots only. It does **not** include the application's source code. Everything here is a record of the project idea and its demo, not software you can reproduce.

## 📑 Contents

- [What is PROTEX-Insight?](#-what-is-protex-insight)
- [Key features](#-key-features)
- [Demo case: EGFR](#-demo-case-egfr)
- [Screenshots](#-screenshots)
- [How the workflow should look](#-how-the-workflow-should-look)
- [What gets recorded](#-what-gets-recorded)
- [Validation approach](#-validation-approach)
- [Limitations](#️-limitations)
- [Roadmap](#️-roadmap)
- [Documentation](#-documentation)
- [Repository structure](#-repository-structure)
- [Who this is for](#-who-this-is-for)
- [How to cite](#-how-to-cite)

---

## 💡 What is PROTEX-Insight?

**In short:** PROTEX-Insight is a computational biology project that puts the main steps of early drug discovery into one easy interface. You can look at a protein structure, study mutations, check a drug molecule's properties, and view molecular docking results, all in one place.

It is built for **learning and exploration**. It focuses on showing not just a result, but also the input, the settings and the limits behind it, because docking results depend heavily on how things were prepared.

**The idea in one line:** *a result is only useful if you can see how it was made.*

---

## ✨ Key features

| # | Module | What it does |
|---|--------|--------------|
| 1 | **Protein Explorer** | View a protein structure and its metadata (name, chain, resolution, ligands, waters) |
| 2 | **Mutation Investigation** | Organise mutation information and explore why a mutation may matter biologically |
| 3 | **Ligand & Drug Analysis** | Check ligand properties (descriptors) and protein–ligand contacts |
| 4 | **Molecular Docking** | Show docking setup and results, only when a docking run was actually done |

---

## 🎯 Demo case: EGFR

The documented demo uses the **epidermal growth factor receptor (EGFR)** kinase domain.

| Item | Value |
|------|-------|
| Target | EGFR kinase domain |
| PDB entry | **1M17** |
| Example ligands | Erlotinib, gefitinib, osimertinib |

These three drugs bind and behave differently, so a docking score alone cannot rank how well they work in patients.

### Docking example shown in the interface

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
> These numbers are copied from the interface screenshot. They have **not** been independently reproduced or verified. To treat them as validated, the exact ligand identity, preparation steps, software version, settings and RMSD atom-matching method must be recorded.

---

## 📸 Screenshots

Add your own screenshots to `assets/screenshots/` using these exact filenames:

| Screen | Filename |
|--------|----------|
| Protein Explorer | `protein-explorer.png` |
| Molecular Docking | `molecular-docking.png` |
| Drug Comparison | `drug-comparison.png` |

### Protein Explorer


![Protein Explorer](assets/screenshots/protein-explorer.png)



### Molecular Docking


![Molecular Docking](assets/screenshots/molecular-docking.png)



### Drug Comparison


![Drug Comparison](assets/screenshots/drug-comparison.png)



---

## 🔄 How the workflow should look

```text
1. Select protein  →  2. Record structure details  →  3. Prepare receptor
        ↓
4. Prepare ligand  →  5. Define binding-site box   →  6. Run docking
        ↓
7. Inspect poses & interactions  →  8. Validate (redocking / cross-docking)
        ↓
9. Compare with experimental evidence (carefully)
```

1. **Select** a protein structure and identify it.
2. **Record** the source, chain, resolution and relevant parts of the structure.
3. **Prepare the receptor** using a written protocol.
4. **Prepare the ligand** and keep its correct chemical identity.
5. **Define the search box** around the binding site and say why.
6. **Run docking** and record the software and settings.
7. **Inspect poses** and interactions using clear geometric and chemical rules.
8. **Validate** with redocking and, where possible, cross-docking.
9. **Compare** with experimental data without treating a match as proof.

---

## 📝 What gets recorded

Every analysis should keep enough information to be repeated.

| Area | What to record |
|------|----------------|
| **Protein** | Name, organism, PDB ID, chain, resolution, missing residues, ligands/ions/waters kept or removed |
| **Receptor prep** | Chain choice, waters removed, hydrogens, protonation, charges, alternate locations, missing atoms |
| **Ligand prep** | Name and ID, SMILES, stereochemistry, protonation/tautomer, 3D conformer method, charges |
| **Docking** | Software and version, input files, search box centre and size, exhaustiveness, poses, seed, logs |
| **Interactions** | Atom/residue IDs, distances, interaction type, geometric rules used |
| **Mutations** | Reference sequence, numbering, amino acid change, accession, evidence source, analysis type |
| **Descriptors** | Tool and version (e.g. RDKit), input used; MW, cLogP, TPSA, H-bond donors/acceptors, rotatable bonds |

> [!WARNING]
> Always check that the ligand shown in the interface is the **same** ligand used in descriptors, interactions and docking. Never mix up a counterion or crystallographic additive (like chloride) with the drug molecule.

---

## ✅ Validation approach

Results should not be called reliable until these checks are done and recorded.

| Check | What it means |
|-------|---------------|
| **Input identity** | Confirm PDB ID, chain, sequence and ligand identity; catch mismatched ligand records |
| **Redocking** | Dock the original crystal ligand back; calculate heavy-atom RMSD with a stated atom mapping (around 2 Å is a common rule of thumb) |
| **Cross-docking** | Dock into more than one relevant structure; compare poses and interactions, not just scores |
| **Sensitivity analysis** | Vary protonation, waters, conformers and search settings to see if conclusions hold |
| **Experimental comparison** | Use sourced data with assay type, units and conditions; IC50, Ki and Kd are not interchangeable |
| **Reproducibility** | Archive inputs, versions, settings, logs, raw outputs and scripts |

---

## ⚠️ Limitations

- A docking score is a **computer estimate**, not a measured binding affinity.
- Scores from different setups or targets should not be compared casually.
- A predicted contact is not automatically a meaningful biological interaction.
- Annotating a mutation is not the same as modelling the mutant structure or proving its effect.
- "Validated" needs written methods, inputs, software versions and reproducible outputs.
- Never report an RMSD, binding score, interaction or experimental comparison unless it was actually calculated or sourced.
- Screenshots alone cannot prove the calculations are correct.
- This repository has no source code and no independently generated docking outputs.

> [!WARNING]
> **Known issue to check:** the ligand-analysis view appeared to show `CL (B:102)` next to erlotinib-related information. Chloride and erlotinib are different molecules. This should be confirmed and fixed before relying on that view.

---

## 🗺️ Roadmap

| Phase | Focus | Examples |
|-------|-------|----------|
| 1 | **Data integrity** | Standard identifiers, file validation, clear error messages |
| 2 | **Reproducible analysis** | Documented preparation, stored configs and raw output, exportable reports |
| 3 | **Validation** | Redocking, cross-docking, sensitivity analysis, sourced experimental comparison |
| 4 | **Mutation analysis** | Map variants to a reference sequence, evidence links, confidence labels |
| 5 | **Release quality** | Example datasets, automated tests, version tracking, accessibility testing |

**A feature counts as complete only when it has:** a defined input and output, a documented method, tests with known examples, clear error handling, reproducible results, and user-facing limitations.

---

## 📚 Documentation

| Document | What's inside |
|----------|---------------|
| [Project Report](docs/PROJECT_REPORT.md) | Goals, background, demo and limits |
| [Scientific Methods](docs/SCIENTIFIC_METHODS.md) | What to record for every analysis |
| [Validation Plan](docs/VALIDATION_PLAN.md) | Checks needed before trusting results |
| [User Guide](docs/USER_GUIDE.md) | How the interface is meant to be used |
| [Development Roadmap](docs/DEVELOPMENT_ROADMAP.md) | Future plans and release rules |

---

## 📁 Repository structure

```text
PROTEX-Insight/
├── README.md
├── docs/
│   ├── PROJECT_REPORT.md
│   ├── SCIENTIFIC_METHODS.md
│   ├── VALIDATION_PLAN.md
│   ├── USER_GUIDE.md
│   └── DEVELOPMENT_ROADMAP.md
└── assets/
    └── screenshots/
        └── ADD_SCREENSHOTS_HERE.md
```

---

## 🎓 Who this is for

Students and early-career researchers interested in structural bioinformatics, molecular docking, protein–ligand analysis and computational drug discovery.

---

## 📝 How to cite

Describe this project as a **computational project / demo** unless you have independently reproduced and validated the calculations. Add a formal citation only after a stable public release, with final author details and release date.
