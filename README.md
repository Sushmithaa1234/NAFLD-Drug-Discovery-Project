# NAFLD Drug Discovery Project: Molecular Docking of Indian Phytochemicals against PPAR-α

## 🧠 Project Overview

Non-Alcoholic Fatty Liver Disease (NAFLD) is an increasingly prevalent metabolic disorder with no definitive cure. This project explores structure-based virtual screening of natural phytochemicals derived from Indian medicinal plants against the **Peroxisome Proliferator-Activated Receptor Alpha (PPAR-α)**, a key target implicated in lipid metabolism and NAFLD progression.

The goal was to identify potential PPAR-α ligands using computational docking and visualize their interactions to shortlist promising lead molecules.

[Information on the ligands, docking results and image of the protein-ligand complex are attached]

---

## 🧪 Tools & Databases Used

| Purpose            | Tool/Database              |
| ------------------ | -------------------------- |
| Ligand Collection  | IMPPAT + PubChem           |
| Ligand Preparation | PyMOL / OpenBabel          |
| Docking Tool       | CB-Dock2                   |
| Visualization      | PyMOL                      |
| Protein Target     | UniProt (P37231), RCSB PDB (2P54) |

---

## 🧬 Target Protein

* **Name:** PPAR-α (Peroxisome Proliferator-Activated Receptor Alpha)
* **UniProt ID:** P37231
* **Structure Used:** PDB ID: 2P54 (chain A)
* Water molecules and heteroatoms removed before docking

---

## 🌿 Ligand Selection

12 bioactive phytochemicals were selected based on literature evidence of their antioxidant or hepatoprotective roles in liver disease. The list includes:

1. Curcumin
2. Berberine
3. Piperine
4. Capsaicin
5. Resveratrol
6. Withaferin A
7. Guggulsterone E
8. Mangiferin
9. Quercetin
10. Luteolin
11. Genistein
12. Apigenin

All ligands were sourced from IMPPAT and validated using PubChem. They were converted to suitable docking formats using CB-Dock2.

---

## ⚙️ Docking Methodology

* **Platform Used:** CB-Dock2 (blind docking with cavity detection)
* **Procedure:**

  1. Uploaded the cleaned receptor PDB file
  2. Uploaded each ligand (mol2 format)
  3. Recorded best **CurPocket** for each ligand (highest negative vina score)
  4. Saved protein-ligand complex files (.pdb format)
  5. Noted key details: cavity volume, center, docking box size, contact residues

### 📄 Example Docking Result Entry

| Ligand    | CurPocket | Vina Score | Volume | Center (x,y,z)   | Docking Size (x,y,z) | Contact Residues                     |
| --------- | --------- | ---------- | ------ | ---------------- | -------------------- | ------------------------------------ |
| Quercetin | C1        | -9.4       | 589.6  | 13.2, 39.6, 27.6 | 20.0, 20.0, 20.0     | PHE273, CYS276, TYR334, MET330, etc. |

*Identical docking pockets across ligands suggest a shared binding region.*

---

## 🧬 Structure Visualization with PyMOL

All 12 ligand-protein complexes were visualized using PyMOL:

* Receptor colored **grey** and grouped as `rec`
* Ligands renamed `lig1` to `lig12` and colored individually
* Superimposed all complexes to visualize binding overlap
* Captured high-res images of the full structure and zoomed-in poses

Hydrogen bond detection was attempted but not all ligands formed H-bonds at cutoff criteria.

---

## 📊 Results & Insights

### 🔽 Ligand Ranking (by Vina Score)

1. Quercetin (-9.4)
2. Luteolin (-9.4)
3. Withaferin A (-9.3)
4. Mangiferin (-9.2)
5. Apigenin (-9.1)
6. Genistein (-9.1)
7. Resveratrol (-8.8)
8. Curcumin (-8.7)
9. Piperine (-8.6)
10. Guggulsterone E (-8.5)
11. Capsaicin (-8.5)
12. Berberine (-8.3)

### 🧠 Interpretation

* Most potent predicted binders: **Quercetin, Luteolin, Withaferin A**
* These ligands docked into the same key pocket (CurPocket C1) with consistent binding residues
* Superposition suggests strong overlap across ligands
* Consistency in cavity volume and pocket center reinforces accuracy of docking predictions

---

## 📁 Repository Structure

```
NAFLD-PPARa-Docking/
├── Docking_Results.xlsx        # Complete CB-Dock2 results
├── Ligands/                    # Ligand files used (.mol2)
├── Receptor/                   # Cleaned PPAR-alpha PDB file
├── Complexes/                  # Protein-ligand docked PDBs
├── PyMOL_Screenshots/          # Final rendered images
├── README.md                   # This file
```

---

## 📌 Conclusion

This project demonstrates a cost-effective and accessible workflow for performing preliminary drug discovery using open-source docking platforms and natural compound databases. While experimental validation is necessary, the insights derived from this project provide a valuable starting point.

---

## 🙋🏻‍♀️ Author

**Sushmithaa Chandrasekar**
B.Tech Biotechnology, VIT Vellore
*Bioinformatics & Drug Discovery Enthusiast*

---

## 🔗 Related Links

* [NAFLD Fact Sheet](https://liverfoundation.org/wp-content/uploads/2022/06/NAFLD-Fact-Sheet.pdf)
* [IMPPAT: Indian Medicinal Plants, Phytochemistry and Therapeutics](https://cb.imsc.res.in/imppat/)
* [CB-Dock2](https://cadd.labshare.cn/cb-dock2/)
* [PPAR-α UniProt Entry (P37231)](https://www.uniprot.org/uniprot/P37231)
* [RCSB PDB](https://www.rcsb.org/)
* [PyMOL](https://pymol.org/2/)
---

## 📣 License

This project is for educational and research purposes only.

---

## 🧭 Future Directions

* Perform MM-GBSA or MD simulations for top-ranked ligands
* Expand the ligand library beyond Indian medicinal plants
* Validate interaction networks with literature docking studies
