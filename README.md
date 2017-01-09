
# CoreOS on Baremetal

[![Build Status](https://travis-ci.org/coreos/coreos-baremetal.svg?branch=master)](https://travis-ci.org/coreos/coreos-baremetal) [![GoDoc](https://godoc.org/github.com/coreos/coreos-baremetal?status.png)](https://godoc.org/github.com/coreos/coreos-baremetal) [![Docker Repository on Quay](https://quay.io/repository/coreos/matchbox/status "Docker Repository on Quay")](https://quay.io/repository/coreos/matchbox) [![IRC](https://img.shields.io/badge/irc-%23coreos-449FD8.svg)](https://botbot.me/freenode/coreos)

Guides and a service for network booting and provisioning CoreOS clusters on virtual or physical hardware.

## Guides

* [Network Setup](Documentation/network-setup.md)
* [Machine Lifecycle](Documentation/machine-lifecycle.md)
* [Background: PXE Booting](Documentation/network-booting.md)

## matchbox

`matchbox` is an HTTP and gRPC service that renders signed [Ignition configs](https://coreos.com/ignition/docs/latest/what-is-ignition.html), [cloud-configs](https://coreos.com/os/docs/latest/cloud-config.html), network boot configs, and metadata to machines to create CoreOS clusters. Groups match machines based on labels (e.g. MAC, UUID, stage, region) and use named Profiles for provisioning. Network boot endpoints provide PXE, iPXE, and GRUB. `matchbox` can be deployed as a binary, as an [appc](https://github.com/appc/spec) container with [rkt](https://coreos.com/rkt/docs/latest/), or as a Docker container.

* [matchbox Service](Documentation/matchbox.md)
* [Profiles](Documentation/matchbox.md#profiles)
* [Groups](Documentation/matchbox.md#groups)
* Config Templates
    * [Ignition](Documentation/ignition.md)
    * [Cloud-Config](Documentation/cloud-config.md)
* Tutorials (QEMU/KVM/libvirt)
    * [matchbox with rkt](Documentation/getting-started-rkt.md)
    * [matchbox with Docker](Documentation/getting-started-docker.md)
* [Configuration](Documentation/config.md)
* [HTTP API](Documentation/api.md)
* [gRPC API](https://godoc.org/github.com/coreos/coreos-baremetal/matchbox/client)
* Installation
    * [CoreOS / Linux distros](Documentation/deployment.md)
    * [rkt](Documentation/deployment.md#rkt) / [docker](Documentation/deployment.md#docker)
    * [Kubernetes](Documentation/deployment.md#kubernetes)
* Clients
    * bootcmd CLI (POC)
    * Tectonic Installer ([guide](https://tectonic.com/enterprise/docs/latest/deployer/platform-baremetal.html), [blog](https://tectonic.com/blog/tectonic-1-3-release.html))
* Backends
    * [FileStore](Documentation/matchbox.md#data)
* [Troubleshooting](Documentation/troubleshooting.md)
* Going Further
    * [gRPC API Usage](Documentation/config.md#grpc-api)
    * [Metadata Endpoint](Documentation/api.md#metadata)
    * OpenPGP [Signing](Documentation/api.md#openpgp-signatures)

### Examples

The [examples](examples) network boot and provision CoreOS clusters. Network boot [QEMU/KVM](scripts/README.md#libvirt) VMs to try the examples on your Linux laptop.

* Multi-node [Kubernetes cluster](Documentation/kubernetes.md)
* Multi-node [rktnetes](Documentation/rktnetes.md) cluster (i.e. Kubernetes with rkt as the container runtime)
* Multi-node [self-hosted](Documentation/bootkube.md) Kubernetes cluster
* [Upgrading](Documentation/bootkube-upgrades.md) self-hosted Kubernetes clusters
* Multi-node etcd2 or etcd3 cluster
* Multi-node [Torus](Documentation/torus.md) distributed storage cluster
* Network boot or Install to Disk
* Multi-stage CoreOS installs
* [GRUB Netboot](Documentation/grub.md) CoreOS
* iPXE Boot CoreOS with a root fs
* iPXE Boot CoreOS
* Lab [examples](https://github.com/dghubble/metal)
