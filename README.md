# AI Agent Workspace

本仓库定义 Codex、WorkBuddy、Muse 的协作分工、触发规则与交接格式。将仓库内容同步到本地 WorkBuddy 工作目录后，WorkBuddy 可按 `ROUTING.md` 判断任务角色。

## 分工

- `codex-project-manager/`：项目经理。拆解需求、明确验收标准、安排执行、协调跨角色工作并汇总交付。
- `workbuddy-executor/`：执行者。按任务计划修改文件、运行可用检查并报告变更与结果。
- `muse-supervisor/`：监工。独立检查需求覆盖、质量、风险和验收结果；指出问题并跟踪修复，不擅自替代执行者完成任务。
- `ROUTING.md`：触发条件、路由优先级及角色交接规则。
- `WORKBUDDY_SYNC.md`：本地同步说明。

## 快速路由

先读取 `ROUTING.md`。新需求或跨角色任务由 Codex 项目经理统筹；明确的实现任务交给 WorkBuddy；完成或需要把关时触发 Muse。小型单步任务可以由 WorkBuddy 直接执行，随后按风险决定是否交 Muse 检查。

---

## 工作区骨架

本仓库同时提供一个用于组织、开发和运行 **AI Agent** 的工作区骨架。统一的目录约定把 Agent 定义、配置、工具、数据、文档和测试集中管理，方便多人协作与持续迭代。

> 当前状态：已初始化目录骨架与角色分工文档，等待填充具体实现内容。

### 目录结构

```
ai-agent-workspace/
├── agents/                   # Agent 定义与角色配置（人格、指令、能力边界）
├── codex-project-manager/    # 项目经理角色说明（ROLE.md）
├── config/                   # 全局配置（模型参数、运行环境变量样例等）
├── data/                     # 数据 / 知识库文件（语料、向量数据、结构化数据）
├── docs/                     # 项目文档（设计说明、架构决策、使用指南）
├── examples/                 # 示例：演示如何定义和调用 Agent
├── muse-supervisor/          # 监工角色说明（ROLE.md）
├── scripts/                  # 运维 / 辅助脚本（初始化、批处理、部署）
├── src/                      # 核心源码：Agent 运行时、调度、编排逻辑
├── tests/                    # 测试用例
├── tools/                    # Agent 可调用的工具函数 / 外部 API 封装
├── workbuddy-executor/       # 执行者角色说明（ROLE.md）
├── ROUTING.md                # 触发条件、路由优先级及角色交接规则
└── WORKBUDDY_SYNC.md         # 本地同步说明
```

每个空目录中的 `.gitkeep` 仅用于占位，加入实际文件后可删除。

### 快速开始

```bash
# 1. 克隆仓库
git clone https://github.com/lxr1521/ai-agent-workspace.git
cd ai-agent-workspace

# 2. 复制环境变量样例（如有需要）
cp .env.example .env

# 3. 按你的技术栈安装依赖并运行
#    具体步骤将在核心代码落地后补充
```

### 开发一个 Agent

1. 在 `agents/` 中添加 Agent 定义（角色、系统提示词、可调用工具）。
2. 在 `tools/` 中实现该 Agent 需要的工具函数。
3. 若涉及模型或运行参数，在 `config/` 中集中配置。
4. 在 `tests/` 中补充对应测试，保证行为可回归。
5. 在 `examples/` 中给出可运行的使用示例。

### 约定

- 配置与密钥不入库：环境变量样例放 `.env.example`，真实值放 `.env`（已加入 `.gitignore`）。
- 数据与代码分离：原始数据和知识库放 `data/`，不要散落在源码中。
- 文档随代码更新：新增能力时同步更新 `docs/` 与本 README。
- 角色与路由随分工更新：调整协作规则时同步更新 `ROUTING.md` 与对应 `ROLE.md`。

### 待办

- [ ] 确定技术栈（Python / TypeScript / 其他）
- [ ] 补充 Agent 运行时核心代码
- [ ] 添加依赖管理与安装说明
- [ ] 编写第一个示例 Agent 与测试用例
