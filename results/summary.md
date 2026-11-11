# Final run, all tables

Total runtime 146.2 min, warnings: 0

## nDCG@10 ×100

|  | miracl:sw | miracl:yo | miracl:bn | miracl:te | mrtydi:sw | mrtydi:bn | MIRACL avg (trained langs) |
|---|---|---|---|---|---|---|---|
| BM25 | 47.1 | 56.4 | 45.0 | 45.4 | 48.9 | 39.0 | 45.8 |
| mE5 dense | 71.3 | 70.3 | 71.9 | 81.5 | 72.5 | 69.2 | 74.9 |
| RRF (equal weights) | 63.7 | 74.1 | 61.8 | 67.2 | 62.8 | 54.5 | 64.2 |
| RRF (tuned weights) | 71.3 | 70.3 | 71.9 | 81.5 | 72.5 | 69.2 | 74.9 |
| Convex fusion (tuned) | 73.1 | 73.3 | 73.4 | 81.6 | 72.5 | 70.5 | 76.0 |
| MLP reranker (no graph) | 74.3 | 78.9 | 75.8 | 84.0 | 73.4 | 71.8 | 78.0 |
| GNN, dense edges only | 74.9 | 77.7 | 76.3 | 84.6 | 74.0 | 71.5 | 78.6 |
| MLP + article evidence (no graph) | 74.8 | 75.5 | 76.3 | 85.4 | 74.5 | 72.9 | 78.8 |
| GNN typed graph + article evidence | 76.3 | 76.2 | 77.4 | 86.5 | 75.8 | 76.2 | 80.1 |
| GNN typed graph + article evidence, no dense edges | 75.4 | 75.0 | 76.6 | 85.8 | 74.4 | 73.9 | 79.3 |
| GNN typed graph + article evidence, no lexical edges | 75.8 | 75.6 | 77.1 | 86.7 | 76.3 | 75.9 | 79.9 |
| GNN typed graph + article evidence, no article/adjacent edges | 76.1 | 76.3 | 76.9 | 86.5 | 76.0 | 76.6 | 79.8 |
| TAG-Rank (cheap) [no gate] | 76.1 | 75.1 | 77.1 | 86.6 | 75.7 | 76.3 | 79.9 |
| TAG-Rank (cheap) | 76.1 | 77.6 | 77.1 | 86.6 | 75.7 | 76.3 | 79.9 |
| TAG-Rank (cheap) ×5 ensemble | 76.7 | 78.7 | 77.4 | 87.0 | 76.0 | 76.2 | 80.4 |
| MLP + CE inputs (budget-conditioned) @k=0 | 74.7 | 78.5 | 76.3 | 85.6 | 74.4 | 72.9 | 78.8 |
| MLP + CE inputs (budget-conditioned) @k=5 | 78.6 | 83.6 | 81.3 | 88.2 | 79.9 | 79.9 | 82.7 |
| MLP + CE inputs (budget-conditioned) @k=10 | 80.4 | 84.0 | 82.9 | 88.6 | 81.0 | 81.2 | 84.0 |
| MLP + CE inputs (budget-conditioned) @k=20 | 81.0 | 84.9 | 84.0 | 88.8 | 81.7 | 81.9 | 84.6 |
| MLP + CE inputs (budget-conditioned) @k=30 | 81.5 | 84.2 | 84.5 | 88.9 | 81.9 | 83.1 | 85.0 |
| TAG-Rank+CE (budget-conditioned) @k=0 | 75.3 | 78.2 | 77.0 | 85.9 | 75.0 | 74.1 | 79.4 |
| TAG-Rank+CE (budget-conditioned) @k=5 | 79.3 | 82.9 | 82.1 | 88.3 | 80.3 | 80.8 | 83.2 |
| TAG-Rank+CE (budget-conditioned) @k=10 | 80.8 | 83.3 | 83.4 | 88.7 | 81.3 | 82.2 | 84.3 |
| TAG-Rank+CE (budget-conditioned) @k=20 | 81.3 | 84.9 | 84.3 | 88.9 | 82.3 | 82.9 | 84.8 |
| TAG-Rank+CE (budget-conditioned) @k=30 | 81.8 | 84.8 | 84.7 | 88.9 | 82.4 | 83.8 | 85.1 |
| MLP + CE inputs (budget-conditioned) @k=5 2-pass | 78.6 | 83.6 | 81.7 | 88.3 | 79.8 | 79.7 | 82.9 |
| MLP + CE inputs (budget-conditioned) @k=10 2-pass | 80.0 | 85.3 | 83.2 | 88.7 | 81.3 | 82.0 | 84.0 |
| MLP + CE inputs (budget-conditioned) @k=20 2-pass | 81.9 | 86.2 | 84.8 | 89.1 | 82.3 | 82.8 | 85.3 |
| MLP + CE inputs (budget-conditioned) @k=30 2-pass | 82.2 | 86.1 | 85.2 | 89.1 | 82.7 | 83.5 | 85.5 |
| TAG-Rank+CE (budget-conditioned) @k=5 2-pass | 79.2 | 83.9 | 82.0 | 88.5 | 80.3 | 81.2 | 83.2 |
| TAG-Rank+CE (budget-conditioned) @k=10 2-pass | 80.8 | 85.0 | 83.9 | 88.8 | 81.8 | 83.1 | 84.5 |
| TAG-Rank+CE (budget-conditioned) @k=20 2-pass | 82.2 | 85.6 | 84.9 | 89.0 | 82.7 | 84.3 | 85.4 |
| TAG-Rank+CE (budget-conditioned) @k=30 2-pass | 82.4 | 86.2 | 85.2 | 89.0 | 83.0 | 84.3 | 85.5 |
| TAG-Rank+CE (budget-conditioned) ×5 ensemble, 2-pass @k=0 | 75.7 | 78.4 | 77.3 | 86.1 | 75.2 | 74.3 | 79.7 |
| TAG-Rank+CE (budget-conditioned) ×5 ensemble, 2-pass @k=5 | 79.4 | 83.8 | 82.4 | 88.7 | 80.8 | 81.4 | 83.5 |
| TAG-Rank+CE (budget-conditioned) ×5 ensemble, 2-pass @k=10 | 80.9 | 85.0 | 83.9 | 88.9 | 82.1 | 83.0 | 84.6 |
| TAG-Rank+CE (budget-conditioned) ×5 ensemble, 2-pass @k=20 | 82.1 | 86.8 | 85.0 | 89.4 | 83.0 | 83.8 | 85.5 |
| TAG-Rank+CE (budget-conditioned) ×5 ensemble, 2-pass @k=30 | 82.5 | 86.7 | 85.3 | 89.2 | 83.0 | 84.3 | 85.7 |
| mE5 dense → CE top-5 | 75.8 | 77.5 | 78.3 | 85.8 | 78.2 | 78.1 | 80.0 |
| mE5 dense → CE top-10 | 77.3 | 78.5 | 80.2 | 86.9 | 78.9 | 79.3 | 81.5 |
| mE5 dense → CE top-20 | 80.4 | 81.0 | 82.2 | 87.3 | 79.9 | 80.4 | 83.3 |
| mE5 dense → CE top-30 | 80.8 | 83.8 | 82.5 | 87.3 | 80.5 | 81.3 | 83.5 |
| Convex fusion → CE top-5 | 77.5 | 80.5 | 79.3 | 86.2 | 78.5 | 78.6 | 81.0 |
| Convex fusion → CE top-10 | 78.7 | 81.0 | 81.2 | 87.0 | 79.4 | 79.7 | 82.3 |
| Convex fusion → CE top-20 | 80.9 | 83.9 | 82.5 | 87.4 | 80.5 | 80.5 | 83.6 |
| Convex fusion → CE top-30 | 81.4 | 83.9 | 82.9 | 87.6 | 80.8 | 81.4 | 84.0 |
| TAG-Rank (cheap) → CE top-5 | 79.3 | 83.8 | 81.5 | 87.7 | 80.0 | 80.6 | 82.8 |
| TAG-Rank (cheap) → CE top-10 | 80.6 | 84.7 | 83.2 | 87.8 | 80.9 | 82.8 | 83.9 |
| TAG-Rank (cheap) → CE top-20 | 81.7 | 85.8 | 83.8 | 88.1 | 81.9 | 82.5 | 84.5 |
| TAG-Rank (cheap) → CE top-30 | 82.6 | 86.9 | 83.8 | 88.0 | 82.2 | 82.2 | 84.8 |

