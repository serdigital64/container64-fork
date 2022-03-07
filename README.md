# Project: Container64

```shell linenums="0"
   █████████                       █████               ███                                 ████████  █████ █████
  ███░░░░░███                     ░░███               ░░░                                 ███░░░░███░░███ ░░███
 ███     ░░░   ██████  ████████   ███████    ██████   ████  ████████    ██████  ████████ ░███   ░░░  ░███  ░███ █
░███          ███░░███░░███░░███ ░░░███░    ░░░░░███ ░░███ ░░███░░███  ███░░███░░███░░███░█████████  ░███████████
░███         ░███ ░███ ░███ ░███   ░███      ███████  ░███  ░███ ░███ ░███████  ░███ ░░░ ░███░░░░███ ░░░░░░░███░█
░░███     ███░███ ░███ ░███ ░███   ░███ ███ ███░░███  ░███  ░███ ░███ ░███░░░   ░███     ░███   ░███       ░███░
 ░░█████████ ░░██████  ████ █████  ░░█████ ░░████████ █████ ████ █████░░██████  █████    ░░████████        █████
  ░░░░░░░░░   ░░░░░░  ░░░░ ░░░░░    ░░░░░   ░░░░░░░░ ░░░░░ ░░░░ ░░░░░  ░░░░░░  ░░░░░      ░░░░░░░░        ░░░░░
```

## Overview

**Container64** is project for building and sharing OCI compliant container images that can be used for testing infrastructure management tools.

### Container collection: Ansible Node

- Purpose: Ansible node testing
- Packages: SystemD, Sudo, Python3

| Image:Tag                          | OS          | Base Image                          |
| ---------------------------------- | ----------- | ----------------------------------- |
| `ubuntu-20.4-ansible-node:0.1.0`   | ubuntu      | `docker.io/library/ubuntu:20.04`    |
| `ubuntu-21.4-ansible-node:0.1.0`   | ubuntu      | `docker.io/library/ubuntu:21.04`    |
| `debian-10-ansible-node:0.1.0`     | debian      | `docker.io/library/debian:buster`   |
| `debian-11-ansible-node:0.1.0`     | debian      | `docker.io/library/debian:bullseye` |
| `oraclelinux-8-ansible-node:0.1.0` | oraclelinux | `docker.io/library/oraclelinux:8`   |
| `fedora-33-ansible-node:0.1.0`     | fedora      | `docker.io/library/fedora:33`       |
| `fedora-35-ansible-node:0.1.0`     | fedora      | `docker.io/library/fedora:35`       |
| `centos-8-ansible-node:0.1.0`      | centos      | `docker.io/library/centos:8`        |

### Container collection: Bash Test

- Purpose: Bash scripts testing
- Packages: Bash, Bats Core, Bash Core plugins

| Image:Tag                       | OS          | Base Image                          |
| ------------------------------- | ----------- | ----------------------------------- |
| `alpine-3-bash-test:0.1.0`      | alpine      | `docker.io/library/alpine:3`        |
| `ubuntu-20.4-bash-test:0.2.0`   | ubuntu      | `docker.io/library/ubuntu:20.04`    |
| `ubuntu-21.4-bash-test:0.2.0`   | ubuntu      | `docker.io/library/ubuntu:21.04`    |
| `debian-10-bash-test:0.2.0`     | debian      | `docker.io/library/debian:buster`   |
| `debian-11-bash-test:0.2.0`     | debian      | `docker.io/library/debian:bullseye` |
| `oraclelinux-8-bash-test:0.2.0` | oraclelinux | `docker.io/library/oraclelinux:8`   |
| `fedora-33-bash-test:0.2.0`     | fedora      | `docker.io/library/fedora:33`       |
| `fedora-35-bash-test:0.2.0`     | fedora      | `docker.io/library/fedora:35`       |
| `centos-8-bash-test:0.2.0`      | centos      | `docker.io/library/centos:8`        |

## Usage

Run a command inside the container:

```shell
# Using docker:
docker run ghcr.io/serdigital64/<IMAGE> <COMMAND>
# Using podman:
podman run ghcr.io/serdigital64/<IMAGE> <COMMAND>
```

## Deployment

Download the image to the local registry:

```shell
# Using docker:
docker pull ghcr.io/serdigital64/<IMAGE>
# Using podman:
podman pull ghcr.io/serdigital64/<IMAGE>`
```

## Development

### Environment

- Prepare dev tools
  - Install GIT
  - Install Docker or Podman
- Clone GIT repository

  ```shell
  git clone https://github.com/serdigital64/container64.git
  ```

- Adjust environment variables to reflect your configuration:

  ```shell
  # Copy environment definition files from templates:
  cp dot.local .local
  cp dot.secrets .secrets
  # Review and update content for both files
  ```

- Initialize dev environment variables

  ```shell
  source bin/devcnt-set
  ```

### Repositories

- Project GIT repository: [https://github.com/serdigital64/container64](https://github.com/serdigital64/container64)
- Project Documentation: [https://serdigital64.github.io/container64/](https://serdigital64.github.io/container64/)

### Contributing

Help on implementing new features and maintaining the code base is welcomed.

[Contributor Covenant Code of Conduct](https://serdigital64.github.io/container64/cod/)

## License

[GPL-3.0-or-later](https://www.gnu.org/licenses/gpl-3.0.txt)

### Author

- [SerDigital64](https://github.com/serdigital64)
