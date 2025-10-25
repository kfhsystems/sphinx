# The Sphinx Tutorials
> Date: Oct.25, 2025  
> Description:
---

## Setting Up the Python ENV
```bash
# Upgrade the PIP
python3 -m pip install --upgrade pip
# Setup the `venv'
python3 -m venv venv
# Activate the 'env'
source venv/bin/activate
```

## Installing the Sphinx
```bash
pip install sphinx
```

## Create the first Sphinx document
```bash
sphinx-quickstart
```
Welcome to the Sphinx 8.2.3 quickstart utility.

Please enter values for the following settings (just press Enter to
accept a default value, if one is given in brackets).

Selected root path: .

You have two options for placing the build directory for Sphinx output.
Either, you use a directory "_build" within the root path, or you separate
"source" and "build" directories within the root path.
> Separate source and build directories (y/n) [n]: y  
> > The project name will occur in several places in the
> > built documentation.
>   
> Project name: kfh_sphinx  
> Author name(s): KFH Inc.  
> Project release []: 0.1  
> Project language [en]:  
