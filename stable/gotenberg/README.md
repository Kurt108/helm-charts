# Gotenberg

[Gotenberg](https://thecodingmachine.github.io/gotenberg) is a Docker-powered stateless API for converting HTML, Markdown and Office documents to PDF.

## Installing the Chart

```console
$ helm repo add kurt108 https://kurt108.github.io/helm-gotenberg
"kurt108" has been added to your repositories
$ helm repo update
Hang tight while we grab the latest from your chart repositories...
...Successfully got an update from the "kurt108" chart repository
...
Update Complete. ⎈ Happy Helming!⎈
$ helm install my-release kurt108/gotenberg
NAME: my-release
LAST DEPLOYED: Mon Sep 14 10:20:30 2020
NAMESPACE: sulu
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
1. Get the application URL by running these commands:
  export POD_NAME=$(kubectl get pods --namespace sulu -l "app=gotenberg,release=my-release" -o jsonpath="{.items[0].metadata.name}")
  echo "Visit http://127.0.0.1:3000 to use your application"
  kubectl port-forward $POD_NAME 3000:3000


```

## Introduction

This chart bootstraps a [Gotenberg](https://thecodingmachine.github.io/gotenberg) deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

## Prerequisites

- Kubernetes 1.4+ with Beta APIs enabled
- PV provisioner support in the underlying infrastructure

The command deploys Gotenberg on the Kubernetes cluster in the default configuration. The [configuration](#configuration) section lists the parameters that can be configured during installation.

> **Tip**: List all releases using `helm list`

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```console
$ helm delete my-release
release "my-release" uninstalled
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

The following table lists the configurable parameters of the Gotenberg chart and their default values.

|              Parameter               |               Description                                  |                   Default                     |
|--------------------------------------|------------------------------------------------------------|-----------------------------------------------|
| `image.repository`                   | DokuWiki image name                                        | `thecodingmachine/gotenberg`                   |
| `image.tag`                          | DokuWiki image tag                                         | `{VERSION}`                                   |
| `image.pullPolicy`                   | Image pull policy                                          | `IfNotpresent`                                |
| `basicAuth.enabled`                  | Secure service by basicAuth                                | `false`                                       |
| `basicAuth.username`                 | Username for BasicAuth                                     | `convert`                                       |
| `basicAuth.passwordMD5`              | Password Hash using htpasswd                               | `convert`                                       |
| `service.type`                       | Kubernetes Service type                                    | `CluserIP`                                    |
| `service.port`                       | Service HTTP port                                          | `3000`                                        |
| `ingress.enabled`                    | Enable ingress controller resource                         | `false`                                       |
| `ingress.hosts[0].name`              | Hostname to your DokuWiki installation                     | `gotenberg.local`                             |
| `ingress.hosts[0].path`              | Path within the url structure                              | `/`                                           |
| `ingress.hosts[0].tls`               | Utilize TLS backend in ingress                             | `false`                                       |
| `ingress.hosts[0].certManager`       | Add annotations for cert-manager                           | `false`                                       |
| `ingress.hosts[0].tlsSecret`         | TLS Secret (certificates)                                  | `gotenberg.local-tls`                         |
| `ingress.hosts[0].annotations`       | Annotations for this host's ingress record                 | `[]`                                          |
| `ingress.secrets[0].name`            | TLS Secret Name                                            | `nil`                                         |
| `ingress.secrets[0].certificate`     | TLS Secret Certificate                                     | `nil`                                         |
| `ingress.secrets[0].key`             | TLS Secret Key                                             | `nil`                                         |
| `resources`                          | CPU/Memory resource requests/limits                        | `nil`                                         |
| `livenessProbe.enabled`              | Enable/disable the liveness probe                          | `true`                                        |
| `livenessProbe.initialDelaySeconds`  | Delay before liveness probe is initiated                   | 120                                           |
| `livenessProbe.periodSeconds`        | How often to perform the probe                             | 10                                            |
| `livenessProbe.timeoutSeconds`       | When the probe times out                                   | 5                                             |
| `livenessProbe.failureThreshold`     | Minimum consecutive failures to be considered failed       | 6                                             |
| `livenessProbe.successThreshold`     | Minimum consecutive successes to be considered successful  | 1                                             |
| `readinessProbe.enabled`             | Enable/disable the readiness probe                         | `true`                                        |
| `readinessProbe.initialDelaySeconds` | Delay before readinessProbe is initiated                   | 30                                            |
| `readinessProbe.periodSeconds`    | How often to perform the probe                             | 10                                            |
| `readinessProbe.timeoutSeconds`      | When the probe times out                                   | 5                                             |
| `readinessProbe.failureThreshold`    | Minimum consecutive failures to be considered failed       | 6                                             |
| `readinessProbe.successThreshold`    | Minimum consecutive successes to be considered successful  | 1                                             |
| `nodeSelector`                       | Node labels for pod assignment                             | `{}`                                          |
| `affinity`                           | Affinity settings for pod assignment                       | `{}`                                          |
| `tolerations`                        | Toleration labels for pod assignment                       | `[]`                                          |
| `annotations`                     | Pod annotations                                            | `{}`                                          |
| `metrics.enabled`                    | Start a side-car prometheus exporter                       | `false`                                       |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example,

```console
$ helm install --name my-release \
  --set image.tag=3 \
    stable/gotenberg
```

The above command sets the Docker tag to 3.0.

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart. For example,

```console
$ helm install my-release -f values.yaml stable/gotenberg
```

> **Tip**: You can use the default [values.yaml](values.yaml)
