#-------------------------------------------------------------------------------------------------------------
# Copyright (c) Microsoft Corporation. All rights reserved.
# Licensed under the MIT License. See https://go.microsoft.com/fwlink/?linkid=2090316 for license information.
#-------------------------------------------------------------------------------------------------------------

FROM rust:1

RUN rustup update
RUN rustup component add rls rust-analysis rust-src

# Install git, process tools
RUN apt-get update && apt-get -y install git procps

# Install other dependencies
RUN apt-get install -y lldb-3.9

# Clean up
RUN apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

RUN ./scripts/dev_setup.sh
# Set the default shell to bash instead of sh
ENV SHELL /bin/bash
