## USTC

该节内容仅适用于 USTC 及通过类似方式同步 GHCup 的站点。

### 使用方法

参考如下步骤可安装完整的 Haskell 工具链。

注意，以下命令会安装并配置 GHCup 0.0.8 版本的元数据。
可查看以下目录的内容，并选择需要安装的 GHCup 版本的 yaml 文件替换以下命令中的 URL。

```{ztmpl}
{{endpoint}}/ghcup-metadata/
```

**第一步（可选）** ：使用镜像源安装 GHCup 本体。如已经安装 GHCup，可跳到下一步。

- Linux, FreeBSD, macOS 用户：在终端中运行如下命令

  ```{ztmpl lang="bash"}
  curl --proto '=https' --tlsv1.2 -LsSf https://{{host}}{{path}}/sh/bootstrap-haskell | BOOTSTRAP_HASKELL_YAML={{endpoint}}/ghcup-metadata/ghcup-0.0.8.yaml sh
  ```

- Windows 用户：以非管理员身份在 PowerShell 中运行如下命令

  ```{ztmpl lang="powershell"}
  $env:BOOTSTRAP_HASKELL_YAML = '{{endpoint}}/ghcup-metadata/ghcup-0.0.8.yaml'
  Set-ExecutionPolicy Bypass -Scope Process -Force;[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072;Invoke-Command -ScriptBlock ([ScriptBlock]::Create((Invoke-WebRequest {{endpoint}}/sh/bootstrap-haskell.ps1 -UseBasicParsing))) -ArgumentList $true
  ```

**第二步** ：配置 GHCup 使用科大源。编辑 `~/.ghcup/config.yaml` 增加如下配置：

```{ztmpl lang="yaml"}
url-source:
  OwnSource: {{endpoint}}/ghcup/ghcup-metadata/ghcup-0.0.7.yaml
```

**第三步（可选）** ：配置 Cabal 和 Stack 使用镜像源，请参考文档 [Hackage 帮助](../hackage/) 和 [Stackage 帮助](../stackage/) 。

镜像站 GHCup 源仅支持较新的 GHCup 版本（元数据格式版本仅支持 0.0.6 及以上）。如果你使用的 GHCup 版本比较旧，请参考上述步骤安装新版本 GHCup。

### 预发布版本

使用预发布频道可以安装尚未正式发布的测试版本。要启用预发布源，将 `~/.ghcup/config.yaml` 文件中 `url-source` 一节修改如下：

```{ztmpl lang="yaml"}
url-source:
  OwnSource:
    - {{endpoint}}/ghcup-metadata/ghcup-0.0.7.yaml
    - {{endpoint}}/ghcup-metadata/ghcup-prereleases-0.0.7.yaml
```
