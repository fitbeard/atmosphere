# SPDX-License-Identifier: Apache-2.0
# Atmosphere-Rebuild-Time: 2024-05-30T20:29:01Z

ARG RELEASE

FROM registry.atmosphere.dev/library/ubuntu-cloud-archive:${RELEASE}
ENV PATH=/var/lib/openstack/bin:$PATH
RUN \
    apt-get update -qq && \
    apt-get install -qq -y --no-install-recommends \
        ca-certificates \
        libpython3.10 \
        lsb-release \
        python3-distutils \
        sudo && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
