This note assume you already have anaconda installed on your machine.

## Install jupyter lab (via anaconda prompt)
```
conda install -c conda-forge jupyterlab
```

## Setup start location
Change the default location of jupyter lab, we need to first generate jupyter lab configuration file.
```
Jupyter notebook --generate-config
```
This will create a configuration file at  ```c:/users/username/.jupyter/jupyter_notebook_config.py```.


Open the configuration file, find **#c.NotebookApp.notebook_dir = ”.**. Change the location (e.g., ```'G:\\My Drive'```).

## Open the jupyter lab
```
jupyter lab
```
