# oscam

![Version: 1.0.2](https://img.shields.io/badge/Version-1.0.2-informational?style=flat-square) ![AppVersion: 11704-ls37](https://img.shields.io/badge/AppVersion-11704--ls37-informational?style=flat-square)

oscam - Open Source Conditional Access Module software used for descrambling DVB transmissions using smart cards.

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <http://www.streamboard.tv/oscam/>

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
helm install oscam k8s-at-home/oscam
```

## Installing the Chart

To install the chart with the release name `oscam`

```console
helm install oscam k8s-at-home/oscam
```

## Uninstalling the Chart

To uninstall the `oscam` deployment

```console
helm uninstall oscam
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install oscam \
  --set env.TZ="America/New York" \
    k8s-at-home/oscam
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install oscam k8s-at-home/oscam -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below | environment variables. See more parameters in the [linuxserver documentation](https://github.com/linuxserver/docker-oscam/pkgs/container/oscam#parameters). |
| env.TZ | string | `"UTC"` | Set the container timezone |
| global.oscamConfig.oscamConf | string | `"[global]\nlogfile       = stdout\n\n[cache]\n\n[webif]\nhttpport      = 8888\nhttpallowed   = 127.0.0.1,192.168.0.0-192.168.255.255,10.0.0.0-10.255.255.255,255.255.255.255\n"` |  |
| global.oscamConfig.oscamServer | string | `""` |  |
| global.oscamConfig.oscamUser | string | `""` |  |
| global.oscamConfig.softCamKey | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"ghcr.io/linuxserver/oscam"` | image repository |
| image.tag | string | `"11704-ls37"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| persistence.reader | object | See values.yaml | Configure hostPathMount(s) to mount (multiple) smart card reader devices in the container. -- See more variants [@linuxserver.io](https://github.com/linuxserver/docker-oscam#passing-through-smart-card-readers). |
| securityContext | object | See values.yaml | Configure persistence settings for the chart under this key. |
| securityContext.privileged | bool | `false` | (bool) Privileged securityContext may be required if smart card devices are accessed directly through the host machine |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

### Version 1.0.2

#### Added

* Initial version

#### Changed

N/A

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/k8s-at-home/oscam?modal=changelog)

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/k8s-at-home/charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community
