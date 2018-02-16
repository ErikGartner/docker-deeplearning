# Base image is the Nvida GPU image.
FROM nvidia/cuda:8.0-cudnn6-devel-ubuntu16.04

LABEL maintainer="Erik Gärtner <erik@gartner.io>"

RUN mkdir -p /opt/
WORKDIR /opt/

# Copy and unpack matlab tar
ARG MATLAB_TAR
ADD $MATLAB_TAR /opt/

# Link extracted files to /matlab
ARG MATLAB_FOLDER
ENV MATLAB_FOLDER $MATLAB_FOLDER
RUN ln -sf /opt/$MATLAB_FOLDER /matlab

# Install Matlab dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
        libglu1-mesa libxrender1 libxtst6 libxi6 libxt6 \
        && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Link Matlab to PATH
WORKDIR /usr/local/bin
RUN ln -s /matlab/bin/matlab matlab
RUN ln -s /matlab/bin/mex mex
RUN ln -s /matlab/bin/mbuild mbuild
RUN ln -s /matlab/bin/mcc mcc-matlab

# Setup CUDA enviroment variables.
# For CUDA profiling, TensorFlow requires CUPTI.
ENV CUDA_HOME /usr/local/cuda
ENV LD_LIBRARY_PATH $CUDA_HOME/lib64
ENV PATH ${CUDA_HOME}/bin:${PATH}
ENV LD_LIBRARY_PATH /usr/local/cuda/extras/CUPTI/lib64:$LD_LIBRARY_PATH

WORKDIR /matlab/bin
