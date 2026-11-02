# Eophis

![Python Version](https://img.shields.io/badge/Python-3.10%20%2F%203.11%20%2F%203.12-blue)
[![C, Fortran, and MPI Required](https://img.shields.io/badge/Compilers-C%20%2F%20Fortran%20%2F%20MPI-important)](https://www.open-mpi.org/)
[![netcdf Required](https://img.shields.io/badge/Build-netCDF%E2%80%93C%20%2F%20netCDF%E2%80%93F-important)](https://www.unidata.ucar.edu/software/netcdf/)
[![Documentation Status](https://readthedocs.org/projects/eophis/badge/?version=latest)](https://eophis.readthedocs.io/en/latest/?badge=latest)


**_Eophis_** is a collection of tools to ease the deployment of Python scripts (as pre-trained Machine Learning components) within Fortran ESM through OASIS3-MCT.
> _Also it is the currently oldest known snake ancestra (2023)_

**Strategy**

[OASIS3-MCT](https://oasis.cerfacs.fr/en/) is a middleware framework widely used in the climate modelling community to performs field exchanges between coupled components. It provides Fortran, C and Python APIs, which enable coupling between non-homogeneously written codes.
Basically, Eophis allows to: 
   - (i) wrap an OASIS3-MCT interface to exchange data with a coupled ESM
   - (ii) wrap inference models into a simple in/out interface
   - (iii) emulate time evolution to synchronize connexions between scripts.

**Current development objectives**
   - tools to write coupling info in geoscientific codes namelists
   - tools for time diagnostic
   - enhance packaging

## Quickstart

Follow this [tutorial](https://eophis.readthedocs.io/en/latest/tutorial.html) to get started.

## Usage, installation and test cases

Check out corresponding sections in [Eophis documentation](https://eophis.readthedocs.io/en/latest/index.html) for further informations.


## *Real-World* cases

Those projects use Eophis:
- [Morays](https://github.com/morays-community) : Python scripts deployed in ocean models
- [LMDZ-GCM96x95-Wind_Bias_Corr](https://github.com/TRACCS-COMPACT/LMDZ-GCM96x95-Wind_Bias_Corr) : Data-driven wind bias correction deployed in the atmospheric general circulation model [LMDZ](https://lmdz.lmd.jussieu.fr/)

## How to cite

[![DOI](https://zenodo.org/badge/713480336.svg)](https://doi.org/10.5281/zenodo.13852038) : Repository archive

[GMD publication](https://doi.org/10.5194/gmd-19-10345-2026)

Please use above DOIs or **Cite this repository** button in the **About** section of the repository



## Contributing

See [CONTRIBUTING.md](https://github.com/meom-group/eophis/blob/main/CONTRIBUTING.md) to get started.

## License

Copyright &copy; IGE-MEOM

Eophis is distributed under the [MIT License](https://github.com/meom-group/eophis/blob/main/LICENSE).
