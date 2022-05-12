FROM nvidia/cuda:11.0-devel-ubuntu18.04

RUN apt-get update && apt-get install -y --no-install-recommends \
        cuda-samples-11-0 && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /usr/local/cuda/samples/5_Simulations/nbody
RUN make

CMD ./nbody -benchmark -numbodies=100000
