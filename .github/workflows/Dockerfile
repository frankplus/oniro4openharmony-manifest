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

FROM swr.cn-south-1.myhuaweicloud.com/openharmony-docker/openharmony-docker:1.0.0

ARG DEBIAN_FRONTEND="noninteractive"

# install git-repo
RUN curl https://gitee.com/oschina/repo/raw/fork_flow/repo-py3 -o /bin/repo \
    && chmod a+x /bin/repo

RUN apt-get update -qq \
    && apt-get install -qq -y \
    libxcursor-dev libxrandr-dev libxinerama-dev sudo \
    build-essential zlib1g-dev pkg-config libglib2.0-dev  binutils-dev \
    libboost-all-dev autoconf libtool libssl-dev libpixman-1-dev virtualenv \
    flex bison ninja-build

# install qemu following https://gitee.com/openharmony/device_qemu/blob/master/README.md
RUN wget https://download.qemu.org/qemu-6.2.0.tar.xz \
    && tar -xf qemu-6.2.0.tar.xz \
    && cd qemu-6.2.0 \
    && mkdir build && cd build \
    && ../configure \
    && make -j16 \
    && make install
