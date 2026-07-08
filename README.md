# Reproducibility materials for “Quantum-inspired spectral engineering of open complex networks”

This repository contains the source notebooks and network files used to reproduce the numerical results and figures from the manuscript:

**Quantum-inspired spectral engineering of open complex networks**  
Submitted to *Physica A*.

Random seeds were not fixed during the original graph-generation runs. Therefore, reproducibility of the network realizations is ensured by the deposited edge-list files. The model calculations and figure-generation procedures are collected in `Model.ipynb`.

## Files

- `Model.ipynb` — main Python notebook containing the Floquet-renormalized network calculations and the construction of the numerical figures from the manuscript, including hub suppression, multi-hub suppression, hub reactivation, betweenness centrality, and clustering.

- `Graphs_parameters.ipynb` — notebook for checking the graph parameters used in Fig. 1, including average degree, degree range, degree distribution, and the degree-heterogeneity parameter.

- `R_Graphs.ipynb` — R notebook documenting the generation procedure for the scale-free and Erdős--Rényi network realizations.

- `N200_y2.4_small_hubs.edgelist` — exact scale-free network realization used in the manuscript. The degree sequence was generated with input exponent `gamma_in = 2.4` and lower cutoff `k_min = 3`.

- `N200_Erdos_Renyi_Graph_0.04.edgelist` — exact Erdős--Rényi network realization used in the manuscript, generated with `N = 200` and connection probability `p = 0.04`.

- `README.md` — description of the repository contents and reproduction workflow.

## Reproducibility

The deposited edge-list files are the exact network realizations used in the manuscript. Since random seeds were not fixed during graph generation, these files should be used directly rather than regenerating the graphs.

`Model.ipynb` reads the deposited edge lists and constructs the Floquet-renormalized effective adjacency matrix

`A_eff[i,j] = A[i,j] * J0(B_i - B_j)`.

The notebook then computes the spectra, inverse participation ratios, betweenness centrality, and clustering visualizations used in the manuscript.

## Figure map

- Fig. 1 — network topologies, degree distributions, and graph parameters.  
  Use `Graphs_parameters.ipynb` and `R_Graphs.ipynb`.

- Fig. 2 — single-hub suppression.  
  Built in `Model.ipynb`.

- Fig. 3 — multi-hub suppression of the highest-degree hubs.  
  Built in `Model.ipynb`.

- Fig. 4 — betweenness centrality before and after suppression of ten hubs.  
  Built in `Model.ipynb`.

- Fig. 5 — spectral comparison after ten-hub suppression and selective hub reactivation.  
  Built in `Model.ipynb`.

- Fig. 6 — clustering protocol based on Floquet-renormalized edge weights.  
  Built in `Model.ipynb`.

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

The Python notebooks use standard scientific Python libraries:

- `numpy`
- `scipy`
- `networkx`
- `matplotlib`
- `mpmath`

The R notebook uses:

- `igraph`

## Notes

The scale-free exponent reported in the manuscript caption, approximately `2.46`, was obtained a posteriori by fitting the degree distribution of the finite generated network. It is not the input generation exponent. The input exponent used in the generation procedure was `gamma_in = 2.4`.

All node labels are used consistently within each notebook and the corresponding edge-list files.
