# AbAgym

This is the data repository of AbAgym, a manually curated collection of 67 antibody-antigen specific DMS datasets from the scientific literature. It contains ~335k non-redundant data points about the effect of single amino acid substitutions on antibody-antigen binding, including 37,361 interface mutations. Also, each DMS dataset comes with an associated 3D structure in PDB format. 

Details about the data collection and curation process can be found in our publication: G.Cia, D. Li, M. Rooman, F. Pucci, ["AbAgym: a well-curated dataset for the mutational analysis of antibody-antigen complexes"](https://www.google.com/) (submitted)

Licence
-------
The dataset and associated files in this repository can only be used for **non-commercial purposes**. For commercial use, and in particular for the training of a commercial computational prediction model, please get in touch with us or our university's knowledge transfer office (ulbkto@ulb.be).

Dataset description
----------
AbAgym is a manually curated collection of 67 antibody-antigen specific DMS datasets from the scientific literature. It contains ~335k non-redundant data points about the effect of single amino acid substitutions on antibody-antigen binding, including 37,361 interface mutations. Also, each DMS dataset comes with an associated 3D structure in PDB format. Details about the data collection and curation process can be found in our publication.

There are 4 files: 
- `AbAgym_data_full.csv`, which contains ~576k data points, including redundant mutations in homo-oligomeric PDB structures (ie structures that contain multiple copies of the same chain).
- `AbAgym_data_non-redundant.csv`, which contains ~335k non-redundant data points, with redundant mutations in homo-oligomeric PDB structures combined into a single row, which corresponds to the biological reality of the experiment.
- `AbAgym_metadata.csv`, which contains general information about the 67 DMS datasets.
- `PDB_files.zip` which contains the PDB structures associated with each DMS dataset.

We also include two additional files that simply correspond to the subset of interface residues in the full and non-redundant datasets, where interface residues are determined using a 6 Å distance thresold on the `closest_interface_atom_distance` column.

The score of each mutation is given by the `DMS_score` column. **It is not an experimental ddG value**, but rather a score that captures the change in binding affinity upon mutation. As noted in our publication, the range of the score differs between DMS datasets, and it is therefore crucial to **normalize** the score before using it to, for example, train a machine learning predictor for antibody binding optimization. For example, you coud use the `DMS_score_range` column from the metadata table to help you normalize each DMS dataset. Also note that experiments with a DMS_score_range of [0/1] only capture destabilizing vs non-destabilizing mutations, and therefore non-destabilizing mutations are a combination of neutral and stabilizing mutations.


# 🧬 AbAgym: A Curated Dataset for Antibody-Antigen Mutations

Welcome to **AbAgym**, a manually curated repository containing 67 deep mutational scanning (DMS) datasets on antibody-antigen complexes. This resource includes over **335,000 non-redundant mutations**, along with structural data, to support the development and evaluation of computational methods for antibody design and immune escape prediction.

📄 _For full details, please refer to our publication:_  
**G. Cia, D. Li, M. Rooman, F. Pucci**  
📝 [“AbAgym: a well-curated dataset for the mutational analysis of antibody-antigen complexes”](https://www.google.com/) _(submitted)_

---

## 📦 Contents of the Repository

| File | Description |
|------|-------------|
| `AbAgym_data_full.csv` | ~576k raw mutation data, includes redundancy from homo-oligomers |
| `AbAgym_data_non-redundant.csv` | ~335k deduplicated mutations (realistic experimental context) |
| `AbAgym_metadata.csv` | Metadata and normalization info for each DMS dataset |
| `PDB_files.zip` | 3D structures of antibody-antigen complexes |
| `AbAgym_interface_full.csv` | Subset of interface residues from full dataset |
| `AbAgym_interface_non-redundant.csv` | Interface subset from non-redundant data |

---

## 🧪 Dataset Description

- ✅ **67 antibody-antigen DMS datasets** from literature  
- 💥 ~**335k non-redundant mutations** (plus a full set of ~576k raw entries)  
- 🧬 Each mutation includes a `DMS_score` describing its impact on binding affinity  
- 🧩 Each dataset is paired with a PDB structure for structural analysis  
- 🔬 Interface residues defined using a **6 Å threshold** (`closest_interface_atom_distance`)  

> **Important:**  
> The `DMS_score` is **not an experimental ΔΔG**, but a proxy for mutation impact.  
> Scores vary per dataset. Use `DMS_score_range` (from metadata) for normalization.  
> Datasets with a [0,1] score range only distinguish destabilizing vs. non-destabilizing.

---

## ⚠️ License

The dataset is released under a **non-commercial use license**.  
📌 For **commercial applications** (e.g., training of prediction tools), please contact:

- us directly, or  
- **Université libre de Bruxelles Knowledge Transfer Office** at: 📧 `ulbkto@ulb.be`

---

## 🔗 Citation

Please cite our publication when using AbAgym in your research:

```bibtex
@article{cia2024abagym,
  title     = {AbAgym: a well-curated dataset for the mutational analysis of antibody-antigen complexes},
  author    = {Cia, G. and Li, D. and Rooman, M. and Pucci, F.},
  journal   = {submitted},
  year      = {2024}
}
