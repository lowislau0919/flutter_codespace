FROM ubuntu:22.04

# 安裝必要工具 + Chromium
RUN apt-get update && apt-get install -y \
    curl git unzip xz-utils zip libglu1-mesa openjdk-17-jdk chromium-browser \
    && apt-get clean

# 建立 vscode 使用者
RUN useradd -m vscode
USER vscode

# 安裝 Flutter
RUN git clone https://github.com/flutter/flutter.git /home/vscode/flutter
ENV PATH="/home/vscode/flutter/bin:/home/vscode/flutter/bin/cache/dart-sdk/bin:${PATH}"
ENV CHROME_EXECUTABLE=/usr/bin/chromium-browser

RUN git config --global --add safe.directory /home/vscode/flutter
RUN flutter doctor
