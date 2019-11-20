## Sharing conda environments

1. create a conda environment.

`conda create -n name jupyter jupyterlab matplotlib pandas scikit-learn rdkit::rdkit`

2. export the contents of the environment.

`conda env export --from-history > rdkit_demo_env.yml`

3. create a new enviroment from the `yml` file.

`conda env create -f rdkit_demo_env.yml `
