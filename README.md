# JMCAI Comfypet

JMCAI Comfypet 是一个面向 ComfyUI 工作流创作与调度的桌面助手，把桌宠交互、多实例管理、Workflow Center 和远程算力接入整合到同一个桌面应用里。

**当前版本：[`v1.3.0`](https://github.com/allen-Jmc/comfypet-jmcai-Dist/releases/tag/v1.3.0)**

## 下载

| 平台 | 推荐包 | 适合谁 | 下载 |
| --- | --- | --- | --- |
| Windows | 安装版 | 大多数用户，支持自动更新与系统集成 | [下载安装包](https://github.com/allen-Jmc/comfypet-jmcai-Dist/releases/download/v1.3.0/JMCAI-1.3.0-setup.exe) |
| Windows | 便携版 | 不想安装、希望放在移动盘或独立目录运行的用户 | [下载便携版](https://github.com/allen-Jmc/comfypet-jmcai-Dist/releases/download/v1.3.0/JMCAI-1.3.0-portable.exe) |
| macOS | DMG 安装包 | 希望直接拖入 Applications 的用户 | [下载 DMG](https://github.com/allen-Jmc/comfypet-jmcai-Dist/releases/download/v1.3.0/JMCAI-1.3.0.dmg) |

macOS 也提供备用压缩包：[下载 ZIP](https://github.com/allen-Jmc/comfypet-jmcai-Dist/releases/download/v1.3.0/JMCAI-1.3.0-universal-mac.zip)

## 核心能力

- 桌宠式桌面入口，把运行状态、反馈和快捷操作集中到一个轻量浮层里。
- 本地 ComfyUI 多实例管理，支持配置维护、批量启动、日志查看和状态追踪。
- Workflow Center 可导入、整理并运行 workflow，支持参数暴露、历史记录和兼容性检查。
- 内置 Agent Bridge，方便与技能包、自动化工具和远程 agent 协作。
- 支持托管实例和外部 ComfyUI 目标，能把远程算力接入到桌面端统一管理。
- 已支持远程 `image / mask / video / audio / file` 资产输入，安装 `comfyui-jmcai` 插件后可免配置接管外部目标上传。

## 安装与升级

### 首次安装

- Windows 日常使用推荐安装版，可获得开始菜单、桌面快捷方式和自动更新支持。
- Windows 便携版无需安装，解压或放到任意目录即可运行；便携版升级建议手动替换为新版本。
- macOS 推荐使用 DMG；如遇系统策略限制，也可以改用 ZIP 版本。

### 升级方式

- 安装版会通过应用内更新能力跟随 Dist 发布页的新版本。
- 便携版和 ZIP 版本建议在本页下载最新版本后手动替换旧文件。
- 每个正式版本都可以在 [Release 页面](https://github.com/allen-Jmc/comfypet-jmcai-Dist/releases/tag/v1.3.0) 查看完整产物列表与发布时间。

## 相关链接

- 主仓库：[Comfypet-JMCAI](https://github.com/allen-Jmc/Comfypet-JMCAI)
- 技能包：[comfypet-jmcai-skill-pack](https://github.com/allen-Jmc/comfypet-jmcai-skill-pack)
- 官网：[jmcai.cn](https://jmcai.cn)
- 问题反馈：[GitHub Issues](https://github.com/allen-Jmc/Comfypet-JMCAI/issues)

## 版本与支持

- 当前分发页只提供正式发布版本的介绍和下载。
- 当前官方产物覆盖 Windows 安装版、Windows 便携版和 macOS 包。
- 如需查看实现细节、架构说明或开发文档，请前往主仓库。
