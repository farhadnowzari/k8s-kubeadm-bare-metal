
```sh
wget https://github.com/containerd/containerd/releases/download/v1.7.2/containerd-1.7.2-linux-amd64.tar.gz
sudo tar Cxzvf /usr/local containerd-1.7.2-linux-amd64.tar.gz
```

```sh
wget https://github.com/opencontainers/runc/releases/download/v1.1.7/runc.amd64
sudo install -m 755 runc.amd64 /usr/local/sbin/runc
```

```sh
wget https://github.com/containernetworking/plugins/releases/download/v1.3.0/cni-plugins-linux-amd64-v1.3.0.tgz
sudo mkdir -p /opt/cni/bin
sudo tar Cxzvf /opt/cni/bin cni-plugins-linux-amd64-v1.3.0.tgz
```

```sh
sudo mkdir -p /usr/local/lib/systemd/system
wget https://raw.githubusercontent.com/containerd/containerd/main/containerd.service
sudo cp ./containerd.service /usr/local/lib/systemd/system/containerd.service
```

```sh
sudo systemctl daemon-reload
sudo systemctl enable --now containerd
```