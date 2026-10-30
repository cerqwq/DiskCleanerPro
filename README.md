# DiskCleaner Pro

> **先看清占用，再决定删除。**
> Windows 本地磁盘扫描与清理工具 —— 单文件便携版，不写注册表，不需要安装。

![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-blue) ![Version](https://img.shields.io/badge/version-4.2.1-green) ![Mode](https://img.shields.io/badge/mode-portable-orange)

DiskCleaner Pro 是一款聚焦「扫描 → 判断 → 再删除」工作流的 Windows 本地维护工具。全部分析在本机完成，没有「一键加速」式的表演按钮；涉及危险操作时，确认、备份和失败提示都写在明处。

产品主页与最新版本：**[sans.asia/disk-cleaner](https://sans.asia/disk-cleaner/)**（雪镇工具屋）

## 能力一览

四组能力，八个页面，围绕空间、软件、清理和系统维护组织。每个扫描结果都带路径和体积；涉及注册表与系统目录时，优先保护和回退。

| 能力 | 说明 |
|---|---|
| 空间定位 | 流式列出最大目录与文件，逐层展开，一键在资源管理器中定位；扫描前先展示占用，而不是直接给「优化分」 |
| 可再生垃圾 | 分析 Temp、浏览器缓存、回收站；**只清内容、保留目录骨架**，每项先算体积再删除，删除后可自动重建的都会注明 |
| 软件管理 | 已安装软件列表，区分普通卸载项与 Windows 更新记录 |
| 系统维护 | 启动项检查、注册表清理（**清理前自动备份**）、隐私记录清理、重复文件查找 |

### 设计细节

- **本地智能评级**：内置离线分析引擎，对目录逐个给出处置建议——「可放心删除 / 删除后自动重建 / 短期内启动稍慢 / 不推荐删」，不联网、不上传任何数据
- **备份保留策略**：清理注册表等敏感项前自动备份，只保留最近 N 份，备份目录不会无限增长
- **两种使用方式**：双击运行本地 Web 界面；或命令行 `DiskCleanerPro.exe cli quick-clean` 快速清理
- **操作留痕**：每一笔成功删除都记入操作历史，事后可查

## 安全边界

规矩写在按钮前面：

- 单文件便携版，**不写注册表、不需要安装**，设置保存在 `%LOCALAPPDATA%\DiskCleanerPro\settings.json`
- 构建**未做数字签名**，Windows 可能提示「未知发布者」——下载后请核对 SHA256；不接受这一风险时请不要运行
- 不可一键撤销的操作，都会先弹确认框、进度条与失败重试提示
- 扫描接口不接受前端提交的路径，一律由服务端自行回查，避免误用

## 下载与校验

从 [Releases](https://github.com/cerqwq/DiskCleanerPro/releases) 下载 `DiskCleanerPro.exe`。

本仓库当前构建 **v4.2.1**：

```text
SHA256: 41990158F14969F862405E9FEDC5D45F8433C0EE13F62676C5F94ED78E9AC6A7
```

校验方法：

```powershell
Get-FileHash .\DiskCleanerPro.exe -Algorithm SHA256
```

> 最新版本以官方页面为准：[sans.asia/disk-cleaner](https://sans.asia/disk-cleaner/)（当前官网最新 v4.2.2）

## 快速上手

1. 下载后双击运行，无需安装
2. 在浏览器打开本地界面
3. 从空间 / 清理 / 软件 / 维护中选择页面；扫描结果都带路径与体积，看清后再勾选执行
4. 命令行用户：`DiskCleanerPro.exe cli quick-clean`

## 反馈

- 问题反馈：本仓库 [Issues](https://github.com/cerqwq/DiskCleanerPro/issues)
- 版本发布动态：[sans.asia/disk-cleaner](https://sans.asia/disk-cleaner/)

---

DiskCleaner Pro © LISU（雪镇工具屋）。本仓库仅用于分发 Windows 便携版构建；如需了解安全设计，请阅读产品页的「安全边界」。
