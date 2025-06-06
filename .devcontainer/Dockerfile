# Use Ubuntu 20.04 with CUDA 11.2 base image
FROM nvidia/cuda:11.2.2-runtime-ubuntu20.04

# Install basic utilities
RUN apt-get update && apt-get install -y \
    lsb-release \
    wget \
    git \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# Install Miniconda for Python 3.8
RUN wget https://repo.anaconda.com/miniconda/Miniconda3-py38_4.10.3-Linux-x86_64.sh -O ~/miniconda.sh && \
    bash ~/miniconda.sh -b -p /opt/conda && \
    rm ~/miniconda.sh

# Add conda to PATH
ENV PATH /opt/conda/bin:$PATH

# Install openmm
RUN pip install openmm==8.1.1

# Create a non-root user
RUN useradd -ms /bin/bash vscode && \
    chown -R vscode /opt/conda

# Switch to vscode user
USER vscode

# Initialize conda for bash shell
RUN conda init bash
