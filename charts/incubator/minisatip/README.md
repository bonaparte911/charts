# minisatip

![Version: 1.0.3](https://img.shields.io/badge/Version-1.0.3-informational?style=flat-square) ![AppVersion: version-30c4f08a](https://img.shields.io/badge/AppVersion-version--30c4f08a-informational?style=flat-square)

minisatip - A multi-threaded satip server version 1.2

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <https://github.com/catalinii/minisatip>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://library-charts.k8s-at-home.com | common | 4.3.0 |

## TL;DR

```console
helm repo add k8s-at-home https://k8s-at-home.com/charts/
helm repo update
helm install minisatip k8s-at-home/minisatip
```

## Installing the Chart

To install the chart with the release name `minisatip`

```console
helm install minisatip k8s-at-home/minisatip
```

## Uninstalling the Chart

To uninstall the `minisatip` deployment

```console
helm uninstall minisatip
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install minisatip \
  --set env.TZ="America/New York" \
    k8s-at-home/minisatip
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install minisatip k8s-at-home/minisatip -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below | environment variables. See more parameters in the [linuxserver documentation](https://github.com/linuxserver/docker-minisatip/pkgs/container/minisatip#parameters). |
| env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"ghcr.io/linuxserver/minisatip"` | image repository |
| image.tag | string | `"version-30c4f08a"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| persistence.dvb | object | See values.yaml | Configure a hostPathMount to mount dvb device in the container. |
| securityContext | object | See values.yaml | Configuration of security context. |
| securityContext.privileged | bool | `false` | (bool) Privileged securityContext may be required if dvb devics are accessed directly through the host machine |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

### Version 1.0.3

#### Added

* Initial version

#### Changed

N/A

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/k8s-at-home/minisatip?modal=changelog)

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/k8s-at-home/charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community
