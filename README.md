# VMC Documentation
## Introduction
The purpose of this document is to present the results of the implementation of the Vulnerability Management Center (VMC) platform, supporting the process of managing vulnerabilities in the client's infrastructure.

This document presents the design of the VMC platform, describes the requirements, installation, architecture and introduces the administrator panel of the VMC platform.

## VMC Platform
Vulnerability Management Center (VMC) is a tool that facilitates and supports the process of managing vulnerabilities in an organization. The tool integrates with infrastructure elements such as: a vulnerability scanner, publicly available knowledge bases on published vulnerabilities, IT resource inventory systems and reporting systems. Thanks to the wide possibilities of data normalization and the transparency of the interface, it presents information on threats in an accessible way and alerts about deviations from the norm and anomalies. The main innovation factor of VMC is the organization's vulnerability analysis, as opposed to the common vulnerability assessment approach without specifying environmental conditions. Thanks to the assessment calculated by the VMC, the cybersecurity team can focus on the most vulnerable elements of the infrastructure in its work, prioritizing repair processes based on the recommendations provided by the tool. In addition, presenting the current state of the infrastructure is possible at any time, in an accessible, user-adapted manner.

The architecture of the solution makes it possible to run it in any environment depending on the demand. It can be a public cloud, a private cloud, a physical server, or a virtual machine.

## Requirements
The following chapter describes the VMC requirements.

### Hardware requirements
The minimum resources listed in Table below are required for the proper operation of the VMC platform

|Hardware|1-n (depending on the required configuration)|
|--------|---------------------------------------------|
| RAM    |minimum 8 GB                                 |
| Storage|minimum 30 GB for every machine              |
| CPU    |minimum 4                                    |

### Required Software
The software listed in Table below is required for the correct operation of the VMC Platform

|Name          |Minimum version   | Description|
|--------------|------------------|------------------------------------------------------------------------------|
| Linux OS     | Centos 7/Debian 9|                                                                              |
| Python3      |  3.5             |                                                                              |
| Nginx        |                  |https://www.nginx.com/ (applies to the server on which VMC Admin is running)  |
| Redis        |  5.0             |https://redis.io/                                                             |
| Rabbitmq     |  3.7             |https://www.rabbitmq.com/                                                     |
| Elasticsearch|  7.5             |https://www.elastic.co/elasticsearch/                                         |
| Postgresql   | 11.5             |https://www.postgresql.org/                                                   |


## Installation
The architecture of the VMC software allows to run in any environment, depending on the demand. This can be a public cloud, private cloud, physical server, or virtual machine. All available installation methods are described in the following chapter.

### Installation on a virtual machine
#### Installing from the source code
To install VMC from source code, execute the following commands on each server instance:
```
git clone https://github.com/DSecureMe/vmc.git
cd vmc
python3 setup.py build
python3 setup.py install
```

#### Installation Using the Package Manager
It is also possible to install VMC from the Python package manager using the command:
```
pip3 install vmcenter
```

### Installation using the docker
If you need to build your own image with a specific VMC version, follow the steps below. The minimum supported docker version is 19.03 (multistage build support).

```
git clone https://github.com/DSecureMe/vmc-docker
cd vmc-docker
make build
```
#### Downloading an image from Docker Hub
The official VMC image can be downloaded from [Docker Hub](https://hub.docker.com/repository/docker/dsecureme/vmc).
```
docker pull dsecureme/vmc:tagname
```


## Table of Contents
###  Configuration
###  [Architecture](./Architecture/Architecture.md)
#### [Knowledge Collector](./Architecture/Architecture.md#knowledge-collector)
#### [Asset Collector](./Architecture/Architecture.md#asset-collector)
#### [Vulnerability Collector](./Architecture/Architecture.md#vulnerability-collector)
#### [Processing Module](./Architecture/Architecture.md#processing-module)
###  Administrator Panel
###  API
###  Integration with the IT asset management base
###  Integration with The Hive
### Introduction to KPI
