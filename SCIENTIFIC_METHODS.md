Scientific Methods and Computational Considerations
This document describes the methods that should be used or documented in PROTEX-Insight. A method must not be described as implemented until the application actually performs it and its output can be inspected.
1. Protein structure data
Data source
Use the RCSB Protein Data Bank as the primary source for experimentally determined PDB structures.
Example:
PDB ID: 1M17
Record: https://www.rcsb.org/structure/1M17
Record the retrieval date, file format, structure identifier, experimental method, resolution (where applicable), chain and biological assembly choice.
Chain and residue numbering
Distinguish author residue numbering from PDB-assigned numbering and sequence numbering.
Preserve insertion codes where present.
Map structural residues to a specified reference sequence before annotating variants.
Distinguish residues absent from coordinates from residues absent from the biological sequence.
Record alternate atom locations and the selection policy.
Structure quality and preparation
Inspect missing residues, alternate conformations, occupancy, B-factors, crystallographic waters, ions, cofactors and relevant non-protein components. Do not automatically remove every water or hetero-residue without considering its structural role.
2. Protein–ligand contact analysis
A simple heavy-atom contact analysis can calculate the minimum distance between protein and ligand heavy atoms:
d(i,j) = ||r_i - r_j||
where r_i and r_j are Cartesian coordinates in ångströms.
For each ligand atom, identify protein atoms within explicitly stated distance cutoffs. Report the cutoff and atom-selection rules.
Important: A distance cutoff identifies spatial proximity. It does not, by itself, establish a hydrogen bond, salt bridge, hydrophobic interaction or aromatic stacking interaction.
Chemically specific interactions require appropriate atom typing, donor/acceptor roles, geometry, charge and, where relevant, ring-orientation criteria.
3. Ligand structure and descriptors
Use a traceable chemical input, such as a PubChem record, a curated SDF/MOL file or a verified SMILES string.
Record:
Compound name and identifier.
Source database and record identifier.
Input structure and stereochemistry.
Protonation/tautomer assumptions.
RDKit version.
Whether descriptors were calculated from the neutral form or another specified state.
Possible RDKit descriptors:
Molecular weight.
Calculated logP.
Topological polar surface area.
Hydrogen-bond donor count.
Hydrogen-bond acceptor count.
Rotatable bond count.
Descriptor values depend on the input representation and software implementation. Lipinski-style rules are heuristics and do not prove drug-likeness, binding or efficacy.
4. Receptor and ligand preparation for docking
A reproducible docking workflow should document:
Receptor
PDB identifier, chain and source file.
Whether a biological assembly or asymmetric unit was used.
Treatment of co-crystallized ligands, waters, ions and cofactors.
Hydrogen addition and protonation method.
Charge assignment and atom typing.
PDBQT preparation tool and version.
Ligand
Chemical source and identifier.
Stereochemistry and protonation state.
Hydrogen addition and geometry optimization method.
Torsion assignment and charge method.
PDBQT preparation tool and version.
The same preparation policy should be applied consistently when comparing candidates, while retaining scientifically justified differences.
5. Docking with AutoDock Vina
Record at minimum:
AutoDock Vina version.
Receptor and ligand file hashes or filenames.
Search-box centre (x, y, z) in ångströms.
Search-box dimensions (x, y, z) in ångströms.
Exhaustiveness.
Number of modes.
Energy range.
Random seed.
Command used.
Exit status and complete output log.
A docking score is an estimate from a scoring function. It is not an experimentally measured binding free energy, Ki, Kd or IC50.
Do not compare scores from different protocols as if they were directly equivalent.
6. Docking pose validation
Redocking
A typical redocking workflow is:
Obtain a protein structure with a co-crystallized ligand.
Preserve the original ligand coordinates as the reference pose.
Prepare the receptor with the reference ligand removed from the docking receptor.
Prepare the ligand using a documented procedure.
Dock the ligand back into the binding site.
Compare the predicted pose with the crystallographic pose.
RMSD
A heavy-atom RMSD calculation requires correct atom correspondence and a defined alignment procedure. Symmetry-equivalent atoms may require symmetry-aware mapping.
A commonly used approximate pose-recovery benchmark is around 2 Å heavy-atom RMSD, but interpretation depends on the ligand, atom mapping and protocol. Do not report a value unless the calculation was actually performed and its method is stated.
Cross-docking
Dock ligands into alternative structures of the same target where suitable structures are available. Record structural differences, ligand identity, binding-site correspondence and preparation settings. Cross-docking can reveal sensitivity to receptor conformation.
7. Sensitivity analysis
Test whether results change under reasonable alternative settings:
Alternative protonation states.
Retention or removal of structurally relevant waters.
Different EGFR receptor structures.
Alternative receptor preparation settings.
Multiple docking seeds or repeated runs.
Different search exhaustiveness values.
Report the full range or distribution of results, not only the most favourable score.
8. Experimental pharmacology comparison
When comparing docking predictions with experimental data, record:
Assay type and biological system.
Endpoint (IC50, Ki, Kd or another measure).
Units and reported uncertainty.
Publication or database source.
Experimental conditions where available.
IC50, Ki and Kd are different quantities. They must not be treated as interchangeable. Values from different assays may not be directly comparable.
9. Data provenance and reproducibility
For every analysis, preserve:
Input file names and source identifiers.
Retrieval dates.
Software and version numbers.
Parameters and command-line arguments.
Random seeds.
Output files and logs.
Error messages and warnings.
A concise record of manual decisions.
10. Reporting rule
Every result should be labelled as one of:
Calculated: generated by the application from identified inputs.
Retrieved: obtained from a cited database or publication.
Illustrative: included only to demonstrate the interface.
Not validated: calculated or displayed but not yet independently checked.
Unavailable: not calculated because required data or software were missing.
Never present illustrative or unavailable values as calculated results.
