# Matlab GPU Docker
*A docker image with NVIDIA CUDA and Matlab.*

- Image name: `erikgartner/dl-matlab-gpu:latest`
- Base: Ubuntu 16.04 with CUDA (devel)

# Detailed content

- The Matlab installed from the tar.

## Build

Use the following command to build the image:

```bash
docker build --build-arg MATLAB_TAR=matlab2015a.tar --build-arg MATLAB_FOLDER=matlab2015a -t erikgartner/dl-matlab-gpu:latest .
```

- `MATLAB_TAR` is the name of tar file containing the prepared Matlab distribution that is pre-activated.
- `MATLAB_FOLDER` is the name of top level directory in the tar file.

## Requirements
Images based of the Nivida Cuda image requires the Nvidia Docker runtime.
Installation instructions can be found [here](https://github.com/NVIDIA/nvidia-docker).
