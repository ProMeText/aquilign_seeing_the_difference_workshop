# AQUILIGN -- Mutilingual aligner and collator -- "Seeing the difference" workshop; Leiden, april 14-17, 2025.


## Use
The notebooks in this repository cannot be used with binder due to the high memory requirements of the language templates. 
We recommend that you run them locally, using jupyter lab for example.

## Prerequisites

- At least 8 GB of memory
- Around 30 GB of space available for full training
 of segmentation models (step can be skipped)



### Closing the repository and creating a virtual environment

A virtual environment allows you to isolate the installation of a project's libraries to avoid version conflicts. Once placed in the directory of your choice:

```
git clone https://github.com/ProMeText/atelier_biblissima_aquilign
cd atelier_biblissima_aquilign
```

Then simply install venv if you haven't already done so `pip install --user virtualenv`. **The code has been verified on python version 3.10: please use this python version.**

```
python3.10 -m venv seeing_the_difference_environment
source seeing_the_difference_environment/bin/activate
pip3 install -r requirements_cpu.txt
```

### Installing ipykernel and linking the virtual environment


Here we use Nikolai Janakiev's excellent manual to link our notebooks with the virtual env: 
: [https://janakiev.com/blog/jupyter-virtual-envs/](https://janakiev.com/blog/jupyter-virtual-envs/).

```
pip3 install ipykernel 
python -m ipykernel install --user --name=seeing_the_difference_environment 
```

The terminal should return: `Installed kernelspec myenv in /home/user/.local/share/jupyter/kernels/myenv`. You can display the `kernel.json` file in the directory indicated by the tool to check that the kernel will be able to use the virtual environment created:

```json
{
 "argv": [
  "path_to_the_python_virtual_environment",
  "-m",
  "ipykernel_launcher",
  "-f",
  "{connection_file}"
 ],
 "display_name": "venv",
 "language": "python"
}
```

That's it! Now just open jupyterlab: `jupyter lab` and the notebooks in the order of the session.

