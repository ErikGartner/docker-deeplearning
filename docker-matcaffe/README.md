# Matcaffe GPU Docker
*A docker image with NVIDIA CUDA, Matlab and Caffe with Matlab bindings.*

- Image name: `erikgartner/dl-matcaffe-gpu:latest`
- Base: Ubuntu 14.04 with CUDA 7.5 and CUDNN 5 (devel)

## Detailed content

- Matlab
- Caffe
- Matcaffe

## Build

Use the following command to build the image:

```bash
docker build --build-arg CAFFE_GIT=https://github.com/shihenw/caffe.git --build-arg COMMITISH=d154e896b48e8fb520cb4b47af8ba10bf9403382 -t erikgartner/dl-matcaffe-gpu:latest .
```

- `CAFFE_GIT` is a git url to a Caffe repository, default: `https://github.com/BVLC/caffe`.
- `COMMITISH` is a commit-ish (commit, tag, branch) of that repository, default: `master`.
- `MATLAB_IMAGE_VERSION` is the version of `erikgartner/dl-matlab-gpu`, default: `7.5-cudnn5-devel-ubuntu14.04`.

Example for using a specific version of `dl-matlab-gpu`:

```bash
docker build --build-arg CAFFE_GIT=https://github.com/shihenw/caffe.git --build-arg COMMITISH=d154e896b48e8fb520cb4b47af8ba10bf9403382 --build-arg MATLAB_IMAGE_VERSION=7.5-cudnn5-devel-ubuntu14.04 -t erikgartner/dl-matcaffe-gpu:7.5-cudnn5-devel-ubuntu14.04 .
```

## Requirements
Images based of the Nvidia Cuda image requires the Nvidia Docker runtime.
Installation instructions can be found [here](https://github.com/NVIDIA/nvidia-docker).

This image also needs my other Docker image: `erikgartner/dl-matlab-gpu:7.5-cudnn5-devel-ubuntu14.04`.
