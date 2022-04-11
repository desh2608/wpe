# Nara-WPE in CuPy

This package is modified from the core parts of [nara_wpe](https://github.com/fgnt/nara_wpe) 
and modifies it to use [CuPy](https://github.com/cupy/cupy) for accelerated GPU-based inference.

At the moment, it is meant to be used with the [GSS](https://github.com/desh2608/gss) toolkit, 
but it can also be used in general for dereverberation. Note that this package only
contains the parts of Nara WPE that are relevant for GSS.

## Installation

```bash
> pip install cupy-cuda102  # modify according to your CUDA version (https://docs.cupy.dev/en/stable/install.html#installing-cupy)
> pip install wpe-gpu
```

## Usage

```python
from wpe import wpe
import cupy as cp

X = cp.random.rand(513, 4, 1000)    # F, D, T
X_hat = wpe(X, taps=10, delay=2, iterations=3, psd_context=0)   # F, D, T
```
