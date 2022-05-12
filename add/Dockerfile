FROM nvidia/cuda:11.1-devel-ubuntu18.04

RUN apt-get update && apt-get install -y --no-install-recommends \
        cuda-samples-11-1 && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /usr/local/cuda/samples/0_Simple/vectorAdd
COPY vectorAdd.cu vectorAdd.cu
RUN make

CMD ./vectorAdd.cu