## MRR@100 ×100

|  | miracl:sw | miracl:yo | miracl:bn | miracl:te | mrtydi:sw | mrtydi:bn | MIRACL avg (trained langs) |
|---|---|---|---|---|---|---|---|
| BM25 | 48.3 | 54.2 | 48.8 | 40.4 | 44.6 | 35.9 | 45.8 |
| mE5 dense | 75.0 | 67.4 | 75.0 | 77.7 | 69.1 | 63.5 | 75.9 |
| RRF (equal weights) | 65.6 | 70.8 | 65.8 | 61.2 | 58.1 | 49.8 | 64.2 |
| RRF (tuned weights) | 75.0 | 67.4 | 75.0 | 77.7 | 69.1 | 63.5 | 75.9 |
| Convex fusion (tuned) | 76.4 | 70.3 | 76.1 | 77.8 | 69.0 | 64.7 | 76.8 |
| MLP reranker (no graph) | 76.8 | 75.2 | 78.4 | 80.7 | 69.5 | 66.2 | 78.6 |
| GNN, dense edges only | 77.4 | 73.3 | 79.1 | 81.4 | 70.2 | 66.1 | 79.3 |
| MLP + article evidence (no graph) | 77.1 | 72.3 | 78.8 | 82.2 | 70.5 | 66.8 | 79.4 |
| GNN typed graph + article evidence | 78.4 | 72.5 | 80.0 | 83.5 | 72.2 | 71.5 | 80.6 |
| GNN typed graph + article evidence, no dense edges | 77.3 | 71.4 | 79.1 | 82.6 | 70.7 | 69.0 | 79.7 |
| GNN typed graph + article evidence, no lexical edges | 77.9 | 71.9 | 79.9 | 83.6 | 72.6 | 70.9 | 80.5 |
| GNN typed graph + article evidence, no article/adjacent edges | 78.1 | 73.0 | 79.6 | 83.5 | 72.4 | 71.8 | 80.4 |
| TAG-Rank (cheap) [no gate] | 78.4 | 71.1 | 80.0 | 83.6 | 72.2 | 71.7 | 80.7 |
| TAG-Rank (cheap) | 78.4 | 73.7 | 80.0 | 83.6 | 72.2 | 71.7 | 80.7 |
| TAG-Rank (cheap) ×5 ensemble | 79.3 | 74.8 | 80.1 | 84.1 | 72.5 | 71.3 | 81.2 |
| MLP + CE inputs (budget-conditioned) @k=0 | 76.8 | 75.6 | 78.9 | 82.3 | 70.4 | 66.7 | 79.3 |
| MLP + CE inputs (budget-conditioned) @k=5 | 81.9 | 82.5 | 86.5 | 85.7 | 77.7 | 76.4 | 84.7 |
| MLP + CE inputs (budget-conditioned) @k=10 | 83.2 | 81.9 | 87.6 | 86.1 | 79.1 | 78.0 | 85.6 |
| MLP + CE inputs (budget-conditioned) @k=20 | 82.9 | 83.3 | 87.5 | 86.2 | 79.4 | 78.7 | 85.6 |
| MLP + CE inputs (budget-conditioned) @k=30 | 83.2 | 82.2 | 87.7 | 86.2 | 79.5 | 79.8 | 85.7 |
| TAG-Rank+CE (budget-conditioned) @k=0 | 77.8 | 74.8 | 79.6 | 82.7 | 71.1 | 68.8 | 80.0 |
| TAG-Rank+CE (budget-conditioned) @k=5 | 82.4 | 81.9 | 86.7 | 85.7 | 78.1 | 77.6 | 84.9 |
| TAG-Rank+CE (budget-conditioned) @k=10 | 83.2 | 81.8 | 87.5 | 86.1 | 79.4 | 79.3 | 85.6 |
| TAG-Rank+CE (budget-conditioned) @k=20 | 83.1 | 83.6 | 87.5 | 86.2 | 80.0 | 79.9 | 85.6 |
| TAG-Rank+CE (budget-conditioned) @k=30 | 83.4 | 83.5 | 87.8 | 86.3 | 80.2 | 80.8 | 85.8 |
| MLP + CE inputs (budget-conditioned) @k=5 2-pass | 81.8 | 82.5 | 86.5 | 85.9 | 77.7 | 76.4 | 84.7 |
| MLP + CE inputs (budget-conditioned) @k=10 2-pass | 82.7 | 83.7 | 87.7 | 86.3 | 79.3 | 79.0 | 85.6 |
| MLP + CE inputs (budget-conditioned) @k=20 2-pass | 83.7 | 84.2 | 88.1 | 86.5 | 79.9 | 79.5 | 86.1 |
| MLP + CE inputs (budget-conditioned) @k=30 2-pass | 83.7 | 83.9 | 88.2 | 86.4 | 80.3 | 80.4 | 86.1 |
| TAG-Rank+CE (budget-conditioned) @k=5 2-pass | 82.1 | 82.9 | 86.5 | 86.1 | 78.1 | 78.3 | 84.9 |
| TAG-Rank+CE (budget-conditioned) @k=10 2-pass | 83.1 | 83.3 | 88.0 | 86.3 | 79.9 | 80.3 | 85.8 |
| TAG-Rank+CE (budget-conditioned) @k=20 2-pass | 83.8 | 83.5 | 88.1 | 86.5 | 80.4 | 81.4 | 86.1 |
| TAG-Rank+CE (budget-conditioned) @k=30 2-pass | 83.9 | 83.9 | 88.2 | 86.4 | 80.6 | 81.4 | 86.1 |
| TAG-Rank+CE (budget-conditioned) ×5 ensemble, 2-pass @k=0 | 78.3 | 75.1 | 80.0 | 83.0 | 71.5 | 68.9 | 80.4 |
| TAG-Rank+CE (budget-conditioned) ×5 ensemble, 2-pass @k=5 | 82.3 | 82.9 | 86.7 | 86.4 | 78.7 | 78.8 | 85.2 |
| TAG-Rank+CE (budget-conditioned) ×5 ensemble, 2-pass @k=10 | 83.2 | 83.6 | 87.7 | 86.5 | 80.2 | 80.4 | 85.8 |
| TAG-Rank+CE (budget-conditioned) ×5 ensemble, 2-pass @k=20 | 83.7 | 84.4 | 88.0 | 86.8 | 80.7 | 80.6 | 86.2 |
| TAG-Rank+CE (budget-conditioned) ×5 ensemble, 2-pass @k=30 | 83.9 | 84.4 | 88.3 | 86.5 | 80.6 | 81.5 | 86.2 |
| mE5 dense → CE top-5 | 80.9 | 77.6 | 85.0 | 83.4 | 76.7 | 75.5 | 83.1 |
| mE5 dense → CE top-10 | 82.0 | 79.2 | 86.5 | 84.7 | 77.5 | 77.0 | 84.4 |
| mE5 dense → CE top-20 | 82.9 | 81.5 | 86.2 | 84.8 | 77.7 | 77.5 | 84.6 |
| mE5 dense → CE top-30 | 82.8 | 83.4 | 86.1 | 84.7 | 77.9 | 78.3 | 84.5 |
| Convex fusion → CE top-5 | 81.9 | 81.0 | 84.8 | 83.8 | 76.9 | 75.9 | 83.5 |
| Convex fusion → CE top-10 | 82.7 | 80.9 | 86.4 | 84.8 | 77.8 | 77.0 | 84.7 |
| Convex fusion → CE top-20 | 83.1 | 82.7 | 86.4 | 84.8 | 78.1 | 77.5 | 84.8 |
| Convex fusion → CE top-30 | 83.2 | 82.5 | 86.2 | 84.9 | 78.3 | 78.3 | 84.8 |
| TAG-Rank (cheap) → CE top-5 | 82.3 | 82.1 | 86.2 | 85.0 | 77.8 | 77.7 | 84.5 |
| TAG-Rank (cheap) → CE top-10 | 83.4 | 83.2 | 87.7 | 85.1 | 78.9 | 80.0 | 85.4 |
| TAG-Rank (cheap) → CE top-20 | 83.6 | 83.7 | 87.0 | 85.3 | 79.3 | 79.4 | 85.3 |
| TAG-Rank (cheap) → CE top-30 | 84.1 | 84.3 | 86.7 | 85.1 | 79.5 | 79.3 | 85.3 |

