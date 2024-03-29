# thumbor

A chart containing Thumbor
2.0.1
[![Artifact HUB](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/kurt108)](https://artifacthub.io/packages/search?repo=kurt108)

Based on the fanastic work from Cloudposse: https://charts.cloudposse.com/incubator/

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

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Affinity for Pod assignment |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `1` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| conf.allowedSources | string | `"'http://domain_or_wildcard', 'comma_seperated'"` |  |
| env.open.ALLOW_UNSAFE_URL | string | `"True"` |  |
| env.open.AUTO_WEBP | string | `"True"` |  |
| env.open.CORS_ALLOW_ORIGIN | string | `"*"` |  |
| env.open.HEALTHCHECK_ROUTE | string | `"/healthcheck"` |  |
| env.open.LOG_LEVEL | string | `"error"` |  |
| env.open.SEND_IF_MODIFIED_LAST_MODIFIED_HEADERS | string | `"True"` | Speed Up Browsing-Experience for Clients. Storage need to support this |
| env.open.THUMBOR_LOG_CONFIG | string | `"None"` | Can be JSON or None |
| env.open.THUMBOR_PORT | string | `"80"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"registry.hub.docker.com/thumbororg/thumbor"` |  |
| image.tag | string | `"7.3-py-3.10"` |  |
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
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
