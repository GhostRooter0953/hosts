# hosts

Role to configure `/etc/hosts` and `/etc/hostname`.

## Usage (example)

```yaml
- role: hosts
  hosts_entries:
    - 8.8.8.8 gns1 googledns1
    - 8.8.4.4 gns2 googledns2
  hosts_ourserver:
    fqdn: 'some-domain.tld'
    ipv4: '69.89.31.226'
    ipv6: '2002:4559:1FE2::4559:1FE2'
```

## Available parameters

### Main

| Param | Default | Description |
| -------- | -------- | -------- |
| `hosts_setup` | `full` | Setup mode |
| `hosts_entries` | `[]` | List of custom `/etc/hosts` file entries |

### Hostname control

| Param | Default | Description |
| -------- | -------- | -------- |
| `hosts_ourserver.fqdn` | - | Fqdn to generate `/etc/hostname` from. |
| `hosts_ourserver.ipv4`, `hosts_ourserver.ipv6` | - | These will be used to create aliases for `hosts_ourserver.fqdn` in `/etc/hosts` |

## TODO

- autogenerate entries for lxc containers
