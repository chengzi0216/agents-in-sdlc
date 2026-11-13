---
title: "第 8 课 - 创建并合并功能 PR"
description: "一起审查筛选功能、指令、技能更新、QA 配置和测试，然后创建 PR 并使用 Agent Merge。"
authors:
  - geektrainer
lastUpdated: 2026-09-18
---

筛选功能实现、指令更新、技能更新、质量保证 (QA) 配置和测试都保存在同一个分支中。现在可以一起审查这些更改并创建拉取请求。你已经亲自合并了星级评分 PR；这次将由 **Agent Merge** 管理合并流程。

> [!NOTE]
> 通常，我们会将功能、指令更新、技能更新和 QA 代理拆分为多个 PR。为了简化研讨会，你在同一会话和分支中完成了整个筛选和质量工作流，并会将所有更改放入这个 PR。

在本课中，你将：

- 了解 Agent Merge 及其如何自动化 PR 生命周期。
- 检查完整的功能更改和验证证据。
- 创建筛选 PR。
- 仅在审查后启用 Agent Merge，并确认 PR 已合并。

## 场景

在筛选工作流中，你使用 Copilot 规划、实现并验证了一项功能。Tailspin Toys 现在希望自动完成剩余的 PR 工作，同时由开发人员控制合并授权。

## 了解 Agent Merge

**Agent Merge** 会自动完成合并拉取请求所需的剩余工作。启用后，Copilot 会处理 PR 的阻碍事项，例如修复失败的持续集成 (CI) 检查、回复审查意见，以及在需要时变基。如果存储库允许，它还会启用 GitHub 自动合并。

到目前为止，你都是亲自选择 **Merge pull request**。Agent Merge 可以接手这项工作。启用之前，请先审查并确认更改已准备就绪。

## 使用 Agent Merge 管理 PR

代码已全部完成。现在一起审查更改、创建 PR，并让 Agent Merge 管理后续流程。

1. 返回 Codespace。
2. 输入 `/agent` 打开代理对话框。
3. 从选项列表中选择 **Default**，然后按 <kbd>Enter</kbd>。
4. 使用命令 `/pr create` 创建新 PR。
5. 使用 `/pr agentmerge` 启用 Agent Merge。
6. Copilot 将监视 PR 的持续集成过程。所有检查通过后，它会执行合并。
7. 确认 Copilot 显示了类似 "PR #14 was squash-merged successfully." 的消息。

> [!IMPORTANT]
> Agent Merge 不会绕过必需的审批、分支保护、合并队列、存储库设置或缺失的权限。如果流程受阻，请查看报告的原因；在存储库允许的情况下，手动完成已审查的合并。

## 总结和后续步骤

你已自动化开发流程中的多个部分，包括代码生成、测试和验证，以及现在的拉取请求流程。你：

- 了解了 Agent Merge 及其如何自动化 PR 生命周期。
- 检查了完整的功能更改和验证证据。
- 创建了筛选 PR。
- 仅在审查后启用 Agent Merge，并确认 PR 已合并。

接下来，你将[探索 Copilot CLI 的实用斜杠命令][next-lesson]，管理上下文、模型、共享和可选云委派。

## 资源

- [使用 Copilot CLI 管理拉取请求][manage-prs]
- [Copilot CLI 命令参考][cli-reference]

[previous-lesson]: ../7-qa-agent/
[next-lesson]: ../9-cli-power-tools/
[manage-prs]: https://docs.github.com/copilot/how-tos/copilot-cli/use-copilot-cli/manage-pull-requests
[cli-reference]: https://docs.github.com/copilot/reference/copilot-cli-reference/cli-command-reference
