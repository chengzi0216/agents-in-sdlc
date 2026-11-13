---
title: "第 2 课 - 添加星级评分：快速改进"
description: "使用 Copilot CLI 修改游戏卡片，在转发的浏览器中检查更改，并将其作为第一个拉取请求合并。"
authors:
  - geektrainer
lastUpdated: 2026-09-18
---

你已安装 Copilot CLI 并尝试过一次对话，现在可以开始对项目进行首次更改。先从小处着手：游戏数据中已有星级评分，但主页上的游戏卡片尚未显示评分。你将请代理显示评分、审查更改，并将其作为第一个拉取请求合并。

在本课中，你将：

- 在功能分支中开始一次专注于特定任务的 Copilot 对话。
- 请代理对项目进行小幅更改。
- 使用 `/diff` 审查更改。
- 运行应用，并在转发的浏览器中确认更改。
- 创建并合并第一个拉取请求。

## 场景

Tailspin Toys 的每款游戏都可以有星级评分，而且游戏详情页已经显示了评分。不过，主页上的游戏卡片只显示标题、类别、发行商和描述。作为热身，请代理在每张卡片上显示现有评分。这个更改很小且独立，非常适合作为首次会话任务。

## 对话的组成

**对话**是你使用 Copilot CLI 完成任务的工作空间。与 Copilot app 不同，普通 CLI 对话使用终端当前检出的存储库和 Git 分支，而不会创建专用工作树。保存的对话允许你稍后返回同一讨论，而文件和分支仍是磁盘上常规的 Git 状态。

对话中有三类内容：你发送的提示和代理的响应、代理探索和编辑文件时的工具活动，以及可通过 `/diff` 检查的更改。

## 开始对话并请求更改

现在开始一个新对话来实现功能。

1. 返回 Codespace。
2. 如果终端尚未打开，请按 <kbd>Control</kbd>+<kbd>\`</kbd>（Mac）或 <kbd>Ctrl</kbd>+<kbd>\`</kbd>（Windows/Linux）。
3. 如果 Copilot 尚未运行，请使用以下命令启动：

   ```bash
   copilot --yolo
   ```

4. 使用斜杠命令 `/new` 并按 <kbd>Enter</kbd>，以确保启动新会话。
5. 发送以下提示：

   ```plaintext
   Show each game's starRating out of 5 in the game cards on the list page. If the rating is null, show "No rating yet". Keep the card layout as it is, add tests, and run the relevant checks.
   ```

Copilot 会探索项目，找到用于显示游戏详情的文件，并创建所需代码。你已使用 Copilot CLI 添加了新功能。

## 审查差异

合并前应审查所有 AI 生成的更改，即使是小改动也不例外。现在在 Copilot CLI 中检查更改。

1. 输入 `/diff` 并检查每个已更改的文件。
2. 确认存在评分时游戏卡片会显示数值；当 `starRating` 为 `null` 时会显示 `No rating yet`。
3. 确认测试覆盖这两种状态。
4. 查看 Copilot 运行的检查结果，并要求它修复任何失败。
5. 完成审查后，按 <kbd>Esc</kbd> 退出差异界面。

> [!NOTE]
> 与所有生成式 AI 工具一样，Copilot 的输出具有概率性，并非确定性，因此具体代码可能有所不同。请检查行为，而不要期待实现完全相同。

## 检查更改

不要只读代码就假定它能正常工作。请 Copilot 启动网站，以便在 Codespaces 转发的浏览器中检查用户界面 (UI)。

1. 请 Copilot 启动应用：

   ```plaintext
   Start the app so I can inspect the star-rating change in my browser. Tell me the URL and leave the server running.
   ```

2. 当 Codespaces 报告端口 `4321` 可用时，选择 **Open in Browser**。
3. 确认游戏卡片显示五星制评分。
4. 返回 Copilot，请它停止启动的服务器：

   ```plaintext
   Stop the development server you started.
   ```

## 创建并合并第一个拉取请求

你已创建此功能！现在创建拉取请求 (PR)，将新代码合并到项目中。

1. 请默认代理提交更改：

   ```plaintext
   Commit the reviewed star-rating changes with an appropriate commit message.
   ```

2. 输入 `/pr create`。Copilot CLI 创建 PR 时会推送现有提交，并显示 PR URL。
3. 按住 <kbd>Command</kbd>（Mac）或 <kbd>Ctrl</kbd>（Windows/Linux），同时选择 Copilot CLI 显示的 URL，以打开 PR。
4. 审查已更改的文件和检查结果。
5. 准备就绪后，选择 **Merge pull request** 并确认合并。
6. 返回 Codespace，并使用 `/exit` 退出 Copilot CLI。
7. 更新本地 `main`：

   ```bash
   git checkout main
   git pull
   ```

## 总结和后续步骤

恭喜！你已使用 GitHub Copilot CLI 交付了第一个更改。具体来说，你：

- 在功能分支中开始一次专注于特定任务的 Copilot 对话。
- 指导代理修改游戏卡片。
- 使用 `/diff` 审查更改。
- 运行应用，并在转发的浏览器中确认星级评分。
- 创建并合并了第一个拉取请求。

接下来，你将[从筛选议题开始，并使用 Plan 和 Autopilot 模式][next-lesson]构建更大的功能。

## 资源

- [关于 GitHub Copilot CLI][about-copilot-cli]
- [Copilot CLI 命令参考][cli-reference]

[previous-lesson]: ../1-install-copilot-cli/
[next-lesson]: ../3-agent-modes/
[about-copilot-cli]: https://docs.github.com/copilot/concepts/agents/about-copilot-cli
[cli-reference]: https://docs.github.com/copilot/reference/copilot-cli-reference/cli-command-reference
