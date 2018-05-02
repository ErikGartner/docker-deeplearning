# Matlab GPU Docker
*A docker image with NVIDIA CUDA and Matlab.*

- Image name: `erikgartner/dl-matlab-gpu:latest`
- Base: Ubuntu 16.04 with CUDA 8.0 and CUDNN (devel)

## Detailed content

- A prepacked matlab in a .tar file must be supplied as the `MATLAB_TAR` argument.

## Build

Use the following command to build the image:

```bash
docker build --build-arg MATLAB_TAR=matlab2015a.tar --build-arg MATLAB_FOLDER=matlab2015a -t erikgartner/dl-matlab-gpu:latest .
```

- `MATLAB_TAR` is the name of tar file containing the prepared Matlab distribution that is pre-activated.
- `MATLAB_FOLDER` is the name of top level directory in the tar file.
- `CUDA_VERSION` is the version of CUDA image to use, valid values are, default is: `8.0-cudnn6-devel-ubuntu16.04`.

Custom CUDA version (e.g. `7.5-cudnn5-devel-ubuntu14.04`):
```bash
docker build --build-arg MATLAB_TAR=matlab2015a.tar --build-arg MATLAB_FOLDER=matlab2015a --build-arg CUDA_VERSION=7.5-cudnn5-devel-ubuntu14.04 -t erikgartner/dl-matlab-gpu:7.5-cudnn5-devel-ubuntu14.04 .
```

## Requirements
Images based of the Nvidia Cuda image requires the Nvidia Docker runtime.
Installation instructions can be found [here](https://github.com/NVIDIA/nvidia-docker).
