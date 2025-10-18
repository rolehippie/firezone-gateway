# firezone-gateway

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/firezone-gateway)
[![General Workflow](https://github.com/rolehippie/firezone-gateway/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/firezone-gateway/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/firezone-gateway/actions/workflows/docs.yml/badge.svg)](https://github.com/rolehippie/firezone-gateway/actions/workflows/docs.yml)
[![Galaxy Workflow](https://github.com/rolehippie/firezone-gateway/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/firezone-gateway/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/firezone-gateway)](https://github.com/rolehippie/firezone-gateway/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.firezone__gateway-blue)](https://galaxy.ansible.com/rolehippie/firezone_gateway)

Ansible role to install and configure a Firezone gateway.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [firezone_gateway_caps](#firezone_gateway_caps)
  - [firezone_gateway_devices](#firezone_gateway_devices)
  - [firezone_gateway_ident](#firezone_gateway_ident)
  - [firezone_gateway_image](#firezone_gateway_image)
  - [firezone_gateway_log_level](#firezone_gateway_log_level)
  - [firezone_gateway_name](#firezone_gateway_name)
  - [firezone_gateway_network](#firezone_gateway_network)
  - [firezone_gateway_no_telemetry](#firezone_gateway_no_telemetry)
  - [firezone_gateway_num_tun_threads](#firezone_gateway_num_tun_threads)
  - [firezone_gateway_pull_image](#firezone_gateway_pull_image)
  - [firezone_gateway_sysctls](#firezone_gateway_sysctls)
  - [firezone_gateway_token](#firezone_gateway_token)
  - [firezone_gateway_version](#firezone_gateway_version)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`

## Default Variables

### firezone_gateway_caps

List of capability settings

#### Default value

```YAML
firezone_gateway_caps:
  - NET_ADMIN
```

### firezone_gateway_devices

List of required devices

#### Default value

```YAML
firezone_gateway_devices:
  - /dev/net/tun:/dev/net/tun
```

### firezone_gateway_ident

Identifier of the firezone gateway

#### Default value

```YAML
firezone_gateway_ident:
```

### firezone_gateway_image

Docker image to use and run

#### Default value

```YAML
firezone_gateway_image: ghcr.io/firezone/gateway:{{ firezone_gateway_version }}
```

### firezone_gateway_log_level

Log level of the forezone gateway

#### Default value

```YAML
firezone_gateway_log_level: info
```

### firezone_gateway_name

Name of the firezone gateway

#### Default value

```YAML
firezone_gateway_name: '{{ inventory_hostname }}'
```

### firezone_gateway_network

A Docker network to assign the container

#### Default value

```YAML
firezone_gateway_network:
```

### firezone_gateway_no_telemetry

Disable telemtry collection

#### Default value

```YAML
firezone_gateway_no_telemetry: false
```

### firezone_gateway_num_tun_threads

Number of TUN threads

#### Default value

```YAML
firezone_gateway_num_tun_threads: 1
```

### firezone_gateway_pull_image

Pull image as part of the tasks

#### Default value

```YAML
firezone_gateway_pull_image: true
```

### firezone_gateway_sysctls

List of sysctl settings

#### Default value

```YAML
firezone_gateway_sysctls:
  - net.ipv4.ip_forward=1
  - net.ipv4.conf.all.src_valid_mark=1
  - net.ipv6.conf.all.disable_ipv6=0
  - net.ipv6.conf.all.forwarding=1
  - net.ipv6.conf.default.forwarding=1
```

### firezone_gateway_token

Token of the firezone gateway

#### Default value

```YAML
firezone_gateway_token:
```

### firezone_gateway_version

Version of the Docker image

#### Default value

```YAML
firezone_gateway_version: 1.4.17
```

## Discovered Tags

**_firezone-gateway_**

## Dependencies

- [rolehippie.docker](https://github.com/rolehippie/docker)
- [community.docker](https://github.com/ansible-collections/community.docker)

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
