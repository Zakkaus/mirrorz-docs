## 常见问题/调试方法

如果怀疑网络问题，请添加 `OSTREE_DEBUG_HTTP=1` 环境变量后再次运行 `flatpak` 命令以获取 libcurl 的详细输出，例如：

```{ztmpl lang="bash"}
OSTREE_DEBUG_HTTP=1 flatpak install com.github.tchx84.Flatseal
```

如果出现 "Can't check signature: public key not found" 错误可尝试导入 GPG 密钥：

```{ztmpl lang="bash"}
wget {{endpoint}}/flathub.gpg
{{sudo}}flatpak remote-modify --gpg-import=flathub.gpg flathub
```

Flathub 中部分软件由于重分发授权问题，需要从官方服务器下载，无法使用镜像站加速。比如 NVIDIA 驱动、JetBrains 系列软件等。如果您的使用体验不佳，请及时通过 GitHub 或邮件向镜像站反馈。

如果您中断了某次安装，重新下载可能会出现找不到文件的问题。您可以使用 `flatpakrepair` 解决相关的问题。
