# spatial_coupling
Do mutations that occur close together in time on the same lineage tend to be clustered in protein structure?

The pipeline for the [Influenza HA](https://github.com/gboyle2/spatial_coupling/blob/master/influenza-ha/analysis/influenza-A_HA_augur.ipynb) protein builds a time-resolved phylogenetic tree using `augur`, traces all nodes in the tree using either the Inchworm method (tip to parent, parent to grandparent, ...) or the Concatenated Inchworm method (tip to parent, tip to grandparent, ..., parent to grandparent, parent to great grandparent, ...), retrieves an all-by-all 3D distance matrix of the HA trimer, and plots a correlation plot with branch length vs 3D distance. There are several housekeeping items that still need addressed with this pipeline.

1. `augur translate` had trouble with our sequences, so we used `PhyDMS` instead. [Sarah](https://github.com/skhilton) aligned the sequences to the WSN sequence and we used `BioPython` to translate them. **This step was not integrated into the pipeline.**
2. A proper configuration cell was never incorporated
3. The notebook should be streamlined and extraneous steps cut out. This could include removing the Inchworm method altogether, and refining which plot outputs to keep. As it stands, there are several redundant plots.

