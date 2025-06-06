# Use Ubuntu 20.04 with CUDA 11.2 base image
FROM nvidia/cuda:11.2.2-devel-ubuntu20.04

# Install basic utilities
RUN apt-get update && apt-get install -y \
    lsb-release \
    wget \
    git \
    build-essential \
    nvidia-utils-525 \
    && rm -rf /var/lib/apt/lists/*

# Install Miniconda for Python 3.8
RUN wget https://repo.anaconda.com/miniconda/Miniconda3-py38_4.10.3-Linux-x86_64.sh -O ~/miniconda.sh && \
    bash ~/miniconda.sh -b -p /opt/conda && \
    rm ~/miniconda.sh

# Add conda to PATH
ENV PATH /opt/conda/bin:$PATH

# Install openmm
RUN pip install openmm[cuda11.2]

# Create a non-root user
RUN useradd -ms /bin/bash vscode && \
    chown -R vscode /opt/conda

# Switch to vscode user
USER vscode

# Initialize conda for bash shell
RUN conda init bash
