# docker-ansible-role

Ansible role to install docker.
Only runs on ubuntu based machines

Role Variables
--------------

```
docker_package_name: docker-ce
docker_version: 18.02.0~ce-0~ubuntu
dockerpy_version: 1.10.6
docker_disks: /dev/sdb
docker_partitions: /dev/sdb1
docker_opts: "--log-opt max-size=50m --log-opt max-file=2"
use_docker_lvm: true
docker_repository_url: https://download.docker.com/linux/ubuntu/
docker_repository_category: edge
#this should be overrided only in case of downgrade of docker version
docker_force_version: no

docker_registries: []
```

Registries  Examples
----------
```
docker_registries:
  # no certificate is required for docker hub
  - url: index.docker.io
  # if you have the ca certificate
  - url: my.custom.registry
    certificate: path/to/ca.crt of the registry
  # if you want ansible to fetch the certificate from the registry itself with openssl
  - url: my.custom.registry
    port: 443
```
License
-------

Apache License 2
