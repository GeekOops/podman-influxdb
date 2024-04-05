# podman-influxdb

Installs a `influxdb` podman container as system service.

## Requirements

Basic ansible, no further dependencies.

## Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `influxdb_container_image` | 'docker.io/library/influxdb:2.7' | Container image to be used |
| `influxdb_config_dir` | `'/etc/influxdb'` | Configuration directory on the host |
| `influxdb_data_dir` | `'/srv/influxdb'` | Data directory on the host |
| `influxdb_service_name` | `'influxdb' | Service name (systemd and container) |
| `influxdb_auto_update` | `true` | If true, podman auto update will be enabled for the resulting container |
| `influxdb_container_network` | `'podman'` | podman network to be used |
| `influxdb_container_ip` |  | If defined, set the following ip for the container |
| `influxdb_mem_limit` | '512M' | If defined, limit the container to this amount of memory |
| `influxdb_publish` | `'[::]:8086:8086/tcp'` and `'8086:8086/tcp'` | List of ports to be published by podman |

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: podman-influxdb
           vars:
             influxdb_container_ip: '10.88.0.2'
             influxdb_mem_limit: '512M'
             influxdb_publish:
               - '[::]:8086:8086/tcp'
               - '8086:8086/tcp'

## License

[`MIT`](LICENSE)

## Author Information

phoenix
