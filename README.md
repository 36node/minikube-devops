# devops

适用于 36node 团队开发的本地 devops，本机主要使用 [docker desktop](https://www.docker.com/products/docker-desktop) 或者[minikube](https://kubernetes.io/docs/tutorials/hello-minikube/)

## 日志采集

- vector.dev 是个不错的选择，但是其对 kubernetes 的支持还不正式

## 本机 kubernetes 集群

有两个选择：

- 开启 docker for mac 自带的 kubernetes 支持
- 安装 minikube

### minikube 网络问题

在国内由于无法直接访问 google 的资源，所以 proxy 是必须的。打开方式

```sh
export HTTP_PROXY=http://<proxy hostname:port>
export HTTPS_PROXY=https://<proxy hostname:port>
export NO_PROXY=localhost,127.0.0.1,10.96.0.0/12,192.168.99.0/24,192.168.39.0/24

minikube start
```

## 集群初始化

`kubectl apply -f src/namespace.yaml`

[详情参考](https://minikube.sigs.k8s.io/docs/handbook/vpn_and_proxy/)
