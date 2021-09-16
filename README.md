# Kubernetes components

Notes about the merics collection from the following Kubernetes components:

1. kube-apiserver
1. kube-controller-manager
1. kube-scheduler
1. kubelet
1. kube-proxy
1. etcd
1. CoreDNS

## kube-apiserver

- Port: `--secure-port` (default: 6443)
- Network interface: `--bind-address` (default: 0.0.0.0)
- Protocol: HTTPS

→ Reference: [kube-apiserver](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-apiserver/)

## etcd

- Port, network interface, and protocol:
  - Default: `--listen-client-urls` (default: http://localhost:2379)
  - Optional (since etcd v3.3): `--listen-metrics-urls` (default: _empty_)

→ Reference: [etcd configuration flags](https://etcd.io/docs/latest/op-guide/configuration/)

## kube-controller-manager

- Port: `--secure-port` (default: 10257)
- Network interface: `--bind-address` (default: 0.0.0.0)
- Protocol: HTTPS

→ Reference: [kube-controller-manager](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-controller-manager/)

## kube-scheduler

- Port:
  - `--secure-port` (default: 10259)
  - DEPRECATED: `--port` (default: 10251)
- Network interface:
  - `--bind-address` (default: 0.0.0.0)
  - DEPRECATED: `--address` (default: 0.0.0.0)
- Protocol:
  - HTTPS
  - DEPRECATED: HTTP

→ Reference: [kube-scheduler](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-scheduler/)

## kubelet

- Port:
  - Config file: `KubeletConfiguration.port` (default: 10250)
  - DEPRECATED: `--port` (default: 10250)
- Network interface:
  - Config file: `KubeletConfiguration.address` (default: 0.0.0.0)
  - DEPRECATED: `--address` (default: 0.0.0.0)
- Protocol:
  - HTTPS

→ References:
  - [kubelet](https://kubernetes.io/docs/reference/command-line-tools-reference/kubelet/)
  - [`KubeletConfiguration`](https://kubernetes.io/docs/reference/config-api/kubelet-config.v1beta1/) (config file)

## kube-proxy

- Port and network interface: `--metrics-bind-address` (default: 127.0.0.1:10249)
- Protocol: HTTP

→ Reference: [kube-proxy](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-proxy/)

## CoreDNS

- Port and network interface: [Corefile](https://coredns.io/2017/07/23/corefile-explained/) (default: localhost:9153)
- Protocol: HTTP

→ Reference: CoreDNS [prometheus](https://coredns.io/plugins/metrics/) plugin
