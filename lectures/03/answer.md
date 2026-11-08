# 第3回 解答

## 演習

- 第1回（素のLLM）とエージェントの回答の違い：素のLLMの知識にない講義特有の正しい答えが返ってきた。
- `--trace` で見えたツール呼び出し（ツール名と引数）：ツール名⇒search_glossary　引数⇒({'query': 'LoRA'})と({'query': 'QLoRA'})
- 1つの質問での LLM 呼び出し回数（`requests`）：２回
- 追加したツールと、docstring に書いた説明：追加したツール⇒make_quiz　docstring に書いた説明⇒指定した回の用語から 1つを選び、確認問題と答えを返す。第2回の確認問題を出して」のように、復習用の問題を求められたときに使う。

## 宿題

- 取り組んだレベル：基礎
- やったこと：agent.pyのINSTRUCTIONSやtools.pyのdocstringを変えて"LoRAとQLoRAの違いは？"を実行
- 結果：INSTRUCTIONSに「嘘をつく」と書くときちんと間違った回答を行い、search_glossaryのdocstringに「queryには調べたい用語をすべて入れる」と書くと、LoRAとQLoRAを一度に引数に入れ、tool_callsも１で済んだ。
- 気づき・疑問：利用者がいちいち前提のプロンプトを入力する必要がないため、ユーザビリティの向上に役立ちそう。ただ、INSTRUCTIONSやdocstringはどの程度強制力があり、回避されることはないのか疑問が生じた。
