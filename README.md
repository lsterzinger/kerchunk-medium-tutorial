# `kerchunk` GOES-16 tutorial

This example notebook accompanies this post I made on medium (link not yet active), explaining how to use [kerchunk](https://github.com/fsspec/kerchunk) to speed up GOES-16/17 NetCDF4 access on AWS S3.

Click on the Binder link below to run this notebook in a cloud environment. The notebook also works if executed locally. 

[![Binder](https://binder.pangeo.io/badge_logo.svg)](https://binder.pangeo.io/v2/gh/lsterzinger/fsspec-reference-maker-tutorial/main)

# Environment setup
## The default Pangeo environment needs a couple tweaks to run this code properly

First, if you're not running this on Pangeo or Binder, you'll want to set up the environment. I've provided the environment.yml file that includes all packages needed to run the notebook.
```
conda env create -f environment.yml
```

Then, activate the new `kerchunk-tutorial` environment (if you want to change the name, you will have to change the "name: kerchunk-tutorial" line at the very top of environment.yml before creating the environment)
```
conda activate kerchunk-tutorial
```

## Manual install without environment.yml
Download and install `kerchunk` from github. You will also need to make sure you have `numcodecs>=0.8.0`

```
pip install kerchunk
```
