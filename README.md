# Karmada

[多云容器平台（Multi-Cloud Container Platform，MCP）是华为云基于多年容器云领域实践经验和社区先进的集群联邦技术（Karmada）](https://support.huaweicloud.com/cce_faq/zh-cn_topic_0148569869.html)

![Architecture diagram](https://support.huaweicloud.com/productdesc-mcp/zh-cn_image_0228801720.png)

功能介绍
统一集群管理
多云容器平台通过集群联邦实现对多个云运营商的集群进行统一管理，支持动态集群接入和全局集群监控仪表盘。通过多云容器平台的多集群统一管理入口可以实现统一部署、统一发布及统一运维。

全局应用管理
基于多集群与Federation联邦技术，多云容器平台可以实现多个不同区域、不同云的Kubernetes管理，支持统一的全局应用管理，支持基于Kubernetes社区集群联邦标准化接口的跨集群应用的部署、删除、升级等全生命周期管理。

跨集群的弹性伸缩能力
多云容器平台支持跨集群的应用弹性伸缩策略，用以均衡各集群的应用实例分布，实现全局负载均衡。您无需再担心集群节点的水平扩展，多云容器平台将根据应用的负载情况，轻松灵活的自动扩缩容应用所需的资源。

跨集群的服务发现能力
多云容器平台支持创建联邦服务，支持跨集群的服务发现机制，能够基于服务就近访问原则实现业务的区域亲和，从而在业务进行多区域部署时，实现访问与服务的同地域优先，降低用户访问时的网络延迟。

标准兼容
多云容器平台兼容Kubernetes社区最新Federation架构，提供原生Kubernetes API及Karmada API。您可使用熟悉的Kubernetes命令行和API来部署容器应用，无需修改任何服务代码即可支持Kubernetes典型应用场景。

单集群应用多云化
多云容器平台支持将单集群应用一键式转换为多云应用，将应用实例部署到多云多集群，方便快捷的完成业务多云容灾、多云业务流量分担等多云价值场景。

跨集群应用克隆和迁移能力
多云容器平台支持将某个集群的应用克隆或者迁移到其他集群，可以使用该能力完成跨云跨集群的应用主动迁移，或者跨云跨region的镜像环境复制等场景应用。

Karmada
Karmada（Kubernetes Armada）是基于Kubernetes原生API的多集群管理系统。在多云和混合云场景下，Karmada提供可插拔，全自动化管理多集群应用，实现多云集中管理、高可用性、故障恢复和流量调度。

关键特性

基于K8s原生API的跨集群应用管理，用户可以方便快捷地将应用从单集群迁移到多集群。
中心式操作和管理Kubernetes集群。
跨集群应用可在多集群上自动扩展，故障转移和负载均衡。
高级的调度策略：区域，可用区，云提供商，集群亲和性/反亲和性。
支持创建分发用户自定义（CustomResourceDefinitions）资源。
框架结构



ETCD：存储Karmada API对象。
Karmada Scheduler：提供高级的多集群调度策略。
Karmada Controller Manager: 包含多个Controller，Controller监听karmada对象并且与成员集群API server进行通信。
基本概念

资源模板（Resource Template）：Karmada使用K8s原生API定义作为资源模板，便于快速对接K8s生态工具链。
分发策略（Propagaion Policy）：Karmada提供独立的策略API，用来配置资源分发策略。
差异化策略（Override Policy）：Karmada提供独立的差异化API，用来配置与集群相关的差异发配置。比如配置不同集群使用不同的镜像。
Karmada资源分发流程图：





![Karmada-logo](docs/images/Karmada-logo-horizontal-color.png)


![build](https://github.com/karmada-io/karmada/actions/workflows/ci.yml/badge.svg)
[![Go Report Card](https://goreportcard.com/badge/github.com/karmada-io/karmada)](https://goreportcard.com/report/github.com/karmada-io/karmada)
[![LICENSE](https://img.shields.io/github/license/karmada-io/karmada.svg)](/LICENSE)
[![Releases](https://img.shields.io/github/release/karmada-io/karmada/all.svg)](https://github.com/karmada-io/karmada/releases)
[![Slack](https://img.shields.io/badge/slack-join-brightgreen)](https://join.slack.com/t/karmada-io/shared_invite/zt-omhy1wfa-LmAkCLfpDMnBjVXp3_U~0w)

## Karmada: Open, Multi-Cloud, Multi-Cluster Kubernetes Orchestration

Karmada (Kubernetes Armada) is a Kubernetes management system that enables you to run your cloud-native applications across multiple Kubernetes clusters and clouds, with no changes to your applications. By speaking Kubernetes-native APIs and providing advanced scheduling capabilities, Karmada enables truly open, multi-cloud Kubernetes.

Karmada aims to provide turnkey automation for multi-cluster application management in multi-cloud and hybrid cloud scenarios,
with key features such as centralized multi-cloud management, high availability, failure recovery, and traffic scheduling.


## Why Karmada:
- __K8s Native API Compatible__
    - Zero change upgrade, from single-cluster to multi-cluster
    - Seamless integration of existing K8s tool chain

- __Out of the Box__
    - Built-in policy sets for scenarios, including: Active-active, Remote DR, Geo Redundant, etc.
    - Cross-cluster applications auto-scaling, failover and load-balancing on multi-cluster.

- __Avoid Vendor Lock-in__
    - Integration with mainstream cloud providers
    - Automatic allocation, migration across clusters
    - Not tied to proprietary vendor orchestration

- __Centralized Management__
    - Location agnostic cluster management
    - Support clusters in Public cloud, on-prem or edge

- __Fruitful Multi-Cluster Scheduling Policies__
    - Cluster Affinity, Multi Cluster Splitting/Rebalancing,
    - Multi-Dimension HA: Region/AZ/Cluster/Provider

- __Open and Neutral__
    - Jointly initiated by Internet, finance, manufacturing, teleco, cloud providers, etc.
    - Target for open governance with CNCF



**Notice: this project is developed in continuation of Kubernetes [Federation v1](https://github.com/kubernetes-retired/federation) and [v2](https://github.com/kubernetes-sigs/kubefed). Some basic concepts are inherited from these two versions.**


## Architecture

![Architecture](docs/images/architecture.png)

The Karmada Control Plane consists of the following components:

- Karmada API Server
- Karmada Controller Manager
- Karmada Scheduler

ETCD stores the karmada API objects, the API Server is the REST endpoint all other components talk to, and the Karmada Controller Manager perform operations based on the API objects you create through the API server.

The Karmada Controller Manager runs the various controllers,  the controllers watch karmada objects and then talk to the underlying clusters’ API servers to create regular Kubernetes resources.

1. Cluster Controller: attach kubernetes clusters to Karmada for managing the lifecycle of the clusters by creating cluster object.

2. Policy Controller: the controller watches PropagationPolicy objects. When PropagationPolicy object is added, it selects a group of resources matching the resourceSelector and create ResourceBinding with each single resource object.
3. Binding Controller: the controller watches ResourceBinding object and create Work object corresponding to each cluster with single resource manifest.
4. Execution Controller: the controller watches Work objects.When Work objects are created, it will distribute the resources to member clusters.


## Concepts

**Resource template**: Karmada uses Kubernetes Native API definition for federated resource template, to make it easy to integrate with existing tools that already adopt on Kubernetes

**Propagation Policy**: Karmada offers standalone Propagation(placement) Policy API to define multi-cluster scheduling and spreading requirements.
- Support 1:n mapping of Policy: workload, users don't need to indicate scheduling constraints every time creating federated applications.
- With default policies, users can just interact with K8s API

**Override Policy**: Karmada provides standalone Override Policy API for specializing cluster relevant configuration automation. E.g.:
- Override image prefix according to member cluster region
- Override StorageClass according to cloud provider


The following diagram shows how Karmada resources are involved when propagating resources to member clusters.

![karmada-resource-relation](docs/images/karmada-resource-relation.png)

## Quick Start

This guide will cover:
- Install `karmada` control plane components in a Kubernetes cluster which as known as `host cluster`.
- Join a member cluster to `karmada` control plane.
- Propagate an application by `karmada`.

### Prerequisites
- Go version v1.14+
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) version v1.19+
- [kind](https://kind.sigs.k8s.io/) version v0.9.0+

### Install karmada control plane

#### 1. Clone this repo to your machine:
```
# git clone https://github.com/karmada-io/karmada
```

#### 2. Change to karmada directory:
```
# cd karmada
```

#### 3. Deploy and run karmada control plane:
```
# hack/local-up-karmada.sh
```
The script `hack/local-up-karmada.sh` will do following tasks for you:
- Start a Kubernetes cluster to run the karmada control plane, aka. the `host cluster`.
- Build karmada control plane components based on current codebase.
- Deploy karmada control plane components on `host cluster`.

If everything goes well, at the end of the script output, you will see similar messages as follows:
```
Local Karmada is running.
To start using your karmada, run:
  export KUBECONFIG=/var/run/karmada/karmada-apiserver.config
To start checking karmada components running status on the host cluster, please run:
  export KUBECONFIG="/root/.kube/karmada-host.config"
```

The two `KUBECONFIG` files after the script run are:
- karmada-apiserver.config
- karmada-host.config

The `karmada-apiserver.config` is the **main kubeconfig** to be used when interacting with karamda control plane, while `karmada-host.config` is only used for debuging karmada installation with host cluster.

### Join member cluster
In the following steps, we are going to create a member cluster and then join the cluster to 
karmada control plane.

#### 1. Create member cluster
We are going to create a cluster named `member1` and we want the `KUBECONFIG` file 
in `/root/.kube/member1.config`. Run following comand:
```
# hack/create-cluster.sh member1 /root/.kube/member1.config
```
The script `hack/create-cluster.sh` will create a standalone cluster.

#### 2. Join member cluster to karmada control plane
The command `karmadactl` will help to join the member cluster to karmada control plane, 
before that, we should set `KUBECONFIG` to karmada apiserver:
```
# export KUBECONFIG=/var/run/karmada/karmada-apiserver.config
```

Then, install `karmadactl` command and join the member cluster:
```
# go get github.com/karmada-io/karmada/cmd/karmadactl
# karmadactl join member1 --cluster-kubeconfig=/root/.kube/member1.config
```
The `karmadactl join` command will create a `Cluster` object to reflect the member cluster.

### 3. Check member cluster status
Now, check the member clusters from karmada control plane by following command:
```
# kubectl get clusters
NAME      VERSION   MODE   READY   AGE
member1   v1.20.2   Push   True    66s
```

### Propagate application
In the following steps, we are going to propagate a deployment by karmada.

#### 1. Create nginx deployment in karmada.
First, create a [deployment](samples/nginx/deployment.yaml) named `nginx`:
```
# kubectl create -f samples/nginx/deployment.yaml
```

#### 2. Create PropagationPolicy that will propagate nginx to member cluster
Then, we need create a policy to drive the deployment to our member cluster.
```
# kubectl create -f samples/nginx/propagationpolicy.yaml
``` 

#### 3. Check the deployment status from karmada
You can check deployment status from karmadda, don't need to access member cluster:
```
# kubectl get deployment
NAME    READY   UP-TO-DATE   AVAILABLE   AGE
nginx   1/1     1            1           43s
```

## Contributing

If you're interested in being a contributor and want to get involved in
developing the Karmada code, please see [CONTRIBUTING](CONTRIBUTING.md) for
details on submitting patches and the contribution workflow.

## License

Karmada is under the Apache 2.0 license. See the [LICENSE](LICENSE) file for details.
