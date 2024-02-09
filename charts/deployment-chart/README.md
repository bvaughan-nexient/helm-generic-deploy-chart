# deployment-chart

![Version: 0.0.2](https://img.shields.io/badge/Version-0.0.2-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.0.2](https://img.shields.io/badge/AppVersion-0.0.2-informational?style=flat-square)

A generic deployment Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bvaughan-nexient.github.io/helm-library | helm-library | ^2.0.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| autoscaling.enabled | bool | `true` | to create the autoscaler or not |
| autoscaling.maxReplicas | int | `10` | maximum replicas for the autoscaler |
| autoscaling.minReplicas | int | `1` | minimum replicas for the autoscaler |
| autoscaling.name | string | `""` | optional: name of the autoscaler, default is .Values.name |
| autoscaling.targetCPUUtilizationPercentage | int | `80` | target CPU utilization percentage for the autoscaler |
| autoscaling.targetMemoryUtilizationPercentage | int | `80` | target memory utilization percentage for the autoscaler |
| configMap.data | object | `{}` | optional: map of objects to be added to the configmap |
| configMap.name | string | `""` | optional: create a configmap with the given name, default is .Values.name |
| container.args | string | `""` | arguments to pass to the command |
| container.command | string | `""` | command to run in the container |
| container.env | list | `[]` | list of environment variables to add to the container |
| container.image | string | `""` | container image to use |
| container.name | string | `""` | name of the container, default is .Values.name |
| container.pullPolicy | string | `"IfNotPresent"` | pullPolicy for the pod |
| container.resources | object | `{}` | map of attributes to add for container limits and requests |
| container.securityContext | object | `{}` | map of attributes to add to the container securityContext |
| container.volumeMounts | object | `{}` | map of objects of volumes to mount into the container |
| deployment.affinity | object | `{}` | map of labels to add to the deployment to determine node affinity |
| deployment.imagePullSecret | string | `""` | name of secret to use for pulling images from private registry |
| deployment.injectLinkerd | bool | `true` | add label to inject linkerd sidecar |
| deployment.minReadySeconds | int | `0` | optional field that specifies the minimum number of seconds for which a newly created Pod should be ready without any of its containers crashing, for it to be considered available |
| deployment.nodeSelector | object | `{}` | map of labels to use to select nodes to schedule pods onto |
| deployment.podSecurityContext | object | `{}` | map of attributes to add to the deployment podSecurityContext |
| deployment.replicaCount | int | `1` | number of replicas to create, overriden if autoscaling is enabled |
| deployment.tolerations | list | `[]` | list of tolerations to apply to the deployment |
| deployment.volumes | object | `{}` | map of volumes to add to the deployment |
| ingress.annotations | object | `{}` | map of annotations to add to the ingress |
| ingress.className | string | `""` | name of the ingressClass to use |
| ingress.enabled | bool | `false` | to create the ingress or not |
| ingress.hosts | object | `{}` | map of hosts to be configured for the ingress |
| ingress.tls | list | `[]` | tls configuration for the ingress |
| name | string | `"chart"` | required: name of the chart |
| podAnnotations | object | `{}` | optional: annoations to add to the pod deployment |
| podLabels | object | `{}` | optional: labels to add to the pod deployment |
| service.name | string | `"test-chart-service"` | name of the service to create, default is .Values.name |
| service.ports | list | `[{"name":"http","port":80,"targetPort":"http"}]` | map of objects to be created as a service. First service defined will be used for ingress. |
| service.type | string | `"ClusterIP"` | type of service to create |
| serviceAccount.annotations | object | `{}` | optional: annotations to add to the serviceAccount |
| serviceAccount.create | bool | `true` | optional: create a service account with the given name or not, default is false |
| serviceAccount.name | string | `""` | optional: name of the service account, default is .Values.name |

