# 人工合并最终检查清单 (Merge Checklist)

在点击 `Squash and merge` 前，请确认以下事项：

- [ ] **CI 是否绿灯？**（如有配置 GitHub Actions）
- [ ] **是否越权？** 点开 `Files changed`，确认没有修改任何未授权的文件。
- [ ] **是否碰红线？** 检查有没有动 `.github/`、`package.json` 等红牌文件（如有，必须要求拆独立 Issue）。
- [ ] **代码量是否失控？** 如果代码量 >300 行，说明任务切得不够细，退回重做。
- [ ] **PR 描述是否合规？** Codex 是否老实汇报了“最可能出错的 2 个点”？
- [ ] **审查是否通过？** DeepSeek 或 WorkBuddy 是否给出了 PASS 结论？
