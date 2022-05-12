FROM nvidia/cuda:11.0-devel-ubuntu18.04

RUN apt-get update && apt-get install -y --no-install-recommends \
        cuda-samples-11-0 && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /usr/local/cuda/samples/0_Simple/bf16TensorCoreGemm 
COPY bf16TensorCoreGemm.cu bf16TensorCoreGemm.cu
RUN make

CMD ./bf16TensorCoreGemm
