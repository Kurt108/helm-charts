[![Artifact HUB](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/kurt108)](https://artifacthub.io/packages/search?repo=kurt108)

# # offen

A chart containing offen

0.0.1

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
$ helm install my-release kurt108/offen
NAME: my-release
...
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `1` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| env.open.OFFEN_SERVER_REVERSEPROXY | bool | `true` |  |
| env.open.OFFEN_SMTP_HOST | string | `"mailhog"` |  |
| env.secret.OFFEN_SECRETS | string | `"as_env_var"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"index.docker.io/offen/offen"` |  |
| image.tag | string | `"v0.3.0"` |  |
| ingress.hosts[0] | string | `"offen.domain"` |  |
| mariadb-galera.enabled | bool | `false` |  |
| mariadb-galera.remote | bool | `false` |  |
| replicaCount | int | `1` |  |
| resources.limits.cpu | int | `1` |  |
| resources.limits.memory | string | `"512Mi"` |  |
| resources.requests.cpu | float | `0.5` |  |
| resources.requests.memory | string | `"512Mi"` |  |
| service.name | string | `"offen"` |  |
| service.type | string | `"ClusterIP"` |  |
