### USTC

**WARNING**: 本镜像处于测试阶段，以下内容可能发生变化。

Flathub 的元数据（`config`, `summary.idx`, `summaries/`）每小时完整同步一次。

Flathub 的 blob 数据（`objects/`）与增量更新数据（`deltas/`, `delta-indexes/`）为动态缓存，根据用户访问情况，每小时更新一次。**在请求未命中时，会 302 重定向到 Flathub 源站点**。本镜像不是 Flathub 的完整镜像，因此仍然需要用户到 Flathub 站点有基本的可连通性。

软件 manifest 中标注为 `extra-data` 的文件不会经过镜像站或 Flathub 服务器，而是直接从标注的源站点下载。
