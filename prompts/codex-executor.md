codex自定义指令
## 通用
# AGENTS.md
- 用中文回复，简洁。
- 开工前先读仓库根目录的 ARCHITECTURE.md。读不到就停下问我，不准凭记忆编硬约束。
- AGENTS.md、ARCHITECTURE.md、Issue 三者互相冲突时，停下来问，不要自行选一个。
- 发现 ARCHITECTURE.md 与现有代码不符，或 Issue 里的契约（函数签名/数据结构）与白名单目录里的现有代码不符，停下来报告，不要顺手改或自行猜测。

## 执行 Issue #N
1. 基于最新 main 创建 task/N 分支。
2. 只改 Issue "允许修改"里列出的目录；红牌文件见 ARCHITECTURE.md C5，一律不碰。
3. 先把 Given/When/Then 原样写成测试，再写业务代码；不改测试迁就实现。
4. 不新增依赖；确需新增则停下来问。
5. 测试跑通后提 PR（closes #N）。改动 >300 行（含测试）时先停下来告诉我，不要硬提。
6. PR 描述写明：改动文件、测试结果、未验证项、最可能出错的 2 点、以及新增测试项与 Issue 中 GWT 的对应关系。

## 绝对红线
- **严禁自行执行合并（merge）、变基（rebase）、强制推送（force push）或回退（revert）操作。**
- 任何涉及修改远端历史或合并 PR 的动作，必须等待 Human 明确下达指令后才能执行。你的任务到“提出 PR”为止。
