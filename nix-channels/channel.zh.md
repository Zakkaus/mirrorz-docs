### Nixpkgs channel

注：SJTUG 提供了 binary cache，未提供该镜像。

单独安装的 Nix 替换 `nixpkgs-unstable` 命令如下：

```{ztmpl lang="bash"}
nix-channel --add {{endpoint}}/nixpkgs-unstable nixpkgs
nix-channel --update
```

替换 NixOS channel 命令如下（以 root 执行）：

```{ztmpl lang="bash" input="version"}
nix-channel --add {{endpoint}}/nixos-{{version}} nixos
nix-channel --update
```
