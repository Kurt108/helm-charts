[![Artifact HUB](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/kurt108)](https://artifacthub.io/packages/search?repo=kurt108)


# gotenberg
=========
Gotenberg is a Docker-powered stateless API for converting HTML, Markdown and Office documents to PDF.

Current chart version is `2.1.7`

Installing the Chart

```console
$ helm repo add kurt108 https://kurt108.github.io/helm-charts
"kurt108" has been added to your repositories
$ helm repo update
Hang tight while we grab the latest from your chart repositories...
...Successfully got an update from the "kurt108" chart repository
...
Update Complete. ⎈ Happy Helming!⎈
$ helm install my-release kurt108/gotenberg
NAME: my-release
...
```



## Chart Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| annotations | object | `{}` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `1` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| basicAuth.enabled | bool | `false` |  |
| basicAuth.passwordMD5 | string | `"$apr1$zQ7F0fKS$X3aXkUCufHQlVe51VWUKu1"` |  |
| basicAuth.username | string | `"convert"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"thecodingmachine/gotenberg"` |  |
| image.tag | string | `"6.3.0"` |  |
| ingress.annotations | object | `{}` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts[0] | string | `"gotenberg.local"` |  |
| ingress.path | string | `"/"` |  |
| ingress.tls | list | `[]` |  |
| nodeSelector | object | `{}` |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| service.port | int | `3000` |  |
| service.type | string | `"ClusterIP"` |  |
| tolerations | list | `[]` |  |