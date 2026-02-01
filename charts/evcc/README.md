# evcc

![Version: 1.0.46](https://img.shields.io/badge/Version-1.0.46-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.300.8](https://img.shields.io/badge/AppVersion-0.300.8-informational?style=flat-square)

Helm chart for EVCC (evcc.io)

**Homepage:** <https://evcc.io/>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Affinity to use for the deployment |
| containerPort | int | `7070` |  |
| deploymentStrategy | object | `{"maxSurge":1,"maxUnavailable":0,"type":"RollingUpdate"}` | Specifies the deployment strategy used to replace old Pods by new ones, default: `RollingUpdate` |
| deploymentStrategy.maxSurge | int | `1` | The maximum number of Pods that can be created over the desired number of Pods. |
| deploymentStrategy.maxUnavailable | int | `0` | The maximum number of Pods that can be unavailable during the update. |
| extraVolumeMounts | list | `[]` | Additional volumeMounts on the output Deployment definition. |
| extraVolumes | list | `[]` | Additional volumes on the output Deployment definition. |
| fullnameOverride | string | `""` | This is to override the chart fullname. |
| httproute.annotations | object | `{}` | Annotations for the HTTPRoute |
| httproute.enabled | bool | `false` | Whether to enable HTTPRoute for the deployment |
| httproute.hostnames | list | `["evcc.local"]` | The hostnames to use for the HTTPRoute |
| httproute.parentRef | object | `{}` | The parent reference for the HTTPRoute |
| httproute.rules | list | `[{"matches":[{"path":{"type":"PathPrefix","value":"/"}}]}]` | The rules to use for the HTTPRoute |
| image.pullPolicy | string | `"IfNotPresent"` | Pull policy for the image. |
| image.registry | string | `"docker.io"` | The image registry to pull the image from. |
| image.repository | string | `"evcc/evcc"` | The image repository to pull the image from. |
| image.tag | string | `""` | Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` | The image pull secrets to use for pulling the image. |
| lifecycle | object | `{}` | Lifecycle hooks for the deployment (copy configmap data to correct location) |
| livenessProbe | object | `{"httpGet":{"path":"/","port":"http"},"initialDelaySeconds":10,"timeoutSeconds":5}` | Liveness probe for the deployment |
| nameOverride | string | `""` | This is to override the chart name. |
| nodeSelector | object | `{}` | NodeSelector to use for the deployment |
| persistence.accessMode | string | `"ReadWriteOnce"` | The access mode to use for the persistent volume claim |
| persistence.enabled | bool | `false` | Whether to enable persistence for the deployment |
| persistence.existingClaim | string | `""` | Use an existing PVC to persist data |
| persistence.size | string | `"5Gi"` | The size of the persistent volume claim |
| persistence.storageClass | string | `"-"` | The storage class to use for the persistent volume claim |
| podAnnotations | object | `{}` | Annotations to add to the Pod |
| podLabels | object | `{}` | Labels to add to the Pod. |
| podSecurityContext | object | `{}` | PodSecurityContext to be set on the pod level. |
| readinessProbe | object | `{"httpGet":{"path":"/","port":"http"},"initialDelaySeconds":10,"timeoutSeconds":5}` | Readyiness probe for the deployment |
| replicaCount | int | `1` | Replica count for the deployment |
| resources | object | `{"limits":{"cpu":"100m","memory":"256Mi"},"requests":{"cpu":"10m","memory":"128Mi"}}` | Resources for the deployment |
| restartPolicy | string | `"Always"` | The restart policy for the deployment. |
| revisionHistoryLimit | int | `0` | Revision history limit for the deployment |
| securityContext | object | `{"allowPrivilegeEscalation":false,"capabilities":{"drop":["ALL"]}}` | SecurityContext to be set on the container level. |
| securityContext.allowPrivilegeEscalation | bool | `false` | Whether the container should run as a non-root user runAsNonRoot: true # -- The UID to run the container as runAsUser: 30000 # -- Configures whether the container can request additional privileges |
| securityContext.capabilities | object | `{"drop":["ALL"]}` | Capabilities to add or drop from the container |
| service | object | `{"annotations":{},"port":80,"type":"ClusterIP"}` | Service for the deployment |
| service.annotations | object | `{}` | Annotations for the service |
| service.port | int | `80` | Kubernetes port where service is exposed |
| service.type | string | `"ClusterIP"` | Kubernetes service type |
| serviceAccount | object | `{"annotations":{},"automount":true,"create":false,"name":""}` | Service account |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.automount | bool | `true` | Automatically mount a ServiceAccount's API credentials? |
| serviceAccount.create | bool | `false` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| tolerations | list | `[]` | Tolerations to use for the deployment |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.14.2](https://github.com/norwoodj/helm-docs/releases/v1.14.2)
