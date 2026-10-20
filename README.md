# HAC-Flow (Human-Agent-Collaboration Flow)

一套抛弃重型自动化、以“人类传指针、异源 QA 兜底”为核心的极简多智能体开发流水线。
**核心哲学：0 后台脚本、0 复杂状态机、拒绝标签流转、人类最终把关。**

## 👥 角色分工
- **规划大脑 (ChatGPT)**：负责质疑需求、读架构、建 Issue，并吐出给 Codex 和 QA 的指令。
- **执行手脚 (本地 Codex)**：读 `AGENTS.md`，建分支、写测试、写代码、提 PR。
- **异源 QA (DeepSeek/WorkBuddy)**：只在**高风险 PR** 时介入。作为黑盒测试员，写独立探针，抓静默失败和逻辑漏洞。
- **厂长 (Human)**：负责复制粘贴指令、本地实跑验收、最终审查 Diff 并 Merge。

## 🔄 标准作业流程 (SOP)

1. **立项（仅首次）**：让大脑读 `ARCHITECTURE_TEMPLATE.md` 生成当前项目的 `ARCHITECTURE.md`，人工提交到 main。
2. **出题**：大脑读架构，自动建 Issue，并直接吐出两段代码块（给 Codex 的代码指令 + 给 QA 的验收指令）。
3. **开发**：你把 Codex 指令复制给本地终端，Codex 跑完测试后提 PR。
4. **验收（核心防线）**：
   - *低风险 PR*：你亲自看 Diff，本地实跑，直接 Merge。
   - *高风险 PR（碰网络/文件读写/并发/正则）*：把 QA 指令和 PR 链接发给 DeepSeek。DeepSeek 跑独立黑盒测试。发现 Bug 打回 Codex 修，直到 DeepSeek 给 `PASS`。
5. **合并**：对照 `MERGE_CHECKLIST.md` 检查无误后，点击 `Squash and merge`，清理分支。

## 🚫 明确抛弃的历史包袱
- **不再审查任务卡格式**：ChatGPT 的出卡模板已经锁死了格式，不需要 AI 审 AI。
- **不再使用任何 GitHub 标签（无 proposed/ready）**：只要人类把指令发给 Codex，它就开始干活；没发，它就不动。
