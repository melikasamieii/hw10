# Non-Spherical Clustering: DBSCAN vs Hierarchical (Moons + Noise)

## Overview
This project compares DBSCAN and Hierarchical (Agglomerative) clustering methods on a non-spherical dataset.
A synthetic two-moons dataset is generated and additional noise points are injected to evaluate:

- How well each method handles non-convex cluster shapes
- How each method behaves in the presence of noise and outliers

The goal is to highlight the strengths and limitations of density-based and hierarchical clustering approaches in noisy, non-linear settings.

## Files in Repository
- `moons_dbscan_hierarchical.ipynb`

## Features
- Generate a two-moons dataset using `make_moons`
- Inject uniformly distributed noise points
- Visualize:
  - Raw dataset
  - Standardized dataset
- Apply `StandardScaler` to support distance-based algorithms
- Build a k-distance plot (k = 5) to guide DBSCAN `eps` selection
- Run DBSCAN with multiple parameter settings:
  - Report number of detected clusters
  - Report number of noise points (`label = -1`)
  - Visualize clusters and detected noise
- Perform hierarchical clustering analysis:
  - Build dendrograms using single and complete linkage (truncated)
  - Demonstrate different cutting strategies (distance-based and max-cluster-based)
  - Apply `AgglomerativeClustering` with `n_clusters = 2`
  - Visualize clustering results for each linkage method

## Requirements
- Python 3.9+
- numpy
- matplotlib
- scipy
- scikit-learn
- jupyter (or VS Code Jupyter extension)

## Setup (Windows 11)
```bash
pip install numpy matplotlib scipy scikit-learn jupyter
How to Run
Open moons_dbscan_hierarchical.ipynb in Jupyter Notebook or VS Code.
Run all cells from top to bottom.
Inspect:
The k-distance plot to understand DBSCAN parameter behavior
DBSCAN results for different (eps, min_samples) settings
Dendrograms and agglomerative clustering outputs (single vs complete linkage)
Notes / Limitations
Feature scaling is essential; running DBSCAN or other distance-based methods on unscaled data can produce misleading results.
Single-linkage hierarchical clustering may suffer from the chaining effect, where clusters are merged through narrow bridges of points.
DBSCAN explicitly labels noise points, while hierarchical clustering assigns every point to a cluster unless interpreted manually.
