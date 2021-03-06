# Validation

This folder details the validation of CytoPy for identification of single cell populations in flow cytometry data. We compared CytoPy to expert manual gates for the identification of T cell subsets in PBMCs from patient samples with significant batch effects. Additionally, supervised classification methods were briefly compared to the FlowCAP submissions.

The analysis is broken up into sections:

**Setup** - in this folder you will find two notebooks that are a preamble to the analysis. Here, we setup the projects and input our flow data into the database.

1. **Batch effect in PBMCs:** using the *variance* module of CytoPy, we visualise and quantify the technical variation that has infiltrated the T cell staining of PBMCs.
2. **Auto gates vs manual gates:** autonomous gates, deployed with landmark registration and hyperparameter search to account for batch effect, identify T cell subsets to equal proficiency as manual gates.
3. **Correcting batch effects with Harmony:** autonomous gates are computationally expensive and can still be labour intensive when choosing the ideal gates for the population(s) of interest. An alternative strategy is supervised classification or high-dimensional clustering. These methods are sensitive to batch effect. We therefore employ Harmony to correct for technical variation and align samples in high dimensional space prior to classification/clustering.
4. **CellClassifier validation with FlowCAP:** before demonstrating CytoPy's supervised classification tools, namely the *CellClassifier* class, on identification of T cell subsets, we briefly compare a handful of classifiers to those submitted in the FlowCAP competition.
5. **CellClassifier vs manual gating:** we use XGBoost with the *CellClassifier* class to generate population data for T cell subsets and compare results to manual gates.
6. **FlowSOM clustering vs manual gating:** using the *Clustering* class of CytoPy, an algorithm-agnostic wrapper for high dimensional clustering, we identify T cell subsets with FlowSOM.
7. **Phenograph clustering vs manual gating:** to a similar vain as the previous notebook, we compare Phenograph clustering to manual gating for identifying T cell subsets in PBMCs.

To see the remainder of the analysis, checkout chapter two in '02-Application' in the same repo as this one.
