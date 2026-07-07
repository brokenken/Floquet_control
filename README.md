# Reproducibility materials for “Quantum-inspired spectral engineering of open complex networks”

This repository contains the source notebooks and network files used to reproduce the numerical figures from the manuscript:

**Quantum-inspired spectral engineering of open complex networks**  
Submitted to *Physica A*.

Random seeds were not fixed during the original generation and optimization runs. Therefore, reproducibility is ensured by the deposited artifacts: the exact network edge lists and the notebook used to generate the figures.

## Files

- `Model.ipynb` — main Python notebook containing the model calculations and the construction of the numerical figures from the manuscript.

- `Graphs_parameters.ipynb` — notebook for checking the graph parameters used in Fig. 1, including average degree, degree range, degree distribution, and the degree-heterogeneity parameter.

- `R_Graphs.ipynb` — R notebook documenting the generation of the scale-free and Erdős--Rényi networks.

- `N200_y2.4_small_hubs.edgelist` — exact scale-free network realization used in the manuscript. The input exponent for the degree-sequence generation was `gamma_in = 2.4`.

- `N200_Erdos_Renyi_Graph_0.04.edgelist` — exact Erdős--Rényi network realization used in the manuscript, generated with `N = 200` and connection probability `p = 0.04`.

- `README.md` — description of the repository contents.

## Reproducibility

The edge-list files are the exact network realizations used in the manuscript. Since random seeds were not fixed, these files should be used directly rather than regenerating the graphs.

The main notebook `Model.ipynb` will contain the calculations needed to reproduce the numerical figures. It uses the deposited edge lists as input and constructs the corresponding effective networks, spectra, inverse participation ratios, betweenness centrality results, and clustering plots.

## Figure map

- Fig. 1 — network topologies, degree distributions, and graph parameters.
- Fig. 2 — single-hub suppression.
- Fig. 3 — multi-hub suppression.
- Fig. 4 — betweenness centrality before and after hub suppression.
- Fig. 5 — spectral comparison after hub suppression and hub reactivation.
- Fig. 6 — clustering protocol.

All model calculations and figure-generation steps are collected in `Model.ipynb`.

## Run in Google Colab

1. Open [Google Colab](https://colab.research.google.com).
2. Upload the notebooks:
   - `Model.ipynb`
   - `Graphs_parameters.ipynb`
   - `R_Graphs.ipynb`
3. Upload the edge-list files:
   - `N200_y2.4_small_hubs.edgelist`
   - `N200_Erdos_Renyi_Graph_0.04.edgelist`
4. Run the notebook cells sequentially.

## Requirements

The Python notebook uses standard scientific Python libraries such as:

- `numpy`
- `scipy`
- `networkx`
- `matplotlib`
- `mpmath`

The R notebook uses:

- `igraph`
