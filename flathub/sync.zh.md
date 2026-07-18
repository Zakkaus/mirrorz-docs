## 同步方法

### SJTUG

Flathub 镜像是 flathub.org 的智能缓存。

当您请求镜像中的资源时，如果文件没有被镜像服务器缓存，我们会将您重定向回原站，并在后台进行缓存。目前镜像服务器上已经预先缓存了所有 Flathub 软件的分支。

目前 sel.flathub.org 已经重定向到 SJTUG 镜像站。如果您原先使用该服务器作为 Flathub 上游，无需做任何设置即可使用。

### USTC

**WARNING**: 本镜像处于测试阶段，以下内容可能发生变化。

Flathub 的元数据（`config`, `summary.idx`, `summaries/`）每小时完整同步一次。

Flathub 的 blob 数据（`objects/`）与增量更新数据（`deltas/`, `delta-indexes/`）为动态缓存，根据用户访问情况，每小时更新一次。**在请求未命中时，会 302 重定向到 Flathub 源站点**。本镜像不是 Flathub 的完整镜像，因此仍然需要用户到 Flathub 站点有基本的可连通性。

软件 manifest 中标注为 `extra-data` 的文件不会经过镜像站或 Flathub 服务器，而是直接从标注的源站点下载。
