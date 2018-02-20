# Base image is the Nvida GPU image.
FROM nvidia/cuda:8.0-cudnn6-devel-ubuntu16.04

LABEL maintainer="Erik Gärtner <erik@gartner.io>"

# Install Python and TF dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
        build-essential \
        curl \
        libfreetype6-dev \
        libpng12-dev \
        libzmq3-dev \
        pkg-config \
        python \
        python-dev \
        rsync \
        software-properties-common \
        unzip \
        libsm6 \
        libxrender1 \
        libfontconfig1\
        python-tk \
        && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Install pip
RUN curl -O https://bootstrap.pypa.io/get-pip.py && \
    python get-pip.py && \
    rm get-pip.py

# Install auxiliary Python libs
RUN pip --no-cache-dir install \
        Pillow \
        h5py \
        ipykernel \
        jupyter \
        matplotlib \
        numpy \
        pandas \
        scipy \
        sklearn

# Install Tensorflow
RUN pip --no-cache-dir install \
    http://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-1.3.0-cp27-none-linux_x86_64.whl

# Install Tensorboard
RUN pip --no-cache-dir install \
    tensorboard

# Setup CUDA enviroment variables.
# For CUDA profiling, TensorFlow requires CUPTI.
ENV CUDA_HOME /usr/local/cuda
ENV LD_LIBRARY_PATH $CUDA_HOME/lib64
ENV PATH ${CUDA_HOME}/bin:${PATH}
ENV LD_LIBRARY_PATH /usr/local/cuda/extras/CUPTI/lib64:$LD_LIBRARY_PATH
