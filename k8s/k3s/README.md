# Kubernetes

## Instalacion de K3S
### k3s
- es una implementaciónde kubernetes ligera y facil de instalar
  - Solo se usa un binario de <100MB para correr (Todas las dependencias estan en el binario)
  -  Caso de usos 
    - NO se requiere personalizar la instalación de un cluster de kubernetes
    - IoT o maquinas pequeñas que no tienen demasiados recursos
    - CI 
  - Usa sqlite3 como reemplazo a etcd, incluye addons 


- Para realizar el curso se utilizara [k3s](https://k3s.io/) y se descarga e [instala](https://rancher.com/docs/k3s/latest/en/quick-start/) lanzando el siguiente comando:
```bash
curl -sfL https://get.k3s.io | sh -
```
Esto creara automaticamente el control plane.
- Para añadir un worker node debemos añadir las varibles de entorno con la IP del Master node y copiar el token que se encuentra en `/var/lib/rancher/k3s/server/node-token` añadiendolo al comando de la siguiente manera
-
```bash
curl -sfL https://get.k3s.io | K3S_URL=https://$MASTER_IP:6443 K3S_TOKEN=$TOKEN sh -
```
- Para que el usario pueda ejecutar kubectl sin sudo, se crea un grupo k3s y se añade al usuario actual al grupo, se cambia los permisso del archivo k3s.yaml para que el usuario pueda usar el kubectl
```bash
sudo groupadd k3s
sudo usermod -a -G k3s $USER
sudo chown root:k3s /etc/rancher/k3s/k3s.yaml
sudo chmod 740 /etc/rancher/k3s/k3s.yaml
```

Es necesario desloguearse para poder usar kubectl sin sudo

#Comandos Utiles en Kubernetes
```
kubectl run cow --image=wernight/funbox --comand -- /bin/sh -c "while true; do fortune | cowsay: sleep 15;done"

kubectl logs cow -f --tail 20
```
Seria lo mismo que hacer

```bash
cat << EOF > pod.yaml
> apiVersion: v1
> kind: Pod
> metadata:
>   name: cowfortune
> spec:
>   containers:
>   - name: funbox
>     image: wernight/funbox
>     command: ["/bin/sh"]
>     args: ["-c", "while true; do fortune | cowsay; sleep 15;done"]
> EOF
```


