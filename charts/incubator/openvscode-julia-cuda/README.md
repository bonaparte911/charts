# openvscode-julia-cuda

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![AppVersion: 11.6.2-cudnn8-devel-ubuntu20.04-1.7.3-1.68.0](https://img.shields.io/badge/AppVersion-11.6.2--cudnn8--devel--ubuntu20.04--1.7.3--1.68.0-informational?style=flat-square)

Visual Studio Code Server with an installation of julia lang with cuda support

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <https://github.com/gitpod-io/openvscode-server>
* <https://github.com/JuliaLang/julia>
* <https://gitlab.com/nvidia/container-images/cuda>

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
helm install openvscode-julia-cuda k8s-at-home/openvscode-julia-cuda
```

## Installing the Chart

To install the chart with the release name `openvscode-julia-cuda`

```console
helm install openvscode-julia-cuda k8s-at-home/openvscode-julia-cuda
```

## Uninstalling the Chart

To uninstall the `openvscode-julia-cuda` deployment

```console
helm uninstall openvscode-julia-cuda
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install openvscode-julia-cuda \
  --set env.TZ="America/New York" \
    k8s-at-home/openvscode-julia-cuda
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install openvscode-julia-cuda k8s-at-home/openvscode-julia-cuda -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below | environment variables. See more environment variables and parameters in the corresponding documentations of [openvscode](https://github.com/gitpod-io/openvscode-server), [Julia](https://docs.julialang.org/en/v1/manual/environment-variables/) and [cuda](https://docs.nvidia.com/cuda/cuda-c-programming-guide/index.html#env-vars). |
| env.CONNECTION_SECRET | string | `nil` | Path to a file (ie. /path/to/file) inside the container that contains the security token that overrides CONNECTION_TOKEN. [OPTIONAL] |
| env.CONNECTION_TOKEN | string | `nil` | Security token for accessing the Web UI. [OPTIONAL] |
| env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"ghcr.io/bonaparte911/openvscode-julia-cuda"` | image repository |
| image.tag | string | `"v11.6.2-cudnn8-devel-ubuntu20.04-1.7.3-1.68.0"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

### Version 1.0.0

#### Added

* Initial version

#### Changed

N/A

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/k8s-at-home/openvscode-julia-cuda?modal=changelog)

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/k8s-at-home/charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community
