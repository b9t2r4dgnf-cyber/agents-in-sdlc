---
title: "レッスン 12 - GitHub Pages でサイトをデプロイする"
description: "GitHub Copilot アプリを使って Pages ワークフローを構成し、その pull request をレビューして、Space Quiz が公開されたことを確認します。"
authors:
  - jamesmontemagno
lastUpdated: 2026-10-12
---

Space Quiz を GitHub Pages にデプロイして、誰でもアクセスできるようにします。Copilot はワークフローを準備し、デプロイを案内できますが、変更をレビューし、サイトが公開されたことを確認する責任はユーザーにあります。

このレッスンでは、次の操作を行います。

- Copilot に GitHub Pages へのデプロイを構成するよう依頼します。
- マージする前に、ワークフローと pull request をレビューします。
- デプロイの進行状況を確認し、公開されたサイトを検証します。

## シナリオ

Space Quiz はすでに GitHub リポジトリにありますが、誰もが簡単に試せる方法が必要です。単一ファイルのサイトを GitHub Pages で公開すれば、サーバーやランタイム依存関係を追加せずに、公開 URL からアクセスできるようになります。

## Copilot にサイトのデプロイを依頼する

`space-quiz` の Copilot アプリのセッションで、次のプロンプトを送信します。

```plaintext
このリポジトリで GitHub Pages を有効にしてください。必要に応じて Web サイトをビルドし、GitHub Pages にデプロイする GitHub Actions ワークフローを作成してください。README がまだない場合は、アプリの説明とローカルでの実行方法を記載した README を追加してください。これらの変更を含む pull request を作成し、必須チェックに合格したらマージしてください。デプロイが成功するまで監視し、その後、公開された Web サイトの最終 URL を報告してください。Pages の有効化やマージの権限がない場合は、何を承認するか、何をすればよいかを正確に伝えてください。サイトが公開されるまでは成功を報告しないでください。
```

![3 段階の図: マージ済みの space-quiz pull request、Build website・Upload artifact・Deploy to Pages の各ステップが成功した GitHub Actions の Deploy website 実行、yourname.github.io/space-quiz/ で公開された Space Quiz。](../../../_images/first-steps-app-pages-deploy.svg)

> [!WARNING]
> このプロンプトは、エージェントに pull request の作成とマージ、およびリポジトリの Pages 設定の変更を依頼します。続行する前に、差分、デプロイ権限、GitHub の承認要求を確認してください。

## ワークフローをレビューしてデプロイを確認する

1. README は、リポジトリにまだ存在しない場合にのみ追加されたことを確認します。
2. ワークフローのビルド手順とデプロイ手順を含め、pull request の変更をレビューします。
3. pull request の必須チェックに合格した後にのみマージします。
4. GitHub Actions のデプロイ実行が成功するまで確認します。
5. 報告された URL を開き、Space Quiz が読み込まれることを確認します。

エージェントが Pages を有効にできない場合や pull request をマージできない場合は、提示された具体的な手順に従ってください。デプロイが成功し、公開サイトが読み込まれるまで、タスクを完了と見なさないでください。

## まとめと次のステップ

Space Quiz が公開サイトとして利用できるようになり、エージェントの報告に頼らずデプロイを確認しました。続けて[レッスン 13: 振り返りと次のステップ][next-lesson]に進みます。

[next-lesson]: ../13-review/
