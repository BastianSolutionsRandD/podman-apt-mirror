# podman-apt-mirror
Mirror hosting binaries of Podman and its dependencies

## Installation
```
sudo apt update
sudo apt install curl tar gpg wget uidmap
sudo apt purge podman* golang-github-container* && \
curl -L https://github.com/BastianSolutionsRandD/podman-apt-mirror/releases/latest/download/InstallPodmanApt | bash
```

## Uninstallation

```
THIRD_PARTY_PACKAGES=(
    buildah
    catatonit
    conmon
    containernetworking-dnsname
    containernetworking-podman-machine
    containernetworking-plugins
    containernetworking
    containers-common
    containers-storage
    cri-o-runc
    crun
    fuse-overlayfs
    libslirp0
    libyajl2
    passt
    podman-aardvark-dns
    podman-gvproxy
    podman-netavark
    podman
    python3-podman-compose
    slirp4netns
    skopeo
)

apt list ${THIRD_PARTY_PACKAGES[@]}
sudo apt remove ${THIRD_PARTY_PACKAGES[@]}

sudo rm -rf "/usr/local/src/podman"
sudo rm /etc/apt/sources.list.d/podman-local.list
sudo rm /etc/apt/trusted.gpg.d/bastian.gpg 
sudo apt update
```
