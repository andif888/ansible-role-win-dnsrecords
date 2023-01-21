# ansible-role-win-dnsrecords

Role to add, remove DNS records and zones on a Windows DNS Server

## Table of content

- [Default Variables](#default-variables)
  - [win_dns_records_add_list](#win_dns_records_add_list)
  - [win_dns_records_remove_list](#win_dns_records_remove_list)
  - [win_dns_zone_add_list](#win_dns_zone_add_list)
  - [win_dns_zone_remove_list](#win_dns_zone_remove_list)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Default Variables

### win_dns_records_add_list

dns records to add

#### Default value

```YAML
win_dns_records_add_list: []
```

#### Example usage

```YAML
win_dns_records_add_list:
  - name: "somehost"
    ttl: 180
    type: "A"
    value: "192.168.232.10"
    zone: "acme.local"
  - name: "otherhost"
    ttl: 180
    type: "CNAME"
    value: "somehost.acme.local"
    zone: "acme.local"
```

### win_dns_records_remove_list

dns records to remove

#### Default value

```YAML
win_dns_records_remove_list: []
```

#### Example usage

```YAML
win_dns_records_remove_list:
  - name: "somehost"
    type: "A"
    value: "192.168.232.10"
    zone: "acme.local"
  - name: "otherhost"
    type: "CNAME"
    value: "somehost.acme.local"
    zone: "acme.local"
```

### win_dns_zone_add_list

dns zones to add

#### Default value

```YAML
win_dns_zone_add_list: []
```

#### Example usage

```YAML
win_dns_zone_add_list:
  - name: "acme.local"
    dynamic_update: "secure"
    replication: "domain"
    type: "primary"
  - name: "232.168.192.in-addr.arpa"
    dynamic_update: "secure"
    replication: "domain"
    type: "primary"
```

### win_dns_zone_remove_list

dns zones to remove

#### Default value

```YAML
win_dns_zone_remove_list: []
```

#### Example usage

```YAML
win_dns_zone_remove_list:
  - "acme.local"
  - "232.168.192.in-addr.arpa"
```



## Dependencies

None.

## License

license (GPL-2.0-or-later, MIT, etc)

## Author

andif888
