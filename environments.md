## Create new customized python environments

Required libraries for working with DLTK: MySQL-python, PIL,
### 1. Create an environment with specific python version
```
conda create -n <name of venv> python=x.x
```

### 2. Install MySQL
```
pip install MySQL-python
```

### 3. Install PIL
```
pip install Pillow
```

### 4. Install Jupyter related packages
```
conda install notebook ipykernel
```

### 5. View installed packages in an environment
```
conda list -n <venv-name>
```

### 6. View installed packages in the default conda environment
```
conda list
```
