FROM nvidia/cuda:10.0-devel-ubuntu18.04

RUN apt-get update && apt-get install -y --no-install-recommends \
        cuda-samples-$CUDA_PKG_VERSION && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /usr/local/cuda/samples/0_Simple/matrixMul
COPY matrixMul.cu /usr/local/cuda/samples/0_Simple/matrixMul/matrixMul.cu
RUN make

CMD ./matrixMul