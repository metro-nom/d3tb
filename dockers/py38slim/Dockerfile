# Those vars are used broadly outside this Dockerfile
# Github Action CI is consuming these variables.

ARG VERSION="20.12.2"
ARG DOCKERHUB_USER="mleist"
ARG APP_NAME="py38slim"

FROM python:3.8-slim-buster

ENV PACKAGES="\
  dumb-init \
  bash \
  make \
  ca-certificates \
"

RUN echo && \
    set -x && \
    apt-get update && \
    apt-get install -y $PACKAGES && \
    easy_install pip && \
    pip install --upgrade pip && \
    pip install wheel && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
    echo
