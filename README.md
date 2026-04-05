# JMCAI Comfypet

JMCAI Comfypet 是一个基于 Electron、React 和 TypeScript 构建的桌面端桌宠控制台，用来承载 ComfyUI 多实例启动、运行监控、workflow 管理、硬件状态查看以及工作站快捷入口。

当前版本已经具备面向 agent 的 Workflow Center、Bridge 契约、远程资产上传和外部算力接入能力，适合用于内部演示、工作流验证和后续产品化迭代。

## 项目定位

- 以桌宠形态常驻桌面，作为轻量入口承载控制和反馈。
- 以控制中心方式管理 ComfyUI 多实例与启动配置。
- 以 Workflow Center 方式管理 ComfyUI 工作流资产、参数暴露与本地 agent bridge。
- 以 Companion 窗口方式提供快捷导航和硬件 HUD。
- 以工作站入口方式打通本地桌面应用和 Web 工作站。

## 当前版本功能

### 1. 灵动的桌宠交互 (Mascot Core)

- **🌈 灵动情感引擎**：实时感知硬件状态，根据 GPU 负载与显存压力（Calm, Warm, Hot, Critical）切换配色与情绪反馈。
- **⏰ 24 小时全天候交互**：具备时间感知能力，清晨（6-11）精神抖擞，深夜（23-6）自动进入深度睡眠模式，最大程度减少视觉干扰。
- **轻量入口**：常驻桌面，通过简单的点击即可唤起控制台、监控中心与反馈提示。

### 2. 🧠 深度联动：AI 技能包 (Skill-Pack)

