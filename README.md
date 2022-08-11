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
module load ml medsci/2022.4 anaconda3/2021.05-gcc-11.2.0-esel
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

If you have yaml file, you should create a conda environment first. And then,
```
export CONDA_ENVS_DIRS=/path/to/tool/python_3.10
export CONDA_PKGS_DIRS=/path/to/tool/python_3.10
source activate python_3.10
conda env update --file environment.yml
```

where yaml file looks like this:
```
name: epi2melabs-wf-clone-validation
channels:
    - epi2melabs
    - bioconda
    - conda-forge
    - defaults
dependencies:
    - python==3.8.*
    - aplanat==0.5.7
    - seqkit
    - scikit-learn
    - trycycler
    - porechop
    - pysam
    - minimap2
    - samtools
    - bedtools
    - mappy
    - canu
    - medaka
    - fastcat==0.3.6
    - last
    - rasusa
    - pyspoa
    - epi2melabs
    - plannotate==1.2.0
```

If you like to remove a conda environment
```
conda env remove -n python_3.10
```


# How to install packages into your own conda environment

install custom packages
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