## Key comparisons (Δ nDCG@10 ×100, Wilcoxon, Holm over MIRACL languages)

| comparison | group | delta_ndcg@10 | p_wilcoxon | p_holm | wins | losses |
|---|---|---|---|---|---|---|
| RQ1 learned reranker vs tuned fusion | miracl:sw | 1.191 | 0.000 | 0.001 | 143 | 80 |
| RQ1 learned reranker vs tuned fusion | miracl:yo | 5.589 | 0.001 | 0.001 | 37 | 13 |
| RQ1 learned reranker vs tuned fusion | miracl:bn | 2.452 | 0.000 | 0.000 | 153 | 95 |
| RQ1 learned reranker vs tuned fusion | miracl:te | 2.344 | 0.000 | 0.000 | 154 | 93 |
| RQ1 learned reranker vs tuned fusion | mrtydi:sw | 0.896 | 0.028 |  | 112 | 87 |
| RQ1 learned reranker vs tuned fusion | mrtydi:bn | 1.287 | 0.110 |  | 30 | 15 |
| RQ1 learned reranker vs tuned fusion | MIRACL trained langs (pooled) | 2.047 | 0.000 |  | 450 | 268 |
| RQ2 dense-only graph vs no graph | miracl:sw | 0.594 | 0.018 | 0.054 | 125 | 98 |
| RQ2 dense-only graph vs no graph | miracl:yo | -1.242 | 0.043 | 0.086 | 16 | 32 |
| RQ2 dense-only graph vs no graph | miracl:bn | 0.490 | 0.240 | 0.240 | 125 | 102 |
| RQ2 dense-only graph vs no graph | miracl:te | 0.610 | 0.001 | 0.006 | 132 | 76 |
| RQ2 dense-only graph vs no graph | mrtydi:sw | 0.571 | 0.029 |  | 118 | 90 |
| RQ2 dense-only graph vs no graph | mrtydi:bn | -0.223 | 0.225 |  | 15 | 26 |
| RQ2 dense-only graph vs no graph | MIRACL trained langs (pooled) | 0.577 | 0.000 |  | 382 | 276 |
| RQ2 typed graph vs no graph (same features) | miracl:sw | 1.447 | 0.000 | 0.000 | 158 | 99 |
| RQ2 typed graph vs no graph (same features) | miracl:yo | 0.697 | 0.229 | 0.229 | 35 | 24 |
| RQ2 typed graph vs no graph (same features) | miracl:bn | 1.153 | 0.000 | 0.000 | 146 | 97 |
| RQ2 typed graph vs no graph (same features) | miracl:te | 1.137 | 0.000 | 0.000 | 140 | 86 |
| RQ2 typed graph vs no graph (same features) | mrtydi:sw | 1.320 | 0.001 |  | 147 | 108 |
| RQ2 typed graph vs no graph (same features) | mrtydi:bn | 3.250 | 0.002 |  | 33 | 18 |
| RQ2 typed graph vs no graph (same features) | MIRACL trained langs (pooled) | 1.228 | 0.000 |  | 444 | 282 |
| RQ2 ablation: remove dense edges | miracl:sw | -0.858 | 0.020 | 0.061 | 120 | 144 |
| RQ2 ablation: remove dense edges | miracl:yo | -1.191 | 0.125 | 0.250 | 22 | 34 |
| RQ2 ablation: remove dense edges | miracl:bn | -0.874 | 0.180 | 0.250 | 134 | 127 |
| RQ2 ablation: remove dense edges | miracl:te | -0.731 | 0.015 | 0.060 | 107 | 136 |
| RQ2 ablation: remove dense edges | mrtydi:sw | -1.424 | 0.000 |  | 109 | 157 |
| RQ2 ablation: remove dense edges | mrtydi:bn | -2.255 | 0.007 |  | 19 | 34 |
| RQ2 ablation: remove dense edges | MIRACL trained langs (pooled) | -0.801 | 0.000 |  | 361 | 407 |
| RQ2 ablation: remove lexical edges | miracl:sw | -0.487 | 0.010 | 0.041 | 111 | 147 |
| RQ2 ablation: remove lexical edges | miracl:yo | -0.616 | 0.319 | 0.637 | 25 | 30 |
| RQ2 ablation: remove lexical edges | miracl:bn | -0.325 | 0.130 | 0.389 | 107 | 132 |
| RQ2 ablation: remove lexical edges | miracl:te | 0.127 | 0.426 | 0.637 | 107 | 104 |
| RQ2 ablation: remove lexical edges | mrtydi:sw | 0.435 | 0.112 |  | 134 | 108 |
| RQ2 ablation: remove lexical edges | mrtydi:bn | -0.333 | 0.885 |  | 28 | 21 |
| RQ2 ablation: remove lexical edges | MIRACL trained langs (pooled) | -0.153 | 0.078 |  | 325 | 383 |
| RQ2 ablation: remove article/adjacent edges | miracl:sw | -0.140 | 0.862 | 1.000 | 126 | 125 |
| RQ2 ablation: remove article/adjacent edges | miracl:yo | 0.082 | 0.831 | 1.000 | 25 | 27 |
| RQ2 ablation: remove article/adjacent edges | miracl:bn | -0.551 | 0.138 | 0.551 | 110 | 126 |
| RQ2 ablation: remove article/adjacent edges | miracl:te | -0.029 | 0.767 | 1.000 | 105 | 106 |
| RQ2 ablation: remove article/adjacent edges | mrtydi:sw | 0.131 | 0.368 |  | 128 | 110 |
| RQ2 ablation: remove article/adjacent edges | mrtydi:bn | 0.453 | 0.508 |  | 26 | 21 |
| RQ2 ablation: remove article/adjacent edges | MIRACL trained langs (pooled) | -0.185 | 0.255 |  | 341 | 357 |
| RQ3 article evidence (no graph) | miracl:sw | 0.555 | 0.613 | 1.000 | 125 | 119 |
| RQ3 article evidence (no graph) | miracl:yo | -3.414 | 0.004 | 0.012 | 19 | 43 |
| RQ3 article evidence (no graph) | miracl:bn | 0.448 | 0.664 | 1.000 | 126 | 126 |
| RQ3 article evidence (no graph) | miracl:te | 1.419 | 0.000 | 0.001 | 158 | 96 |
| RQ3 article evidence (no graph) | mrtydi:sw | 1.071 | 0.002 |  | 132 | 90 |
| RQ3 article evidence (no graph) | mrtydi:bn | 1.178 | 0.261 |  | 24 | 19 |
| RQ3 article evidence (no graph) | MIRACL trained langs (pooled) | 0.945 | 0.002 |  | 409 | 341 |
| RQ3 structure-aware training + gate | miracl:sw | -0.116 | 0.864 | 1.000 | 118 | 121 |
| RQ3 structure-aware training + gate | miracl:yo | 1.445 | 0.178 | 0.534 | 33 | 24 |
| RQ3 structure-aware training + gate | miracl:bn | -0.356 | 0.040 | 0.158 | 94 | 128 |
| RQ3 structure-aware training + gate | miracl:te | 0.015 | 0.804 | 1.000 | 96 | 89 |
| RQ3 structure-aware training + gate | mrtydi:sw | -0.115 | 0.580 |  | 110 | 115 |
| RQ3 structure-aware training + gate | mrtydi:bn | 0.073 | 0.833 |  | 22 | 22 |
| RQ3 structure-aware training + gate | MIRACL trained langs (pooled) | -0.110 | 0.262 |  | 308 | 338 |
| RQ3 gate on vs off (same model) | miracl:sw | 0.000 | 1.000 | 1.000 | 0 | 0 |
| RQ3 gate on vs off (same model) | miracl:yo | 2.550 | 0.020 | 0.080 | 39 | 23 |
| RQ3 gate on vs off (same model) | miracl:bn | 0.000 | 1.000 | 1.000 | 0 | 0 |
| RQ3 gate on vs off (same model) | miracl:te | 0.000 | 1.000 | 1.000 | 0 | 0 |
| RQ3 gate on vs off (same model) | mrtydi:sw | 0.000 | 1.000 |  | 0 | 0 |
| RQ3 gate on vs off (same model) | mrtydi:bn | 0.000 | 1.000 |  | 0 | 0 |
| RQ3 gate on vs off (same model) | MIRACL trained langs (pooled) | 0.000 | 1.000 |  | 0 | 0 |
| 5-seed ensemble vs single model | miracl:sw | 0.582 | 0.014 | 0.042 | 130 | 103 |
| 5-seed ensemble vs single model | miracl:yo | 1.060 | 0.033 | 0.067 | 25 | 15 |
| 5-seed ensemble vs single model | miracl:bn | 0.339 | 0.048 | 0.067 | 126 | 94 |
| 5-seed ensemble vs single model | miracl:te | 0.433 | 0.007 | 0.029 | 111 | 81 |
| 5-seed ensemble vs single model | mrtydi:sw | 0.254 | 0.291 |  | 117 | 109 |
| 5-seed ensemble vs single model | mrtydi:bn | -0.063 | 0.756 |  | 23 | 22 |
| 5-seed ensemble vs single model | MIRACL trained langs (pooled) | 0.453 | 0.000 |  | 367 | 278 |
| Final cheap model vs no-graph reranker | miracl:sw | 2.468 | 0.000 | 0.000 | 140 | 97 |
| Final cheap model vs no-graph reranker | miracl:yo | -0.212 | 0.604 | 0.604 | 17 | 24 |
| Final cheap model vs no-graph reranker | miracl:bn | 1.584 | 0.001 | 0.002 | 141 | 99 |
| Final cheap model vs no-graph reranker | miracl:te | 3.005 | 0.000 | 0.000 | 163 | 61 |
| Final cheap model vs no-graph reranker | mrtydi:sw | 2.530 | 0.000 |  | 133 | 83 |
| Final cheap model vs no-graph reranker | mrtydi:bn | 4.437 | 0.001 |  | 37 | 14 |
| Final cheap model vs no-graph reranker | MIRACL trained langs (pooled) | 2.515 | 0.000 |  | 444 | 257 |
| RQ4 graph effect at CE budget k=0 | miracl:sw | 0.692 | 0.004 | 0.013 | 142 | 96 |
| RQ4 graph effect at CE budget k=0 | miracl:yo | -0.315 | 0.494 | 0.494 | 23 | 23 |
| RQ4 graph effect at CE budget k=0 | miracl:bn | 0.686 | 0.002 | 0.009 | 129 | 87 |
| RQ4 graph effect at CE budget k=0 | miracl:te | 0.299 | 0.209 | 0.418 | 106 | 93 |
| RQ4 graph effect at CE budget k=0 | mrtydi:sw | 0.589 | 0.018 |  | 125 | 100 |
| RQ4 graph effect at CE budget k=0 | mrtydi:bn | 1.258 | 0.118 |  | 25 | 20 |
| RQ4 graph effect at CE budget k=0 | MIRACL trained langs (pooled) | 0.501 | 0.000 |  | 377 | 276 |
| RQ4 graph effect at CE budget k=5 | miracl:sw | 0.781 | 0.000 | 0.001 | 133 | 78 |
| RQ4 graph effect at CE budget k=5 | miracl:yo | -0.745 | 0.156 | 0.156 | 8 | 19 |
| RQ4 graph effect at CE budget k=5 | miracl:bn | 0.775 | 0.000 | 0.001 | 116 | 70 |
| RQ4 graph effect at CE budget k=5 | miracl:te | 0.122 | 0.077 | 0.154 | 84 | 55 |
| RQ4 graph effect at CE budget k=5 | mrtydi:sw | 0.362 | 0.052 |  | 100 | 74 |
| RQ4 graph effect at CE budget k=5 | mrtydi:bn | 0.920 | 0.102 |  | 19 | 14 |
| RQ4 graph effect at CE budget k=5 | MIRACL trained langs (pooled) | 0.463 | 0.000 |  | 333 | 203 |
| RQ4 graph effect at CE budget k=10 | miracl:sw | 0.464 | 0.013 | 0.053 | 111 | 78 |
| RQ4 graph effect at CE budget k=10 | miracl:yo | -0.753 | 0.326 | 0.589 | 15 | 18 |
| RQ4 graph effect at CE budget k=10 | miracl:bn | 0.429 | 0.049 | 0.148 | 97 | 76 |
| RQ4 graph effect at CE budget k=10 | miracl:te | 0.083 | 0.294 | 0.589 | 75 | 49 |
| RQ4 graph effect at CE budget k=10 | mrtydi:sw | 0.304 | 0.075 |  | 95 | 70 |
| RQ4 graph effect at CE budget k=10 | mrtydi:bn | 1.027 | 0.038 |  | 19 | 9 |
| RQ4 graph effect at CE budget k=10 | MIRACL trained langs (pooled) | 0.272 | 0.001 |  | 283 | 203 |
| RQ4 graph effect at CE budget k=20 | miracl:sw | 0.368 | 0.016 | 0.066 | 100 | 80 |
| RQ4 graph effect at CE budget k=20 | miracl:yo | -0.035 | 0.788 | 1.000 | 15 | 10 |
| RQ4 graph effect at CE budget k=20 | miracl:bn | 0.319 | 0.247 | 0.741 | 88 | 78 |
| RQ4 graph effect at CE budget k=20 | miracl:te | 0.066 | 0.594 | 1.000 | 69 | 61 |
| RQ4 graph effect at CE budget k=20 | mrtydi:sw | 0.607 | 0.003 |  | 100 | 65 |
| RQ4 graph effect at CE budget k=20 | mrtydi:bn | 0.953 | 0.055 |  | 18 | 8 |
| RQ4 graph effect at CE budget k=20 | MIRACL trained langs (pooled) | 0.211 | 0.017 |  | 257 | 219 |
| RQ4 graph effect at CE budget k=30 | miracl:sw | 0.279 | 0.032 | 0.128 | 102 | 80 |
| RQ4 graph effect at CE budget k=30 | miracl:yo | 0.653 | 0.200 | 0.599 | 18 | 8 |
| RQ4 graph effect at CE budget k=30 | miracl:bn | 0.181 | 0.892 | 1.000 | 82 | 92 |
| RQ4 graph effect at CE budget k=30 | miracl:te | 0.053 | 0.560 | 1.000 | 73 | 67 |
| RQ4 graph effect at CE budget k=30 | mrtydi:sw | 0.541 | 0.035 |  | 88 | 74 |
| RQ4 graph effect at CE budget k=30 | mrtydi:bn | 0.721 | 0.051 |  | 21 | 6 |
| RQ4 graph effect at CE budget k=30 | MIRACL trained langs (pooled) | 0.147 | 0.079 |  | 257 | 239 |
| RQ4 CE as graph input vs cascade, k=5 | miracl:sw | 1.867 | 0.000 | 0.000 | 136 | 74 |
| RQ4 CE as graph input vs cascade, k=5 | miracl:yo | 2.309 | 0.043 | 0.043 | 19 | 10 |
| RQ4 CE as graph input vs cascade, k=5 | miracl:bn | 2.826 | 0.000 | 0.000 | 134 | 66 |
| RQ4 CE as graph input vs cascade, k=5 | miracl:te | 2.162 | 0.000 | 0.000 | 111 | 62 |
| RQ4 CE as graph input vs cascade, k=5 | mrtydi:sw | 1.780 | 0.000 |  | 112 | 71 |
| RQ4 CE as graph input vs cascade, k=5 | mrtydi:bn | 2.152 | 0.078 |  | 22 | 9 |
| RQ4 CE as graph input vs cascade, k=5 | MIRACL trained langs (pooled) | 2.238 | 0.000 |  | 381 | 202 |
| RQ4 CE as graph input vs cascade, k=10 | miracl:sw | 2.157 | 0.000 | 0.000 | 123 | 64 |
| RQ4 CE as graph input vs cascade, k=10 | miracl:yo | 2.254 | 0.041 | 0.041 | 20 | 11 |
| RQ4 CE as graph input vs cascade, k=10 | miracl:bn | 2.155 | 0.000 | 0.000 | 111 | 76 |
| RQ4 CE as graph input vs cascade, k=10 | miracl:te | 1.699 | 0.000 | 0.000 | 101 | 61 |
| RQ4 CE as graph input vs cascade, k=10 | mrtydi:sw | 1.920 | 0.000 |  | 106 | 58 |
| RQ4 CE as graph input vs cascade, k=10 | mrtydi:bn | 2.502 | 0.066 |  | 19 | 11 |
| RQ4 CE as graph input vs cascade, k=10 | MIRACL trained langs (pooled) | 1.936 | 0.000 |  | 335 | 201 |
| RQ4 CE as graph input vs cascade, k=20 | miracl:sw | 0.462 | 0.067 | 0.133 | 114 | 81 |
| RQ4 CE as graph input vs cascade, k=20 | miracl:yo | 1.012 | 0.191 | 0.191 | 14 | 9 |
| RQ4 CE as graph input vs cascade, k=20 | miracl:bn | 1.846 | 0.000 | 0.001 | 111 | 70 |
| RQ4 CE as graph input vs cascade, k=20 | miracl:te | 1.436 | 0.000 | 0.000 | 106 | 62 |
| RQ4 CE as graph input vs cascade, k=20 | mrtydi:sw | 1.846 | 0.000 |  | 105 | 62 |
| RQ4 CE as graph input vs cascade, k=20 | mrtydi:bn | 2.365 | 0.052 |  | 21 | 9 |
| RQ4 CE as graph input vs cascade, k=20 | MIRACL trained langs (pooled) | 1.261 | 0.000 |  | 331 | 213 |
| RQ4 CE as graph input vs cascade, k=30 | miracl:sw | 0.380 | 0.206 | 0.374 | 113 | 88 |
| RQ4 CE as graph input vs cascade, k=30 | miracl:yo | 0.980 | 0.187 | 0.374 | 16 | 9 |
| RQ4 CE as graph input vs cascade, k=30 | miracl:bn | 1.806 | 0.001 | 0.004 | 109 | 77 |
| RQ4 CE as graph input vs cascade, k=30 | miracl:te | 1.353 | 0.000 | 0.001 | 107 | 62 |
| RQ4 CE as graph input vs cascade, k=30 | mrtydi:sw | 1.614 | 0.000 |  | 101 | 63 |
| RQ4 CE as graph input vs cascade, k=30 | mrtydi:bn | 2.466 | 0.050 |  | 22 | 9 |
| RQ4 CE as graph input vs cascade, k=30 | MIRACL trained langs (pooled) | 1.189 | 0.000 |  | 329 | 227 |
| RQ4 2-pass ensemble vs fusion picks, k=5 | miracl:sw | 0.059 | 0.212 | 0.424 | 115 | 82 |
| RQ4 2-pass ensemble vs fusion picks, k=5 | miracl:yo | 0.921 | 0.471 | 0.471 | 16 | 11 |
| RQ4 2-pass ensemble vs fusion picks, k=5 | miracl:bn | 0.297 | 0.104 | 0.311 | 111 | 79 |
| RQ4 2-pass ensemble vs fusion picks, k=5 | miracl:te | 0.431 | 0.014 | 0.055 | 81 | 54 |
| RQ4 2-pass ensemble vs fusion picks, k=5 | mrtydi:sw | 0.507 | 0.046 |  | 98 | 69 |
| RQ4 2-pass ensemble vs fusion picks, k=5 | mrtydi:bn | 0.617 | 0.394 |  | 16 | 11 |
| RQ4 2-pass ensemble vs fusion picks, k=5 | MIRACL trained langs (pooled) | 0.295 | 0.002 |  | 307 | 215 |
| RQ4 2-pass ensemble vs fusion picks, k=10 | miracl:sw | 0.115 | 0.173 | 0.346 | 93 | 75 |
| RQ4 2-pass ensemble vs fusion picks, k=10 | miracl:yo | 1.730 | 0.178 | 0.346 | 17 | 9 |
| RQ4 2-pass ensemble vs fusion picks, k=10 | miracl:bn | 0.561 | 0.043 | 0.130 | 99 | 67 |
| RQ4 2-pass ensemble vs fusion picks, k=10 | miracl:te | 0.241 | 0.018 | 0.071 | 74 | 44 |
| RQ4 2-pass ensemble vs fusion picks, k=10 | mrtydi:sw | 0.716 | 0.001 |  | 91 | 58 |
| RQ4 2-pass ensemble vs fusion picks, k=10 | mrtydi:bn | 0.816 | 0.338 |  | 14 | 9 |
| RQ4 2-pass ensemble vs fusion picks, k=10 | MIRACL trained langs (pooled) | 0.282 | 0.001 |  | 266 | 186 |
| RQ4 2-pass ensemble vs fusion picks, k=20 | miracl:sw | 0.773 | 0.830 | 0.830 | 83 | 88 |
| RQ4 2-pass ensemble vs fusion picks, k=20 | miracl:yo | 1.889 | 0.082 | 0.165 | 15 | 7 |
| RQ4 2-pass ensemble vs fusion picks, k=20 | miracl:bn | 0.699 | 0.009 | 0.034 | 93 | 66 |
| RQ4 2-pass ensemble vs fusion picks, k=20 | miracl:te | 0.519 | 0.020 | 0.061 | 73 | 55 |
| RQ4 2-pass ensemble vs fusion picks, k=20 | mrtydi:sw | 0.672 | 0.011 |  | 90 | 56 |
| RQ4 2-pass ensemble vs fusion picks, k=20 | mrtydi:bn | 0.907 | 0.382 |  | 9 | 16 |
| RQ4 2-pass ensemble vs fusion picks, k=20 | MIRACL trained langs (pooled) | 0.634 | 0.004 |  | 249 | 209 |
| RQ4 2-pass ensemble vs fusion picks, k=30 | miracl:sw | 0.737 | 0.227 | 0.520 | 93 | 89 |
| RQ4 2-pass ensemble vs fusion picks, k=30 | miracl:yo | 1.835 | 0.130 | 0.520 | 16 | 10 |
| RQ4 2-pass ensemble vs fusion picks, k=30 | miracl:bn | 0.590 | 0.130 | 0.520 | 91 | 77 |
| RQ4 2-pass ensemble vs fusion picks, k=30 | miracl:te | 0.258 | 0.294 | 0.520 | 67 | 59 |
| RQ4 2-pass ensemble vs fusion picks, k=30 | mrtydi:sw | 0.640 | 0.020 |  | 83 | 59 |
| RQ4 2-pass ensemble vs fusion picks, k=30 | mrtydi:bn | 0.443 | 0.502 |  | 8 | 16 |
| RQ4 2-pass ensemble vs fusion picks, k=30 | MIRACL trained langs (pooled) | 0.471 | 0.029 |  | 251 | 225 |
| RQ4 TAG-Rank+CE on 10 vs fusion cascade on 30 | miracl:sw | -0.468 | 0.679 | 0.718 | 76 | 73 |
| RQ4 TAG-Rank+CE on 10 vs fusion cascade on 30 | miracl:yo | 1.147 | 0.359 | 0.718 | 13 | 7 |
| RQ4 TAG-Rank+CE on 10 vs fusion cascade on 30 | miracl:bn | 1.044 | 0.088 | 0.263 | 94 | 74 |
| RQ4 TAG-Rank+CE on 10 vs fusion cascade on 30 | miracl:te | 1.380 | 0.001 | 0.005 | 87 | 41 |
| RQ4 TAG-Rank+CE on 10 vs fusion cascade on 30 | mrtydi:sw | 1.276 | 0.007 |  | 75 | 41 |
| RQ4 TAG-Rank+CE on 10 vs fusion cascade on 30 | mrtydi:bn | 1.654 | 0.172 |  | 19 | 9 |
| RQ4 TAG-Rank+CE on 10 vs fusion cascade on 30 | MIRACL trained langs (pooled) | 0.782 | 0.002 |  | 257 | 188 |

