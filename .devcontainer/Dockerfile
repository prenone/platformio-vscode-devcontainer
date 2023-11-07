ARG VARIANT=20-bullseye
FROM mcr.microsoft.com/vscode/devcontainers/typescript-node:0-${VARIANT}

RUN <<EOF 
  apt-get update 
  export DEBIAN_FRONTEND=noninteractive 
  apt-get -y install --no-install-recommends \
    clang \
    udev     
  
  curl -fsSL https://raw.githubusercontent.com/platformio/platformio-core/develop/platformio/assets/system/99-platformio-udev.rules | sudo tee /etc/udev/rules.d/99-platformio-udev.rules
  service udev restart 
  usermod -a -G dialout node
  usermod -a -G plugdev node 
  
EOF
