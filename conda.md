# Tips for using conda

Use `conda env list` to see available environments.
Use `conda list` to see installed packages in your environment.

To create an environment that you can use in a notebook:
```
conda create -n jhub_myenv
source activate jhub_myenv
conda install jupyter nb_conda ipykernel any_module_you_need
source deactivate
```
This will complete the installation of a new conda environment. 
The last step is to create a Jupyter kernel based on the conda environment. To do that

```
source activate jhub_myenv
python -m ipykernel install --user --name jhub_myenv
source deactivate
```
After these steps, you will see jhub_myenv kernel when you click new on Jupyter Hub. 
When you open a new notebook using jhub_myenv kernel, you can use the custom environment 
you created with the modules you want. 
Alternatively, for an open notebook you can change the kernel using the 'Kernel' tab at the top. 
You can use environment.yml files to simplify the process of installing packages from different channels. 
Don't forget to include jupyter nb_conda ipykernel modules in your list of modules to be installed.

Note that `environment.yml` does not work with `conda install --file <filename>`.
You need to create the installation file with `conda list --export`.
# sample environment.yml
```
name: chemdash

channels:
  - openbabel
  - mcs07
  - rpmuller
  - pyscf
  - psi4

dependencies:
  - python=2.7
  - pip
  - jupyter
  - nb_conda
  - ipykernel 
  - psutil
  - numpy
  - matplotlib
  - openbabel
  - cirpy
  - pyquante2
  - pyscf
  - psi4
  - pip:
    - py3Dmol
    - ase
    - cclib
    - basis_set_exchange
    - "--editable=git+https://github.com/jaimergp/ebsel.git#egg=ebsel"
```
# Links
* https://conda.io/docs/user-guide/tasks/manage-environments.html
* http://jakevdp.github.io/blog/2017/12/05/installing-python-packages-from-jupyter/
* https://jupyter4edu.github.io/jupyter-edu-book/
