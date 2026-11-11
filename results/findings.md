# Findings (generated from this run)

nDCG@10 ×100 on MIRACL dev, averaged over sw, bn, te unless stated. p-values: paired Wilcoxon over queries.

## RQ1: First-stage retrieval
- Dense mE5 74.9 vs BM25 45.8; equal-weight RRF 64.2 (worse than dense alone); tuned convex fusion (λ = 0.1) 76.0.
- A learned reranker without a graph reaches 78.0: +2.05 (p = 6.32e-14, 450 wins / 268 losses) over tuned fusion.

## RQ2: Does the graph help, and which edges?
- Dense-similarity edges only: +0.58 (p = 5.2e-05, 382 wins / 276 losses) over the no-graph MLP.
- Typed graph vs the same features without a graph: +1.23 (p = 3.52e-11, 444 wins / 282 losses); 3 of 3 training languages significant after Holm.
- Removing dense edges: -0.80 (p = 0.000392, 361 wins / 407 losses) (3 seeds).
- Removing lexical edges: -0.15 (p = 0.0779, 325 wins / 383 losses) (3 seeds).
- Removing article/adjacent edges: -0.18 (p = 0.255, 341 wins / 357 losses) (3 seeds).

## RQ3: Article evidence and transfer to Yorùbá
- Article evidence without a graph: +0.95 (p = 0.00196, 409 wins / 341 losses).
- Passages per article: miracl:sw 2.76, miracl:yo 1.48, miracl:bn 4.66, miracl:te 7.81, mrtydi:sw 2.86, mrtydi:bn 4.77; gate threshold 2.21 → article channel off for miracl:yo.
- Yorùbá, gate on vs off (same model): +2.55 (p = 0.02, 39 wins / 23 losses). Yorùbá nDCG@10: no-graph MLP 78.9, TAG-Rank 77.6, ungated 75.1.
- Structure-aware training + gate on training languages: -0.11 (p = 0.262, 308 wins / 338 losses).
- 5-seed ensemble: +0.45 (p = 3.63e-05, 367 wins / 278 losses). Final cheap model vs no-graph MLP: +2.52 (p = 3.25e-17, 444 wins / 257 losses).

## RQ4: Making the cross-encoder cheaper
- Graph gain without CE (k = 0): +0.50 (p = 9.95e-05, 377 wins / 276 losses).
- Graph gain with CE scores for the top-5: +0.46 (p = 4.37e-08, 333 wins / 203 losses).
- Graph gain with CE scores for the top-10: +0.27 (p = 0.00087, 283 wins / 203 losses).
- Graph gain with CE scores for the top-20: +0.21 (p = 0.017, 257 wins / 219 losses).
- Graph gain with CE scores for the top-30: +0.15 (p = 0.0793, 257 wins / 239 losses).
- CE scores as graph inputs vs fusion cascade, both on top-5: +2.24 (p = 1.74e-18, 381 wins / 202 losses).
- CE scores as graph inputs vs fusion cascade, both on top-10: +1.94 (p = 5.05e-14, 335 wins / 201 losses).
- CE scores as graph inputs vs fusion cascade, both on top-20: +1.26 (p = 5.19e-08, 331 wins / 213 losses).
- CE scores as graph inputs vs fusion cascade, both on top-30: +1.19 (p = 1.09e-06, 329 wins / 227 losses).
- TAG-Rank+CE scoring 10 passages vs fusion cascade scoring 30: +0.78 (p = 0.00219, 257 wins / 188 losses).
- Router: Spearman correlation of predicted vs true CE gain on MIRACL dev = 0.28.

## Final systems vs published results (MIRACL dev nDCG@10 ×100)
| system | sw | bn | te | yo |
|---|---|---|---|---|
| mE5-large (published) | 74.9 | 75.9 | 84.6 | 78.3 |
| BGE-M3 all (published) | 79.6 | 81.5 | 88.1 | 83.5 |
| TAG-Rank, no cross-encoder (ours) | 76.7 | 77.4 | 87.0 | 78.7 |
| TAG-Rank+CE, CE on top-10 (ours) | 80.9 | 83.9 | 88.9 | 85.0 |
| TAG-Rank+CE, CE on top-30 (ours) | 82.5 | 85.3 | 89.2 | 86.7 |

## RQ5: Why the graph helps
- Homophily ratio (1 = random) per edge type: train:sw: dense 2.4, lex 2.8, article 2.5, adjacent 3.8; train:bn: dense 3.0, lex 4.2, article 2.4, adjacent 4.9; train:te: dense 1.2, lex 1.9, article 1.1, adjacent 2.8; miracl:sw: dense 3.4, lex 3.8, article 2.9, adjacent 6.3; miracl:yo: dense 3.1, lex 4.3, article 5.6, adjacent 2.3; miracl:bn: dense 3.1, lex 4.0, article 2.2, adjacent 3.7; miracl:te: dense 0.3, lex 0.4, article 0.1, adjacent 0.0; mrtydi:sw: dense 0.9, lex 0.9, article 2.1, adjacent 4.3; mrtydi:bn: dense 0.8, lex 1.7, article 1.7, adjacent 4.0
- Graph gain by number of relevant passages in the pool: 0: +0.00 (n=18), 1: +1.06 (n=1336), 2: +1.44 (n=265), 3+: +1.69 (n=221)

Runtime 146.2 min; warnings: 0.
