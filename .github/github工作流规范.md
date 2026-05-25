# GitHub 工作流规范

## 分支规范

| 分支名 | 用途 | 保护级别 |
|--------|------|----------|
| `main` | 生产发布 | 🔒 完全保护，仅通过 PR 合并 |
| `develop-multi-qclaw` | 主开发分支（共享） | 🔒 受保护，仅通过 PR 合并 |
| `chore/Ag{X}-NWB/...` | Agent 功能分支 | ✓ 可自由推送 |

**主分支：`develop-multi-qclaw`**

- 所有 Agent 共用 `develop-multi-qclaw` 作为基础分支
- 功能分支命名规范：`{type}/Ag{X}-NWB/{short-description}`
  - `type`: `chore` / `feat` / `fix` / `docs`
  - `X`: Agent 编号（0-8）
  - 示例：`chore/Ag1-NWB/update-config`

## 预提交检查（Pre-commit Checklist）

提交前请确认：

- [ ] 功能分支已从 `develop-multi-qclaw` 检出
- [ ] 提交信息格式正确：`{type}(Ag{X}-NWB): {简短描述}`
- [ ] 关联 Issue：`Fixes #{issue_number}`
- [ ] 文件编码为 UTF-8，无 BOM
- [ ] 不涉及本地配置文件（如 thinking 配置）

## Issue 驱动工作流

1. **创建 Issue**：描述问题/任务
2. **创建功能分支**：从 `develop-multi-qclaw` 检出
3. **提交更改**：提交信息包含 `Fixes #{issue_number}`
4. **创建 PR**：目标分支 `develop-multi-qclaw`，关联 Issue
5. **审查合并**：Ag0-NWB 审查后合并
6. **关闭 Issue**：PR 合并后自动关闭

## Agent 专属分支命名规范

| Agent | 功能分支前缀 |
|-------|--------------|
| Ag0-NWB | `chore/Ag0-NWB/...` |
| Ag1-NWB | `chore/Ag1-NWB/...` |
| Ag2-NWB | `chore/Ag2-NWB/...` |
| Ag3-NWB | `chore/Ag3-NWB/...` |
| Ag4-NWB | `chore/Ag4-NWB/...` |
| Ag5-NWB | `chore/Ag5-NWB/...` |
| Ag6-NWB | `chore/Ag6-NWB/...` |
| Ag7-NWB | `chore/Ag7-NWB/...` |
| Ag8-NWB | `chore/Ag8-NWB/...` |

## 禁止操作

- ❌ 直接推送到 `main` 或 `develop-multi-qclaw`
- ❌ 在 Issue 中混入本地配置问题（如 thinking 配置）
- ❌ 功能分支从错误的 base 检出
