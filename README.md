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
