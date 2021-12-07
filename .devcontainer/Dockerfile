FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu

RUN apt-get update \
    && apt-get -qqy install \
    bc \
    sudo \
    build-essential \
    ca-certificates \
    clang \
    curl \
    gcc \
    git \
    python3 \
    python3-dev \
    python3-distutils \
    python3-pip \
    python3-setuptools \
    srecord \
    udev \
    xz-utils \
    && apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

RUN curl -fLo /etc/udev/rules.d/99-platformio-udev.rules --create-dirs https://raw.githubusercontent.com/platformio/platformio-core/master/scripts/99-platformio-udev.rules

USER $USERNAME

RUN python3 -c "$(curl -fsSL https://raw.githubusercontent.com/platformio/platformio/develop/scripts/get-platformio.py)"