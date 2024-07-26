# Use the base image you need for your development environment
FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu

# Install dependencies and Zig
RUN apt-get update && apt-get install -y \
	curl \
	unzip \
	&& rm -rf /var/lib/apt/lists/*

# Install Zig
ARG ZIG_VERSION=0.13.0
RUN curl -LO https://ziglang.org/download/${ZIG_VERSION}/zig-linux-x86_64-${ZIG_VERSION}.tar.xz \
	&& tar -xf zig-linux-x86_64-${ZIG_VERSION}.tar.xz \
	&& mv zig-linux-x86_64-${ZIG_VERSION} /usr/local/zig \
	&& ln -s /usr/local/zig/zig /usr/local/bin/zig

# Clean up
RUN rm zig-linux-x86_64-${ZIG_VERSION}.tar.xz

# Set the default shell to bash
SHELL ["/bin/bash", "-c"]
