# TAG-Rank: Typed Article Graphs for Reranking in Low-Resource Multilingual Passage Retrieval

DA 331 (Big Data) course project, IIT Guwahati.

| Name | Roll No. |
|---|---|
| Aditya Garg | 240150001 |
| Rachit Gupta | 240150027 |
| Nilay Mittal | 240150022 |

TAG-Rank reranks the top ~110 candidates from a BM25 + mE5 hybrid retriever with a 2-layer graph attention network
over a typed passage graph (dense, lexical, same-article and adjacent-passage edges) plus whole-article evidence.
TAG-Rank+CE additionally takes scores from a cross-encoder (`BAAI/bge-reranker-v2-m3`) for a small budget of passages
as input features. Corpus profiling and corpus-wide MinHash-LSH similarity search run in PySpark.

Languages: Swahili, Bengali, Telugu (training and evaluation) and Yorùbá (zero-shot) on MIRACL dev;
Swahili and Bengali on the Mr. TyDi test set.

## Repository contents

| File | What it is |
|---|---|
| `bigdata-project.ipynb` | The complete pipeline (data download, Spark jobs, retrieval, training, evaluation, plots, findings), with all outputs from the submitted full run (2×T4, 146 min). |
| `results/` | Outputs of the full run: metric tables (CSV), `results.json`, `findings.md`, `summary.md`, plots, run log |
| `README.md` | This file: how to run it |

## Requirements

Nothing needs to be uploaded. The notebook downloads everything from the Hugging Face Hub on first run:

| Resource | Hugging Face id |
|---|---|
| MIRACL topics and qrels | `miracl/miracl` (dataset) |
| MIRACL corpora (sw, bn, te, yo) | `miracl/miracl-corpus` (dataset) |
| Mr. TyDi test topics (sw, bn) | `castorini/mr-tydi` (dataset) |
| Mr. TyDi corpora (sw, bn) | `castorini/mr-tydi-corpus` (dataset) |
| Dense encoder | `intfloat/multilingual-e5-base` |
| Cross-encoder | `BAAI/bge-reranker-v2-m3` |

Python packages missing from the Kaggle image (PySpark and a few small ones) are installed by the setup cell.

## How to run on Kaggle (recommended)

1. Go to kaggle.com → **Create → New Notebook → File → Import Notebook** and upload `bigdata-project.ipynb`.
2. In the right-hand panel (**Session options**):
   - **Accelerator:** GPU T4 ×2
   - **Internet:** On (requires a phone-verified Kaggle account)
3. Recommended: **Add-ons → Secrets → Add secret** named `HF_TOKEN` holding a Hugging Face read token, and tick it for
   this notebook. It avoids download rate limits; the notebook still runs without it.
4. Choose the mode in the **Configuration** cell:
   - `RUN_MODE = "quick"`: about 20–30 minutes. Swahili + Yorùbá only, subsampled, one seed. Use it to check that the
     environment works; the last printed line should be `DONE`.
   - `RUN_MODE = "full"` (default): the full experiment reported in the report, about 2.5 hours on 2×T4.
5. **Save Version → Save & Run All (Commit)**. When the version finishes, its **Output** tab contains `results.zip`
   and the notebook with all outputs.

## How to run elsewhere

Any Linux machine with a CUDA GPU (≥16 GB in total), Java 8+ (for Spark), Python 3.10+, and about 40 GB of free disk:

```bash
pip install jupyter pyspark torch transformers sentence-transformers huggingface_hub scipy scikit-learn pandas matplotlib
export HF_TOKEN=hf_...          # optional
export GRR_MODE=quick           # or full
export GRR_WORK=./grr_work      # output directory (default ./grr_work outside Kaggle)
jupyter nbconvert --to notebook --execute --ExecutePreprocessor.timeout=-1 bigdata-project.ipynb
```

## Outputs

Everything is written to `<work_dir>/results/` and zipped as `results.zip`:

| File | Contents |
|---|---|
| `table_ndcg_at_10.csv` | nDCG@10 for every method × language (main metric) |
| `table_recall_at_20.csv`, `table_recall_at_100.csv`, `table_mrr_at_100.csv` | Secondary metrics |
| `key_comparisons.csv` | Paired comparisons with Wilcoxon p-values and Holm correction |
| `cost_quality_pareto.csv` | Quality vs. number of cross-encoder calls |
| `homophily.csv` | Relevance homophily per edge type and language |
| `gar_recall_study.csv` | Budget-matched recall study of graph-based candidate expansion |
| `spark_profile.csv` | PySpark corpus profile (lengths, vocabulary, passages per article) |
| `per_query_metrics.csv.gz` | Per-query scores for every method (used for significance tests) |
| `findings.md`, `summary.md` | Auto-generated findings per research question, using this run's numbers |
| `plots/` | All figures |
| `run_log.txt` | Full log with timings |

## Reproducibility

- Fixed seeds: TAG-Rank is trained with seeds 13, 42, 2026, 7 and 99, and the five models are ensembled; edge-type
  ablations use seeds 13, 42 and 2026.
- Hyperparameters are all in the `CFG` object in the Configuration cell and are listed in the appendix of the report.
- Two independent full runs gave the same headline numbers (no-graph reranker 78.0, TAG-Rank+CE 85.7 nDCG@10).
  Small differences (≤0.1) can come from non-deterministic GPU kernels.

## Troubleshooting

| Symptom | Fix |
|---|---|
| Out of time or GPU quota | In the Configuration cell, set `seeds = [13, 42, 2026]` |
| CUDA out of memory in the cross-encoder step | Set `ce_batch = 16` |
| Hugging Face 429 / download errors | Add the `HF_TOKEN` secret (step 3) and rerun |
| A `WARNING:` line in the log | The run continues; check `run_log.txt` for which step it came from |
