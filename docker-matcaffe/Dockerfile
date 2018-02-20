ARG MATLAB_IMAGE_VERSION=7.5-cudnn5-devel-ubuntu14.04
FROM erikgartner/dl-matlab-gpu:${MATLAB_IMAGE_VERSION}

LABEL maintainer="Erik Gärtner <erik@gartner.io>"

# Install dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
        git ca-certificates \
        libprotobuf-dev libleveldb-dev libsnappy-dev libopencv-dev libhdf5-serial-dev protobuf-compiler libatlas-base-dev  \
        freeglut3-dev build-essential libx11-dev libxmu-dev libxi-dev libgl1-mesa-glx libglu1-mesa libglu1-mesa-dev \
        build-essential \
        cmake \
        git \
        wget \
        libatlas-base-dev \
        libboost-all-dev \
        libgflags-dev \
        libgoogle-glog-dev \
        libhdf5-serial-dev \
        libleveldb-dev \
        liblmdb-dev \
        libopencv-dev \
        libprotobuf-dev \
        libsnappy-dev \
        protobuf-compiler \
        python-dev \
        python-numpy \
        python-pip \
        python-setuptools \
        python-scipy \
        && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

ARG CAFFE_GIT
ARG COMMITISH

WORKDIR /
RUN git clone $CAFFE_GIT caffe
WORKDIR /caffe
RUN git checkout $COMMITISH

COPY Makefile.config.caffe Makefile.config

RUN make -j5
RUN make matcaffe

ENV LD_LIBRARY_PATH=/caffe/build/lib
RUN mkdir /app
WORKDIR /app
VOLUME /app
