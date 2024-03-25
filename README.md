# Ansible role [elasticsearch](https://galaxy.ansible.com/ui/standalone/roles/buluma/elasticsearch/documentation)

Install and configure Elasticsearch on your system.

|GitHub|Version|Issues|Pull Requests|Downloads|
|------|-------|------|-------------|---------|
|[![github](https://github.com/buluma/ansible-role-elasticsearch/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-elasticsearch/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-elasticsearch.svg)](https://github.com/buluma/ansible-role-elasticsearch/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-elasticsearch.svg)](https://github.com/buluma/ansible-role-elasticsearch/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-elasticsearch.svg)](https://github.com/buluma/ansible-role-elasticsearch/pulls/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/elasticsearch)](https://galaxy.ansible.com/ui/standalone/roles/buluma/elasticsearch/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-elasticsearch/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.elasticsearch
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-elasticsearch/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: buluma.bootstrap
    - role: buluma.core_dependencies
    - role: buluma.elastic_repo
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-elasticsearch/blob/master/defaults/main.yml):

```yaml
---
# defaults file for elasticsearch

# Elastic offers both "oss" (Apache 2.0 license) and "elastic"
# (Elastic license). Select the type here. Either "oss" or "elastic"
elasticsearch_type: oss

# The IP address to bind on.
elasticsearch_network_host: "0.0.0.0"

# The port to bind on.
elasticsearch_http_port: 9200

# Provides a list of the addresses of the master-eligible nodes in the cluster
elasticsearch_discovery_seed_hosts: []

# Sets the initial set of master-eligible nodes in a brand-new cluster.
elasticsearch_cluster_initial_master_nodes: []
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-elasticsearch/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.core_dependencies](https://galaxy.ansible.com/buluma/core_dependencies)|[![Ansible Molecule](https://github.com/buluma/ansible-role-core_dependencies/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-core_dependencies/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-core_dependencies.svg)](https://github.com/shadowwalker/ansible-role-core_dependencies)|
|[buluma.elastic_repo](https://galaxy.ansible.com/buluma/elastic_repo)|[![Ansible Molecule](https://github.com/buluma/ansible-role-elastic_repo/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-elastic_repo/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-elastic_repo.svg)](https://github.com/shadowwalker/ansible-role-elastic_repo)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-elasticsearch/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Amazon](https://hub.docker.com/r/buluma/amazonlinux)|all|
|[Debian](https://hub.docker.com/r/buluma/debian)|all|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|7, 8|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|focal, bionic|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-elasticsearch/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-elasticsearch/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-elasticsearch/blob/master/LICENSE)

## [Author Information](#author-information)

[Shadow Walker](https://buluma.github.io/)
