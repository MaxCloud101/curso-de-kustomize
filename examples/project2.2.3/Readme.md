Actualmente helm 4, no es compatible, se requiere helm v3
```
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
```
Para que funcione nos colocamos en la carpeta del proyecto y lanzamos el siguiente comando:
```
kubectl kustomize  --enable-helm .
```
