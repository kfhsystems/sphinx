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
### Lets create the HTML documents
```bash
# To make sure that we are in the root folder of our project
pwd
> /Users/khasanov/repo/sphinx
# Generate the HTML files
make html
> ...
> The HTML pages are in build/html.
```
### Create a RST page
Go to the *source" and create a RST file ( "page1.rst")
```
This is out first Sphinx Page
=============================

Lets create a sphinx document
```
Now we have let our "index.rst" know about it
From this:
```
kfh_sphinx documentation
=========================

.. toctree::
   :maxdepth: 2
   :caption: Contents:
```
To this:
```

kfh_sphinx documentation
=========================

.. toctree::
   :maxdepth: 2
   :caption: Part One

   page1
```
After the modification , run the build command :
```bash
make html
```
## Changing the Themes
```note
The default theme is **Alabaster** and we are going to change it to **sphinx_rtd_theme**
```
We need to install the *sphinx_rtd_theme* module first:
```bash
pip install sphinx_rtd_theme
```
Now we can modify the *source/conf.py* file
```python
extensions = ['sphinx_rtd_theme']
import sphinx_rtd_theme
#html_theme = 'alabaster'
html_theme = 'sphinx_rtd_theme'
```
Rebuild the HTML pages
```bash
make html
```
## Changing the main page layout using the CSS
Create a custom CSS file under the **build/html/_static** folder.
Lets give a name *custom_kfh.css*
```css
.wy-nav-content {
    max-width: 1400px !important;
}
```
Also add these lines to the **source/conf.py** file
```python
html_static_path = ['_static']
def setup(app):
    app.add_css_file("css/custom_kfh.css")
```

## Recommended HTML Theme Options
Edit the *source/conf.py* and add the following options:
```python
html_theme_options = {
    'logo_only': True,
    'collapse_navigation': True,
    'sticky_navigation': True,
    'includehidden': True,
    'navigation_depth': 4,
    'titles_only': False
}
```