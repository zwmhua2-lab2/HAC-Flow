# AGENTS.md

## 通用
- 用中文回复，简洁。
- 开工前读仓库根目录 ARCHITECTURE.md 和指定 Issue；读不到就停下报告，不凭记忆编约束。
- AGENTS.md、ARCHITECTURE.md、Issue 互相冲突，或与现有代码不符时，停下报告，不自行挑一份，不顺手改。

## 执行 Issue #N
1. 基于最新 main 建 task/N 分支；已有同名分支或 PR 先核对状态，不覆盖未提交的工作。
2. 只改 Issue "允许修改"里列出的文件。红牌文件（ARCHITECTURE.md C5）普通任务一律不碰；
   专项独立 Issue 中 Human 明确授权的路径除外。
3. 先把 Given/When/Then 原样写成测试，再写业务代码；不弱化、不删断言迁就实现。
4. 默认不新增依赖；确需新增则停下来问。
5. Issue 允许时，在 ARCHITECTURE.md 第 7 节追加一行记录，只保留最近 5 条，其余章节不动。
6. 总改动超过 ARCHITECTURE.md 第 5 节的单 PR 上限（含测试）时，先停下说明、请求拆分，不硬提。
7. 测试跑通后提 PR（closes #N）。描述写：改动文件、测试命令与实际结果、未验证项、
   最可能出错的 2 点、每条 GWT 对应哪个测试。涉及 P4 附黄金样本输出。
8. 没运行的验收不写通过。

## 结束边界
- 到提 PR 为止。不自行 merge、rebase、force push、revert；这些要我对具体动作明确下指令。
