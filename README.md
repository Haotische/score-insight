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

本仓库同时通过 GitHub Pages 提供静态更新清单：

```text
https://haotische.github.io/score-insight/latest.json
```

客户端中的更新地址：

```text
https://haotische.github.io/score-insight
```

安装包通过 GitHub Releases 分发；客户端会校验 SHA256 后静默升级。

## 文件说明

- `latest.json`：最新版本、安装包地址、SHA256、文件大小和更新说明
- Release assets：`ScoreInsight-Setup-x.y.z.exe`

## 构建

- 主程序：`pyinstaller ScoreInsight.spec --noconfirm --clean`
- 安装包：`ISCC.exe installer\ScoreInsight.iss`
