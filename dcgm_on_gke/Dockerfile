FROM debian:9

#FROM nvcr.io/nvidia/cuda:11.2.1-base-ubuntu20.04

RUN apt-get update && apt-get install -y --no-install-recommends \
    libcap2-bin \
    libgomp1 \
    wget && \
    rm -rf /var/lib/apt/lists/* && \
    wget --no-check-certificate https://developer.download.nvidia.com/compute/redist/dcgm/2.1.8/DEBS/datacenter-gpu-manager_2.1.8_amd64.deb && \
    dpkg -i datacenter-gpu-manager_*.deb && \
    rm -f datacenter-gpu-manager_*.deb

# Required for DCP metrics
ENV NVIDIA_DRIVER_CAPABILITIES=compute,utility,compat32
# disable all constraints on the configurations required by NVIDIA container toolkit
ENV NVIDIA_DISABLE_REQUIRE="true"
ENV NVIDIA_VISIBLE_DEVICES=all