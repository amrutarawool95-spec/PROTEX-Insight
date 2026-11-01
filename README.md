PROTEX-Insight
Protein Structure Analysis, Mutation Investigation & Computational Drug-Discovery Exploration
PROTEX-Insight is an exploratory computational biology project designed to bring protein-structure visualization, protein–ligand analysis, mutation-focused investigation, molecular docking and drug-candidate comparison into one research-oriented interface.
The current demonstration focuses on the epidermal growth factor receptor (EGFR) kinase structure, using PDB ID: 1M17, and selected EGFR inhibitors as example compounds.
Project status: Research prototype / ongoing development. This repository documents the project, its intended workflow and selected application screenshots. It does not contain the complete application source code or independently verified computational outputs unless explicitly added and documented.
Scientific caution: Docking scores and computational predictions are not experimental measurements and must not be interpreted as proof of binding, potency, safety or clinical efficacy.
At a glance
Item
Description
Project
PROTEX-Insight
Domain
Structural bioinformatics, cheminformatics and computational drug discovery
Demonstration target
EGFR kinase
Example structure
RCSB PDB: 1M17
Interface
Interactive web application
Intended computational tools
Python, Biopython, RDKit, AutoDock Vina and molecular-visualization libraries
Current repository contents
Project documentation, methodology notes, validation plan and screenshots
Development status
Prototype; computational validation is ongoing
Why this project?
Protein structures provide a way to investigate how small molecules may interact with biological targets. However, structural data, ligand preparation, docking configuration and result interpretation can be technically demanding.
PROTEX-Insight aims to make several stages of this workflow accessible through a single interface while keeping the underlying scientific assumptions visible.
Main modules
1. Protein Explorer
Explore a selected protein structure in 3D.
Display protein-chain and residue information.
Highlight selected functional residues.
Inspect structure metadata and ligand records.
2. Structure Analysis
Inspect chains, residues, atoms and hetero-residues.
Examine structural features and missing-coordinate regions.
Identify protein-associated ligands and other non-protein components.
Explore protein–ligand proximity and contact information.
3. Mutation Analysis
Provide a framework for investigating selected EGFR variants, including L858R, T790M and C797S.
Validate residue identity and numbering against an appropriate reference sequence.
Distinguish sequence annotation from actual mutant-structure modelling.
4. Ligand Analysis
Explore ligand structures and molecular descriptors.
Intended descriptors include molecular weight, cLogP, topological polar surface area, hydrogen-bond donors and acceptors, and rotatable bonds.
Examine ligand–protein contacts where the required structural data are available.
5. Molecular Docking
Provide a workflow interface for docking experiments using AutoDock Vina.
Configure receptor, ligand, search box and docking parameters.
Inspect predicted poses and scores when an actual docking run has completed.
Support redocking validation where suitable reference structures and atom mapping are available.
6. Drug Comparison
Provide a framework for comparing selected EGFR inhibitors, such as erlotinib, gefitinib and osimertinib.
Compare computational results only when compounds have been processed using comparable methods.
Keep experimental pharmacology separate from predicted docking scores.
Example application screenshots
Add your screenshots to assets/screenshots/ and use the filenames below, or change the paths to match your files.
Protein Explorer
�
Molecular Docking
�
Drug Comparison
�
Screenshots demonstrate the application's interface and displayed information. They are not, by themselves, evidence that a calculation has been independently reproduced or validated.
Scientific workflow
The intended end-to-end workflow is:
Retrieve or upload a protein structure.
Confirm the PDB entry, chain, residue numbering and ligand identity.
Inspect structure quality, missing residues and relevant structural components.
Prepare the receptor and ligand using documented, reproducible settings.
Define the binding site using a justified reference, such as a co-crystallized ligand.
Run docking using a recorded software version, configuration and random seed.
Inspect predicted poses and calculate relevant interaction features.
Validate the workflow using redocking and, where possible, cross-docking.
Compare computational predictions with experimental pharmacology from traceable sources.
Report limitations and avoid interpreting docking scores as experimental affinity.
See docs/SCIENTIFIC_METHODS.md and docs/VALIDATION_PLAN.md.
Technology direction
The project is designed around the following tools. Only list a tool as implemented if it is genuinely used by the current application.
Tool
Intended role
Python
Application logic and scientific computation
Biopython
Protein structure and sequence handling
RDKit
Ligand parsing and molecular descriptors
AutoDock Vina
Molecular docking
Streamlit
Interactive application interface
3Dmol.js / py3Dmol
Molecular structure visualization
NumPy / Pandas / SciPy
Numerical analysis and data handling
Plotly / Matplotlib
Scientific plots and visual summaries
Important scientific limitations
A docking score is a scoring-function estimate, not an experimentally measured binding free energy.
A favourable predicted pose does not establish biological activity or clinical effectiveness.
Protein preparation choices, protonation states, retained waters, cofactors, ions and receptor conformation can affect results.
Contact distances alone do not prove hydrogen bonds, salt bridges or other chemically specific interactions.
Mutation annotation is not the same as generating and validating a mutant 3D structure.
Experimental IC50, Ki or Kd values depend on assay conditions and should not be compared casually across different studies.
A reported RMSD is meaningful only when the reference pose, atom correspondence, alignment procedure and calculation method are documented.
Repository structure
PROTEX-Insight/
├── README.md
├── assets/
│   └── screenshots/
│       ├── protein-explorer.png
│       ├── molecular-docking.png
│       └── drug-comparison.png
└── docs/
    ├── PROJECT_REPORT.md
    ├── SCIENTIFIC_METHODS.md
    ├── VALIDATION_PLAN.md
    ├── USER_GUIDE.md
    └── DEVELOPMENT_ROADMAP.md
How to use this repository
This repository is currently a documentation and project-showcase repository. It does not provide a runnable installation package.
Browse the project report and methodology documents.
View the screenshots in assets/screenshots/.
Review the validation plan to understand what must be tested before scientific claims are made.
If the application source code becomes available, add installation instructions, pinned dependencies, test instructions and a reproducible example.
Future work
Reproducible receptor and ligand preparation.
Explicit tracking of protonation and retained-water choices.
Cross-docking across multiple EGFR structures.
Sensitivity analysis across preparation settings.
Automated pose and interaction validation.
Comparison with traceable experimental pharmacology.
Downloadable reports containing parameters, provenance and limitations.
Automated tests and continuous integration.
References and data resources
RCSB Protein Data Bank: https://www.rcsb.org/
PDB entry 1M17: https://www.rcsb.org/structure/1M17
UniProt: https://www.uniprot.org/
PubChem: https://pubchem.ncbi.nlm.nih.gov/
Biopython: https://biopython.org/
RDKit: https://www.rdkit.org/
AutoDock Vina: https://vina.scripps.edu/
AutoDock Vina documentation: https://autodock-vina.readthedocs.io/
Always cite the specific record, publication, software version and access date used for an actual analysis.
Author
Project developer: [Your name]
LinkedIn: [Your LinkedIn URL]
GitHub: [Your GitHub profile URL]
Disclaimer
PROTEX-Insight is an educational and research-oriented computational project. It is not a clinical decision-support system and must not be used to make treatment recommendations. Computational results require independent validation and experimental evidence.
