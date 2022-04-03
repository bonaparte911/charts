# osemu

![Version: 1.0.1](https://img.shields.io/badge/Version-1.0.1-informational?style=flat-square) ![AppVersion: v732](https://img.shields.io/badge/AppVersion-v732-informational?style=flat-square)

OSEmu - Standalone Emu reader for OSCam server

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <https://github.com/oscam-emu/OSEmu>

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
helm install osemu k8s-at-home/osemu
```

## Installing the Chart

To install the chart with the release name `osemu`

```console
helm install osemu k8s-at-home/osemu
```

## Uninstalling the Chart

To uninstall the `osemu` deployment

```console
helm uninstall osemu
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install osemu \
  --set env.TZ="America/New York" \
    k8s-at-home/osemu
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install osemu k8s-at-home/osemu -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below | environment variables. See more parameters in the [osemu documentation](https://github.com/oscam-emu/OSEmu/blob/master/README). |
| env.OSEMU_PASSWORD | string | `"password"` | Set the password [REQUIRED] |
| env.OSEMU_USER | string | `"user"` | Set the user [REQUIRED] |
| env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"ghcr.io/bonaparte911/osemu"` | image repository |
| image.tag | string | `"v732"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| service | object | See values.yaml | Configures service settings for the chart. |
| softCamKey | string | `"#*#*#*#*#*#*#*#*#*#*# KEYS #*#*#*#*#*#*#*#*#*#*#\n"` |  |

## Changelog

### Version 1.0.1

#### Added

* Initial version

#### Changed

N/A

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/k8s-at-home/osemu?modal=changelog)

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/k8s-at-home/charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community
