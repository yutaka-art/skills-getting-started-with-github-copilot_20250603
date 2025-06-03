## ステップ3: Copilot Edits でさらに _速く_ 作業しよう

これまでのステップでは、Copilot の手動ガイドが多い機能を使い、主にローカルな変更を行ってきました。ここでは、リポジトリ全体を俯瞰して編集できる Copilot Edits 機能を体験します。

[Copilot - 編集モード（Edit Mode）](https://code.visualstudio.com/docs/copilot/copilot-edits) は、**複数ファイル**に対して**自然言語**で指示を出し、AIが直接エディタ上で編集案を提示してくれる機能です。周囲のコードも含めて、その場でレビューできます。

#### 主な特徴

- **複数ファイル編集**: Copilot Edits はワークスペース内の複数ファイルにまたがって変更を加えられます。
- **反復的なワークフロー**: 生成されたコードを素早く確認し、受け入れる・破棄するを選択できます。
- **インプレース編集**: エディタ上で直接編集内容を確認でき、コードレビューのような流れで進められます。
- **ワーキングセット**: どのファイルに編集を適用するか指定できます。

#### 使い方

1. **コンテキストの設定**: 編集対象とするファイルを選択します。
1. **指示を出す**: 必要な変更を自然言語で説明します。
1. **変更内容を確認**: 提案された変更をコード上で確認します。
1. **受け入れ or 破棄**: 各編集案を確認し、必要に応じて採用します。
1. **繰り返し**: 必要なら追加指示を出して調整します。

### :keyboard: アクティビティ: Copilot で新機能を追加しよう！:rocket:

1. Copilot Chat パネルが表示されていなければ、再度開いてください。

1. Copilot Chat ウィンドウ下部のドロップダウンから **編集（Edit）** モードに切り替えます。

   <img width="350" alt="image" src="https://github.com/user-attachments/assets/646fc94a-7d60-4821-b9cf-9ec6f4fd03d7" />

1. Webページ関連のファイルを開き、それぞれのエディタウィンドウ（またはファイル）をチャットパネルにドラッグして、Copilot にコンテキストとして認識させます。

   - `src/static/app.js`
   - `src/static/index.html`
   - `src/static/styles.css`

   > **ヒント:** **Add Context...** ボタンを使えば、GitHub Issue やコードベース全体、ターミナルの出力などもコンテキストとして追加できます。

1. Copilot に「活動カードに参加者一覧を表示するよう編集して」と依頼しましょう。編集案が適用されるまで少し待ちます。

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Copilot、活動カードに参加者セクションを追加してください。
   > その活動に既に登録されている参加者を箇条書きリストで表示したいです。
   > 見た目もきれいにお願いします！
   > ```

   - ファイル名やエディタウィンドウの横に編集案があることを示すアイコンが表示されます。
   - エディタ右下に編集案ナビゲーションパネルが現れ、推奨変更箇所にジャンプできます。

      <img width="200" alt="files with icons indicating they have been edited" src="https://github.com/user-attachments/assets/9c7c2e10-cd18-43c5-9947-cffd6dde0473" />

      <img width="250" alt="edit navigation panel" src="https://github.com/user-attachments/assets/a84965a5-2f43-4c93-a814-0fdeb3a06494" />

   <details>
   <summary>困ったときは？ 🤷</summary><br/>

   編集対象ファイルをワーキングセットに追加しているか確認してください。

   ![screenshot of working set](https://github.com/user-attachments/assets/d3eadc8e-583e-4a28-9e82-be128eab843b)

   </details>

1. 変更をそのまま受け入れる前に、Webサイトを再度確認し、期待通りに更新されているかチェックしましょう。下記は更新後の活動カード例です。アプリの再起動やページのリロードが必要な場合もあります。

   <img width="350" alt="Activity card with participant info" src="https://github.com/user-attachments/assets/c4d56187-4791-4c8e-87d7-d5ce7cdc0bee" />

   > **注:** あなたの活動カードは例と異なる場合があります。Copilot の結果は毎回同じとは限りません。

   <details>
   <summary>困ったときは？ 🤷</summary><br/>
   Webサイトが表示されない場合は以下を確認してください。

   - VS Code のデバッガを再起動し、最新のWebサイトが配信されているか確認
   - URLを忘れた・ウィンドウを閉じた場合はステップ1を見直す
   - ページをハードリロード、またはプライベートウィンドウで開き直してキャッシュをクリア

   </details>

1. 変更内容に問題がなければ、パネルで各編集案を確認し、**Keep** ボタンで適用してください。

   > **ヒント:** 変更を直接受け入れるだけでなく、修正したり、チャットで追加指示を出して調整することもできます。

1. 新機能が完成したら、**コミット**して**GitHub にプッシュ**しましょう。

1. Mona が作業内容を確認し、フィードバックや最後のレッスンを案内するまで少し待ちます。あと少しです！

1. （任意）Agent モードを簡単に知りたい場合は、**@professortocat** に Issue コメントで質問してみましょう。🚀

   ```txt
   Hey @professortocat, Agent mode sounds pretty cool. Can you please tell me more about it?
   ```

<details>
<summary>困ったときは？ 🤷</summary><br/>

フィードバックが届かない場合は、以下を確認してください。

- `src/static/` ディレクトリの変更が `accelerate-with-copilot` ブランチにコミット・プッシュされているか
- Mona にミスを指摘された場合は修正して再度プッシュしてください。何度でもチェックしてくれます。

</details>
