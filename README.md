# AbAgym

This is the data repository of the publication [AbAgym: a well-curated dataset for the mutational analysis of antibody-antigen complexes](https://www.google.com/).

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

To obtain interface mutations as we did in our publication, simply subset the data to residues within 6 Å using the `closest_interface_atom_distance` column.

The score of each mutation is given by the `DMS_score` column. **It is not an experimental ddG value**, but rather a score that captures the change in binding affinity upon mutation. As noted in our publication, the range of the score differs between DMS datasets, and it is therefore crucial to **normalize** the score before using it to, for example, train a machine learning predictor for antibody binding optimization. For example, you coud use the `DMS_score_range` column from the metadata table to help you normalize each DMS dataset. Also note that experiments with a DMS_score_range of [0/1] only capture destabilizing vs non-destabilizing mutations, and therefore non-destabilizing mutations are a combination of neutral and stabilizing mutations.
