---
title: "レッスン 10 - まとめと次のステップ"
description: "Copilot CLI のワークフロー、2 つのプルリクエスト、再利用できるカスタマイズ、追加リソースを振り返ります。"
authors:
  - geektrainer
lastUpdated: 2026-09-29
---

一連の Tailspin Toys のワークフローで GitHub Copilot CLI を使用しました。次のことを行いました。

- Codespace を準備し、Copilot CLI をインストールし、プロジェクトを確認して、登録済みのフィルタリング issue を見つけました。
- 星評価を追加し、転送されたブラウザーで結果を確認して、最初のプルリクエスト (PR) を手動でマージしました。
- フィルタリング issue から始め、Plan モードでアプローチを決め、Autopilot モードで実装し、Interactive モードでレビューしました。
- カスタム指示でエージェントをガイドし、既存の `quality-checks` スキルをカスタマイズして、単体テスト、lint、型チェックを実行しました。
- Playwright Model Context Protocol (MCP) サーバーを追加し、実際のブラウザーでフィルタリングを確認しました。
- 品質保証 (QA) のカスタム エージェントを作成して選択し、要件、カバレッジ、スキルの結果、ブラウザーでの検証結果を評価しました。
- フィルタリングの変更全体をレビューし、フィルタリング PR の Agent Merge を承認しました。
- コンテキスト、モデル、共有、任意のクラウドへの委任に使えるスラッシュ コマンドを確認しました。

## 成果

このワークショップでは、更新済みの `main` から作成したそれぞれ独自のブランチで、2 つの PR を行います。

1. **星評価:** 既存の `starRating` と、評価がないことを明示する状態をゲーム カードに表示します。
2. **フィルタリングと品質ワークフロー:** フィルタリングを実装し、指示を更新して機能に適用し、`quality-checks` レポートをカスタマイズし、QA プロファイルを作成して、関連するテストを含めます。

フィルタリングの計画から PR の作成まで、同じ会話とブランチを使用しました。ワークショップを効率化するため、この作業を 1 つの PR にまとめました。

## さまざまな検証方法

自動テスト、自分で行うブラウザー確認、MCP を通じた Copilot のブラウザー操作など、複数の方法でコードを確認しました。`quality-checks` スキルは単体テスト、lint、型チェックを実行し、新しい形式で結果を報告しました。QA では、それらの結果と PR 前の要件およびテスト カバレッジのレビューをまとめました。

追加するテストは実際の不足を補うものである必要があります。QA の実行で新しいテストが不要と判断されても、正しい場合があります。ツールの不足、未実施のチェック、失敗は明確なブロッカーであり、合格ではありません。マージを承認する前にコードと検証結果を確認し、変更後は影響を受ける検証結果を更新してください。

## ベスト プラクティス

Copilot に提供するコンテキストとツールが、作業の内容を左右します。このワークショップでは、指示を更新し、スキルをカスタマイズし、QA プロファイルを作成し、MCP サーバーを構成しました。これらのカスタマイズをセッション間で再利用し、チームのニーズに合わせて調整してください。指示は標準を定め、スキルは繰り返し実行するタスクを説明し、カスタム エージェントは専門的な役割を定義し、MCP サーバーは外部ツールに接続します。エージェントの要約だけでなく、実際の変更とツールの結果を確認してください。

タスクに合わせて**モードとモデル**を選びます。実装前に方法を検討するときは **Plan**、範囲の絞られた変更を進めながら確認するときは **Interactive**、範囲が明確で独立したタスクに限り **Autopilot** を使います。定型的な編集には高速なモデルを、複雑な作業には推論能力の高いモデルを選びます。

コンテキストは、インフラストラクチャと同じくらい重要です。何を、なぜ、どのように作りたいかを明確に伝えることで、出力は大きく変わります。簡単なチャットでアイデアを整理してから、完全なセッションを開始することもできます。

## さらに確認する

基本的なワークフローを学びました。次の機能も確認できます。

- [**自動化**][using-automations] は、最近の作業の要約など、定期的または必要に応じて実行するタスクに使えます。利用する前にスケジュール、権限、範囲を確認してください。自動化の作成は次のステップであり、このワークショップには含まれません。
- **Rubber duck** を使うと、実装前に問題を話し合い、的確なフィードバックを得られます。
- [`/chronicle`][chronicle] を使うと、セッションで起きたことを物語形式で生成できます。
- [独自のキーを持ち込む (BYOK)][byok] と、Ollama、Foundry Local、LM Studio などを使ったローカル モデルを含め、独自のプロバイダーのモデルを利用できます。
- [ディープ リンク][deep-links] を使うと、リポジトリ、セッション、プロンプトを指定してアプリを直接開けます。

## 次のステップ

どのツールでも、上達する最善の方法は使い続けることです。本番コード、個人のプロジェクト、何年も作ろうと思いながら実現できていない小さなアプリなどで活用してください。学んだことをチームと共有し、チームの経験からも学びましょう。そして、いつものようにドキュメントを確認してください。

GitHub Copilot のエコシステムをさらに確認するには、[VS Code ハーネス][vscode-harness]、[Copilot CLI ハーネス][cli-harness]、または [Cloud agent ハーネス][cloud-harness]を参照してください。

## リソース

- [GitHub Copilot app について][about-copilot-app]
- [GitHub Copilot app を使い始める][getting-started]
- [GitHub Copilot app をカスタマイズする][customize]
- [自動化を使用する][using-automations]
- [キャンバス拡張機能を使う][canvas-docs]

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
