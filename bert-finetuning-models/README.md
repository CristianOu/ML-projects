# AML Project

## Create new conda environment:

conda env create -f `<conda-environment.yml>` -n `<env-name>`

## Run when new package is added:

conda env export -n `<env-name>` > `<conda-environment.yml>`

## Update local conda environment:

conda env update -n `<env-name>` --file `<conda-environment.yml>`

## Installation of CUDA Nvidia:

[Installatio](https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/)
