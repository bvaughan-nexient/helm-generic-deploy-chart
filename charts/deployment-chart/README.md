# deploymentChart

![Version: 0.0.1](https://img.shields.io/badge/Version-0.0.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.0.1](https://img.shields.io/badge/AppVersion-0.0.1-informational?style=flat-square)

A generic deployment Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bvaughan-nexient.github.io/helm-library | helm-library | ^2.0.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| autoscaling.enabled | bool | `true` |  |
| autoscaling.maxReplicas | int | `10` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.name | string | `""` | optional: name of the autoscaler, default is .Values.name |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| autoscaling.targetMemoryUtilizationPercentage | int | `80` |  |
| configMap.data | object | `{}` | optional: map of objects to be added to the configmap |
| configMap.name | string | `""` | optional: create a configmap with the given name, default is .Values.name |
| container.args | string | `""` |  |
| container.command | string | `""` |  |
| container.env | list | `[]` |  |
| container.image | string | `""` |  |
| container.name | string | `""` |  |
| container.pullPolicy | string | `"IfNotPresent"` |  |
| container.resources | object | `{}` |  |
| container.securityContext | object | `{}` |  |
| container.volumeMounts | object | `{}` |  |
| deployment.affinity | object | `{}` |  |
| deployment.imagePullSecret | string | `""` |  |
| deployment.injectLinkerd | bool | `true` |  |
| deployment.minReadySeconds | int | `0` |  |
| deployment.nodeSelector | object | `{}` |  |
| deployment.podSecurityContext | object | `{}` |  |
| deployment.replicaCount | int | `1` |  |
| deployment.tolerations | list | `[]` |  |
| deployment.volumes | object | `{}` |  |
| ingress.annotations | object | `{}` |  |
| ingress.className | string | `""` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts | object | `{}` |  |
| ingress.tls | list | `[]` |  |
| name | string | `"chart"` | required: name of the chart |
| podAnnotations | object | `{}` |  |
| podLabels | object | `{}` |  |
| service.name | string | `"test-chart-service"` |  |
| service.ports | list | `[{"name":"http","port":80,"targetPort":"http"}]` | map of objects to be created as a service. First service defined will be used for ingress. |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |

