# Guidance to use virtual environment of Python

Because programs may rely on diffirent dependencies or packages, or even different version of python,to avoid unistallation of  current working environment, setting different environments is better way to manage packages and different of python.

### 0. Find your current working environments:
```sh
$ conda info --envs
$ root                  *  D:\Anaconda3
```



### 1.	Save your current working environment

Change the diretory the you want to place the image of working environment by Anacoda Promot Command or gir bash:

```sh
$ cd your directory
$ conda-env  export -n base > your_env_name.yml
```
Your default environment name is base

After running above command there should be yml configuration file in your current directory which contain information of your conda environment

### 2. To create new environment using yml configuration file run
```sh
$ conda-env create -n new_env -f=path\base.yml 
```

### 3.	To create a virtual environment with specific python version in Anacondae:
```sh
$ conda create -n yourenvname python=x.x anaconda 
```

### 4.	Add env environment into your juypter notebook:
```sh
$ conda activate ENVNAME
$ pip install ipykernel
$ python -m ipykernel install --user --name ENVNAME --display-name "Python (whatever you want to call it)"
```

After addition, you can create a juyter notebook assigned to different to environment 

### 5.	Delete the virtual environment
- Delete it from anacoda
```sh
$ conda-env remove -n ENV_NAME
```

- Delte it from juypter notebook
```sh
$ jupyter kernelspec list
Available kernels:
  myenv1     /home/user/.local/share/jupyter/kernels/myenv1
  myenv3     /home/user/.local/share/jupyter/kernels/myenv3
  python2    /home/user/myenv3/share/jupyter/kernels/python2
  python3    /usr/local/share/jupyter/kernels/python3
$ ipython kernelspec uninstall myenv3
```

### 6. Activate and deactivate
```sh
$ conda activate my_env
```
After activation, the python script will run on the assigned virtual environment