## Cost vs. quality (MIRACL dev pooled)

| policy | 0.0 | 3.0 | 5.0 | 6.0 | 9.0 | 10.0 | 12.0 | 15.0 | 18.0 | 20.0 | 24.0 | 30.0 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Convex fusion → CE top-k (cascade) | 77.0 |  | 82.0 |  |  | 83.1 |  |  |  | 84.4 |  | 84.7 |
| MLP, CE scores as inputs (fusion picks) | 80.2 |  | 83.8 |  |  | 84.9 |  |  |  | 85.4 |  | 85.7 |
| MLP, CE scores as inputs (model picks, 2-pass) |  |  | 84.0 |  |  | 85.0 |  |  |  | 86.1 |  | 86.2 |
| TAG-Rank (cheap) → CE top-k (cascade) | 81.6 |  | 83.9 |  |  | 84.7 |  |  |  | 85.3 |  | 85.6 |
| TAG-Rank+CE (fusion picks) | 80.6 |  | 84.2 |  |  | 85.1 |  |  |  | 85.6 |  | 85.8 |
| TAG-Rank+CE (model picks, 2-pass) |  |  | 84.3 |  |  | 85.4 |  |  |  | 86.1 |  | 86.3 |
| TAG-Rank+CE ×5 ensemble (model picks, 2-pass) | 80.9 |  | 84.6 |  |  | 85.5 |  |  |  | 86.3 |  | 86.4 |
| mE5 dense → CE top-k (cascade) | 76.0 |  | 81.0 |  |  | 82.3 |  |  |  | 83.9 |  | 84.3 |
| router: learned router | 80.9 | 82.1 |  | 83.2 | 83.9 |  | 84.7 | 85.4 | 85.8 |  | 85.9 | 86.0 |
| router: low-margin first (heuristic) | 80.9 | 82.0 |  | 82.9 | 83.4 |  | 84.7 | 85.4 | 85.8 |  | 85.9 | 86.0 |
| router: oracle (true gain, upper bound) | 80.9 | 85.3 |  | 87.3 | 87.7 |  | 87.7 | 87.7 | 87.7 |  | 87.7 | 86.0 |
| router: random | 80.9 | 81.4 |  | 81.7 | 82.3 |  | 82.8 | 83.5 | 84.1 |  | 85.0 | 86.0 |

