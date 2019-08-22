# goldilocks

A chart for installing [goldilocks](https://github.com/FairwindsOps/goldilocks)

## Requirements

This has a hard requirement on VPA being installed. Please see the [Goldilocks README](https://github.com/fairwindsops/goldilocks)

VPA Can be installed using a post-install hook if `installVPA` is set to true in the values.

## Usage

| Parameter                              | Description                                                                                                                      | Default                        |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------|
| `installVPA`                           | Whether or not to install the VPA controller from the vpa repository                                                             | false                          |
| `image.pullPolicy`                     | imagePullPolicy - Highly recommended to leave this as `Always`                                                                   | `Always`                       |
| `image.repository`                     | Repository for the goldilocks image                                                                                              | `quay.io/fairwinds/goldilocks` |
| `image.tag`                            | The goldilocks image tag to use                                                                                                  | `v1.2.2`                       |
| `controller.enabled`                   | Whether or not to install the controller deployment                                                                              | `True`                         |
| `controller.affinity`                  | Affinity for the controller pod                                                                                                  | `{}`                           |
| `controller.nodeSelector`              | Node selector for the controller pod                                                                                             | `{}`                           |
| `controller.rbac.create`               | If set to true, rbac resources will be created for the controller                                                                | `True`                         |
| `controller.resources.limits.cpu`      | Controller cpu limit                                                                                                             | `25m`                          |
| `controller.resources.limits.memory`   | Controller memory limit                                                                                                          | `32Mi`                         |
| `controller.resources.requests.cpu`    | Controller CPU request                                                                                                           | `25m`                          |
| `controller.resources.requests.memory` | Controller memory request                                                                                                        | `32Mi`                         |
| `controller.serviceAccount.create`     | If true, a service account will be created for the controller. If set to false, you must set `controller.serviceAccount.name`    | `True`                         |
| `controller.serviceAccount.name`       | The name of an existing service account to use for the controller                                                                | ``                             |
| `controller.tolerations`               | Tolerations for the controller pod                                                                                               | `[]`                           |
| `dashboard.enabled`                    | If true, the dashboard component will be installed.                                                                              | `True`                         |
| `dashboard.affinity`                   | Affinity for the dashbaord pods.                                                                                                 | `{}`                           |
| `dashboard.excludeContainer`           | A comma-separated list of container names to ignore in the dashboard globally.                                                   | `linkderd-proxy,istio-proxy`   |
| `dashboard.ingress.enabled`            | If true, an ingress object will be created. Further configuration is necessary. See [values.yaml](values.yaml) for an example.   | `False`                        |
| `dashboard.ingress.annotations`        | Annotations on the ingress object.                                                                                               | `{}`                           |
| `dashboard.ingress.hosts.0.host`       | Ingress host. See [values.yaml](values.yaml) for an example.                                                                     | `chart-example.local`          |
| `dashboard.ingress.hosts.0.paths`      | Ingress path. See [values.yaml](values.yaml) for an example.                                                                     | `[]`                           |
| `dashboard.ingress.tls`                | Ingress TLS block. See [values.yaml](values.yaml) for an example.                                                                | `[]`                           |
| `dashboard.logVerbosity`               | Dashboard log verbosity. Can be set from 1-10 with 10 being the most verbose                                                     | `2`                            |
| `dashboard.nodeSelector`               | Node selector for dashboard pods                                                                                                 | `{}`                           |
| `dashboard.rbac.create`                | If true, rbac resources will be created for the dashboard service account                                                        | `True`                         |
| `dashboard.replicaCount`               | Number of dashboard pods to run                                                                                                  | `2`                            |
| `dashboard.resources.limits.cpu`       | Dashboard CPU limit                                                                                                              | `25m`                          |
| `dashboard.resources.limits.memory`    | Dashboard memory limits                                                                                                          | `32Mi`                         |
| `dashboard.resources.requests.cpu`     | Dashboard CPU request                                                                                                            | `25m`                          |
| `dashboard.resources.requests.memory`  | Dashboard memory request                                                                                                         | `32Mi`                         |
| `dashboard.service.port`               | Dashboard service port.                                                                                                          | `80`                           |
| `dashboard.service.type`               | Servvice type for the dashboard service.                                                                                         | `ClusterIP`                    |
| `dashboard.serviceAccount.create`      | If true, a service account will be created for the dashboard. If set to false, then you must set `dashboard.serviceAccount.name` | `True`                         |
| `dashboard.serviceAccount.name`        | The name of an existing service account to use for the dashboard.                                                                | ``                             |
| `dashboard.tolerations`                | Tolerations for the dashboard pod                                                                                                | `[]`                           |
| `fullnameOverride`                     | Override the fullName in the chart                                                                                               | ``                             |
| `nameOverride`                         | Override the name field in the chart                                                                                             | ``                             |