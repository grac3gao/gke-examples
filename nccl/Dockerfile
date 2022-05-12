FROM nvidia/cuda:11.0-devel-ubuntu18.04 as builder

RUN apt-get update && apt-get install -y --no-install-recommends git curl gnupg
RUN git clone https://github.com/NVIDIA/nccl-tests.git 
WORKDIR /nccl-tests/
RUN make NCCL_HOME=/usr/lib/x86_64-linux-gnu

FROM nvidia/cuda:11.0-runtime-ubuntu18.04
COPY --from=builder /nccl-tests/build/all_reduce_perf /all_reduce_perf

CMD NCCL_DEBUG=INFO /all_reduce_perf    # Will load fastsocket plugin dynamically, if present.
