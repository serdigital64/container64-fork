# Base image
FROM docker.io/library/ubuntu:22.04 AS base

# Prepare package installer
ENV container="docker"

#
# Environment definition
#
# * See docs/base-environment.md for details
#

ENV CNT64_DEBUG=""
ENV CNT64_USER="dev"
ENV CNT64_TMP="/tmp"
ENV CNT64_OPT_ROOT="/opt"
ENV CNT64_INSTALLER_ROOT="${CNT64_OPT_ROOT}/installer64"
ENV CNT64_LOCAL_ROOT="/usr/local"
ENV CNT64_LOCAL_BIN="${CNT64_LOCAL_ROOT}/bin"
ENV CNT64_BASHLIB64="${CNT64_OPT_ROOT}/bl64/bashlib64.bash"

#
# Bootstrap image
#

# Copy image setup scripts
COPY helpers/bootstrap/bootstrap /bootstrap
COPY helpers/dev/setup /setup
COPY installer/install-installer64 /install-installer64

# Set Installer64 parameters
ARG INST64_DEBUG="${CNT64_DEBUG}"
ENV INST64_OPT_ROOT="${CNT64_OPT_ROOT}"
ENV INST64_LOCAL_ROOT="${CNT64_LOCAL_ROOT}"
ENV INST64_LOCAL_BIN="${CNT64_LOCAL_BIN}"
ENV INST64_BASHLIB64="${CNT64_BASHLIB64}"
ENV INST64_INSTALLER64_TARGET="${CNT64_INSTALLER_ROOT}"
ENV INST64_INSTALLER64_VERSION='v1.1.0'

# Bootstrap
RUN \
    apt-get update && \
    apt-get install --assume-yes curl && \
    chmod 700 /install-installer64 /bootstrap /setup && \
    /install-installer64 && \
    ${CNT64_INSTALLER_ROOT}/install-bashlib64 && \
    /bootstrap && \
    rm /install-installer64 /bootstrap

#
# Setup image
#

RUN \
    /setup && \
    rm /setup

# Set default user and entrypoint
USER ${CNT64_USER}
ENTRYPOINT [ "/bin/bash", "--login" ]