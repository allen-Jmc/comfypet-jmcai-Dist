# JMCAI Comfypet

JMCAI Comfypet 是一个把 **桌宠陪伴感** 和 **ComfyUI 工作流控制中心** 融合在一起的桌面应用。它不只是启动器，还会通过表情、颜色和状态反馈，把你的硬件压力、运行情况和工作流操作变成有存在感的桌面交互。

**当前版本：[`v1.3.0`](https://github.com/allen-Jmc/comfypet-jmcai-Dist/releases/tag/v1.3.0)**

它的核心体验不是“再做一个控制面板”，而是让一个会观察状态、会表达情绪、会陪你工作的桌面伙伴，去承载 ComfyUI 的管理、运行和反馈。

## 下载

| 平台 | 推荐包 | 适合谁 | 下载 |
| --- | --- | --- | --- |
| Windows | 安装版 | 大多数用户，支持自动更新与系统集成 | [下载安装包](https://github.com/allen-Jmc/comfypet-jmcai-Dist/releases/download/v1.3.0/JMCAI-1.3.0-setup.exe) |
| Windows | 便携版 | 不想安装、希望放在移动盘或独立目录运行的用户 | [下载便携版](https://github.com/allen-Jmc/comfypet-jmcai-Dist/releases/download/v1.3.0/JMCAI-1.3.0-portable.exe) |
| macOS | DMG 安装包 | 希望直接拖入 Applications 的用户 | [下载 DMG](https://github.com/allen-Jmc/comfypet-jmcai-Dist/releases/download/v1.3.0/JMCAI-1.3.0.dmg) |

macOS 也提供备用压缩包：[下载 ZIP](https://github.com/allen-Jmc/comfypet-jmcai-Dist/releases/download/v1.3.0/JMCAI-1.3.0-universal-mac.zip)

## 核心能力

- 桌宠会根据运行状态给出表情和颜色反馈，把 GPU 压力、忙闲变化和系统状态变成直观的情绪化交互。
- 常驻桌面的轻量入口可以随时呼出控制台、反馈提示和快捷操作，不用反复切换窗口找功能。
- Companion 式交互把监控、硬件 HUD 和工作入口合并到一个更轻、更有陪伴感的桌面体验里。
- 本地 ComfyUI 多实例管理，支持配置维护、批量启动、日志查看和状态追踪。
- Workflow Center 可导入、整理并运行 workflow，支持参数暴露、历史记录和兼容性检查。
- 内置 Agent Bridge，方便与技能包、自动化工具和远程 agent 协作。
- 支持托管实例和外部 ComfyUI 目标，能把远程算力接入到桌面端统一管理。
- 已支持远程 `image / mask / video / audio / file` 资产输入，安装 `comfyui-jmcai` 插件后可免配置接管外部目标上传。

## 安装与升级

### 首次安装

- Windows 日常使用推荐安装版，可获得开始菜单、桌面快捷方式、常驻体验和自动更新支持。
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
- 如果你最关心的是“桌宠交互感”，推荐优先体验安装版，它更适合常驻桌面和持续升级。
- 如需查看实现细节、架构说明或开发文档，请前往主仓库。
