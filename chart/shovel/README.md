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
## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | postgresql | 15.4.0 |

## Quick Start

```bash
helm install shovel chart/shovel
```

## PostgreSQL

By default the chart will install a postgresql database using the bitnami postgresql chart.
If you want to use your own existing database instead (e.g. managed postgresql or cloudnative-pg),
specify the url in the values.yaml:

```yaml
shovel:
  pgUrl: "postgres:///my-postgresql"
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| fullnameOverride | string | `""` | Overrides the chart's computed fullname |
| global.affinity | object | `{}` | Set affinity |
| global.imagePullSecrets | object | `{}` | A list of pull secrets is used when credentials are needed to access a container registry with username and password. |
| global.nodeSelector | object | `{}` |  |
| global.podMonitor.create | bool | `false` | Create a [PodMonitor](https://github.com/prometheus-operator/prometheus-operator/blob/main/Documentation/user-guides/getting-started.md) |
| global.postgresql.auth.database | string | `"shovel"` |  |
| global.postgresql.auth.password | string | `"shovel"` |  |
| global.postgresql.auth.username | string | `"shovel"` |  |
| global.postgresql.enabled | bool | `true` |  |
| global.securityContext | object | `{"fsGroup":1000,"runAsGroup":1000,"runAsNonRoot":true,"runAsUser":1000}` | Pod security context |
| global.service.annotations | object | `{}` | Service annotations |
| global.service.enabled | bool | `true` | Enable Service |
| global.service.type | string | `"ClusterIP"` | Service type, ClusterIP, LoadBalancer or ClusterIP. |
| global.serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| global.serviceAccount.create | bool | `true` | Enable service account (Note: Service Account will only be automatically created if `global.serviceAccount.name` is not set) |
| global.serviceAccount.name | string | `""` | Name of an already existing service account. Setting this value disables the automatic service account creation |
| global.tolerations | list | `[]` |  |
| nameOverride | string | `""` | Overrides the chart's name |
| shovel.config | object | `{"eth_sources":[{"chain_id":1,"name":"mainnet","url":"https://eth.merkle.io"}],"integrations":[{"block":[{"column":"log_addr","filter_arg":["a0b86991c6218b36c1d19d4a2e9eb0ce3606eb48"],"filter_op":"contains","name":"log_addr"}],"dashboard":{"disable_authn":true},"enabled":true,"event":{"anonymous":false,"inputs":[{"column":"from","indexed":true,"name":"from","type":"address"},{"column":"to","indexed":true,"name":"to","type":"address"},{"column":"value","name":"value","type":"uint256"}],"name":"Transfer","type":"event"},"name":"usdc-transfer","sources":[{"batch_size":1000,"name":"mainnet"}],"table":{"columns":[{"name":"log_addr","type":"bytea"},{"name":"block_time","type":"numeric"},{"name":"from","type":"bytea"},{"name":"to","type":"bytea"},{"name":"value","type":"numeric"}],"name":"usdc"}}],"pg_url":"$PG_URL"}` | shovel config |
| shovel.containerSecurityContext.runAsGroup | int | `1000` |  |
| shovel.containerSecurityContext.runAsNonRoot | bool | `true` |  |
| shovel.containerSecurityContext.runAsUser | int | `1000` |  |
| shovel.image.pullPolicy | string | `"IfNotPresent"` | Container pull policy |
| shovel.image.repository | string | `"nbtim/shovel"` |  |
| shovel.image.tag | string | `"v1.6"` | Image tag |
| shovel.name | string | `"shovel"` | Name of the container |
| shovel.pgUrl | string | `"postgres:///shovel"` | shovel pg_url, use for setting your own postgresql endpoint, by default it uses the integrated postgresql from the bitnami/postgresql dependency |
| shovel.podAnnotations | object | `{}` | Pod annotation to be added |
| shovel.podLabels | object | `{}` | Pod labels to be added |
| shovel.podMonitor.interval | string | `"30s"` |  |
| shovel.podMonitor.path | string | `"/metrics"` |  |
| shovel.podMonitor.scrapeTimeout | string | `"10s"` |  |
| shovel.ports | object | `{"http":8546,"metrics":9090}` | Static peers settings |
| shovel.ports.http | int | `8546` | Dashboard port |
| shovel.ports.metrics | int | `9090` | Metrics port |
| shovel.resources | object | `{"limits":{"cpu":"2000m","memory":"8Gi"},"requests":{"cpu":"1000m","memory":"4Gi"}}` | Resource requests and limits |