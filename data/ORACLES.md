# Oracle models

Five `ExtraTreesRegressor` models, one per kinase target, stand in for the
assay. They total \~352 MB and are archived separately rather than in git.

|target|ChEMBL|training compounds|held-out R2|
|-|-|-|-|
|ABL1|CHEMBL1862|1,635|0.704|
|JAK2|CHEMBL2971|8,377|0.608|
|EGFR|CHEMBL203|6,821|0.582|
|p38alpha|CHEMBL260|3,927|0.527|
|CDK2|CHEMBL301|1,833|0.443|

Features: 2048-bit ECFP4 + 1024-bit FCFP4 + 14 physicochemical descriptors
(3,086 columns). Trained on IC50 only; IC50 and Ki are never pooled. Held-out
performance is on a generic Bemis-Murcko scaffold split, 20% held out,
averaged over three seeds.

Download the archive from Zenodo and extract it to `data/oracles/` so that the directory
contains `abl1\\\\\\\\\\\\\\\_extratrees.joblib` and its four counterparts.

**The oracles are needed only to re-run campaigns.** Every analysis in the
paper regenerates from the archived run records without them, and without
RDKit.

