# Kubernetes
- Para realizar el curso se utilizara [k3s](https://k3s.io/) y se descarga e [instala](https://rancher.com/docs/k3s/latest/en/quick-start/) lanzando el siguiente comando:
```bash
curl -sfL https://get.k3s.io | sh -
```
Esto creara automaticamente el control plane.
- Para añadir un worker node debemos añadir las varibles de entorno con la IP del Master node y copiar el token que se encuentra en `/var/lib/rancher/k3s/server/node-token` añadiendolo al comando de la siguiente manera
-
```bash
curl -sfL https://get.k3s.io | K3S_URL=https://172.31.18.195:6443 K3S_TOKEN=K1016482a067c890f94059ffc5e4fda748d29ee87eb09abb1cc4256facd7d2d852e::server:c91b6807b038614aa74fc20a sh -
```
```bash
sudo groupadd k3s
sudo usermod -a -G k3s $USER
sudo chown root:k3s /etc/rancher/k3s/k3s.yaml
sudo chmod 740 /etc/rancher/k3s/k3s.yaml
```

#
