# SPDX-License-Identifier: Apache-2.0
# Atmosphere-Rebuild-Time: 2024-05-30T20:29:01Z

ARG RELEASE

FROM registry.atmosphere.dev/library/openstack-venv-builder:${RELEASE} AS build
RUN --mount=type=cache,mode=0755,target=/root/.cache/pip,sharing=private <<EOF bash -xe
pip3 install \
    --constraint /upper-constraints.txt \
        python-openstackclient \
        python-barbicanclient \
        python-designateclient \
        python-glanceclient \
        python-heatclient \
        python-magnumclient \
        python-manilaclient \
        python-neutronclient \
        python-octaviaclient \
        osc-placement \
        python-swiftclient
EOF

FROM registry.atmosphere.dev/library/python-base:${RELEASE}
COPY --from=build --link /var/lib/openstack /var/lib/openstack
