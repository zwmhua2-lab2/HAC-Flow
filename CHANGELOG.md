# 更新日志 · v6.6
## v6.6
- WorkBuddy 全局指令重写：岗位改为审阅、核对、整理与建议；默认只看不动；执行类请求须先复述动作、经 Human 明确许可后才做；删除"做QA 时读取 workbuddy-reviewer.md"入口。
- 删除 `prompts/workbuddy-reviewer.md`（v6.6 初版误覆盖为全局指令）；QA 判法只保留在 `prompts/qa-prompt.md`。
- 角色表落地到 README；质检统一交给 DeepSeek，WorkBuddy 只做小助手。
- 现存 8 个文件版本号统一 v6.6。

## v6.5
- QA：输入不全只提问；BLOCKED 仅用于无法验证（拉取/运行失败、HEAD 不一致）；测试断言失败与探针复现缺陷归 FAIL。
- 决定：合并保持人工，暂不引入 auto-merge。

## v6.4
- 架构拆分：ARCHITECTURE 只放项目边界、组件、硬约束、风险区域、技术栈；删除第 7 节"当前状态"。
- 白名单只在任务卡中定义，不再写在架构文件。
- Codex：删除"Issue 允许时追加第 7 节"规则，条目重新编号。
- 大脑：任务卡模板删除"状态同步"一行。
- 进度来源改为 open Issue、open PR、git log、closed Issue。
- 已有项目补改：ARCHITECTURE.md 删第 7 节、C5 去掉"仅第 7 节追加除外"；AGENTS.md 整份覆盖。
## v6.3
- Codex：删除第 9 条（内嵌 QA 模板），QA 指令只由大脑生成；新增开工前 git status 检查、测试只读已提交文件、禁止自行改名。
- 大脑：执行确认只认上一条建议里的单一动作；删除、强推、合并等操作必须由我写明具体动作。
- 合并清单：新增本地环境干净检查。

## 版本：v6.2
- QA 规则：拉取后核对 HEAD 与被测 commit；先跑 PR 自带测试，失败直接 FAIL。
- QA 输出：PASS 增加 HEAD 核对行，与 GPT 质检模板一致。
- 版本号写入所有文件标题。
