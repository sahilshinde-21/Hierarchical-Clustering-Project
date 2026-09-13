# Student Performance Grouping — Hierarchical Clustering

Grouping students by study habits and results, without telling the model what "good" or "bad"
performance means — and letting the data figure that out on its own.

## What this is

A small, beginner-friendly clustering project that takes just two numbers per student — hours studied
and score obtained — and uses **hierarchical clustering** to find natural performance groups. No labels,
no assumptions going in. The model builds a dendrogram (a merge tree), and the number of groups is chosen
using the **silhouette score** rather than a guess.

## Dataset

- **File:** `score_updated.csv`
- **Rows:** 96 students
- **Columns:**
  - `Hours` — number of hours studied (range: ~1 to 9.8)
  - `Scores` — marks obtained, out of 100 (range: 12 to 99)
- No missing values, no cleaning required — kept intentionally simple so the focus stays on
  understanding the clustering itself.

## Workflow

1. Load and inspect the data
2. Visualize Hours vs Scores
3. Scale the features (so Scores' larger numbers don't dominate distance calculations)
4. Build a dendrogram using Ward linkage
5. Use silhouette score to find the best number of clusters (K)
6. Cluster students using Agglomerative Clustering
7. Label clusters in plain terms — Low / Average / High Performers
8. Visualize the final grouped result

## Results

Using the silhouette score, K = 3 came out as the best split, roughly matching:

| Group | Avg. Hours Studied | Avg. Score |
|---|---|---|
| Low Performers | ~2.3 | ~24 |
| Average Performers | ~5.0 | ~52 |
| High Performers | ~8.1 | ~83 |

## Tools used

Python, pandas, NumPy, Matplotlib, scikit-learn, SciPy

## How to run

1. Clone this repo
2. Make sure `score_updated.csv` is in the same folder as the notebook
3. Open `Hierarchical_Clustering_Project.ipynb` in Jupyter and run all cells top to bottom

## Files

- `Hierarchical_Clustering_Project.ipynb` — the full notebook
- `score_updated.csv` — the dataset
