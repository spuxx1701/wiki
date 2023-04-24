# Complete setup guide

## Install homebrew

Brew is a handy package manager that can be used to easily install tools like kubectl or k9s. Installation is documented [here](https://brew.sh/).

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## Install snap & Microk8s

This guide assumes you're getting Canonical's [Microk8s](https://ubuntu.com/tutorials/install-a-local-kubernetes-with-microk8s#1-overview). Microk8s is best installed via Ubuntu's [snap](https://snapcraft.io/docs/installing-snapd) package manager. In case your Linux distribution does not already come with snap, you might need to install it:

```bash
sudo apt update
sudo apt install snapd
```

With snap, you can then install Microk8s:

```bash
# On debian, you might need to install 'core' first
sudo snap install core
sudo snap install microk8s
```

After that, you can start up microk8s.

```bash
microk8s start
# Get the status
microk8s status
# Get a lot more details (may help in case of errors)
microk8s inspect
```

With microk8s running, we can enable some basic services.

```bash
microk8s enable dns # Enables DNS
microk8s enable hostpath-storage # Allows storing files on the host system
microk8s enable cert-manager # Enables cert-manager for certificate management
microk8s enable helm # Enables helm package manager
microk8s enable ingress # Enables the NGINX ingress controller
```

Now make the server listen to Microk8s' API server port.

```bash
sudo ufw allow 16443/tcp
``` 
