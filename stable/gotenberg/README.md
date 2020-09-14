gotenberg
=========
Gotenberg is a Docker-powered stateless API for converting HTML, Markdown and Office documents to PDF.

Current chart version is `2.0.0`





## Chart Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| annotations | object | `{}` |  |
| basicAuth.enabled | bool | `false` |  |
| basicAuth.passwordMD5 | string | `"$apr1$zQ7F0fKS$X3aXkUCufHQlVe51VWUKu1"` |  |
| basicAuth.username | string | `"convert"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"thecodingmachine/gotenberg"` |  |
| image.tag | string | `"6.2.1"` |  |
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
