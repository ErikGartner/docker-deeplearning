# TensorFlow GPU Docker
*A docker image with NVIDIA CUDA and TensorFlow.*

- Image name: `erikgartner/dl-tensorflow-gpu:latest`
- Base: Ubuntu 16.04 with CUDA (devel)

Pre-built image available using:
```
docker pull erikgartner/dl-tensorflow-gpu:latest
```

# Detailed content

- Ubuntu 16.04
- CUDA 8.0
- CUDNN 6
- TensorFlow GPU 1.3
- TensorBoard
- Basic Python packages:
  - Pillow
  - h5py
  - jupyter
  - matplotlib
  - numpy
  - pandas
  - scipy
  - sklearn

## Build

Use the following command to build the image:

```bash
docker build --build-arg MATLAB_TAR=matlab2015a.tar --build-arg MATLAB_FOLDER=matlab2015a -t erikgartner/dl-matlab-gpu:latest .
```

- `MATLAB_TAR` is the name of tar file containing the prepared Matlab distribution that is pre-activated.
- `MATLAB_FOLDER` is the name of top level directory in the tar file.

## Requirements
Images based of the Nivida CUDA image requires the Nvidia Docker runtime.
Installation instructions can be found [here](https://github.com/NVIDIA/nvidia-docker).
