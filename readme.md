# V2ray Forward Quickstart

[知乎专栏](https://zhuanlan.zhihu.com/p/103350360)

## How to Install (As forward server)

* Clone this repository

   ```bash
   git clone https://github.com/nofacer/v2ray-forward.git
   ```

* Install v2ray

   **Online Install**

   ```bash
   wget https://install.direct/go.sh && \
   sudo bash go.sh
   ```

   **Offline Install**

   ```bash
   sudo bash go.sh -l v2ray-linux-<64/arm>.zip
   ```

* Config

   **Backup original config file**

   ```bash
   sudo mv /etc/v2ray/config.json /etc/v2ray/config.json.backup
   ```

   **Edit config**

   ```bash
   sudo cp config.json /etc/v2ray/config.json
   sudo vi /etc/v2ray/config.json
   ```

* Run

   **Add to Path**

   ```bash
   PATH=$PATH:/usr/bin/v2ray
   ```

   **Test Config**

   ```bash
   v2ray -test -config /etc/v2ray/config.json
   ```

   **Commands**

   ```bash
   systemctl stop v2ray
   systemctl start v2ray
   systemctl restart v2ray
   ```

## How to Use (As forward client)

```bash
export http_proxy="http://<forward_server>:<forward_port>";\
export HTTP_PROXY="http://<forward_server>:<forward_port>";\
export https_proxy="http://<forward_server>:<forward_port>";\
export HTTPS_PROXY="http://<forward_server>:<forward_port>"
```

## Uninstall

```bash
systemctl stop v2ray
systemctl disable v2ray

rm -rf /etc/v2ray/*
rm -rf /usr/bin/v2ray/*
rm -rf /var/log/v2ray/*
rm -rf /lib/systemd/system/v2ray.service
rm -rf /etc/init.d/v2ray
```
