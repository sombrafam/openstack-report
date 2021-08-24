# OpenStack Report Plugin

OpenStack Report (osreport) collects information of the resources on an
OpenStack cloud like VMs, networks, routers, etc. The information is organized
in a directory based structure making easier to browse and query on the
resources. It can take a long time to run depending on the size and speed of
the cloud API.

This is a snipet sample of the data colected by the tool:

```
│   ├── networks
│   │   ├── 9ddb756f-0f90-4f8d-b42f-b174bdc060b0_private
│   │   │   ├── info
│   │   │   ├── ports
│   │   │   │   ├── 09d6329d-2d67-425f-b558-0bdfb845173e -> ../../../ports/09d6329d-2d67-425f-b558-0bdfb845173e
│   │   │   │   ├── 3b7b28e6-695f-41e4-9eaf-382b332e964b -> ../../../ports/3b7b28e6-695f-41e4-9eaf-382b332e964b
│   │   │   │   ├── 5a8c9fe0-b758-47dd-a117-b9121cc63c39 -> ../../../ports/5a8c9fe0-b758-47dd-a117-b9121cc63c39
│   │   │   │   ├── 73829e03-f2a3-4a81-b49c-dec9ab95d333 -> ../../../ports/73829e03-f2a3-4a81-b49c-dec9ab95d333
│   │   │   │   ├── 90303700-d57f-4dc3-acad-d366244ce528 -> ../../../ports/90303700-d57f-4dc3-acad-d366244ce528
│   │   │   │   ├── f4d00462-cd74-47da-bc39-7ffacf7bcfad -> ../../../ports/f4d00462-cd74-47da-bc39-7ffacf7bcfad
│   │   │   │   └── list
│   │   │   └── subnets
│   │   │       ├── 864084c7-3875-40d1-bf34-9c18410677cb_private_subnet -> ../../../subnets/864084c7-3875-40d1-bf34-9c18410677cb_private_subnet
│   │   │       └── list
```

## How to install and use

The tool can be installed using the snap:

```sh
sudo snap install osreport
```

Usage:

```sh
osreport <options>
```

Options:

```
  --help: Print this info.
  --plugins <plugins>: Can be any of: neutron, nova, nova-hypervisors, keystone
    or octavia. You can use multiple options separated by commas.
  --all-plugins: Runs all the above plugins. Can take some time to run.
```
Environment:
```sh
# Usualy you just need to source your novarc

export OS_AUTH_URL=''
export OS_AUTH_VERSION=''
export OS_IDENTITY_API_VERSION=''
export OS_PASSWORD=''
export OS_PROJECT_DOMAIN_NAME=''
export OS_PROJECT_NAME=''
export OS_REGION_NAME=''
export OS_USERNAME=''
export OS_USER_DOMAIN_NAME=''
```

To run it in debug mode (Will leave uncompressed results and print debug
information):

```sh
export OS_REPORT_DEBUG=True
```