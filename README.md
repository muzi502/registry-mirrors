# Container Registry mirrors of Kubernetes

Bypass GFW, container registry mirrors for  kubernetes developer in China mainland.

## Registry list

| origin     | mirror      |
| ---------- | ----------- |
| docker.io  | hub.k8s.li  |
| k8s.gcr.io | gcr.k8s.li  |
| quay.io    | quay.k8s.li |

## Usage

### Kubeadm

```shell
$ kubeadm config images pull --image-repository=gcr.k8s.li
[config/images] Pulled gcr.k8s.li/kube-apiserver:v1.20.6
[config/images] Pulled gcr.k8s.li/kube-controller-manager:v1.20.6
[config/images] Pulled gcr.k8s.li/kube-scheduler:v1.20.6
[config/images] Pulled gcr.k8s.li/kube-proxy:v1.20.6
[config/images] Pulled gcr.k8s.li/pause:3.2
[config/images] Pulled gcr.k8s.li/etcd:3.4.13-0
[config/images] Pulled gcr.k8s.li/coredns:1.7.0
```

### Kubespray

- container image `quay.k8s.li/kubespray/kubespray:$TAG`

```shell
$ docker pull quay.k8s.li/kubespray/kubespray:v2.15.1
```

- `roles/download/defaults/main.yml`

```yaml
kube_image_repo: "gcr.k8s.li"
docker_image_repo: "hub.k8s.li"
quay_image_repo: "quay.k8s.li"
```