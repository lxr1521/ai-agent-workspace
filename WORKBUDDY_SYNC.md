# 同步到本地 WorkBuddy 工作目录

本仓库只提供 GitHub 文件变更能力，无法直接访问或写入你的电脑、本地 WorkBuddy 工作目录，也无法确认该目录的实际路径。因此，本次提交的是可同步的配置文件；请在本地将仓库内容拉取/复制到 WorkBuddy 实际读取的工作目录，并将该目录配置为优先读取 `ROUTING.md`。

## 建议同步内容

```text
README.md
ROUTING.md
WORKBUDDY_SYNC.md
codex-project-manager/ROLE.md
workbuddy-executor/ROLE.md
muse-supervisor/ROLE.md
```

如果 WorkBuddy 支持工作区规则文件或项目指令，将 `ROUTING.md` 设置为入口，并让三个角色分别引用对应的 `ROLE.md`。不要覆盖已有个人配置；先备份并确认 WorkBuddy 实际加载的目录及规则文件名。

同步完成后，可用一个简单任务验证：清晰的实现需求路由给 WorkBuddy；多步骤需求由 Codex 拆分；完成后按规则触发 Muse 检查。
