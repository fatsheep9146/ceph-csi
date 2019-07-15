# 鲸舵维护的 ceph-csi 分支介绍

由于鲸舵采用 csi 机制作为后续交付私有云客户场景下 ceph 对接的方案。有一些针对自身需求的改动，便维护在自己的仓库中。

## 构建 rbd-plugin，cephfs-plugin 方式

```
$ export ENV_RBD_IMAGE_NAME=reg.kpaas.io/kpaas/rbdplugin
$ export ENV_RBD_IMAGE_VERSION=<指定版本号>
$ make push-image-rbdplugin

$ export ENV_CEPHFS_IMAGE_NAME=reg.kpaas.io/kpaas/cephfsplugin
$ export ENV_CEPHFS_IMAGE_VERSION=<指定版本号>
$ make push-image-cephfsplugin

```
## 分支记录 

### csi-v1.0-kpaas-io-v1.0.1

该分支依赖于 ceph 官方提供的 csi 插件的 csi-v1.0 分支，[链接](https://github.com/ceph/ceph-csi/tree/csi-v1.0)

#### 该分支的修改 

#### 1. 修改 rbd，cephfs plugin 镜像依赖的 ceph 版本为 12.2 版本 

PR: [https://github.com/kpaas-io/ceph-csi/pull/2](https://github.com/kpaas-io/ceph-csi/pull/2)

#### 2. 修改 cephfs plugin 逻辑，删除设置 cephfs 的 quota 的逻辑，因为 12.2 版本的 ceph 尚不支持该特性

PR: [https://github.com/kpaas-io/ceph-csi/pull/3](https://github.com/kpaas-io/ceph-csi/pull/3) 


