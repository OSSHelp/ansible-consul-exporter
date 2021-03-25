# consul-exporter

[![Build Status](https://drone.osshelp.ru/api/badges/ansible/consul-exporter/status.svg)](https://drone.osshelp.ru/ansible/consul-exporter)

This role helps with the installation and configuration of consul_exporer.

## Usage (example)

``` yaml
    - role: consul-exporter
      consul_exporter_params:
        consul:
          server: localhost:8500
          timeout: 10
        log:
          level: info
        web:
          listen_address: localhost:1286
        kv:
          prefix: /
```

## Available parameters

### Main

| Param | Default | Description |
| -------- | -------- | -------- |
| `consul_exporter_setup` | `full` | Setup mode. See [OSSHelp KB article](https://oss.help/kb4895) |
| `consul_exporter_params` | `{}` | Consul exporter configuration parameters |

### Consul-exporter params

See example usage above.

| Param | Default | Description |
| -------- | -------- | -------- |
| `consul.allow_stale` | `-` | Allows any Consul server (non-leader) to service a read |
| `consul.ca_file` | `-` | File path to a PEM-encoded certificate authority used to validate the authenticity of a server certificate |
| `consul.cert_file` | `-` | File path to a PEM-encoded certificate used with the private key to verify the exporter's authenticity |
| `consul.health_summary` | `-` | Collects information about each registered service and exports `consul_catalog_service_node_healthy` |
| `consul.key_file` | `-` | File path to a PEM-encoded private key used with the certificate to verify the exporter's authenticity |
| `consul.insecure` | `-` | Disable TLS host verification |
| `consul.require_consistent` | `-` | Forces the read to be fully consistent |
| `consul.server` | `-` | Address (host and port) of the Consul instance we should connect to |
| `consul.server_name` | `-` | When provided, this overrides the hostname for the TLS certificate |
| `consul.timeout` | `-` | Timeout on HTTP requests to consul |
| `consul.request_limit` | `-` | Limit the maximum number of concurrent requests to consul, 0 means no limit |
| `log.format` | `-` | Set the log target and format |
| `log.level` | `-` | Logging level |
| `web.listen_address` | `-` | Address to listen on for web interface and telemetry |
| `web.telemetry_path` | `-` | Path under which to expose metrics |
| `kv.filter` | `-` | Only store keys that match this regex pattern |
| `kv.prefix` | `-` | Prefix under which to look for KV pairs |

## FAQ

None, so far.

## Useful links

- [Official documentation for consul-exporter](https://github.com/prometheus/consul_exporter)
- [Official documentation for Consul](https://www.consul.io/docs)
- [Prometheus documentation on exporters](https://prometheus.io/docs/instrumenting/exporters/)

## TODO

None, so far.

## License

GPL3

## Author

OSSHelp Team, see <https://oss.help>
