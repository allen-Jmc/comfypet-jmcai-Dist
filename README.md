# JMCAI Comfypet

JMCAI Comfypet 是一个把 **桌宠陪伴感** 和 **ComfyUI 工作流控制中心** 融合在一起的桌面应用。它不只是启动器，还会通过表情、颜色和状态反馈，把你的硬件压力、运行情况和工作流操作变成有存在感的桌面交互。

**当前版本：[`v1.3.0`](https://github.com/allen-Jmc/comfypet-jmcai-Dist/releases/tag/v1.3.0)**

它的核心体验不是“再做一个控制面板”，而是让一个会观察状态、会表达情绪、会陪你工作的桌面伙伴，去承载 ComfyUI 的管理、运行和反馈。

## 为什么它像桌宠

- 它会根据运行状态切换表情、颜色和反馈节奏，让忙闲变化、报错、完成和等待都变成有情绪的桌面互动。
- 它常驻桌面，但尽量保持轻量和低打扰，需要时可以快速呼出控制台、HUD 和快捷操作。
- 它强调的是陪伴式工作体验，不是把一堆按钮塞到面板里，而是把状态感知、工作入口和反馈提醒放到一个更自然的位置。

## 下载

| 平台 | 推荐包 | 适合谁 | 下载 |
| --- | --- | --- | --- |
| Windows | 安装版 | 大多数用户，支持自动更新与系统集成 | [下载安装包](https://github.com/allen-Jmc/comfypet-jmcai-Dist/releases/download/v1.3.0/JMCAI-1.3.0-setup.exe) |
| Windows | 便携版 | 不想安装、希望放在移动盘或独立目录运行的用户 | [下载便携版](https://github.com/allen-Jmc/comfypet-jmcai-Dist/releases/download/v1.3.0/JMCAI-1.3.0-portable.exe) |
| macOS | DMG 安装包 | 希望直接拖入 Applications 的用户 | [下载 DMG](https://github.com/allen-Jmc/comfypet-jmcai-Dist/releases/download/v1.3.0/JMCAI-1.3.0.dmg) |

macOS 也提供备用压缩包：[下载 ZIP](https://github.com/allen-Jmc/comfypet-jmcai-Dist/releases/download/v1.3.0/JMCAI-1.3.0-universal-mac.zip)

## 你可以用它做什么

- **桌宠交互反馈**：根据 GPU 压力、实例忙闲、执行成功或失败切换表情和颜色，让状态变化不是藏在日志里，而是直接被看见。
- **常驻桌面入口**：把 Companion、HUD、快捷操作和消息提示放到桌面侧边，不必为了一个小动作来回切换多个窗口。
- **多实例管理**：统一维护本地 ComfyUI 多实例，支持配置管理、批量启动、状态追踪、日志查看和基础运维。
- **Workflow Center**：集中导入、整理和运行 workflow，支持参数暴露、目标绑定、兼容性检查、运行记录和结果回看。
- **远程算力接入**：可连接托管实例或外部 ComfyUI 目标，把办公室、云端或其他机器的算力接入同一个桌面入口。
- **远程资产输入**：已支持远程 `image / mask / video / audio / file` 资产输入，安装 `comfyui-jmcai` 插件后可免配置接管外部目标上传。
- **Agent 与技能包联动**：内置 Agent Bridge，可和技能包、自动化工具、远程 agent 协作，让工作流不只手动点运行，也能被调度和编排。

## 功能介绍

### 桌宠陪伴与状态感知

JMCAI Comfypet 的第一层体验不是传统控制台，而是一个会“表达状态”的桌面伙伴。它会把实例空闲、生成进行中、资源占用变化、异常反馈这些原本偏技术的信息，转成更容易感知的表情、颜色和提醒节奏。

### ComfyUI 实例控制中心

如果你本机跑了多个 ComfyUI，它可以帮你把这些实例统一收进一个地方管理。你可以在桌面端查看实例状态、维护配置、启动和停止服务、检查日志，不需要自己到处翻脚本和终端窗口。

### Workflow Center

Workflow Center 用来承接真正的工作流使用场景。你可以导入 workflow、整理分类、暴露给 agent 或技能包使用的参数、绑定目标实例，并在同一个界面里查看兼容性、执行历史和输出结果。

### 远程算力与跨设备协作

你可以把外部 ComfyUI 作为算力目标接进来，让桌面端既管理本机，也管理远程机器。对于图片、遮罩、视频、音频和文件这类输入资产，桌面端已经支持更完整的远程传输链路，适合把家里电脑、办公室机器或云端算力接入统一工作流。

### 技能包与自动化协作

如果你还在用技能包、agent 或自动化任务，JMCAI Comfypet 可以继续作为桥接层。它负责把 workflow、参数和运行结果整理成更适合上层工具调用的入口，让“桌面使用”和“自动化调用”能用同一套工作流体系。

## 安装与升级

### 首次安装

- Windows 日常使用推荐安装版，可获得开始菜单、桌面快捷方式、常驻体验和自动更新支持，也更适合长期体验桌宠交互。
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
- 如果你最关心的是“桌宠交互感”，推荐优先体验安装版，它更适合常驻桌面、持续升级和完整的陪伴式体验。
- 如需查看实现细节、架构说明或开发文档，请前往主仓库。
