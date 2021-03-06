# Application

After validating the CytoPy framework in the first chapter, we use the entire toolkit to investigate the immune infiltrate of the peritoneum in patients undergoing peritoneal dialysis. A subset of these patients can develop complications including acute peritonitis, an infection of the peritoneal cavity. Drain fluid was obtained from patients with and without symptoms of acute peritonitis and the immune infiltrate phenotyped by flow cytometry. Two flow cytometry staining panels were used (see setup/panels for panel designs), one staining for major leukocyte subsets (neutrophils, eosinophils, monocytes, dendritic cells, T cells and B cells), the other for specific T cell subsets (CD4<sup>+</sup>, CD8<sup>+</sup>, Vδ2<sup>+</sup> γδ T cells, and MAIT cells).

We employ CytoPy to characterise immune cells in this material and use the *feature_selection* module to identify signatures predictive of acute peritonitis.

Analysis is separated into the following steps:

**Setup:** similar to the validation work, this folder contains the project setup, loading the flow data, and inserting some meta-data

1. **Cleaning:** using autonomous gates, the CD45<sup>+</sup> fraction of cells was acquired for leukocyte staining, and the CD3<sup>+</sup> fraction of cells acquired for T cell staining, prior to additional analysis.
2. **Correcting batch effects:** technical variation is visualised and then accounted for using the Harmony algorithm to align similar cells from different batches in high dimensional space.
3. **Label training data for CellClassifier:** with technical variation accounted for, an example was manually labelled using the gating infrastructure in CytoPy and then used to train an XGBoost classifier.
4. **Classify T cell and Leukocyte subsets:** XGBoost is used to classify leukocyte and T cell subsets using manually annotated training data
5. **Cluster T cell and Leukocyte subsets:** to provide an unbiased analysis to accompany supervised classification, FlowSOM and Phenograph clustering were performed independently.
6. **Feature engineering and selection:** the *feature_selection* module was used to create a feature space that describes the peritoneal immune landscape by collating findings from XGBoost, FlowSOM, and Phenograph. Feature selection techniques are then used to find a signature predictive of acute peritonitis.
