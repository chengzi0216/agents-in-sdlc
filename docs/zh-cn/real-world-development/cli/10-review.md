---
title: "第 10 课 - 总结与后续步骤"
description: "回顾 Copilot CLI 工作流、两个拉取请求、可复用的自定义项和更多资源。"
authors:
  - geektrainer
lastUpdated: 2026-09-29
---

你在 Tailspin Toys 的连续工作流中使用了 GitHub Copilot CLI。你完成了以下工作：

- 准备 Codespace、安装 Copilot CLI、浏览项目，并找到预先创建的筛选议题。
- 添加星级评分，在转发的浏览器中检查结果，并手动合并了第一个拉取请求 (PR)。
- 从筛选议题开始，在 Plan 模式下确定方案，在 Autopilot 模式下实现，并在 Interactive 模式下审查。
- 使用自定义指令指导代理，然后自定义现有的 `quality-checks` 技能，用它运行单元测试、lint 和类型检查。
- 添加 Playwright Model Context Protocol (MCP) 服务器，并用它在真实浏览器中探索筛选功能。
- 创建并选择质量保证 (QA) 自定义代理，以评估需求、覆盖范围、技能结果和浏览器证据。
- 审查完整的筛选更改，并授权 Agent Merge 合并筛选 PR。
- 探索用于管理上下文、模型、共享以及可选云委派的斜杠命令。

## 已交付的内容

本研讨会有两个 PR 里程碑，每个里程碑都从更新后的 `main` 创建独立分支：

1. **星级评分：** 在游戏卡片上显示现有的 `starRating`，并明确显示未评分状态。
2. **筛选和质量工作流：** 实现筛选，更新指令并将其应用于功能，自定义 `quality-checks` 报告，创建 QA 配置，并加入相关测试。

从规划筛选功能到创建 PR，你一直使用同一会话和分支。为了简化研讨会，我们将这些工作合并到一个 PR 中。

## 不同的验证方式

你通过多种方式检查代码：自动化测试、亲自在浏览器中检查，以及通过 MCP 使用 Copilot 探索浏览器。`quality-checks` 技能运行了单元测试、lint 和类型检查，并按新格式报告结果。创建 PR 之前，QA 将这些结果与需求及测试覆盖率审查结合起来。

添加的测试应弥补真实缺口；QA 运行后无需添加测试也可能是正确结果。缺少工具、跳过检查和失败都是明确的阻碍，不能视为通过。授权合并之前，请审查代码和证据；更改后应更新受影响的证据。

## 最佳实践

你提供给 Copilot 的上下文和工具会影响它的工作。在本研讨会中，你更新了指令、自定义了技能、创建了 QA 配置，并配置了 MCP 服务器。可以在多个会话中重复使用这些自定义项，并根据团队需求调整。指令设定标准，技能描述可重复执行的任务，自定义代理定义专家角色，MCP 服务器连接外部工具。请审查实际更改和工具结果，而不只是代理的摘要。

根据任务选择**模式和模型**。在开始构建前分析方案时使用 **Plan**，处理范围明确的更改并保持参与时使用 **Interactive**，仅对范围清晰且相互独立的任务使用 **Autopilot**。日常编辑可选择较快的模型；复杂工作则选择推理能力更强的模型。

上下文和基础设施同样重要。清楚说明要构建*什么*、*为什么*以及*如何*构建，会显著影响输出。快速聊天有助于在开始完整会话前理清想法。

## 进一步探索

你已经完成核心工作流。还可以了解以下功能：

- [**自动化**][using-automations] 可用于定期或按需执行的任务，例如总结近期工作。采用自动化之前，请检查计划、权限和范围。创建自动化是后续步骤，不属于本研讨会的内容。
- **Rubber duck** 可用于讨论问题，并在开始构建前获得有价值的反馈。
- [`/chronicle`][chronicle] 可生成会话过程的叙述。
- [使用自己的密钥 (BYOK)][byok] 可使用自己提供商的模型，包括通过 Ollama、Foundry Local 或 LM Studio 使用本地模型。
- [深层链接][deep-links] 可直接打开应用中的存储库、会话或提示。

## 后续步骤

提升任何工具使用能力的最好方法就是持续使用它。将它用于生产代码、个人项目，或那个想了很多年却一直没开始开发的小应用。与团队分享经验，也向团队学习。一如既往，请继续查阅文档。

如果想继续探索 GitHub Copilot 生态系统，请参阅 [VS Code 路径][vscode-harness]、[Copilot CLI 路径][cli-harness] 或 [Cloud agent 路径][cloud-harness]。

## 资源

- [关于 GitHub Copilot app][about-copilot-app]
- [开始使用 GitHub Copilot app][getting-started]
- [自定义 GitHub Copilot app][customize]
- [使用自动化][using-automations]
- [使用画布扩展][canvas-docs]

[vscode-harness]: ../../vscode/
[cli-harness]: ../../cli/
[cloud-harness]: ../../cloud/
[about-copilot-app]: https://docs.github.com/copilot/concepts/agents/github-copilot-app
[getting-started]: https://docs.github.com/copilot/how-tos/github-copilot-app/getting-started
[customize]: https://docs.github.com/copilot/how-tos/github-copilot-app/customize-github-copilot-app
[using-automations]: https://docs.github.com/copilot/how-tos/github-copilot-app/using-automations
[canvas-docs]: https://docs.github.com/copilot/how-tos/github-copilot-app/working-with-canvas-extensions
[chronicle]: https://docs.github.com/copilot/how-tos/copilot-cli/use-copilot-cli/chronicle
[byok]: https://docs.github.com/copilot/how-tos/github-copilot-app/use-byok-models
[deep-links]: https://docs.github.com/copilot/how-tos/github-copilot-app/open-with-deep-links
