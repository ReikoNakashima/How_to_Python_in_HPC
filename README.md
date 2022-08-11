# How to set up virtual env
Load appropriate module. For example, on Delta, I loaded
```
module load medsci/2020.3 conda/nanopore/2.0
```
Check the versions.
```
$ which python
/gpfs/apps/medsci/stacks/3/condaenv/nanopore/1.0/conda/bin/python

$ python --version
Python 3.6.13 :: Anaconda, Inc.
```
Create an environment, named .venv, in the current directory.
```
python -m venv .venv
```

Activate it. For example,
```
source /gpfs/workspace/projects/pharmsciARD_ngs/tools/.venv/bin/activate
```

Install a package.
```
python -m pip install --ignore-installed pandas
```

Then, also install Jupyter kernel
```
pip install ipykernel
python -m ipykernel install --user --name=.venv
```
Now, you can choose your kernel, .venv, as a Jupyter kernel.


# How to set up conda environment

```
module load anaconda3/2019.10-gcc-9.2.0-qzda
export CONDA_ENVS_DIRS=/path/to/tool
conda create -n python_3.10 python=3.10
```
You can check
```
conda env list
```
You should see the environment /path/to/tool/python_3.10. Then,
```
source activate python_3.10
```

Then, also install Jupyter kernel
```
pip install ipykernel
python -m ipykernel install --user --name=python_3.10
```


# How to install packages into your own conda environment

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


# How to re-install a package
```
$ pip uninstall plotly
$ conda uninstall plotly
$ conda install -c plotly plotly
```
