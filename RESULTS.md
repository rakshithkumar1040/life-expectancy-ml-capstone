# Life Lens — Results Summary

This report summarises the saved outputs from the Review 2 notebook. For the full analysis, refer to `notebooks/Review_2_Life_Expectancy_FINAL.ipynb`.

## Headline results

- **Regression:** Support Vector Regressor achieved **R² = 0.9361**, **RMSE = 2.4422**, and **MAE = 1.6222**.
- **Classification:** Bagging (Decision Tree) was selected by the notebook's weighted-F1 rule, with **accuracy = 0.9575**, **weighted F1 = 0.9577**, and **ROC-AUC = 0.9867**.
- **Tuned Random Forest classification:** weighted F1 increased from **0.9458** to **0.9516** (+0.0058).
- **PCA:** 14 components retained 96.2375% of regression variance and 96.4752% of classification variance.
- **Clustering:** Agglomerative complete linkage had silhouette 0.7157 and Davies–Bouldin 0.6618; K-Means had the highest Calinski–Harabasz index (638.96).

## Regression highlights

| Model | R² | RMSE | MAE |
|---|---:|---:|---:|
| Support Vector Regressor | 0.9361 | 2.4422 | 1.6222 |
| Polynomial Regression (degree 2) | 0.9207 | 2.7209 | 2.0462 |
| Gradient Boosting (tuned) | 0.9090 | 2.9148 | 2.1167 |
| K-Nearest Neighbors Regressor | 0.9056 | 2.9683 | 2.1026 |
| Random Forest Regressor | 0.9054 | 2.9728 | 2.1176 |

## Classification highlights

| Model | Accuracy | Weighted F1 | ROC-AUC |
|---|---:|---:|---:|
| Bagging (Decision Tree) | 0.9575 | 0.9577 | 0.9867 |
| Random Forest (tuned) | 0.9524 | 0.9516 | 0.9829 |
| Random Forest | 0.9473 | 0.9458 | 0.9819 |
| K-Nearest Neighbors | 0.9456 | 0.9454 | 0.9661 |
| Support Vector Machine | 0.9456 | 0.9454 | 0.9728 |

## Clustering comparison

| Configuration | Silhouette ↑ | Davies–Bouldin ↓ | Calinski–Harabasz ↑ |
|---|---:|---:|---:|
| Agglomerative — complete | 0.7157 | 0.6618 | 245.73 |
| Agglomerative — average | 0.7110 | 0.6783 | 248.97 |
| K-Means | 0.2412 | 1.4297 | 638.96 |
| Agglomerative — ward | 0.2219 | 1.4506 | 584.36 |

## Visualisations

All extracted notebook plot images are stored in [`results/plots/`](results/plots/). The Word report `Life_Lens_Results_Report.docx` embeds the complete saved plot gallery and includes the headline tables.

## Interpretation notes

- These metrics reproduce saved notebook outputs; the models were not retrained during report generation.
- K-Means produced a small cluster of 20 records with k=3. Inspect cluster composition and stability before making strong claims.
- Clustering metrics differ in what they reward; do not select a method from one metric alone.
- Preserve the dataset source and licence information when publishing the repository.
