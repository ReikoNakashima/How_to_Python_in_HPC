# How to set up virtual env
Load appropriate module. For example, on Delta, I loaded
```
module load medsci/2020.3 conda/nanopore/1.0
```
Check the versions.
```
$ which python
/gpfs/apps/medsci/stacks/3/condaenv/nanopore/1.0/conda/bin/python

$ python --version
Python 3.6.10 :: Anaconda, Inc.
```
Create an environment, named .venv, in the current directory.
```
python -m venv .venv
```

Activate it.
```
source .venv/bin/activate
```

Install a package.
```
python -m pip install --ignore-installed pandas
```


# How to activate your own conda environment (Durham HPC)

```
module load eb/2019
module load Anaconda2/5.3.0 
```
check environment that exists
```
conda info --envs
```
activate my environment
```
source activate /lustre/workspace/home/nakasr04/condaenvs
```
install packages
```
export CONDA_ENVS_DIRS=/lustre/workspace/home/nakasr04/condaenvs
export CONDA_PKGS_DIRS=/lustre/workspace/home/nakasr04/condaenvs
conda install <my_package>
```
check python version
```
which python
```
deactivate my environment
```
conda deactivate
```
