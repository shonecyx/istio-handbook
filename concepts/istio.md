---
authors: ["malphi"]
reviewers: ["rootsongjc"]
---

#  什么是 Istio

通过前面章节的介绍，相信你对什么是 Service Mesh 已经有了初步的认识。Istio 作为一个开源的 Service Mesh 实现产品，一经推出就备受瞩目，成为了各大厂商和开发者争相追捧的对象。我们有理由相信，Istio 会成为继 Kubernetes 之后又一个明星级产品。Istio 官方文档是这样来定义自己的：

> 它是一个完全开源的服务网格，以透明的方式构建在现有的分布式应用中。它也是一个平台，拥有可以集成任何日志、遥测和策略系统的 API 接口。Istio 多样化的特性使你能够成功且高效地运行分布式微服务架构，并提供保护、连接和监控微服务的统一方法。

从官方定义我们可以看出，Istio 提供了一个完整的解决方案，可以以统一的方式去管理和监测你的微服务应用。同时，它还具有管理流量、实施访问策略、收集数据等方面的能力，而所有的这些都对应用透明，几乎不需要修改业务代码就能实现。

有了 Istio，你几乎可以不再需要其他的微服务框架，也不需要自己去实现服务治理等功能。只要把网络层委托给 Istio，它就能帮你完成这一系列的功能。简单来说，Istio 就是一个提供了服务治理能力的服务网格。

## 为什么使用 Istio？

Service Mesh 也是一种服务治理技术，其核心能力是对流量进行控制。从这一点来说，Service Mesh 和现有的服务治理产品在功能上是有重合的。作为一个企业，如果你的微服务应用已经具有了非常完备的服务治理能力，那么你不一定非得引入 Service Mesh。但是假设你的系统并不具有完善的治理功能，或者系统架构中的痛点正好可以被 Service Mesh 所解决，那么使用 Service Mesh 就是你的最佳选择。

相对于基于公共库的服务治理产品，Service Mesh 最大的特性就是对应用透明。你可以将你的微服务应用无缝的接入网格，而无需修改业务逻辑。目前 Istio 提供了以下重要的功能：

- 为 HTTP、gRPC、WebSocket 和 TCP 流量自动负载均衡。
- 通过丰富的路由规则、重试、故障转移和故障注入对流量行为进行细粒度控制。
- 提供完善的可观察性方面的能力，包括对所有网格控制下的流量进行自动化度量、日志记录和追踪。
- 提供身份验证和授权策略，在集群中实现安全的服务间通信。

##   Istio 的平台支持

Istio 独立于平台，被设计为可以在各种环境中运行，包括跨云、内部环境、Kubernetes 等等。目前 Istio 支持的平台有：
1. Kubernetes
1. Consul
1. GCP

在最新推出的 1.6 版本中，Istio 还提供了对虚拟机（VM）的支持。尽管 Istio 支持多种平台，但还是和 Kubernetes 结合的更好，这也和 Kubernetes 在容器编排领域的地位有很大关系。总的来说，在 Kubernetes 上使用 Istio 会更能发挥出它的强大实力。