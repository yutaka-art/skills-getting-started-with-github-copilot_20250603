## ステップ1: Hello Copilot

**「GitHub Copilot はじめてガイド」** 演習へようこそ！:robot:

この演習では、Mergington High School の生徒が課外活動に申し込めるウェブサイトを題材に、さまざまな GitHub Copilot の機能を使っていきます。🎻 ⚽️ ♟️

<img width="600" alt="screenshot of Mergington High School WebApp" src="https://github.com/user-attachments/assets/472398fd-1aa1-4084-b443-4e242deb30d9" />

### GitHub Copilot とは？

<img width="150" align="right" alt="copilot logo" src="https://github.com/user-attachments/assets/4d22496d-850b-4785-aafe-11cba03cd5f2" />

GitHub Copilot は、より速く、より少ない労力でコードを書くのを助けてくれるAIコーディングアシスタントです。問題解決やコラボレーションにより多くのエネルギーを注ぐことができます。

GitHub Copilot は開発者の生産性を向上させ、ソフトウェア開発のスピードを加速させることが実証されています。詳細は [GitHubブログ: Copilotの生産性と幸福度への影響を定量化した調査](https://github.blog/news-insights/research/research-quantifying-github-copilots-impact-on-developer-productivity-and-happiness/) をご覧ください。

主な利用方法は以下の通りです:

- **インライン提案**: タイピング中に、Copilot が周辺の文脈をもとにエディタ内で直接コードを提案します。Intellisense などのコード補完ツールに慣れている方には馴染みやすいですが、Copilot の場合は関数全体など大きな単位で提案されることもあります。
- **Copilot - 質問モード (Ask Mode)**: コーディングに関する質問ができる専用チャットパネルです。オンラインAIアシスタントのチャットに似ていますが、プロジェクトファイルの内容を自動的に参照して、より適切な回答をしてくれます。
- **Copilot - 編集モード (Edit Mode)**: 質問モードに似ていますが、会話的ではなく、選択したファイルに直接変更を加えます。
- **Copilot - エージェントモード (Agent Mode)**: Copilot がリクエストを達成するまで繰り返し動作します。文脈の選択、コード変更、ターミナルコマンドやツールの実行、作業のレビューと調整まで自動で行います。

> [!TIP]
> 現在および今後の機能については [GitHub Copilot の機能](https://docs.github.com/ja/copilot/about-github-copilot/github-copilot-features) ドキュメントをご覧ください。異なる[モデル](https://docs.github.com/ja/github-models)の選択や[拡張機能](https://github.com/features/copilot/extensions)の作成も可能ですが、それはまた別のレッスンで！

### GitHub Copilot はどう使うの？

作業を進める中で、Copilot はウェブサイトのさまざまな場所や、お気に入りのコーディング環境（VS Code、Jet Brains、Xcode など）で活躍します。今回は [Codespace](https://github.com/features/codespaces) という事前構成済みの開発環境で VS Code を使って練習します。

### :keyboard: アクティビティ: Copilot Chat でプロジェクト紹介を受けよう

まずは開発環境を立ち上げ、Copilot を使ってプロジェクトについて学び、実際に動かしてみましょう。

1. 下のボタンを左クリックして、**Create Codespace** ページを新しいタブで開きます。設定はデフォルトのままでOKです。

   [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/{{full_repo_name}}?quickstart=1)

1. **Repository** フィールドが自分のコピーになっていることを確認し、緑色の **Create Codespace** ボタンをクリックします。

   - ✅ 自分のコピー: `/{{{full_repo_name}}}`
   - ❌ オリジナル: `/skills/getting-started-with-github-copilot`

1. 少し待つと、Visual Studio Code がブラウザで起動します。

1. 左サイドバーで拡張機能タブをクリックし、`GitHub Copilot` と `Python` の拡張機能がインストールされ有効になっていることを確認します。

   <img width="350" alt="copilot extension for VS Code" src="https://github.com/user-attachments/assets/ef1ef984-17fc-4b20-a9a6-65a866def468" />

   <img width="350" alt="python extension for VS Code" src="https://github.com/user-attachments/assets/3040c0f5-1658-47e2-a439-20504a384f77" />

1. VS Code 上部の **Copilot アイコン** をクリックして Copilot Chat パネルを開きます。

   <img width="150" alt="image" src="https://github.com/user-attachments/assets/5e64db46-95cb-415d-badc-b6b8677f10c1" />

1. 初めて GitHub Copilot を使う場合は、利用規約に同意する必要があります。

1. 下記のプロンプトを入力して、Copilot にプロジェクトの紹介をしてもらいましょう。

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > @workspace このプロジェクトの構成を簡単に説明してください。
   > 実行するにはどうすればいいですか？
   > ```

   > **注**: Copilot の指示に従う必要はありません。すでに環境は準備済みです。

   <details>
   <summary>@workspace とは？</summary>
   細かいところに気づきましたね！今はそのまま使ってください。🤓 次のステップで説明します。
   </details>

1. プロジェクトについて理解できたら、実際に動かしてみましょう！左サイドバーで `Run and Debug` タブを選択し、**Start Debugging** アイコンを押します。

   <img width="300" alt="image" src="https://github.com/user-attachments/assets/50b27f2a-5eab-4827-9343-ab5bce62357e" />

1. ウェブページをブラウザで表示したいので、URLとポート番号を確認します。見つからない場合は下部パネルを展開し、**Ports** タブを選択してください。

1. リストからポート `8000` と関連リンクを探し、リンクにカーソルを合わせて **Open in browser** アイコンをクリックします。

   ![image](https://github.com/user-attachments/assets/92d5642e-ce99-4a66-850c-2d311a673596)

### :keyboard: アクティビティ: Copilot でターミナルコマンドを思い出そう 🙋

素晴らしい！アプリに慣れ、動作確認もできたので、今度はカスタマイズ用のブランチを作るために Copilot に手伝ってもらいましょう。

1. まだであれば、VS Code に戻ります。

1. 下部パネルで **Terminal** タブを選択し、右側の `+` をクリックして新しいターミナルウィンドウを作成します。

   > **注:** これにより、既存のデバッグセッション（Webアプリのサービス）が止まるのを防げます。

1. 新しいターミナルウィンドウで、`Ctrl + I`（Windows）または `Cmd + I`（Mac）を押して **Copilot のターミナルインラインチャット** を起動します。

1. Copilot に「ブランチを作成して公開するコマンド」を尋ねてみましょう。

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Copilot、Git の新しいブランチを作成して公開するにはどうすればいいですか？
   > ```

   > **ヒント:** これは簡単な例ですが、Copilot はループやパターンマッチ、ファイル操作など、より複雑なコマンドも提案してくれます。気軽に Copilot に相談してみましょう。ただし、提案はあくまで提案なので、必ず内容を確認してから実行してください。

1. Copilot から下記のようなコマンドが提案されるはずです。手動で修正せず、Copilot にブランチ名を指定するよう伝えましょう。

   ```bash
   git checkout -b {new_branch_name}
   git push -u origin {new_branch_name}
   ```

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > ありがとう Copilot！ブランチ名は "accelerate-with-copilot" にしましょう。
   > ```

   > **ヒント:** Copilot の提案が希望通りでない場合は、さらに説明を続けてください。Copilot は会話履歴を覚えているので、追加の要望にも対応できます。

1. コマンドに満足したら、`Run` ボタンを押して Copilot に実行してもらいましょう。コピペは不要です！

1. 少し待つと、VS Code の下部ステータスバー左側にアクティブなブランチ名が表示されます。`accelerate-with-copilot` になっていれば完了です！

1. ブランチが GitHub にプッシュされたので、Mona が進捗確認を始めます。しばらく待ってコメント欄を確認しましょう。進捗情報や次のレッスンが届きます。

<details>
<summary>うまくいかない場合 🤷</summary><br/>

フィードバックが届かない場合は、以下を確認してください:

- ブランチ名が正確に `accelerate-with-copilot` になっているか（接頭辞や接尾辞なし）。
- ブランチがリポジトリに正しく公開されているか。

</details>
