# `fsspec-reference-maker` GOES-16 tutorial

This example notebook accompanies this post I made on medium (link not yet active), explaining how to use [fsspec-reference-maker](https://github.com/intake/fsspec-reference-maker) to speed up GOES-16/17 NetCDF4 access on AWS S3.

Click on the Binder link below to run this notebook in a cloud environment. The notebook also works if executed locally. 

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/lsterzinger/fsspec-reference-maker-tutorial/multizarr)

# Environment setup
## The default Pangeo environment needs a couple tweaks to run this code properly

First, if you're not running this on Pangeo or Binder, you'll want to set up the environment. I've provided the environment.yml file that includes all packages needed to run the notebook.
```
conda env create -f environment.yml
```

Then, activate the new `fsspec-tutorial` environment (if you want to change the name, you will have to change the "name: fsspec-tutorial" line at the very top of environment.yml before creating the environment)
```
conda activate fsspec-tutorial
```

## Manual install without environment.yml
Download and install `fsspec-reference-maker` from github. You will also need to make sure you have `numcodecs>=0.8.0`

```
pip install git+https://github.com/intake/fsspec-reference-maker
```