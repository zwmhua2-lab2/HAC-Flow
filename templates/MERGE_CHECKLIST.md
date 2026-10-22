# 合并检查清单 · v6.5

点击 Squash and merge 前逐项确认。

- [ ] 本地 `git status` 干净，且本地 AGENTS.md、ARCHITECTURE.md 与远端 main 一致（`git diff origin/main -- AGENTS.md ARCHITECTURE.md` 无输出）。
- [ ] Files changed 里只有 Issue 允许的文件，没有碰红牌文件（见 ARCHITECTURE.md C5）。
- [ ] 总改动未超过 ARCHITECTURE.md 第 5 节的单 PR 行数上限。
- [ ] PR 描述按 AGENTS.md 规则 10 齐全，每条 GWT 都有对应测试。
- [ ] 我本地拉分支实跑过，结果符合 Issue 的验收标准。
- [ ] 未验证项我看过，不把"没跑"当"通过"。

风险以项目 ARCHITECTURE.md 第 6 节为准。

## 低风险（未命中风险区域）
以上勾完即可合并。

## 高风险（命中风险区域），另加
- [ ] 已让大脑出质检指令，并在新对话里交给 WorkBuddy / DeepSeek 执行。
- [ ] 报告写明被测 commit，且与 PR 最新 commit 一致；代码改过则重新质检。
- [ ] 真实缺陷已打回 Codex 修复；纯过度防御建议（fsync、防掉电等）已过滤，不当 Bug。
- [ ] 拿到 PASS。FAIL 或 BLOCKED 不合并。PASS 只是参考，我仍亲自看关键 diff。
