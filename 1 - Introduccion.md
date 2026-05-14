# Introducción

Kustomize es una herramienta de configuración para Kubernetes que permite modificar archivos YAML sin usar templates.

Fue creada para trabajar de forma nativa con Kubernetes y viene integrada en kubectl.

Con Kustomize puedes:

- Cambiar nombres
- Agregar labels o annotations
- Modificar imágenes
- Aplicar parches
- Crear configuraciones para distintos ambientes (dev, qa, prod)
- Reutilizar manifests base

## Idea principal

En lugar de usar variables dentro del YAML como hace Helm, Kustomize trabaja con:

- Base → configuración común
- Overlays → modificaciones por entorno

## Estructura típica

```
project/
├── base/
│   ├── deployment.yaml
│   ├── service.yaml
│   └── kustomization.yaml
│
└── overlays/
    ├── dev/
    │   └── kustomization.yaml
    │
    └── prod/
        └── kustomization.yaml
```

- Para generar los temaplates lanzamos el comando:

```
kubectl kustomize overlays/prod
```

- Para lanzar los templates directamente contra el cluster

```
kubectl apply -k overlays/prod
```
