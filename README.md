# pihole Helm Chart

**Warning**: Chart is still under development.

- [Installing](#installing)
- [Configuration](#configuration)

## Installing

* Add the Konkube Helm charts repo:
`helm repo add konkube https://`

* Install it:
  - with Helm 3: `helm upgrade -i pihole --namespace pihole --create-namespace ./pihole-1.0.0.tgz -f pihole-values.yaml`

## Configuration
| Parameter             | Description                                                                                                                     | Default         |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------|-----------------|
| `nameOverride`        | Overrides the chart name for resources.                                                                                         | `""`            |
| `fullnameOverride`    | Overrides the full name of the resources.                                                                                       | `""`            |
| `image`               | The pihole image                                                                                                                | `pihole/pihole` |
| `imageTag`            | The pihole image tag                                                                                                            | `2021.10`       |
| `imagePullPolicy`     | The imagePullPolicy value                                                                                                       | `IfNotPresent`  |
| `imagePullSecrets`    | The imagePullSecrets configuration                                                                                              | `[]`            |
| `updateStrategy`      | Update Strategy value                                                                                                           | `RollingUpdate` |
| `labels`              | Additional Labels which will be applied                                                                                         | `{}`            |
| `podAnnotations`      | Additional annotations which will be applied                                                                                    | `{}`            |
| `nodeSelector`        | Configurable nodeSelector                                                                                                       | `{}`            |
| `tolerations`         | Configurable tolerations                                                                                                        | `[]`            |
| `affinity`            | Configurable affinity                                                                                                           | `{}`            |
| `service`             | Add container services and service ports                                                                                        | `""`            |
| `extraEnvs`           | Additional environment variables which can be defined in the values.yaml. (Available options are commented out)                 | `[]`            |
| `envFrom`             | Additional option for setting environment variables using templatable string of envFrom                                         | `[]`            |
| `secretMounts`        | Enables to mount a secret as a file                                                                                             | `[]`            |
| `encryptedSecrets`    | Enables the use of sealed secrets and refered it as the WEBPASSWORD variable (if not set a secret will be generated as default) | `{}`            |
| `resources`           | Allows you to set the resources                                                                                                 | see values.yaml |
| `podSecurityContext`  | Configurable podSecurityContext                                                                                                 | see values.yaml |
| `securityContext`     | Configurable securityContext                                                                                                    | see values.yaml |
| `priorityClassName`   | The name of the PriorityClass                                                                                                   | `""`            |
| `extraConfigMap`      | Allows you to add any config files to the pods                                                                                  | see values.yaml |
| `extraVolumes`        | Templatable string of additional volumes                                                                                        | `[]`            |
| `extraVolumeMounts`   | Templatable string of additional volumeMounts                                                                                   | `[]`            |
| `extraContainers`     | Templatable string of additional containers                                                                                     | `""`            |
| `extraInitContainers` | Templatable string of additional containers                                                                                     | `""`            |
| `ingress`             | Configurable ingress                                                                                                            | see values.yaml |
| `readinessProbe`      | Parameters to pass to readiness probe                                                                                           | see values.yaml |
| `livenessProbe`       | Parameters to pass to liveness probe                                                                                            | see values.yaml |
| `lifecycle`           | Allows you to add lifecycle configuration.                                                                                      | `{}`            |
| `hostAliases`         | Adds the ability to configure hostAliases                                                                                       | `[]`            |
| `podDnsConfig`        | Enables the ability to set specific DNS configuration to the pods                                                               | `{}`            |

## Build
helm package pihole