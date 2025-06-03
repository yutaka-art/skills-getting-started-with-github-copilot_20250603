## ステップ2: Copilot で作業を進めよう

前のステップでは、GitHub Copilot のおかげでプロジェクトの概要を素早く把握できました。それだけでも大きな時短ですが、ここからは実際に作業を進めていきましょう！

最近、生徒が同じ活動に2回登録できてしまうバグがあることが判明しました。これは見過ごせませんので、修正しましょう！

残念ながら、この問題を解決するための情報はほとんどありません。そこで、Copilot に協力してもらい、問題箇所を特定し、解決策を考えてもらいましょう。

その前に、Copilot についてもう少し学んでみましょう！🧑‍🚀

### Copilot はどうやって動くの？

簡単に言えば、Copilot はとても専門的な同僚のような存在です。効果的に使うには、背景（コンテキスト）と明確な指示（プロンプト）を与える必要があります。また、人によって得意分野が違うように、Copilot もモデルによって得意なことが異なります。

- **どうやってコンテキストを与える？**: コーディング環境では、Copilot は自動的に近くのコードや開いているタブを考慮します。チャットを使う場合は、ファイルを明示的に指定することもできます。

- **どのモデルを選べばいい？**: 今回の演習では、どのモデルでも大きな違いはありません。いろいろ試してみるのも楽しいですよ！これはまた別のレッスンで。

- **プロンプトはどう作る？**: 明確で具体的な指示を出すと、Copilot はより良い提案をしてくれます。ただし、従来のシステムと違い、後から追加で説明することもできます。

