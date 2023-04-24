# Complete setup guide

## Install homebrew

Brew is a handy package manager that can be used to easily install tools like kubectl or k9s. Installation is documented [here](https://brew.sh/).

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## Install snapd & Microk8s

This guide assumes you're getting Canonical's [Microk8s](https://ubuntu.com/tutorials/install-a-local-kubernetes-with-microk8s#1-overview). Microk8s is best installed via Ubuntu's [snap](https://snapcraft.io/docs/installing-snapd) package manager. In case your Linux distribution does not already come with snap, you might need to install it:

```bash
sudo apt update
sudo apt install snapd
```

With snapd, you can then install Microk8s:

```bash
# On debian, you might need to install 'core' first
sudo snap install core
sudo snap install microk8s
```
