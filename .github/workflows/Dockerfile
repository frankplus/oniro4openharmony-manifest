# Copyright 2023 Huawei Inc.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
# SPDX-License-Identifier: Apache-2.0

FROM swr.cn-south-1.myhuaweicloud.com/openharmony-docker/docker_oh_standard:3.2

ARG DEBIAN_FRONTEND="noninteractive"

# install git-repo
RUN curl https://gitee.com/oschina/repo/raw/fork_flow/repo-py3 -o /bin/repo \
    && chmod a+x /bin/repo

RUN apt-get update -qq \
    && apt-get install -qq -y \
    libxcursor-dev libxrandr-dev libxinerama-dev sudo \
    build-essential zlib1g-dev pkg-config libglib2.0-dev  binutils-dev \
    libboost-all-dev autoconf libtool libssl-dev libpixman-1-dev virtualenv \
    flex bison ninja-build parted

# Set working directory
WORKDIR /opt

# Download QEMU sources
RUN wget https://download.qemu.org/qemu-6.2.0.tar.xz

# Extract the sources
RUN tar -xf qemu-6.2.0.tar.xz && \
    rm qemu-6.2.0.tar.xz

# Enter the extracted directory
WORKDIR /opt/qemu-6.2.0

# Configure and install QEMU
RUN ./configure && \
    make && \
    make install

# Clean up by removing the sources
WORKDIR /opt
RUN rm -rf qemu-6.2.0

WORKDIR /home/openharmony
