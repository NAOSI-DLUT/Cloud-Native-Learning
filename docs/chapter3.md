# K8S网络以及高性能网络

## K8S网络

k8s网络指的是一个普通的集群的全部网络结构。而不同的业务也会对k8s提出不同的需求，
有一些超出k8s基础功能的需求就需要自定义一些网络架构来实现。

k8s网络预计要讲Flannel、Calico、Multus、Cilium。
[CNI（容器网络接口）](https://www.cni.dev/plugins/current/)
同时他们都对应着这个接口。

### Flannel

Flannel应该是在k8s官网安装时自带的网络插件。

### Calico

OpenShift云平台使用了calico。

### Multus

TBD

### Cilium

Google的GDCE会使用cilium。


## 高性能网络

k8s中高性能网络一般通过使用SRIOV-plugin来实现，设计思路为控制面（control plan）与数据面（data plane）网络分开，让控制面走k8s网络，数据面走高性能网络，从而提高吞吐量。

同时，高性能网络也需要软硬件上的支持。
比如之前提到的SRIOV，还有DPDK，以及支持这类驱动的网卡。所以一般支持高性能网络架构部署的云也是定制或专用的。