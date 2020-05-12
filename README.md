Introduction
-------------------------

Floating point for [Sprintz](https://github.com/dblalock/sprintz) is an attempt to added lossless floating point compression to the exiting Sprintz architecture. [Sprintz](https://github.com/dblalock/sprintz) is a compression algorithm designed for low memory and low bit width devices. 



Usage
-------------------------

Follow the instructions in the Reproduction of Results section of [Sprintz](https://github.com/dblalock/sprintz) repo. 

Instead of downloading benchmark suite from [benchmark repository](https://github.com/dblalock/lzbench), download everything from this current repo.

Instead of downloading data from all the sources mentioned in Sprintz repo, only download the data from [UCR Archive](http://www.cs.ucr.edu/~eamonn/time_series_data/) 2015. The current version does not support other datasets.

In order to see the results using our lossless floating point compression methods, in the Quantization phase, instead of running [`_python/datasets/compress_bench.py`](https://github.com/dblalock/lzbench/blob/master/_python/datasets/compress_bench.py), run ` _python/datasets/compress_bench_ucr_float.py` to reproduce data using float splitting method one as stated in [our paper](https://github.com/Atlas-Yu/Floating_point_Sprintz/blob/master/Floating_Point_for_Sprintz.pdf):

```
python -m _python.datasets.compress_bench_ucr_float
```

Run` _python/datasets/compress_bench_ucr_float_IEEE.py` to reproduce data using float splitting method two as stated in the paper:

```
python -m _python.datasets.compress_bench_ucr_float_IEEE
```

Before running any of the above command, make sure to always delete all the previously generated data in the _python/datasets/compress/rowmajor and _python/datasets/compress/colmajor folders. Otherwise the quantization will return errors.