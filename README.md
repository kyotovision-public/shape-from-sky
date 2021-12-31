# Shape from Sky: Polarimetric Normal Recovery Under the Sky, CVPR2021

This repository provides an inplementation of our paper [Shape From Sky: Polarimetric Normal Recovery Under the Sky](https://openaccess.thecvf.com/content/CVPR2021/html/Ichikawa_Shape_From_Sky_Polarimetric_Normal_Recovery_Under_the_Sky_CVPR_2021_paper.html) in CVPR 2021.  If you find our work useful in your research please consider citing our paper.

Please note that this is research software and may contain bugs or other issues – please use it at your own risk. If you experience major problems with it, you may contact us, but please note that we do not have the resources to deal with all issues.

```
@InProceedings{Ichikawa_2021_CVPR,
    author    = {Ichikawa, Tomoki and Purri, Matthew and Kawahara, Ryo and Nobuhara, Shohei and Dana, Kristin and Nishino, Ko},
    title     = {Shape From Sky: Polarimetric Normal Recovery Under the Sky},
    booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
    month     = {June},
    year      = {2021},
    pages     = {14832-14841}
}
```

## Prerequisites

We tested our code with Python 3.8.10 on Ubuntu 20.04 LTS.  Our code depends:
* bm3d
* matplotlib
* numba
* numpy
* opencv_python
* scipy
* tqdm

Please browse [`requirements.txt`](requirements.txt) generated by [`pipreqs`](https://pypi.org/project/pipreqs/) to find the specific versions we used in our test environment, or you can simply do
```
$ python3 -m pip install -r requirements.txt
```
in your (virtual) environment.

Alternatively, you can use [`sfsky.def`](sfsky.def) to build your [`singularity`](https://sylabs.io/) container by
```
$ singularity build --fakeroot ./sfsky.sif ./sfsky.def
INFO:    Starting build...
Getting image source signatures
(snip)
INFO:    Creating SIF file...
INFO:    Build complete: ./sfsky.sif
```
The file size of the generated container file (`sfsky.sif` in this example) will be around 560MB.

## Usage

Please open the following Jupyter notebooks in the `code/process/python_code/` directory.
* [`shape_from_sky.ipynb`](code/process/python_code/shape_from_sky.ipynb)
* [`shape_from_sky_spatially_varying.ipynb`](code/process/python_code/shape_from_sky_spatially_varying.ipynb)

In case you have built your singularity container as mentioned above, you can launch `jupyter` in `singularity` by
```
$ singularity exec ./sfsky.sif jupyter notebook --port 12345
    To access the notebook, open this file in a browser:
        file:/// ...
    Or copy and paste one of these URLs:
        http://localhost:12345/?token= ...
     or http://127.0.0.1:12345/?token= ...
```
