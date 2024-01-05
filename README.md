# Categorization of phenotype trajectories utilizing transformers on clinical time-series

This implementation is based on the STraTS(see below) code with some modifications to the architecture to fit vital data with an uneven sampling rate.
The STraTS model is used as an encoder that outputs a fixed-length vector so that each time series input can be represented with a single point and clustered to find structures in the data.

The code is written for the data of 16 months of vital sign recordings obtained from the Nordland Hospital Trust (NHT). This data is not openly available, physionet2012 (open access) can be used with some modifications.

How to use:
Run the scripts in the following order from the <STraTS SPKI GIT> folder.
* dataset_scrubb_analysis.ipynb
    * Scrubbing the data, removing patients with short/long stays, duplicates, etc.
* preprocess_bodo.ipynb (preprocess_physionet2012.py)
    * Rewrite the data to triplet form
* STraTS_encoder.ipynb
    * Train the STraTS encoder
* Manually move the weights from the <STraTS SPKI GIT> to the <weights> folder
    * This is to avoide to overwright previously saved weights.
* clustering_STraTS_encoder.ipynb
    * Cluster the output from the STraTS encoder

Make sure that the name-convention/config-values is followed between the scripts.

Good luck! (You might need it.)


# STraTS: Self-Supervised Transformer for Multivariate Clinical Time-Series with Missing Values

The is the official keras implementation of STraTS https://github.com/sindhura97/STraTS (https://arxiv.org/abs/2107.14293)
