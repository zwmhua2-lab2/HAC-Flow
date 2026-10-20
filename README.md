# HAC-Flow (Human-Agent-Collaboration Flow)

一套抛弃重型自动化、以“人类传指针、标签门禁”为核心的极简多智能体开发流水线。
**核心哲学：0 后台脚本、0 复杂状态机、AI 流水线作业、人类最终把关。**

## 👥 角色分工
- **规划大脑 (ChatGPT)**：负责质疑需求、写架构、建 Issue（打 `proposed` 标签）。
- **格式质检 (WorkBuddy/DeepSeek)**：只审查 `proposed` 状态的任务卡，开具无情的诊断书。
- **执行手脚 (本地 Codex)**：只执行 `ready` 状态的任务卡，写代码并提 PR。
- **厂长 (Human)**：负责复制粘贴、切换标签、最终审查 Diff 并 Merge。

## 🔄 标准作业流程 (SOP)
1. **立项**：让大脑读 `ARCHITECTURE_TEMPLATE.md` 生成当前项目的 `ARCHITECTURE.md`。
2. **出题**：大脑读 `ISSUE_TEMPLATE.md`，自动在 GitHub 建 Issue，打上 `proposed` 标签。
3. **质检**：对 WorkBuddy 发暗号，让 WorkBuddy 读 `Reviewer-Rules.md` 去审查。
   - 若 FAIL：复制诊断书给大脑，大脑改完后，你手动把标签切回 `proposed`。
   - 若 PASS：你手动把标签改为 `ready`。
4. **开发**：把带 `ready` 检查的指令复制给本地 Codex，Codex 建分支、写代码、提 PR。
5. **法医**：把 PR 链接发给 DeepSeek 深度审查（查逻辑与作弊）。
6. **合并**：你看一眼 Diff，点击 `Squash and merge`。

## 🏷️ 标签状态流转
- `proposed`：待审查。
- `needs-fix`：审查未通过，待修改。
- `ready`：已放行，允许写代码。
- `blocked`：熔断，停止一切自动调用，等待人类介入。
