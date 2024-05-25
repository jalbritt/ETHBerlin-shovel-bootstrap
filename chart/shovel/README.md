# shovel

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.6](https://img.shields.io/badge/AppVersion-1.6-informational?style=flat-square)

Helm chart for shovel

## Maintainers
| Name | Email | Url |
| ---- | ------ | --- |
| laibe |  |  |
| jalbritt |  |  |

## Source Code

* <https://github.com/indexsupply/code>

## Quick Start

TODO

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| fullnameOverride | string | `""` | Overrides the chart's computed fullname |
| global.affinity | object | `{}` | Set affinity |
| global.imagePullSecrets | object | `{}` | A list of pull secrets is used when credentials are needed to access a container registry with username and password. |
| global.nodeSelector | object | `{}` |  |
| global.podMonitor.create | bool | `false` | Create a [PodMonitor](https://github.com/prometheus-operator/prometheus-operator/blob/main/Documentation/user-guides/getting-started.md) |
| global.securityContext | object | `{"fsGroup":1000,"runAsGroup":1000,"runAsNonRoot":true,"runAsUser":1000}` | Pod security context |
| global.service.annotations | object | `{}` | Service annotations |
| global.service.enabled | bool | `true` | Enable Service |
| global.service.type | string | `"ClusterIP"` | Service type, ClusterIP, LoadBalancer or ClusterIP. |
| global.serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| global.serviceAccount.create | bool | `true` | Enable service account (Note: Service Account will only be automatically created if `global.serviceAccount.name` is not set) |
| global.serviceAccount.name | string | `""` | Name of an already existing service account. Setting this value disables the automatic service account creation |
| global.tolerations | list | `[]` |  |
| nameOverride | string | `""` | Overrides the chart's name |
| shovel.containerSecurityContext.runAsGroup | int | `1000` |  |
| shovel.containerSecurityContext.runAsNonRoot | bool | `true` |  |
| shovel.containerSecurityContext.runAsUser | int | `1000` |  |
| shovel.image.pullPolicy | string | `"IfNotPresent"` | Container pull policy |
| shovel.image.repository | string | `"nbtim/shovel"` |  |
| shovel.image.tag | string | `"v1.6"` | Image tag |
| shovel.name | string | `"shovel"` | Name of the container |
| shovel.podAnnotations | object | `{}` | Pod annotation to be added |
| shovel.podLabels | object | `{}` | Pod labels to be added |
| shovel.podMonitor.interval | string | `"30s"` |  |
| shovel.podMonitor.path | string | `"/metrics"` |  |
| shovel.podMonitor.scrapeTimeout | string | `"10s"` |  |
| shovel.ports | object | `{"http":8546,"metrics":9090}` | Static peers settings |
| shovel.ports.http | int | `8546` | Dashboard port |
| shovel.ports.metrics | int | `9090` | Metrics port |
| shovel.resources | object | `{"limits":{"cpu":"2000m","memory":"8Gi"},"requests":{"cpu":"1000m","memory":"4Gi"}}` | Resource requests and limits |
| shovel.shovelConfig.eth_sources[0].chain_id | int | `1` |  |
| shovel.shovelConfig.eth_sources[0].name | string | `"mainnet"` |  |
| shovel.shovelConfig.eth_sources[0].url | string | `"https://ethereum-rpc.publicnode.com"` |  |
| shovel.shovelConfig.integrations[0].block[0].column | string | `"log_addr"` |  |
| shovel.shovelConfig.integrations[0].block[0].filter_arg[0] | string | `"a0b86991c6218b36c1d19d4a2e9eb0ce3606eb48"` |  |
| shovel.shovelConfig.integrations[0].block[0].filter_arg[1] | string | `"833589fCD6eDb6E08f4c7C32D4f71b54bdA02913"` |  |
| shovel.shovelConfig.integrations[0].block[0].filter_op | string | `"contains"` |  |
| shovel.shovelConfig.integrations[0].block[0].name | string | `"log_addr"` |  |
| shovel.shovelConfig.integrations[0].enabled | bool | `true` |  |
| shovel.shovelConfig.integrations[0].event.anonymous | bool | `false` |  |
| shovel.shovelConfig.integrations[0].event.inputs[0].column | string | `"from"` |  |
| shovel.shovelConfig.integrations[0].event.inputs[0].indexed | bool | `true` |  |
| shovel.shovelConfig.integrations[0].event.inputs[0].name | string | `"from"` |  |
| shovel.shovelConfig.integrations[0].event.inputs[0].type | string | `"address"` |  |
| shovel.shovelConfig.integrations[0].event.inputs[1].column | string | `"to"` |  |
| shovel.shovelConfig.integrations[0].event.inputs[1].indexed | bool | `true` |  |
| shovel.shovelConfig.integrations[0].event.inputs[1].name | string | `"to"` |  |
| shovel.shovelConfig.integrations[0].event.inputs[1].type | string | `"address"` |  |
| shovel.shovelConfig.integrations[0].event.inputs[2].column | string | `"value"` |  |
| shovel.shovelConfig.integrations[0].event.inputs[2].name | string | `"value"` |  |
| shovel.shovelConfig.integrations[0].event.inputs[2].type | string | `"uint256"` |  |
| shovel.shovelConfig.integrations[0].event.name | string | `"Transfer"` |  |
| shovel.shovelConfig.integrations[0].event.type | string | `"event"` |  |
| shovel.shovelConfig.integrations[0].name | string | `"usdc-transfer"` |  |
| shovel.shovelConfig.integrations[0].sources[0].name | string | `"mainnet"` |  |
| shovel.shovelConfig.integrations[0].sources[1].name | string | `"base"` |  |
| shovel.shovelConfig.integrations[0].table.columns[0].name | string | `"log_addr"` |  |
| shovel.shovelConfig.integrations[0].table.columns[0].type | string | `"bytea"` |  |
| shovel.shovelConfig.integrations[0].table.columns[1].name | string | `"block_time"` |  |
| shovel.shovelConfig.integrations[0].table.columns[1].type | string | `"numeric"` |  |
| shovel.shovelConfig.integrations[0].table.columns[2].name | string | `"from"` |  |
| shovel.shovelConfig.integrations[0].table.columns[2].type | string | `"bytea"` |  |
| shovel.shovelConfig.integrations[0].table.columns[3].name | string | `"to"` |  |
| shovel.shovelConfig.integrations[0].table.columns[3].type | string | `"bytea"` |  |
| shovel.shovelConfig.integrations[0].table.columns[4].name | string | `"value"` |  |
| shovel.shovelConfig.integrations[0].table.columns[4].type | string | `"numeric"` |  |
| shovel.shovelConfig.integrations[0].table.name | string | `"usdc"` |  |
| shovel.shovelConfig.pg_url | string | `"postgres:///shovel"` |  |