# Multiscale Distribution Entropy Analysis of Short Epileptic EEG Signals

## Status

| Item | Status |
|---|---|
| Research | Published · Mathematical Biosciences and Engineering 2024 |
| Implementation | Method and results available; analysis code: **To be uploaded** |

Dae Hyeon Kim, Jin-Oh Park, Dae-Young Lee, and Young-Seok Choi  
*Mathematical Biosciences and Engineering* 21(4), 5556–5576, 2024. [Paper](https://doi.org/10.3934/mbe.2024245)

Dae Hyeon Kim and Jin-Oh Park contributed equally.

Multiscale entropy analysis of short EEG segments using coarse-graining (MDE-CG) and moving averaging (MDE-MA).

## Method

![Moving-average construction at two scales](figures/moving-average.png)

*Moving-average construction retains overlapping samples at each scale.*

| Method | Scale construction | Entropy estimator |
|---|---|---|
| MSE | Non-overlapping coarse-graining | Sample entropy |
| MDE-CG | Non-overlapping coarse-graining | Distribution entropy |
| MDE-MA | Sliding moving average | Distribution entropy |

At scale s, coarse-graining produces floor(N/s) samples; moving averaging produces N − s + 1. Distribution entropy is computed from the distribution of distances between embedded vectors.

## Experiments

| Dataset | Comparison | Evaluation |
|---|---|---|
| Bonn | Normal, interictal, and ictal EEG | Three five-second intervals; entropy across scales; pairwise Mann–Whitney U tests and ROC AUC |
| Bern–Barcelona | Focal and non-focal EEG | Multiscale entropy and ROC AUC |

### Bonn: pairwise discrimination

![ROC AUC across scales for three intervals and three class pairs](figures/auc-bonn.png)

*Rows correspond to intervals A, B, and C; columns compare normal/interictal, normal/ictal, and interictal/ictal EEG.*

### Bern–Barcelona: focal versus non-focal

![ROC AUC for focal and non-focal EEG](figures/auc-bern.png)

*MDE-MA maintains higher AUC than the compared estimators over most scales above one. AUC is evaluated separately at each scale.*
