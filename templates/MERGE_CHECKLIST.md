# 人工合并最终检查清单 (Merge Checklist)

在点击 `Squash and merge` 前，请确认以下事项：

- [ ] **CI 是否绿灯？**（如有配置 GitHub Actions）
- [ ] **是否越权？** 点开 `Files changed`，确认没有修改任何未授权的文件。
- [ ] **是否碰红线？** 检查有没有动 `.github/`、`package.json` 等红牌文件（如有，必须要求拆独立 Issue）。
- [ ] **代码量是否失控？** 如果代码量 >300 行，说明任务切得不够细，退回重做。
- [ ] **PR 描述是否合规？** Codex 是否老实汇报了“最可能出错的 2 个点”？

**【核心门禁检查】**
- [ ] **任务卡审查**：该 Issue 是否由 WorkBuddy/DeepSeek 审查通过，并由 Human 或经 Human 明确授权者将标签切换为 `ready`？
- [ ] **代码审查**：
   - 风险判定以当前项目 `ARCHITECTURE.md` 定义的风险区域为准，不因“纯 UI”或“工具函数”就直接判定为低风险。
   - 如果**未命中风险区域**，由 Human（你）核对 Diff、验收结果和未验证项后确认。
   - 如果**命中风险区域**，**必须**将 PR 链接发给 DeepSeek 或 WorkBuddy 做代码级审查，并拿到代码审查的 **PASS**。（注意：任务卡的格式 PASS 不能替代代码审查的 PASS）。
