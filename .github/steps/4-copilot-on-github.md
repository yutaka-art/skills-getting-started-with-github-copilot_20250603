## ステップ4: プルリクエストで GitHub Copilot を使おう

おめでとうございます！この演習（および VS Code でのコーディング）は完了です。いよいよ作業をマージしましょう。:tada: 最後に、プルリクエストを効率化できる Copilot の限定機能を2つ紹介します！

#### Copilot プルリクエスト要約

通常は、メモやコミットメッセージを見直してプルリクエストの説明をまとめますが、コミットメッセージがバラバラだったりコードにコメントが少ないと時間がかかります。Copilot なら、プルリクエスト内のすべての変更を考慮し、重要なポイントを（参照付きで）要約してくれます。

> [!NOTE]  
> この機能は **GitHub Copilot Free** では利用できません。[[ドキュメント]](https://docs.github.com/ja/enterprise-cloud@latest/copilot/using-github-copilot/using-github-copilot-for-pull-requests/creating-a-pull-request-summary-with-github-copilot)

#### Copilot コードレビュー

作業を他の目でチェックするのはとても有効です。通常のピアレビューの前に、Copilot に一次レビューを依頼しましょう。Copilot は簡単な修正で直せる一般的なミスを見つけるのが得意ですが、使う際は責任を持って活用してください。

> [!NOTE]  
> この機能は **GitHub Copilot Free** では利用できません。[[ドキュメント]](https://docs.github.com/ja/copilot/using-github-copilot/code-review/using-copilot-code-review)

### :keyboard: アクティビティ: Copilot でPRの要約とレビューをしよう

**Copilot プルリクエスト要約** と **Copilot コードレビュー** はどちらも限定機能なので、このアクティビティは基本的に任意です。利用できる場合は Mona が作業をチェックしてくれます。利用できない場合はこのステップをスキップしても構いません。

1. Webブラウザで新しいタブを開き、自分の演習リポジトリにアクセスします。

1. **新しいプルリクエストを作成する**よう通知バナーが表示される場合があります。それをクリックするか、上部の **Pull Requests** タブから新規プルリクエストを作成してください。以下の内容を使いましょう：

   - **base:** `main`
   - **compare:** `accelerate-with-copilot`
   - **title:** `Add registration validation and more activities`

1. （任意）**Add a description** エリアで編集モードに切り替え、**Copilot actions** アイコンから **Summary** を選択します。しばらくすると Copilot が説明文を追加してくれます。:memo:

   <img alt="Copilot summarize button " width="300px" src="https://github.com/user-attachments/assets/3fc5fab4-db03-4ab8-8a16-cdd71ec2ded0">

1. （任意）右側の情報パネル上部にある **Reviewers** セクションで、**Copilot アイコン**横の **Request** ボタンをクリックします。しばらく待つと Copilot がレビューコメントを追加してくれます。

   <img alt="Copilot review button" width="300px" src="https://github.com/user-attachments/assets/39b15002-a235-4c25-b09d-6a8097e27b62">

   > **ヒント:** Copilot にレビューを依頼したログが記録されていることに注目してください。

1. 下部の **Merge pull request** ボタンを押します。お疲れさまでした！これで完了です！:tada:

1. Mona が作業を確認し、フィードバックやこのレッスンの最終レビューを投稿するまで少し待ちましょう。