## Homophily ratio

|  | dense | lex | article | adjacent |
|---|---|---|---|---|
| train:sw | 2.43 | 2.76 | 2.53 | 3.78 |
| train:bn | 3.03 | 4.16 | 2.37 | 4.90 |
| train:te | 1.23 | 1.88 | 1.15 | 2.81 |
| miracl:sw | 3.38 | 3.77 | 2.86 | 6.32 |
| miracl:yo | 3.06 | 4.34 | 5.62 | 2.31 |
| miracl:bn | 3.07 | 4.02 | 2.16 | 3.72 |
| miracl:te | 0.28 | 0.35 | 0.09 | 0.00 |
| mrtydi:sw | 0.91 | 0.91 | 2.15 | 4.28 |
| mrtydi:bn | 0.81 | 1.69 | 1.72 | 4.03 |

## GAR recall study (×100)

| lang | BM25 top-30 | BM25 top-50 | +20 dense-graph nbrs | +20 LSH lexical nbrs |
|---|---|---|---|---|
| bn | 68.9 | 74.7 | 77.7 | 69.2 |
| sw | 72.9 | 77.0 | 78.1 | 73.0 |
| te | 72.7 | 74.8 | 80.1 | 72.9 |
| yo | 84.3 | 86.4 | 89.6 | 84.3 |

