<div align="center">

# 🧬 PROTEX-Insight

**Protein structure analysis, mutation investigation and computational drug discovery in one place**



![Status](https://img.shields.io/badge/status-documentation%20only-lightgrey)




![Field](https://img.shields.io/badge/field-structural%20bioinformatics-blue)




![Demo](https://img.shields.io/badge/demo-EGFR%20%7C%201M17-green)



</div>

---

> [!IMPORTANT]
> **Project status:** This repository has documentation and example screenshots only. It does **not** contain the application's source code. Please read everything here as a record of the project idea and its demo, not as software you can reproduce.

## 📑 Contents

- [Overview](#-overview)
- [Demo case: EGFR](#-demo-case-egfr)
- [Screenshots](#-screenshots)
- [Limitations](#️-limitations)
- [Documentation](#-documentation)
- [Repository structure](#-repository-structure)
- [Who this is for](#-who-this-is-for)
- [How to cite](#-how-to-cite)

---

## 🔬 Overview

PROTEX-Insight brings protein structure exploration, mutation investigation, ligand analysis and molecular docking into one easy interface.

| # | Module | What it does |
|---|--------|--------------|
| 1 | **Protein Explorer** | Look at a protein structure and its metadata |
| 2 | **Mutation Investigation** | Organise mutation information and see why a mutation may matter |
| 3 | **Ligand & Drug Analysis** | Check ligand properties and protein–ligand contacts |
| 4 | **Molecular Docking** | Show docking setup and results (only when a docking run was actually done) |

---

## 🎯 Demo case: EGFR

| Item | Value |
|------|-------|
| Target | Epidermal growth factor receptor (EGFR) kinase |
| PDB entry | **1M17** |
| Example ligands | Erlotinib, gefitinib, osimertinib |

The screenshots show an EGFR structure view and a docking screen for erlotinib.

> [!NOTE]
> Values in the screenshots are what the interface reported. They have **not** been independently checked.

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

## ⚠️ Limitations

- A docking score is a **computer estimate**, not a measured binding affinity.
- Scores from different setups or targets should not be compared casually.
- A predicted contact is not automatically a meaningful biological interaction.
- Annotating a mutation is not the same as modelling the mutant structure or proving its effect.
- "Validated" needs written methods, inputs, software versions and reproducible outputs.
- Never report an RMSD, binding score, interaction or experimental comparison unless it was actually calculated or sourced.

More detail: [Scientific Methods](docs/SCIENTIFIC_METHODS.md) · [Validation Plan](docs/VALIDATION_PLAN.md)

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
