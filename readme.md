# Analysis code for "Quantitative measurement of synthetic repression curves reveals design challenges for genetic circuit engineering under growth arrest"

This GitHub repository contains jupyter notebooks that perform all of the analysis and plotting involved in generating the results of the paper "Quantitative measurement of synthetic repression curves reveals design challenges for genetic circuit engineering under growth arrest" by John P Marken, Mark L Prator, Bruce A Hay, and Richard M Murray, published in May 13 2026 by ACS Synthetic Biology ( https://doi.org/10.1021/acssynbio.6c00123 ).

## Downloading the raw data

Because the raw data for this work consists of a large number of flow cytometry (.fcs) files, these are housed separtely in a Zenodo repository which can be accessed at doi: 10.5281/zenodo.18415278

The fcs data are organized into six zip files which should be downloaded and extracted into the /data/ subfolder of this repository.

In order for the scripts to work directly, the entire repository should be downloaded with its folder structure intact.

## How to run the analysis files

Because the data processing that occurs prior to analysis takes some time, the analysis pipeline takes the raw data and generates processed data as pickle objects which are then referenced by downstream notebooks that do the actual analysis and plotting.

Once the raw data files are downloaded and extracted to the correct location, users should first run the notebook 'FCS_gating.ipynb' in order to generate density-gated flow cytometry data, stored as pickle objects.

Users should then run the notebooks 'BPE_with_MCMC_Dgates.ipynb' and 'BPE_with_MCMC_FPgates.ipynb' in order to perform Bayesian Parameter Estimation via Markov Chain Monte Carlo and store the results of these runs as pickle objects.

Users can then run the analysis notebooks 'Plots_and_Analysis_Dgates.ipynb' and 'Plots_and_Analysis_FPgates.ipynb' in order to perform the actual calculations and plotting required to reproduce the results in the manuscript. Users wishing to make modifications to these notebooks can do so rapidly by working in these notebooks alone, without having to re-run the time-intensive density gating and MCMC procedures each time.

## Locations of outputs

Specific values about parameters and changes to parameter values across experimental conditions are printed directly in the relevant section of each jupyter notebook. Plots are saved to subfolder /figs/, with the direct plots of the flow cytometry data going to subfolder /figs/2Dplots/ and the plots of the BPE fits going to /figs/BPEplots/.