## Spark MinHash-LSH

|  | passages_hashed | pairs | near_dup_pairs | same_article_pairs | edges_kept | passages_with_neighbour | seconds |
|---|---|---|---|---|---|---|---|
| sw | 63194 | 10132 | 3730 | 722 | 15996 | 9693 | 31 |
| yo | 17953 | 2531 | 1413 | 1047 | 4088 | 2162 | 12 |
| bn | 189689 | 14565 | 4463 | 3286 | 22779 | 14655 | 65 |
| te | 199947 | 32865 | 12875 | 1885 | 43654 | 19277 | 103 |

## Spark corpus profile

|  | lang | passages | articles | avg_words | median_words | p95_words | total_tokens | vocab | hapax_ratio | passages_per_article | train_queries | train_avg_q_words | train_avg_rel_per_q | train_avg_judged_per_q | train_rel_article_diversity | train_q_relpassage_overlap | train_zero_overlap_frac | dev_queries | dev_avg_q_words | dev_avg_rel_per_q | dev_avg_judged_per_q | dev_rel_article_diversity | dev_q_relpassage_overlap | dev_zero_overlap_frac |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| sw | sw | 131924 | 47793 | 34.226 | 26 | 93 | 4515170 | 205034 | 0.562 | 2.760 | 1901 | 6.652 | 1.413 | 4.923 | 0.834 | 0.479 | 0.028 | 482 | 6.622 | 1.888 | 10.564 | 0.809 | 0.509 | 0.014 |
| yo | yo | 49043 | 33094 | 26.494 | 9 | 105 | 1299322 | 110803 | 0.636 | 1.482 |  |  |  |  |  |  |  | 119 | 7.916 | 1.210 | 9.983 | 0.852 | 0.423 | 0.021 |
| bn | bn | 297265 | 63762 | 55.069 | 42 | 144 | 16370123 | 646163 | 0.571 | 4.662 | 1631 | 6.977 | 2.366 | 10.272 | 0.769 | 0.448 | 0.029 | 411 | 7.002 | 2.100 | 10.234 | 0.808 | 0.461 | 0.025 |
| te | te | 518079 | 66353 | 51.517 | 36 | 141 | 26690078 | 1188203 | 0.621 | 7.808 | 3452 | 5.133 | 1.193 | 5.390 | 0.794 | 0.412 | 0.091 | 828 | 5.053 | 1.031 | 1.940 | 0.895 | 0.412 | 0.089 |

## Timings (s)

- download / locate data: 8.9
- PySpark profiling: 351.7
- Spark MinHash-LSH lexical corpus graph: 211.1
- first-stage retrieval + graph construction (MIRACL): 1469.5
- first-stage retrieval + graph construction (Mr. TyDi): 564.8
- cross-encoder scoring of pools: 1516.2
- training-free baselines: 4.5
- train + evaluate graph rerankers: 4603.8
- cascades, Pareto and router: 20.3
