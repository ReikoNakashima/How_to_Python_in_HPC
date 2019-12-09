# How to set up conda and python environment

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
