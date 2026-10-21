# HAC-Flow

一人开发流水线：规划大脑建 Issue → 本地 Codex 实施 → Human 本地验收 → 高风险任务异源 QA → Human 合并。
无标签、无后台脚本、无任务卡格式审查。

## 角色
- 规划大脑（ChatGPT）：质疑需求，读项目 ARCHITECTURE.md，建 Issue，回复 Issue 链接和一行执行指令。
- 执行（本地 Codex）：读项目 AGENTS.md，建分支、先写测试、写代码、提 PR。
- 异源 QA（DeepSeek / WorkBuddy）：仅高风险 PR 介入，写独立探针实跑，输出 PASS / FAIL / BLOCKED 和证据。
- Human：确认任务，本地实跑验收，决定合并。

## 流程
1. 立项（仅首次）：大脑读 templates/ARCHITECTURE_TEMPLATE.md 生成项目 ARCHITECTURE.md，Human 提交到 main。
2. 出卡：大脑建 Issue，回复 Issue 链接和一行执行指令。
3. 开发：Human 把指令交给 Codex，Codex 提 PR。
4. 验收：低风险 Human 看 Diff 并实跑；高风险再交 QA。风险区域以项目 ARCHITECTURE.md 第 6 节为准。
5. 合并：对照 templates/MERGE_CHECKLIST.md，Squash and merge。

## 文件
- prompts/workbuddy-reviewer.md：QA 规则，WorkBuddy 按链接读取，改动即生效
- templates/ARCHITECTURE_TEMPLATE.md：新项目生成架构时读取
- templates/MERGE_CHECKLIST.md：合并清单
