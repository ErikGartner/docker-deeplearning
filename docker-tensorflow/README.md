# Deep Learning Dockerfiles
*Contains the base images for Deep Learning in Docker*

## Requirements
Images based of the Nivida Cuda image requires the Nvidia Docker runtime.
Installation instructions can be found [here](https://github.com/NVIDIA/nvidia-docker).

## Image Description
Below follows brief descriptions of what the images contain.

### Dockerfile-tensorflow

Available as:
```
docker pull erikgartner/dl-tensorflow-gpu:latest
```

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
