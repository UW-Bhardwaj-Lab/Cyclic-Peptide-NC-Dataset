# Cyclic Peptide Complex Dataset

This repository contains a curated dataset of cyclic peptide–protein complexes meant for model benchmarking. 

---

## Dataset Overview

Structures in this set were extracted from the [Cyclic Peptide DataBank](https://www.frcbs.tsinghua.edu.cn/cpdb/), filtering for Xtal or NMR complex structures only. 
Remaining structures were clustered using [Foldseek Multimer](https://github.com/steineggerlab/foldseek?tab=readme-ov-file#multimercluster) 

```bash
foldseek easy-multimercluster example/ clu tmp \
  --multimer-tm-threshold 0.65 \
  --chain-tm-threshold 0.5 \
  --interface-lddt-threshold 0.65
```

---

## File Structure

```text
cyclic-peptide-NC-dataset/
├── README.md
├── clusters/ #directory with each cif sorted into its respective cluster 
│ ├── cluster_1/
│ │ ├── member1.cif.gz
│ │ │ ...
│ │ └── memberN.cif.gz
│ │ ...
│ ├── cluster_N/
│ └── cluster_reps.list #list of representatives for each cluster (designated by foldseek)
├── foldseek_outputs/ #for clustering transparency 
│ ├── clu_cluster.tsv
│ ├── clu_cluster_report
│ └── clu_rep_seq.fasta
├── CycPepDB.csv #list of all structures in the CPDB
├── complexes.zip #Zip of all cif complexes in the CPDB
├── analysis.ipynb #Notebook for filtering and processing cluster outputs
└── filtered_complexes.csv #list csv for info of complexes only
```
