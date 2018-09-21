# FROM tensorflow/tensorflow:latest-gpu-py3
FROM nvidia/cuda:8.0-cudnn6-devel
RUN apt-get update && apt-get install -y --no-install-recommends \
    python3 \
    python3-dev \
    curl \
    && \
    rm -rf /var/lib/apt/lists/*

RUN curl -fSsL -O https://bootstrap.pypa.io/get-pip.py && \
    python3 get-pip.py && \
    rm get-pip.py

COPY requirements_gpu.txt /opt
RUN pip install -r /opt/requirements_gpu.txt
RUN rm -f /opt/requirements_gpu.txt
RUN pip install tensorflow-gpu==1.3.0
