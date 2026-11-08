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

如果加速镜像失效，可以：

1. 把 `latest.json` 中的 `url` 换回
   `https://github.com/Haotische/score-insight/releases/download/v1.2.2/ScoreInsight-Setup-1.2.2.exe`；
2. 或换成其他可用的 GitHub 下载镜像；
3. 更新 `latest.json` 后等待 GitHub Pages 重新发布。

## 文件说明

- `latest.json`：最新版本、安装包地址、SHA256、文件大小和更新说明
- Release assets：`ScoreInsight-Setup-x.y.z.exe`

## 构建

- 主程序：`pyinstaller ScoreInsight.spec --noconfirm --clean`
- 安装包：`ISCC.exe installer\ScoreInsight.iss`
