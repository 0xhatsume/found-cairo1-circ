FROM --platform=linux/arm64 shardlabs/cairo-cli:0.11.0.2-arm

# update bins
RUN apk add git musl-dev gmp-dev g++ gcc curl curl-dev
#RUN apk add gmp-dev g++ gcc curl curl-dev

# add rust
RUN curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh -s -- -y
ENV PATH="/root/.cargo/bin:${PATH}"

# add circom
# RUN git clone https://github.com/iden3/circom.git /home/circom && \
# cd /home/circom && cargo build --release && \
# cargo install --path circom

# # add scarb
RUN mkdir /home/scarb && curl -L https://github.com/software-mansion/scarb/releases/download/v0.1.0/scarb-v0.1.0-aarch64-unknown-linux-gnu.tar.gz | \
tar -xz -C /home/scarb --strip-components 1
ENV PATH="/home/scarb/bin:${PATH}"