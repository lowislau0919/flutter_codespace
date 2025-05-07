FROM mcr.microsoft.com/devcontainers/base:ubuntu

RUN apt-get update && apt-get install -y \
    curl unzip git xz-utils zip libglu1-mesa \
    openjdk-17-jdk \
    && apt-get clean

ENV FLUTTER_VERSION=3.19.5
RUN git clone https://github.com/flutter/flutter.git /opt/flutter \
    && cd /opt/flutter \
    && git checkout ${FLUTTER_VERSION} \
    && /opt/flutter/bin/flutter doctor

ENV PATH="/opt/flutter/bin:/opt/flutter/bin/cache/dart-sdk/bin:${PATH}"

RUN flutter config --enable-web

ENV PUB_CACHE=/workspaces/.pub-cache

RUN useradd -m vscode
USER vscode
