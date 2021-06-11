# `fsspec-reference-maker` GOES-16 tutorial

This example notebook accompanies this post I made on medium (link not yet active), explaining how to use [fsspec-reference-maker](https://github.com/intake/fsspec-reference-maker) to speed up GOES-16/17 NetCDF4 access on AWS S3.

Click on the Binder link below to run this notebook in a cloud environment. The notebook also works if executed locally. 

[![Binder](https://binder.pangeo.io/badge_logo.svg)](https://binder.pangeo.io/v2/gh/lsterzinger/fsspec-reference-maker-tutorial/main?filepath=tutorial.ipynb)

# Environment setup
## The default Pangeo environment needs a couple tweaks to run this code properly

First, if you're not running this on Pangeo or Binder, you'll want to set up the environment. I've provided the environment.yml file that includes all packages needed to run (minus fsspec-reference-maker itself, the installation of which I'll cover below).
```
conda env create -f environment.yml
```

Then, activate the new `fsspec-tutorial` environment (if you want to change the name, you will have to change the "name: fsspec-tutorial" line at the very top of environment.yml before creating the environment)
```
conda activate fsspec-tutorial
```

Make sure that fsspec and s3fs are both up to date by running
```
pip install --upgrade --user fsspec s3fs
```

## Get fsspec-reference-maker
Download and install `fsspec-reference-maker` from github. 

In a recent update, there's an import that doesn't work unless you're using the development version of numcodecs, but the added features do not affect our work in this guide. To get around this, install `fsspece-reference-maker` from an earlier commit with:
```
pip install --user git+https://github.com/intake/fsspec-reference-maker@84c15d98a1e0ca04469f2453028b936b124e7df
```


If for you want to install from the main branch, and numcodecs hasn't updated with a new release yet, simply edit `./fsspec-reference-maker/fsspec_reference_maker/hdf.py` and change

```
from numcodecs import Zlib, Shuffle
```
to:
```
from numcodecs import Zlib
```
Then, in the base `fsspec-reference-maker/` directory, run:
```
pip install --user .
```
---