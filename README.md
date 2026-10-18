# 无悔 · Android 安装包下载

> **这是公开发布仓库，只放安装包与下载页，不含任何源码、签名材料或密钥。**
> 源码仓库为私有：`Zou82/wuhui-study-app`（private）。

## 直接下载（点开即开始下载）

| 用途 | 链接 |
|---|---|
| **永久下载地址（始终最新版）** | <https://github.com/Zou82/wuhui-dl/releases/latest/download/wuhui.apk> |
| 下载页（含版本信息与二维码） | <https://zou82.github.io/wuhui-dl/> |
| 全部版本列表 | <https://github.com/Zou82/wuhui-dl/releases> |

> 安装包文件名固定为 `wuhui.apk`，版本号在「Releases 说明」与 `version.json` 中标注——
> 这样永久链接永远指向最新版，不需要每发一版就换链接。

## 当前版本

| 项 | 值 |
|---|---|
| 版本 | **v1.0.1**（versionCode 2） |
| 发布日 | 2026-10-18 |
| 体积 | 12,309,851 字节（约 11.7 MiB） |
| 最低系统 | Android 8.0（API 26） |
| 包名 | `com.wuhui.study` |
| APK SHA-256 | `0d691a5ec3ee8361124ff42e5de111abd61392659ca3c6e1a11e0ae027fe1896` |
| 签名证书 SHA-256 | `1389a458b6d5178e8801af3402788d7b57a66d03d898b6ecb91b843fb3ed5a4b`（CN=Wuhui Study） |

## 安装步骤

1. 用 **手机浏览器** 打开上面的下载地址（微信/QQ 内置浏览器不能下载 APK，需点右上角「⋯」→「在浏览器打开」）。
2. 下载完成后点击安装；首次会提示「禁止安装未知应用」，允许当前浏览器安装即可。
3. 若已装旧版本，直接覆盖安装即可（**签名必须一致**，否则会提示「应用未安装」，只能卸载重装且丢数据）。

## 安全校验

下载后可自行核对文件完整性：

```bash
sha256sum wuhui.apk
# 期望：6693c734b6815621345d95052f954787143abcedbf8a74f62989ec5c02574e35
```

签名证书指纹（用 `apksigner verify --print-certs wuhui.apk` 可求证）：

```
CN=Wuhui Study, OU=Mobile, O=Wuhui, L=Beijing, ST=Beijing, C=CN
SHA-256: 1389a458b6d5178e8801af3402788d7b57a66d03d898b6ecb91b843fb3ed5a4b
```

## 版本历史

| 版本 | versionCode | 日期 | 主要变更 |
|---|---|---|---|
| v1.0.1 | 2 | 2026-10-18 | 更换正式品牌图标（三张错题卡）+ Android 13 主题图标单色层；功能同 v1.0.0 |
| v1.0.0 | 1 | 2026-10-18 | 首个公开版本（见 Releases 说明） |

## 发版流程（维护者）

1. 在源码仓库执行 `./gradlew :app:assembleRelease` 并校验签名。
2. 跑 `tools/publish-dl.sh <版本号> <apk路径>`（源码仓库内，自动建 Release、传包、更新 `version.json`）。
3. 同步更新源码仓库的 `无悔-发布物料.md` §1 下载区块与 SSOT §18 版本表，私有一并推送。

---

> 本仓库为二进制分发通道。应用全部数据只存用户本机，AI 走 BYOK（用户自备 Key），不含任何统计 SDK。
