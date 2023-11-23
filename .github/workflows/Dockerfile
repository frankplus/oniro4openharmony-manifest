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
    qemu-system libxcursor-dev libxrandr-dev libxinerama-dev sudo
