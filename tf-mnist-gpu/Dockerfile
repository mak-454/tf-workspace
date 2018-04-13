# Docker image for running examples in Tensorflow models.
# base_image depends on whether we are running on GPUs or non-GPUs
FROM nvidia/cuda:9.0-cudnn7-runtime-ubuntu16.04

RUN apt-get update && apt-get install -y --no-install-recommends \
    ca-certificates \
    build-essential \
    git \
    python \
    python-pip \
    python-setuptools

RUN pip install tf-nightly-gpu

RUN mkdir /root/tf-mnist-gpu
ADD mnist /root/tf-mnist-gpu/mnist
ADD utils /root/tf-mnist-gpu/utils
ADD run.sh /root/tf-mnist-gpu/
RUN chmod +x /root/tf-mnist-gpu/run.sh

ENV PYTHONPATH "$PYTHONPATH:/root/tf-mnist-gpu"