> [!TIP]
> Copilot の知識や能力を補う方法として、[チャット参加者](https://docs.github.com/ja/copilot/using-github-copilot/copilot-chat/github-copilot-chat-cheat-sheet?tool=vscode#chat-participants)、[チャット変数](https://docs.github.com/ja/copilot/using-github-copilot/copilot-chat/github-copilot-chat-cheat-sheet?tool=vscode#chat-variables)、[スラッシュコマンド](https://docs.github.com/ja/copilot/using-github-copilot/copilot-chat/github-copilot-chat-cheat-sheet?tool=vscode#slash-commands-1)、[MCPツール](https://code.visualstudio.com/docs/copilot/chat/mcp-servers) などもあります。

### :keyboard: アクティビティ: Copilot で登録バグを修正しよう :bug:

1. まずは Copilot にバグの原因となりそうな箇所を提案してもらいましょう。**Copilot Chat** パネルを **質問モード（Ask mode）** で開き、次の内容を尋ねてください。

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > @workspace 生徒が同じ活動に2回登録できてしまいます。
   > このバグはどこから来ている可能性がありますか？
   > ```

   <details>
   <summary>@workspace とは？</summary>

   これは、プロジェクトリポジトリ全体を探索し、関連する追加コンテキストを含めてくれる特別な[チャット参加者](https://docs.github.com/ja/copilot/using-github-copilot/copilot-chat/github-copilot-chat-cheat-sheet?tool=vscode#chat-participants)です。

   </details>

1. `src/app.py` ファイルの `signup_for_activity` メソッドが問題箇所だと分かったら、Copilot の提案に従って修正しましょう（半自動で進めます）。まずコメントを書き、Copilot に続きを任せます。

   1. VS Code の **エクスプローラータブ** で `src/app.py` ファイルを開きます。

   1. ファイルの下部付近にある `signup_for_activity` メソッドを探します。

   1. 生徒を追加する処理のコメント行を見つけ、その上に登録済みかどうかのチェックを入れるのが自然です。

   1. 下記のコメントを入力し、Enter で次の行に進みます。しばらくすると、Copilot からサジェスト（影付きテキスト）が表示されます。ナイス！:tada:

      ```python
      # すでに登録済みでないか確認
      ```

   1. `Tab` を押して Copilot の提案を受け入れ、影付きテキストをコードに変換します。

      > **ヒント:** 他の提案も見たい場合は、`Tab` の代わりに影付きテキストにカーソルを合わせ、ツールバーの矢印や `...` から `Open Completions Panel` を選択してください。

   <details>
   <summary>例: Copilot の提案例</summary><br/>

   Copilot の提案は日々進化しているため、必ずしも同じ結果になるとは限りません。うまくいかない場合は、下記の例を参考に進めてください。

   ```python
   @app.post("/activities/{activity_name}/signup")
   def signup_for_activity(activity_name: str, email: str):
      """Sign up a student for an activity"""
      # 活動が存在するか確認
      if activity_name not in activities:
         raise HTTPException(status_code=404, detail="Activity not found")

      # 活動を取得
      activity = activities[activity_name]

      # すでに登録済みでないか確認
      if email in activity["participants"]:
        raise HTTPException(status_code=400, detail="Student is already signed up")

      # 生徒を追加
      activity["participants"].append(email)
      return {"message": f"Signed up {email} for {activity_name}"}
   ```

   </details>

### :keyboard: アクティビティ: Copilot でサンプルデータを生成しよう 📋

新しいプロジェクト開発では、テスト用にリアルなダミーデータがあると便利です。Copilot はこの作業も得意なので、サンプル活動をさらに追加し、**インラインチャット** という別の Copilot の使い方も体験しましょう。

**インラインチャット** と **Copilot Chat パネル** はよく似ていますが、自動的に参照するコンテキストが少し異なります。Copilot Chat はプロジェクト全体の説明に向いていますが、インラインチャットは特定の行や関数について質問するのに便利です。

1. まだ開いていなければ、`src/app.py` ファイルを開きます。

1. ファイル冒頭（23行目付近）にある `activities` 変数（課外活動の例が設定されている部分）を探します。

1. 関連する行のいずれかをクリックし、`Ctrl + I`（Windows）または `Cmd + I`（Mac）で Copilot インラインチャットを起動します。

   > **ヒント:** 行を右クリック → `Copilot` → `Editor Inline Chat` でも起動できます。

1. 下記のプロンプトを入力し、Enter または **Send and Dispatch** ボタンを押します。

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > スポーツ系の活動を2つ、芸術系の活動を2つ、知的活動を2つ追加してください。
   > ```

1. しばらくすると、Copilot が直接コードを編集し始めます。追加や削除が分かりやすく表示されるので、内容を確認して **Accept** ボタンを押しましょう。

   <details>
   <summary>例: Copilot の提案例</summary><br/>

   Copilot の提案は日々変わるため、うまくいかない場合は下記の例を参考にしてください。

   ```python
   # メモリ上の活動データベース
   activities = {
      "Chess Club": {
         "description": "Learn strategies and compete in chess tournaments",
         "schedule": "Fridays, 3:30 PM - 5:00 PM",
         "max_participants": 12,
         "participants": ["michael@mergington.edu", "daniel@mergington.edu"]
      },
      "Programming Class": {
         "description": "Learn programming fundamentals and build software projects",
         "schedule": "Tuesdays and Thursdays, 3:30 PM - 4:30 PM",
         "max_participants": 20,
         "participants": ["emma@mergington.edu", "sophia@mergington.edu"]
      },
      "Gym Class": {
         "description": "Physical education and sports activities",
         "schedule": "Mondays, Wednesdays, Fridays, 2:00 PM - 3:00 PM",
         "max_participants": 30,
         "participants": ["john@mergington.edu", "olivia@mergington.edu"]
      },
      "Basketball Team": {
         "description": "Competitive basketball training and games",
         "schedule": "Tuesdays and Thursdays, 4:00 PM - 6:00 PM",
         "max_participants": 15,
         "participants": []
      },
      "Swimming Club": {
         "description": "Swimming training and water sports",
         "schedule": "Mondays and Wednesdays, 3:30 PM - 5:00 PM",
         "max_participants": 20,
         "participants": []
      },
      "Art Studio": {
         "description": "Express creativity through painting and drawing",
         "schedule": "Wednesdays, 3:30 PM - 5:00 PM",
         "max_participants": 15,
         "participants": []
      },
      "Drama Club": {
         "description": "Theater arts and performance training",
         "schedule": "Tuesdays, 4:00 PM - 6:00 PM",
         "max_participants": 25,
         "participants": []
      },
      "Debate Team": {
         "description": "Learn public speaking and argumentation skills",
         "schedule": "Thursdays, 3:30 PM - 5:00 PM",
         "max_participants": 16,
         "participants": []
      },
      "Science Club": {
         "description": "Hands-on experiments and scientific exploration",
         "schedule": "Fridays, 3:30 PM - 5:00 PM",
         "max_participants": 20,
         "participants": []
      }
   }
   ```

   </details>

### :keyboard: アクティビティ: Copilot で作業内容を説明しよう 💬

バグ修正と活動例の拡充、お疲れさまでした！最後に、Copilot の力を借りてコミットメッセージを作成し、作業内容を GitHub にプッシュしましょう。

1. 左サイドバーで `ソース管理` タブを選択します。

   > **ヒント:** ソース管理エリアからファイルを開くと、単に開く場合と違い、差分が表示されます。

1. `app.py` ファイルを見つけて `+` ボタンを押し、変更をステージングエリアに追加します。

   ![image](https://github.com/user-attachments/assets/7d3daf4e-4125-4775-88a7-33251cd7293e)

1. ステージ済み変更リストの上にある **Message** テキストボックスを見つけますが、**まだ何も入力しないでください**。

   - 通常はここに変更内容の説明を書きますが、今回は Copilot に任せましょう！

1. **Message** テキストボックス右側の **Copilot でコミットメッセージ生成** ボタン（キラキラアイコン）をクリックします。

1. **Commit** ボタンと **Sync Changes** ボタンを押して、変更を GitHub にプッシュします。

1. しばらく待つと、Mona が作業内容を確認し、フィードバックや次のレッスンを案内してくれます。

<details>
<summary>うまくいかない場合 🤷</summary><br/>

フィードバックが届かない場合は、以下を確認してください:

- `src/app.py` の変更が `accelerate-with-copilot` ブランチにプッシュされているか。

</details>
