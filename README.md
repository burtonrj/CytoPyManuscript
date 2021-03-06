# CytoPy validation & application

This repository of Jupyter Notebooks accompanies our <a>manuscript</a> detailing <a href='https://github.com/burtonrj/CytoPy'>CytoPy</a>, a Python framework for automated analysis of cytometry data. CytoPy offers a data-centric framework, integrated with MongoDB for data management, and an algorithm-agnostic API for applying machine learning algorithms to cytometry data in the Python ecosystem.

This repository details validation of CytoPy but also serves as an example of it's application for those interested in applying CytoPy to their own data. For a basic overview of the framework please consult our webpage: https://cytopy.readthedocs.io/en/latest/

This work is divided into two chapters:

1. **Validation:** we demonstrate the ability of CytoPy's autonomous gating, supervised classification, and high dimensional clustering methods to identify T cell subsets compared to expert manual gates
2. **Application:** the entire framework (including batch-effect correction with Harmony) is applied to immunophenotyping the local immune infiltrate of peritoneum of patients undergoing peritoneal dialysis.

The additional notebook named 'sup_gates' is a detailed tutorial of autonomous gating and is not part of the original manuscript but rather for users that want a more in-depth understanding of all of CytoPy's gating features.
