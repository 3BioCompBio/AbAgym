# AbAgym

This is the data repository of the publication [AbAgym: a well-curated dataset for the mutational analysis of antibody-antigen complexes](google.com).

Licence
-------
The dataset and associated files in this repository can only be used for **non-commercial purposes**. For commercial use, and in particular for the training of a commercial computational prediction model based on this dataset, please get in touch with us or our university's knowledge transfer office (ulbkto@ulb.be).

Dataset description
----------
AbAgym is a manually curated collection of 67 antibody-antigen specific DMS datasets from the scientific literature. It contains approx. 335k data points about the effect of single amino acid substitutions on antibody-antigen binding, including 37,361 interface mutations. Also, each DMS dataset comes with an associated 3D structure in PDB format. Details about the data collection and curation process can be found in our publication.

There are 3 files: 1) `AbAgym_data.csv`, which contains the 335k data points; 2) `AbAgym_metadata.csv`, which contains general information about each DMS dataset; 3) `PDB_files.zip` which contains the PDB structures associated with each DMS dataset.

The score of each mutation is given by the `DMS_score` column. **It is not an experimental ddG value**, but rather a score that captures the change in binding affinity upon mutation. As noted in our publication, the range of the score differs between DMS datasets, and it is therefore crucial to **normalize** the score before using it to, for example, train a machine learning predictor for antibody binding optimization. For example, you cold use the `DMS_score_range` column from the metadata table to help you normalize each DMS dataset.