- **身体与内核**：本项目作为“身体”承载视觉与调度，[comfypet-jmcai-skill-pack](https://github.com/allen-Jmc/comfypet-jmcai-skill-pack) 作为“灵魂”承载 AI 能力。
- **Agent Bridge**：内置 HTTP 服务，支持通过 API 远程触发工作流，完美对接 Claude/GPT 等 AI Agent 进行自动化绘图。

### 2. 运行中心

- 支持基于默认配置快速启动实例。
- 支持按配置批量启动多个 ComfyUI 实例。
- 支持实例状态管理：`starting`、`running`、`stopping`、`idle`、`error`。
- 支持查看实例端口、PID、实时日志。
- 支持停止实例、恢复实例、删除实例。
- 运行中的实例可一键打开浏览器访问对应端口。

### 3. 配置中心

- 支持创建、编辑、删除启动配置。
- 支持设置默认配置，供快速启动直接使用。
- 支持维护以下关键字段：
  - 配置名称
  - Python 路径
  - 工作目录
  - 补充启动参数
  - 监听地址
  - 起始端口
- 支持设置全局实例槽位上限，限制系统同时管理的实例数量。
- 对“被实例占用的配置删除”“容量小于已占用槽位”等场景提供拦截。

### 4. 硬件 HUD

- 实时展示内存占用情况。
- 在检测到 NVIDIA GPU 时展示显存占用情况。
- 当 GPU 不可用时给出原因说明。
- 硬件压力会反向影响桌宠的情绪和视觉状态。

### 5. Dock 快捷入口

- 提供监控、设置、硬件、工作站四个快捷入口。
- 可从桌宠快速展开，作为 Companion 窗口附着在主窗口周边。
- 支持打开工作站和进入工作站配置。

### 6. Workflow Center 与 Agent Bridge

- 控制中心新增 `Workflow Center` 工作区，用于管理 workflow 导入、参数暴露、目标绑定、Run Lab 和历史记录。
- 支持导入本地 ComfyUI JSON workflow：
  - API workflow 可直接导入
  - editor workflow 可借助参考 target 转换导入
- 支持“自动建议 + 人工确认”的字段暴露模式，约束 AI 只能操作暴露后的 schema。
- 支持绑定两类执行目标：
  - 托管实例池 `managedProfile`
  - 外部 ComfyUI 服务器 `externalServer`
- 支持运行前兼容性检查，避免把 workflow 提交到缺少节点的目标环境。
- 支持从 Run Lab 手工测试运行，并查看执行历史、错误和输出文件。
- 支持 workflow schema 的自动约束导入与手工修正，可区分字段约束的自动/人工来源。
- 支持维护 workflow 的 agent metadata：
  - `summary`
  - `tags`
  - `input_modalities`
  - `output_modalities`
  - `example_prompts`
- bridge run/status/history 已统一返回 typed outputs，可区分图片、视频和其他文件。
- 支持本地 HTTP Agent Bridge：
  - `GET /api/v1/health`
  - `GET /api/v1/workflows`
  - `POST /api/v1/uploads`
  - `POST /api/v1/workflows/:workflowId/runs`
  - `GET /api/v1/runs/:runId`
  - `GET /api/v1/runs/:runId/outputs/:index/content`
  - `GET /api/v1/workflows/:workflowId/history`
- 已具备供独立 Skill Pack / Python CLI 对接的桥接契约，可供 OpenClaw、Codex、Claude Code 安装后调用。
- 当前独立 skill 仓规范名为 `comfypet-jmcai-skill-pack`，GitHub 地址为 `https://github.com/allen-Jmc/comfypet-jmcai-skill-pack`，正式可安装 payload 位于 `skills/comfypet-jmcai-skill/`。
- 当前 bridge 默认监听 `0.0.0.0:32100`，可在 Workflow Center 切换为仅本机或自定义监听地址。
- 远程调用场景下，skill 可自动上传本机 `image / mask / video / audio / file` 资产参数，并自动下载 bridge 侧输出到调用机本地路径。
- `externalServer` 目标已支持 `audio / video / file` 远程输入；安装 `comfyui-jmcai` 插件后，可自动接管这三类上传能力，无需用户手工配置适配器。

### 7. 工作站入口

- 支持优先拉起本地桌面工作站应用。
- 当本地桌面应用启动失败时，自动回退到 Web 工作站。
- 支持独立配置桌面端执行路径和命令行参数。
- 默认 Web 工作站地址为 `https://jmcai.cn`。

### 8. 系统体验

- 启动阶段包含 Splash 反馈。
- 支持系统托盘常驻。
- 关闭应用前会自动停止已管理实例。
- 支持跨窗口状态同步与轻提示反馈。

## 技术栈

- Electron
- React 19
- TypeScript
- electron-vite
- Tailwind CSS
- Playwright（QA 自动化）

## 快速开始

### 安装依赖

```bash
npm install
```

### 启动开发环境

```bash
npm run dev
```

### 启动预览

```bash
npm run start
```

### 类型检查

```bash
npm run typecheck
```

### 代码检查

```bash
npm run lint
```

## 打包命令

```bash
# 通用构建
npm run build

# Windows 安装包
npm run build:win

# Windows 目录输出
npm run build:dir

# Windows 便携版
npm run build:portable

# macOS
npm run build:mac

# Linux
npm run build:linux
```

## 发布与分发

- 源码版本使用 `vX.Y.Z` tag，例如 `v1.3.0`。
- 安装包构建使用 `desktop-vX.Y.Z` tag，例如 `desktop-v1.3.0`。
- 用户可下载安装包、便携版和 DMG 统一发布到 `allen-Jmc/comfypet-jmcai-Dist`，桌面端主仓本身不单独维护 installer release。

## QA / 验证命令

```bash
# 真实冒烟验证
npm run qa:real-smoke

# 监听地址相关冒烟验证
npm run qa:listen-smoke

# Workflow Center / Agent Bridge 冒烟验证
npm run qa:workflow-smoke
```

QA 产物会输出到仓库下的 `qa-artifacts/` 目录。

## 项目结构

```text
src/
  main/        Electron 主进程、窗口控制、IPC、实例管理、workflow 服务
  preload/     渲染进程安全桥接 API
  renderer/    React 界面与交互逻辑
  shared/      主进程与渲染进程共享协议
docs/          架构、规范与使用说明
qa/            Playwright 冒烟测试脚本
resources/     图标与品牌资源
```

## 配置与运行说明

- 应用启动配置由本地配置文件持久化管理。
- 默认全局实例槽位上限为 `5`。
- workflow 资产独立持久化在 `userData/workflows/`，不并入 `config.json`。
- 新建配置时默认监听地址为 `0.0.0.0`，系统会自动补充：
  - `--port`
  - `--listen`
  - `--enable-cors-header *`
- 如果用户已经在“补充启动参数”里手动传入这些参数，系统会以用户参数为准，不再重复注入。

## 文档导航

- [项目使用说明](./docs/project-usage-guide.md)
- [架构总览](./docs/architecture-overview.md)
- [Workflow 架构总览](./docs/workflow-architecture-overview.md)
- [Workflow 通信与数据流](./docs/workflow-communication-and-dataflow.md)
- [Workflow 存储与生命周期](./docs/workflow-storage-and-lifecycle.md)
- [Workflow 维护规范](./docs/workflow-maintenance-guidelines.md)
- [Workflow Bridge API](./docs/workflow-bridge-api.md)
- [Workflow Agent Integration Guide](./docs/workflow-agent-integration-guide.md)
- [状态与事件规范](./docs/state-and-event-conventions.md)
- [窗口与 Companion 规范](./docs/window-and-companion-guidelines.md)
- [Renderer 分层规范](./docs/renderer-structure-guidelines.md)

## 当前版本边界

- 当前主要面向 Windows 场景验证，特别是 ComfyUI 本地多实例管理流程。
- GPU 数据依赖 `nvidia-smi`，非 NVIDIA 环境会显示不可用说明。
- Workflow Bridge 当前仅监听 `127.0.0.1`，且第一阶段导入来源仅支持本地 JSON。
- 当前版本重点完成基础功能闭环，后续仍可继续补强安装引导、日志诊断、配置导入导出和更完整的异常处理体验。
