FROM nvidia/cuda:11.5.0-devel-ubuntu20.04

RUN apt-get update && apt-get install -y --no-install-recommends \
        cuda-samples-11-5 && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /usr/local/cuda/samples/0_Simple/vectorAdd
COPY vectorAdd.cu vectorAdd.cu
RUN make

CMD ./vectorAdd.cu
