Gaia XP Forward Model
=====================

A data-driven forward model of Gaia XP stellar spectra, which maps from atmospheric parameters, distance and extinction to predicted XP spectra. The model is learned from a subset of XP stars with observed higher-resolution spectra (e.g., from LAMOST). After the model has been learned, it can be applied to *all* XP spectra to obtain inferred stellar parameters.

Workflow
========

1. Download all the Gaia continuous mean spectra in HDF5 format (available [here](https://sdsc-users.flatironinstitute.org/~gaia/dr3/hdf5/XpContinuousMeanSpectrum/)) to the folder `data/xp_continuous_mean_spectrum/`.
2. Create the folder `data/xp_metadata/` and run `query_xp_metadata.py`, which queries the [Gaia Archive](https://gea.esac.esa.int/archive/) for additional information about each XP source.
3. Create the folder `data/xp_tmass_match/` and run `query_2mass.py`, which queries the Gaia Archive for 2MASS photometry for each XP source.
4. Download the unWISE catalog (for example, from [here](https://portal.nersc.gov/project/cosmo/data/unwise/neo6/unwise-catalog/cat/)). Set the environment variable `UNWISE_DIR` to the directory into which you downloaded the catalog files. Create the folder `data/xp_unwise_match/` and run `match_unwise_gaia.py`.
5. ...
