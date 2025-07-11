# 🧬 AbAgym: A Curated Dataset for Antibody-Antigen Mutations

Welcome to **AbAgym**, a manually curated dataset containing 67 deep mutational scanning (DMS) datasets on antibody-antigen complexes, along with 3D structures of each complex. The dataset includes over **335,000 non-redundant mutations**, including 37,361 interface mutations, which can support the development and evaluation of computational methods for antibody design and immune escape prediction.

📄 _For full details, please refer to our publication:_  
**G. Cia, D. Li, M. Rooman, F. Pucci** [“AbAgym: a well-curated dataset for the mutational analysis of antibody-antigen complexes”](https://www.google.com/) _(submitted)_

---

## 📦 Contents of the Repository

The table below describes the data and files contained in this repository.

| File | Description |
|------|-------------|
| `AbAgym_data_full.csv` | ~576k redundant mutation data (i.e all individual mutations, including those on identical chains of homo-oligomeric PDB structures)|
| `AbAgym_data_non-redundant.csv` | ~335k non-redundant mutation data (i.e mutations on identical chains of homo-oligomeric chains combined into a single row) |
| `AbAgym_metadata.csv` | General information of each DMS dataset |
| `PDB_files.zip` | 3D structures of antibody-antigen complexes |
| `AbAgym_data_full_interface.csv` | Subset of mutations located at the Antibody-Antigen interface, which we used to benchmark computational prediction methods. Interface residues are determined using a 6 Å heavy atom distance thresold|

---

In the AbAgym data files, the score of each mutation is given by the DMS_score column. This score originates from deep mutational scanning (DMS) experiments and is therefore not a direct experimental measurement of binding affinity changes upon mutation. Although related, DMS scores and binding affinities are not equivalent, and DMS scores depend on the specific experimental assay used. As noted in our publication, different assay types produce scores with varying ranges. Some assays output scores between 0 and 1, where 0 indicates complete neutralization (no effect on binding) and 1 indicates full immune escape. Others produce scores ranging from negative to positive values: in these cases, 0 typically indicates no effect, positive scores indicate escape mutations, and negative scores suggest enhanced binding. If you plan to use this dataset to train machine learning models, it could be necessary to normalize the scores across datasets to account for these differences. For details on the DMS assays, please refer to the Supplementary Material of our paper.


## ⚠️ License

The dataset is freely accessible for **non-commercial use only**. For **commercial applications** (e.g., training of prediction tools), please contact us (Fabrizio.Pucci@ulb.be).

---

## 🔗 Citation

Please cite our publication when using AbAgym in your research:

```bibtex
@article{cia2024abagym,
  title     = {AbAgym: a well-curated dataset for the mutational analysis of antibody-antigen complexes},
  author    = {Cia, G. and Li, D. and Rooman, M. and Pucci, F.},
  journal   = {submitted},
  year      = {2025}
}
