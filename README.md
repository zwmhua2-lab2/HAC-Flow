# HAC-flow (Human-Agent-Collaboration Flow)

**HAC-flow** 是一套专为个人开发者设计的极简人机协作流水线。
核心哲学：0 后台脚本、0 自动状态机、人类传指针、AI 流水线作业。

## 核心原则（五步法）
1. 质疑需求：不盲从，先确认真实目标。
2. 删除废话：砍掉所有不影响目标的功能。
3. 只简化核心：不优化本就不该存在的东西。
4. 加速循环：最短路径交付。
5. 拒绝过早自动化：绝不引入复杂后台监听。

## 角色分工
- **规划大脑 (ChatGPT)**：出架构、建 Issue、写契约。
- **格式质检 (WorkBuddy/DeepSeek)**：只审 proposed 状态的 Issue，抓格式漏洞。
- **执行手脚 (本地 Codex)**：只执行 ready 状态的 Issue，写代码提 PR。
- **厂长 (Human)**：传指针、打标签、审查 Diff、点 Merge。

## 标签流转门禁
- `proposed`：AI 刚建卡，等待质检。
- `needs-fix`：质检未通过，等待大脑修改。
- `ready`：人类确认，允许 Codex 开工。
