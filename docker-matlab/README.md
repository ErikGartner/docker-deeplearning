# Matlab GPU Docker
*A docker image with NVIDIA CUDA and Matlab*

## Build

Use the following command to build the image. `MATLAB_TAR` is the name of
tar file containing the prepared Matlab distribution that is pre-activated.
```bash
docker build --build-arg MATLAB_TAR=matlab2015a.tar --build-arg MATLAB_FOLDER=matlab2015a -t erikgartner/dl-matlab-gpu:latest .
```
