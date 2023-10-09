---
description: 强大的中州韵（RIME）输入法引擎使得键道输入法可以方便地运行在各个平台
---

# 安装与更新

键道方案基于[中州韵](https://rime.im)输入法引擎，不同平台有不同的前端实现，需要先安装对应的前端。

{% tabs %}
{% tab title="Windows" %}
Windows 中的 Rime 前端推荐中州韵官方开发的[小狼毫](https://github.com/rime/weasel)。

> 若已安装的小狼毫版本为 0.14.3 及以下，且未手动更新过 librime，请使用手动安装。

## 使用安装器安装或更新

1. **（仅初次安装时）**前往[中州韵输入法引擎网站](https://rime.im/download/)下载小狼毫并安装
2. 使用 `Win+R` 打开运行窗口，输入 `powershell` 并回车
3. 在弹出的 `PowerShell` 命令行窗口中，粘贴以下命令并回车，之后按照弹出窗口提示进行即可

```powershell
irm 0xa.nl/get-jd-win | iex
```

{% hint style="warning" %}
如果 PowerShell 命令报错，请运行以下命令后再重试一遍

`Set-ExecutionPolicy RemoteSigned -Scope CurrentUser`
{% endhint %}

{% hint style="info" %}
命令中的 `0xa.nl/get-jd-win` 可替换为以下两个网址之一

* [https://gitee.com/amorphobia/rime-jiandao/raw/master/scripts/installer.ps1](https://gitee.com/amorphobia/rime-jiandao/raw/master/scripts/installer.ps1)
* [https://raw.githubusercontent.com/amorphobia/rime-jiandao/master/scripts/installer.ps1](https://raw.githubusercontent.com/amorphobia/rime-jiandao/master/scripts/installer.ps1)
{% endhint %}

## 手动安装或更新

1. **（仅初次安装时）**前往[中州韵输入法引擎网站](https://rime.im/download/)下载小狼毫并安装
2. 前往键道仓库发布页面（[GitHub](https://github.com/amorphobia/rime-jiandao/releases)，[Gitee](https://gitee.com/amorphobia/rime-jiandao/releases)）下载最新发布的键道压缩包 `jiandao-v<版本号>.zip`

{% hint style="info" %}
如果 librime 版本低于 1.8.5（通常是小狼毫 0.14.3 及以下自带），请下载 `jiandao-legacy-v<版本号>.zip`
{% endhint %}

3. 将压缩包内全部文件解压到 Rime 用户目录中（通常是 `C:\Users\<用户名>\AppData\Roaming\Rime`，或者可以右键点击小狼毫的状态栏图标，选择“用户文件夹”来打开）
4. **（仅初次安装时）**在 Rime 用户目录中新建或修改 `default.custom.yaml` 文件，添加以下内容

```yaml
patch:
  schema_list:
    - schema: jiandao
```

5. 右键点击小狼毫的状态栏图标，选择“重新部署”
{% endtab %}

{% tab title="macOS" %}
macOS 的 Rime 前端推荐中州韵官方开发的[鼠须管](https://github.com/rime/squirrel)。

## 安装或更新

1. **（仅初次安装时）**使用 Homebrew 安装鼠须管

```bash
brew install --cask squirrel
```

2. 前往键道仓库发布页面（[GitHub](https://github.com/amorphobia/rime-jiandao/releases)，[Gitee](https://gitee.com/amorphobia/rime-jiandao/releases)）下载最新发布的键道压缩包 `jiandao-v<版本号>.zip`
3. 将压缩包内全部文件解压到 Rime 用户目录中（通常是 `~/Library/Rime`，或者可以通过“系统输入法菜单 / 鼠须管 / 用户设定...”来打开）
4. **（仅初次安装时）**在 Rime 用户目录中新建或修改 `default.custom.yaml` 文件，添加以下内容

```
patch:
  schema_list:
    - schema: jiandao
```

5. 在系统输入法菜单中选择“重新部署”
{% endtab %}

{% tab title="GNU/Linux" %}
TODO
{% endtab %}

{% tab title="iOS" %}
TODO
{% endtab %}
{% endtabs %}
