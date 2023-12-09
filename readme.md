# Overview
Based on [https://github.com/accetto/ubuntu-vnc-xfce-g3](https://github.com/accetto/ubuntu-vnc-xfce-g3/tree/d7aa0dbca655b190ad7a560d47aad6cd0fcff1da) | base image: [accetto/ubuntu-vnc-xfce-firefox-g3](https://hub.docker.com/layers/accetto/ubuntu-vnc-xfce-firefox-g3/latest/images/sha256-ff9452015948ee19985c5d1130d72bfb63e2301d955b987756ac1f1b4b30e44a?context=explore)

# Usage details
## Running container
```console
docker run -d --shm-size=1gb -p "36901:6901" --name ubuntuquick --hostname ubuntuquick pradhyumna85/ubuntu-vnc-xfce-firefox-vscode-miniconda-g3
```

## Access details
- access at: http://localhost:36901 | novnc password: headless

## User credentials
User: **headless**

Password: **headless**

# Basic installations done (Not required as this image already has these)
## install vscode
```console
sudo apt-get update && sudo apt-get install -y gpg && wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg && sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg && sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list' && rm -f packages.microsoft.gpg && sudo apt install -y apt-transport-https && sudo apt update && sudo apt install -y code
```

## Install vscode extensions
```console
export DONT_PROMPT_WSL_INSTALL=1 && code --install-extension ms-python.python && code --install-extension ms-toolsai.jupyter && code --install-extension eamodio.gitlens && code --install-extension redhat.vscode-yaml && code --install-extension rangav.vscode-thunder-client
```

## Install miniconda
```console
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh && chmod +x Miniconda3-latest-Linux-x86_64.sh && ./Miniconda3-latest-Linux-x86_64.sh -b && source ~/miniconda3/etc/profile.d/conda.sh && conda init && echo "Done. Shell will close in 5 seconds" && sleep 5 && exit
```

