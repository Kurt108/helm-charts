[![Artifact HUB](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/kurt108)](https://artifacthub.io/packages/search?repo=kurt108)

# statping

A chart containing statping

0.0.2

Installing the Chart

```console
$ helm repo add kurt108 https://kurt108.github.io/helm-charts
"kurt108" has been added to your repositories
$ helm repo update
Hang tight while we grab the latest from your chart repositories...
...Successfully got an update from the "kurt108" chart repository
...
Update Complete. ⎈ Happy Helming!⎈
$ helm install my-release kurt108/statping
NAME: my-release
...
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"statping/statping"` |  |
| image.tag | string | `"v0.90.74"` |  |
| ingress.annotations | object | `{}` |  |
| ingress.hosts[0] | string | `"statping.domain"` |  |
| ingress.path | string | `"/"` |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| service.name | string | `"statping"` |  |
| service.type | string | `"ClusterIP"` |  |