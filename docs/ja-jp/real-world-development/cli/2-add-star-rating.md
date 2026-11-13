---
title: "レッスン 2 - 星評価を追加する: すぐにできる小さな改善"
description: "Copilot CLI でゲーム カードに小さな変更を加え、転送されたブラウザーで確認して、最初のプルリクエストとしてマージします。"
authors:
  - geektrainer
lastUpdated: 2026-09-18
---

Copilot CLI をインストールし、会話を試しました。次は、プロジェクトに最初の変更を加えます。変更は小さくします。ゲームのデータにはすでに星評価がありますが、ホーム ページのゲーム カードにはまだ表示されていません。エージェントに表示を依頼し、変更をレビューして、最初のプルリクエストとしてマージします。

このレッスンでは、次の操作を行います。

- 機能ブランチで Copilot との会話を開始します。
- エージェントにプロジェクトの小さな変更を依頼します。
- `/diff` で変更をレビューします。
- アプリを実行し、転送されたブラウザーで変更を確認します。
- 最初のプルリクエストを作成してマージします。

## シナリオ

Tailspin Toys の各ゲームには星評価を設定でき、ゲームの詳細ページにはすでに表示されています。一方、ホーム ページのゲーム カードにはタイトル、カテゴリ、パブリッシャー、説明しか表示されていません。ウォームアップとして、各カードに既存の評価を表示するようエージェントに依頼します。初めてのセッションに適した、小規模で独立した変更です。

## 会話の構造

**会話**は、Copilot CLI でタスクに取り組む場所です。Copilot app と異なり、通常の CLI 会話では専用の worktree を作成せず、ターミナルで現在チェックアウトされているリポジトリと Git ブランチを使用します。保存した会話に戻って同じ話題を続けることができますが、ファイルとブランチはディスク上の通常の Git 状態のままです。

会話では、プロンプトとエージェントの応答、ファイルを調査 / 編集する際のエージェントのツール操作、`/diff` で確認できる変更の 3 つを確認できます。

## 会話を開始して変更を依頼する

新しい会話を開始して機能の実装に取りかかります。

1. Codespace に戻ります。
2. ターミナルが開いていない場合は、<kbd>Control</kbd>+<kbd>\`</kbd> (Mac) または <kbd>Ctrl</kbd>+<kbd>\`</kbd> (Windows/Linux) を押します。
3. まだ Copilot を起動していない場合は、次のコマンドを実行します。

   ```bash
   copilot --yolo
   ```

4. スラッシュ コマンド `/new` を実行し、<kbd>Enter</kbd> を押して新しいセッションを開始します。
5. 次のプロンプトを送信します。

   ```plaintext
   Show each game's starRating out of 5 in the game cards on the list page. If the rating is null, show "No rating yet". Keep the card layout as it is, add tests, and run the relevant checks.
   ```

Copilot がプロジェクトを調査し、ゲーム詳細を表示するファイルを見つけて、必要なコードを作成します。Copilot CLI で新機能を追加できました。

## 差分をレビューする

小さな変更でも、AI が生成した変更はすべてマージ前にレビューします。Copilot CLI で変更を確認しましょう。

1. `/diff` を入力し、変更されたファイルをすべて確認します。
2. 評価がある場合は数値が表示され、`starRating` が `null` の場合は `No rating yet` と表示されることを確認します。
3. テストが両方の状態を対象にしていることを確認します。
4. Copilot が実行したチェックの結果を確認し、失敗があれば修正を依頼します。
5. レビューが終わったら <kbd>Esc</kbd> を押して差分画面を終了します。

> [!NOTE]
> Copilot は、すべての生成 AI ツールと同様に確率的に動作し、決定的ではありません。そのため、コードの内容は異なる場合があります。完全に同じ実装を期待するのではなく、動作を確認してください。

## 変更を確認する

コードを読んだだけで動作すると判断しないでください。Copilot に Web サイトを起動してもらい、Codespaces から転送されたブラウザーで UI を確認します。

1. Copilot にアプリの起動を依頼します。

   ```plaintext
   Start the app so I can inspect the star-rating change in my browser. Tell me the URL and leave the server running.
   ```

2. Codespaces でポート `4321` が使用可能になったら、**Open in Browser** を選択します。
3. ゲーム カードに 5 段階の評価が表示されることを確認します。
4. Copilot に戻り、起動したサーバーの停止を依頼します。

   ```plaintext
   Stop the development server you started.
   ```

## 最初のプルリクエストを作成してマージする

機能を作成できました。新しいコードをプロジェクトに取り込むプルリクエスト (PR) を作成します。

1. 既定のエージェントに変更のコミットを依頼します。

   ```plaintext
   Commit the reviewed star-rating changes with an appropriate commit message.
   ```

2. `/pr create` を入力します。Copilot CLI は PR の作成時に既存のコミットをプッシュし、PR の URL を表示します。
3. <kbd>Command</kbd> (Mac) または <kbd>Ctrl</kbd> (Windows/Linux) を押しながら、Copilot CLI が表示した URL を選択して PR を開きます。
4. 変更されたファイルとチェック結果を確認します。
5. 問題がなければ **Merge pull request** を選択し、マージを確定します。
6. Codespace に戻り、`/exit` で Copilot CLI を終了します。
7. ローカルの `main` を更新します。

   ```bash
   git checkout main
   git pull
   ```

## まとめと次のステップ

おめでとうございます。GitHub Copilot CLI を使って最初の変更をリリースしました。具体的には、次のことを行いました。

- 機能ブランチで Copilot との会話を開始しました。
- エージェントにゲーム カードの小さな変更を依頼しました。
- `/diff` で変更をレビューしました。
- アプリを実行し、転送されたブラウザーで星評価を確認しました。
- 最初のプルリクエストを作成してマージしました。

次は、[フィルタリング issue から始めて Plan モードと Autopilot モードを使い][next-lesson]、より大きな機能を作成します。

## リソース

- [GitHub Copilot CLI について][about-copilot-cli]
- [Copilot CLI コマンド リファレンス][cli-reference]

[previous-lesson]: ../1-install-copilot-cli/
[next-lesson]: ../3-agent-modes/
[about-copilot-cli]: https://docs.github.com/copilot/concepts/agents/about-copilot-cli
[cli-reference]: https://docs.github.com/copilot/reference/copilot-cli-reference/cli-command-reference
