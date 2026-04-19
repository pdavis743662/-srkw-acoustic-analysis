# -srkw-acoustic-analysis
Acoustic analysis of Southern Resident Killer Whale vocalizations using PCA, Hidden Markov Models, and directed transition networks to discover sequential structure in orca communication.

## SRKW Acoustic Analysis

Computational analysis of Southern Resident Killer Whale (Orcinus orca) vocalizations from San Juan Island, WA. This project extracts acoustic features from hydrophone recordings, discovers call type categories using unsupervised learning, and models the sequential structure of orca call sequences as a directed transition network.
Overview

Orcas produce complex vocalizations including pulsed calls, whistles, and echolocation clicks. This project asks: is the ordering of these calls random, or does it follow a structured pattern — something resembling a grammar?

The pipeline works in two phases:
Phase 1 (Notebook 1): Extract ~80 acoustic features (MFCCs, spectral descriptors, chroma) from 9,600 three-second SRKW clips. Reduce dimensionality with PCA. Cluster with K-Means to discover acoustic groupings.
Phase 2 (Notebook 2): Apply the trained feature pipeline to continuous long-duration recordings from the Orcasound Pod.Cast archive. Fit a Hidden Markov Model to the ordered call sequences. Extract the transition probability matrix and build a directed network. Validate with chi-squared tests, entropy analysis, and permutation testing.
Data Sources

Zenodo (Phase 1): 9,600 three-second clips from San Juan Island, 64 kHz. DOI: 10.5281/zenodo.15390884
Orcasound Pod.Cast (Phase 2): Continuous hydrophone recordings with timestamped call annotations from the Orcasound Lab, San Juan Island. Pod.Cast data archive

## Methods

Feature extraction: librosa (MFCCs, delta MFCCs, spectral centroid/bandwidth/rolloff/contrast/flatness, ZCR, RMS, chroma)
Dimensionality reduction: PCA
Clustering: K-Means with silhouette optimization
Sequence modeling: Hidden Markov Model (hmmlearn)
Network analysis: directed transition graph (NetworkX, Plotly)
Statistical validation: chi-squared test, Shannon entropy, permutation testing, mixing time analysis

Repository Structure
srkw-acoustic-analysis/
* orca_PCA_pipeline.ipynb      # Phase 1: feature extraction, PCA, clustering
* orca_HMM_pipeline.ipynb      # Phase 2: HMM, transition network, statistics
*  scaler.pkl                   # Trained StandardScaler
* pca_2d.pkl                   # Trained PCA
*  kmeans.pkl                   # Trained K-Means
*  hmm_model.pkl                # Fitted HMM
* kmeans_network.html          # Interactive K-Means network (Plotly)
*  hmm_network.html             # Interactive HMM network (Plotly)
* README.md

#Key Findings
To be updated with final results.
Requirements
* librosa
* soundfile
* numpy
* pandas
* matplotlib
* seaborn
* scikit-learn
* hmmlearn
* networkx
* plotly
* scipy
* joblib


#Citation

If referencing the acoustic data:

Frazao, F. (2025). Audio clips of Orca (Orcinus orca) and non-orca sounds for the exploration of multiple acoustic representations. Zenodo. https://doi.org/10.5281/zenodo.15390884


Watkins Marine Mammal Sound Database, Woods Hole Oceanographic Institution and the New Bedford Whaling Museum.


Orcasound Pod.Cast data archive. https://github.com/orcasound/orcadata/wiki/Pod.Cast-data-archive

## License
MIT
