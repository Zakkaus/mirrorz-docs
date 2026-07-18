## 其他配置

### XDG 支持

参考 [GHCup xdg-support](https://www.haskell.org/ghcup/guide/#xdg-support)。

对于 Linux、FreeBSD、macOS 用户，如果想要让 GHCup 遵循 XDG 规范，可以使用 `GHCUP_USE_XDG_DIRS` 变量，例如：

```bash
export GHCUP_USE_XDG_DIRS=1
```

还可以将上述内容写入 `~/.profile` 等文件中。

使用 `GHCUP_USE_XDG_DIRS` 后，GHCup 配置目录将由默认的 `~/.ghcup` 变成 `~/.config/ghcup`；
而二进制目录会使用 `~/.local/bin`，需要将该目录加入 `PATH` 才能够正常使用 GHCup 安装的 GHC 以及其他工具。

```bash
export PATH=$HOME/.local/bin:$PATH
```

### 安装目录变更

参考 [GHCup env-variables](https://www.haskell.org/ghcup/guide/#env-variables)。

对于 Windows 用户或不想使用 XDG 目录的 Linux、FreeBSD、macOS 用户，可以使用 `GHCUP_INSTALL_BASE_PREFIX` 来更改默认安装路径。
默认安装路径，对 Windows 用户而言是 `C:\ghcup`，而对于 Linux、FreeBSD、macOS 用户而言是 `$HOME/.ghcup`。

如果想要将 GHCup 的安装目录放到某一个特定目录下，例如 `~/sdk`：

- **Windows 用户**

  可以在终端使用如下方法：

  ```powershell
  $env:GHCUP_INSTALL_BASE_PREFIX = $env:USERPROFILE/sdk
  ```

  或使用系统设置添加该环境变量。

- **Linux、FreeBSD、macOS 用户**

  可以在终端使用如下方法：

  ```bash
  export GHCUP_INSTALL_BASE_PREFIX=$HOME/sdk
  ```

  还可以将上述内容写入 `~/.profile` 等文件中。

### MSYS2 设置

参考 [GHCup env-variables](https://www.haskell.org/ghcup/guide/#env-variables)。

对于 Windows 用户，如果系统中已经安装了 MSYS2 环境，则可以使用 `GHCUP_MSYS2` 来指定想要让 GHCup 使用的 MSYS2 环境。
如果不指定使用的 MSYS2 环境，则会默认新安装一个 MSYS2 环境，并且使用新安装的 MSYS2 环境。
