# Phylogenomic Analysis Utilities

A collection of Python scripts for phylogenomic analyses.

## 1. Combine all gene trees in NEXUS format
Please put all of the gene trees and this script in the same dir. 
Usage: python combine_trees_in_nexus.py.

This python script is used to combine all the gene trees in PhyloNet format in 
Tree gt0=(...)
Tree gt1=(...)
Tree gt2=(...)
....
After generating the file in the name 'infer_Network_MPL.nexus', you have to manually add the head "#NEXUS" and tail "BEGIN PHYLONET;

InferNetwork_MPL (all) 3 -x 20 -pl 20;

END;" to complete the input.





## 2. Add Outgroups from MO to RT

This Python script adds specified outgroup sequences from MO ortholog datasets to the corresponding RT ortholog datasets and realigns the sequences using MAFFT.

Please prepare an `outgroup.txt` file with one outgroup ID per line.

The directory names for the MO datasets, RT datasets, and output files should be `MO_seq`, `RT_seq`, and `RT_added_outgroup`, respectively.

Example `outgroup.txt`:

```text
NH500
NH501
NZY080
```

Usage:

```bash
python3 add_outgroup_from_MO_to_RT.py outgroup.txt MO_seq RT_seq RT_added_outgroup
```

