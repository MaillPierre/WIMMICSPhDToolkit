# Using Virtual Environments in Jupyter Notebooks

A virtual environment is an isolated working copy of Python. This means that each environment can have its own dependencies or even its own Python versions. This is useful if you need different versions of Python or packages for different projects. This also keeps things tidy when testing packages and making sure your main Python installation stays healthy.

First of all, **you should not install packages in the default environment**, only in a dedicated virtual environment.
This keeps things tidy when testing packages and making sure your main Python installation stays healthy.

Second, **in Jupyter Notebooks, Python environments are managed using kernels**. You have to manually add a kernel with a virtual environment. Then the Notebook will work in that environment, meaning that if you install packages from the Notebook this will modify the Python environment.
Most importantly, **never use ```!pip install``` in a Notebook**. Explanations below...

Below I use [Mamba](https://github.com/conda-forge/miniforge#mambaforge) to manage the packages and environements.
It is an equivalent of [conda](https://conda.io/projects/conda/en/latest/user-guide/getting-started.html), it has exactly the same command line options as conda, but it is [much faster than conda](https://pythonspeed.com/articles/faster-conda-install/).


## Install Python, Jupyter Notebook or Jupyterlab

The example below will use Jupyerlab.

After you have installed [Mamba](https://github.com/conda-forge/miniforge#mambaforge), in a Mamba shell:

```python
mamba update -y mamba
mamba update -y --all
mamba install -y -c conda-forge jupyterlab
```

## Manage Python virtual environements

Below I'll create an environment to work with Langchain.

First create environment _mylangchain_:
```python
mamba create --name mylangchain --clone <path of the default environement>
```

Example on Windows 10:
```python
mamba create --name mylangchain --clone C:\Users\user\mambaforge
```


Activate that environment and install the packages you need:
```python
mamba activate mylangchain
mamba install langchain -c conda-forge
```

You can check the list of existing environments with:
```python
mamba info --envs           (alt.: mamba env list)
```

To return to the default environment:
```python
mamba deactivate
```

Later on, if you want to remove an environment:
```python
mamba env remove --name mylangchain -y
```


## Create a Jupyter kernel for a Python virtual environement

Make the environment available in Jupyter as a new kernel:
```python
mamba activate mylangchain        # do it before the ipykernel
python -m ipykernel install --user --name=mylangchain --display-name "Python (langchain)"
```

To list the available kernels:
```python
jupyter kernelspec list
```

Later on, if you want to remove a kernel:
```python
jupyter kernelspec uninstall -y mylangchain
```


## Install packages in a Notebook (the right way)

Create a Notebook and select the kernel you created with ipykernel. In the above, the kernel name is "Python (langchain)", which runs in the "mylangchain" environment.

Then, **do not use `!pip install` in a Notebook.**
It will install the package in the default environment, not in the active environment that corresponds to the selected kernel.

Instead, to install a package in the virtual environment where the current Notebook kernel is running, you should do this:

#### Using mamba:
```python
import sys
!mamba install --yes --prefix {sys.prefix} <package_name>
```

You can check that the package has been installed in the right environement this way:
```python
!mamba list --prefix {sys.prefix} "<package_name>"
```

Example:
```python
import sys
!mamba install -c conda-forge -y --prefix {sys.prefix} langchain openai
!mamba list --prefix {sys.prefix} "langchain|openai"

# packages in environment at C:\Users\user\mambaforge\envs\mylangchain:
#
# Name                    Version                   Build  Channel
langchain                 0.0.239            pyhd8ed1ab_0    conda-forge
openai                    0.27.8             pyhd8ed1ab_0    conda-forge

```

#### Using pip
```python
import sys
!{sys.executable} -m pip install <package_name>
```
