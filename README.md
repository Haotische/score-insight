# 成绩洞察 / Score Insight

开发者 / Developer：**Haotische**

## 下载安装

前往 [Releases](https://github.com/Haotische/score-insight/releases) 下载最新的
`ScoreInsight-Setup-x.y.z.exe`。

- 默认安装到 `D:\ScoreInsight`（没有 D 盘时使用系统盘）
- 安装目录可以自选
- 桌面快捷方式默认创建，可以取消
- 覆盖安装和自动更新都会保留 `data` 中的成绩、报告和设置

## 自动更新

本仓库通过 GitHub Pages 提供静态更新清单：

```text
https://haotische.github.io/score-insight/latest.json
```

客户端中的更新地址：

```text
https://haotische.github.io/score-insight
```

安装包以 GitHub Releases 为原始来源。由于中国大陆直连 GitHub Releases
下载较慢，`latest.json` 中的下载地址会使用 `ghfast.top` 加速镜像；
客户端下载完成后会用清单里的 SHA256 校验，文件被篡改或损坏会拒绝安装。

更新流程：检查清单 → 下载安装包 → 校验 SHA256 → 关闭旧程序 →
静默覆盖安装 → 自动启动新版本。用户数据 `data` 始终保留。

如果加速镜像失效，可以：

1. 把 `latest.json` 中的 `url` 换回
   `https://github.com/Haotische/score-insight/releases/download/v1.3.0/ScoreInsight-Setup-1.3.0.exe`；
2. 或换成其他可用的 GitHub 下载镜像；
3. 更新 `latest.json` 后等待 GitHub Pages 重新发布。

## 代码签名

主程序 `ScoreInsight.exe` 和安装包 `ScoreInsight-Setup-x.y.z.exe` 使用
**Haotische** 自签名代码签名证书签名，包含 SHA256 摘要和 DigiCert 时间戳。

- 当前开发电脑已将证书加入“受信任的根证书颁发机构”和“受信任的发布者”，
  因此签名验证为 `Valid`，不会提示未知发布者。
- 其他电脑如果没有安装该证书，Windows 仍可能提示“未知发布者”。
- 面向公众分发时，建议换成商业代码签名证书（OV/EV），或使用
  Azure Trusted Signing / SignPath 等服务。

## 文件说明

- `latest.json`：最新版本、安装包地址、SHA256、文件大小和更新说明
- Release assets：`ScoreInsight-Setup-x.y.z.exe`

## 构建

- 主程序：`pyinstaller ScoreInsight.spec --noconfirm --clean`
- 签名主程序：`powershell -File installer\sign_artifacts.ps1 dist\ScoreInsight\ScoreInsight.exe`
- 安装包：`ISCC.exe installer\ScoreInsight.iss`
- 签名安装包：`powershell -File installer\sign_artifacts.ps1 installer_output\ScoreInsight-Setup-x.y.z.exe`
