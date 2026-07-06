FROM mcr.microsoft.com/devcontainers/go:1

ARG NODE_MAJOR=22
ARG HUGO_VERSION=0.156.0

RUN apt-get update \
  && export DEBIAN_FRONTEND=noninteractive \
  && apt-get install -y --no-install-recommends ca-certificates curl gnupg \
  && mkdir -p /etc/apt/keyrings \
  && curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key \
    | gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg \
  && echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_${NODE_MAJOR}.x nodistro main" \
    > /etc/apt/sources.list.d/nodesource.list \
  && apt-get update \
  && apt-get install -y --no-install-recommends nodejs \
  && curl -fsSL -o /tmp/hugo.deb \
    "https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-arm64.deb" \
  && apt-get install -y /tmp/hugo.deb \
  && rm -f /tmp/hugo.deb \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*
