# AWX-On-K3s
A guide on how to bring up an AWX instance using k3s in an air gapped environment.

## Prerequistites
- Alma Linux VM  
- GitLab Container Registry

## [Air-Gap Install for k3s](https://rancher.com/docs/k3s/latest/en/installation/airgap/) 
1. Download dependencies from https://github.com/k3s-io/k3s/releases
```sh
k3s-airgap-images-amd64.tar
k3s
```
2. Add dependencies to the images directory
```sh
sudo mkdir -p /var/lib/rancher/k3s/agent/images/
sudo cp ./k3s-airgap-images-amd64.tar /var/lib/rancher/k3s/agent/images/
sudo cp ./k3s /usr/local/bin/k3s
```
3. Ensure that the k3s binary is executable
```sh
cd /usr/local/bin
sudo chmod +x k3s
ls -l k3s
```

4. Download the k3s install script from https://get.k3s.io and place it in the same folder as the k3s binary
```sh
cp ./install.sh /usr/local/bin
```

5. Run the install script
```sh
INSTALL_K3S_SKIP_DOWNLOAD=true ./install.sh
```

6. Check if k3s are running!
```sh
systemctl status k3s
```

## Deploy awx-operator

## Deploy AWX Instance
