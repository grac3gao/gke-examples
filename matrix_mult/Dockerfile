FROM nvidia/cuda:11.5.0-devel-ubuntu20.04

RUN apt-get update && apt-get install -y --no-install-recommends \
        cuda-samples-11-5 && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /usr/local/cuda/samples/0_Simple/matrixMul
COPY matrixMul.cu /usr/local/cuda/samples/0_Simple/matrixMul/matrixMul.cu
RUN make

CMD ./matrixMul