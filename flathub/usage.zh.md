## 配置方法

如果之前从未使用过 Flathub，那么首先需要添加 Flathub 远程源：

```{ztmpl lang="bash"}
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```

在已有 `flathub` 远程源的基础上：

```{ztmpl lang="bash"}
{{sudo}}flatpak remote-modify flathub --url={{endpoint}}
```

恢复默认值：

```{ztmpl lang="bash"}
{{sudo}}flatpak remote-modify flathub --url=https://dl.flathub.org/repo
```
