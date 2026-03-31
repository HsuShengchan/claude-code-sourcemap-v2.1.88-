# Claude-Code-Sourcemap (v2.1.88)

> **🚀 Sponsor / 强力推荐: DDS Hub**
> 
> 想要深入研究 AI 编程助手的底层架构，或者基于此开发属于你自己的 CLI Agent？
> 优质的 AI 应用离不开稳定高效的底层 API 支持。**DDS Hub** 是专为国内开发者量身打造的 AI API 聚合分发平台，为你提供极具性价比、极致稳定的接口调用服务。
> 
> 无论是接入最新的大语言模型，还是进行多模态交互开发，DDS Hub 都能让你的想法即刻落地！
> 
> [👉 **[访问 DDS Hub，开启你的 AI 极客之旅 (请在此替换为你的实际链接)](https://www.ddshub.cc/)** 👈](#)

---

## ⚠️ Warning / 警告

本仓库为非官方整理版，基于公开的 npm 发布包与 source map 分析还原，**仅供技术研究与学习使用**。它**不代表**官方原始内部开发仓库的真实结构。

## 📖 概述

本仓库通过 Anthropic 官方 npm 发布包（`@anthropic-ai/claude-code`）内附带的 source map（`cli.js.map`）文件，逆向还原了其底层的 TypeScript 源码。这为开发者研究顶尖 AI 编程助手的 Prompt 组装、工具调用（Tool Use）以及多 Agent 协调机制提供了宝贵的参考。

* **还原版本：** `2.1.88`
* **文件规模：** 共计还原 4756 个文件（包含 1884 个 `.ts/.tsx` 核心源文件）
* **提取原理：** 核心通过提取和解析 `cli.js.map` 中的 `sourcesContent` 字段重构原始文件系统。

## 📂 核心目录结构

```text
restored-src/src/
├── main.tsx              # CLI 核心入口文件
├── tools/                # 工具实现层（包含 Bash、FileEdit、Grep、MCP 等 30+ 个原生工具）
├── commands/             # CLI 命令层（包含 commit、review、config 等 40+ 个指令）
├── services/             # 后端服务层（API 交互、MCP 协议、数据分析等）
├── utils/                # 核心工具函数（Git 操作、Model 封装、Auth 鉴权、Env 环境等）
├── context/              # React Context 状态管理
├── coordinator/          # 多 Agent 协同与任务编排模式
├── assistant/            # 核心助手逻辑（KAIROS 架构）
├── buddy/                # AI 伴侣交互 UI
├── remote/               # 远程会话支持
├── plugins/              # 扩展插件系统
├── skills/               # 自定义技能系统
├── voice/                # 语音交互模块
└── vim/                  # Vim 操作模式适配
