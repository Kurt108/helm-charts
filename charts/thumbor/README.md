[![Artifact HUB](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/kurt108)](https://artifacthub.io/packages/search?repo=kurt108)


# thumbor
=======
A chart containing Thumbor

Current chart version is `1.0.2`

## Based on

the fanastic work from Cloudposse: https://charts.cloudposse.com/incubator/

## Installing the Chart

```console
$ helm repo add kurt108 https://kurt108.github.io/helm-charts
"kurt108" has been added to your repositories
$ helm repo update
Hang tight while we grab the latest from your chart repositories...
...Successfully got an update from the "kurt108" chart repository
...
Update Complete. ⎈ Happy Helming!⎈
$ helm install my-release kurt108/thumbor
NAME: my-release
...
```



## Chart Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env.ALLOWED_SOURCES[0] | string | `'http://s.glbimg.com'` |  |
| env.ALLOW_UNSAFE_URL | string | `"True"` |  |
| env.AUTO_WEBP | string | `"True"` |  |
| env.CORS_ALLOW_ORIGIN | string | `"*"` |  |
| env.HEALTHCHECK_ROUTE | string | `"/"` |  |
| env.LOG_LEVEL | string | `"error"` |  |
| env.MAX_AGE | string | `"3600"` |  |
| env.MAX_AGE_TEMP_IMAGE | string | `"300"` |  |
| env.RESULT_STORAGE | string | `"thumbor.result_storages.no_storage"` |  |
| env.RESULT_STORAGE_EXPIRATION_SECONDS | string | `"31536000"` |  |
| env.RESULT_STORAGE_STORES_UNSAFE | string | `"True"` |  |
| env.STORAGE | string | `"thumbor.storages.file_storage"` |  |
| env.THUMBOR_NUM_PROCESSES | string | `"1"` |  |
| env.THUMBOR_PORT | string | `"80"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"registry.hub.docker.com/minimalcompact/thumbor"` |  |
| image.tag | string | `"6.7.5"` |  |
| ingress.annotations."nginx.ingress.kubernetes.io/rewrite-target" | string | `"/$2"` |  |
| ingress.hosts[0] | string | `"thumbor.domain"` |  |
| ingress.path | string | `"/scale(/|$)(.*)"` |  |
| persistence.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.enabled | bool | `false` |  |
| persistence.size | string | `"8Gi"` |  |
| persistence.storageClass | string | `"generic"` |  |
| replicaCount | int | `1` |  |
| resources.limits.cpu | int | `1` |  |
| resources.limits.memory | string | `"1Gi"` |  |
| resources.requests.cpu | int | `1` |  |
| resources.requests.memory | string | `"512Mi"` |  |
| service.name | string | `"thumbor"` |  |
| service.type | string | `"ClusterIP"` |  |
