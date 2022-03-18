# AWX-On-K3s
A guide on how to bring up an AWX instance using k3s in an air gapped environment.

## Prerequistites
Alma Linux VM
GitLab Container Registry

### Install k3s
1. Download dependencies from https://github.com/k3s-io/k3s/releases
```k3s-airgap-images-amd64.tar
k3s
```
2. Add dependencies to the images directory
```sudo mkdir -p /var/lib/rancher/k3s/agent/images/
sudo cp ./k3s-airgap-images-amd64.tar /var/lib/rancher/k3s/agent/images/
sudo cp ./k3s /usr/local/bin/k3s
```

### Deploy awx-operator

### Deploy AWX Instance
