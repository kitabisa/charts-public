# Pandemi chart by Kitabisa
Pandemi is kubernetes controller for global configmap and secrets.
When this controller running, it will create global namespaces for itself, and put the global configmap and secrets into
it.
Then it will distribute it's configmap and secret values to all other namespace by creating new configmap and secret.
It will redistribute if any changes occured in configmap and secret in the global namespace.

You can see in more details how Pandemi works [here](https://github.com/kitabisa/pandemi/blob/master/README.md).

> This is an initial release and not considered stable. Use at your own risk.

## TL;DR
```shell
$ helm repo add kitabisa https://github.com/kitabisa/charts-public
$ helm install my-release kitabisa/pandemi
```

## Installing the Chart
To install the chart with the release name my-release:

```shell
$ helm install my-release kitabisa/pandemi
```
The command deploys Pandemi on the Kubernetes cluster in the default configuration.

## Uninstalling the Chart
To uninstall/delete the my-release deployment:

```shell
$ helm delete my-release
```
The command removes all the Kubernetes components associated with the chart and deletes the release.

## Parameters
| Name                      | Description                                      | Value                      |
| ------------------------- | -------------------------------------------------| -------------------------- |
| `replicaCount`            | The replica count. Should be 1                   | `1`                        |
| `image.repository`        | Docker image repository                          | `kitabisa/pandemi`         |
| `image.pullPolicy`        | Docker image pull policy                         | `Always`                   |
| `image.tag`               | Docker image tag                                 | `latest`                   |
| `namespace`               | Default namespace for pandemi                    | `global`                   |
| `serviceAccountName`      | Default service account name for pandemi         | `pandemi-service-account`  |
| `clusterRole.name`        | Default cluster role name for pandemi            | `pandemi-cluster-role`     |
| `clusterRole.apiGroups`   | Default cluster role api groups for pandemi      | `""`                       |